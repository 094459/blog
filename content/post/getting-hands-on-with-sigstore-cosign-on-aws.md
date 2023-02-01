---
title: 'Getting hands on with Sigstore Cosign on AWS'
date: '2023-01-31'
tags: [Amazon ECR, AWS KMS, Cosign, Sigstore, Docker, sget]
---

### Getting hands on with Sigstore Cosign on AWS

I am currently putting together some content around how you can use a number of open source tools to help build a stronger defence against common software supply chain attacks. In this blog post, I look at emerging tools from Sigstore, and focus in this post on Cosign, a tool that supports container image signing, verification, and storage in an Open Container Initiative (OCI) registry. Cosign aims to make signatures frictionless. I will look at other tools in future posts.

This blog post is not intended to cover the broader topics around supply chain security. I will cover that in separate posts and talks. This is intended to dive deeper into the tools and explore how you put into practice some of the concepts.

**Pre-reqs**

* an AWS account with enough access to create Amazon ECR repositories and images, and create/use AWS KMS keys
* a Mac/Ubuntu developer machine

**Installation**

Installing it was very simple as they provide both source and binaries, as well as integrate with most package managers you are likely to be using. I used both Mac and Linux versions when creating this post.

To install, it is as simple as 

```
brew install cosign
```

After installation, we can see the Cosign version by issuing the "cosign version" command.

```
  ______   ______        _______. __    _______ .__   __.
 /      | /  __  \      /       ||  |  /  _____||  \ |  |
|  ,----'|  |  |  |    |   (----`|  | |  |  __  |   \|  |
|  |     |  |  |  |     \   \    |  | |  | |_ | |  . `  |
|  `----.|  `--'  | .----)   |   |  | |  |__| | |  |\   |
 \______| \______/  |_______/    |__|  \______| |__| \__|
cosign: A tool for Container Signing, Verification and Storage in an OCI registry.

GitVersion:    1.13.1
GitCommit:     d1c6336475b4be26bb7fb52d97f56ea0a1767f9f
GitTreeState:  "clean"
BuildDate:     2022-10-17T18:00:05Z
GoVersion:     go1.19.2
Compiler:      gc
Platform:      darwin/amd64
```

On linux (ubuntu), I installed via the Linux version of homebrew (which I am increasingly using over apt as it is less things to remember for me)

```
  ______   ______        _______. __    _______ .__   __.
 /      | /  __  \      /       ||  |  /  _____||  \ |  |
|  ,----'|  |  |  |    |   (----`|  | |  |  __  |   \|  |
|  |     |  |  |  |     \   \    |  | |  | |_ | |  . `  |
|  `----.|  `--'  | .----)   |   |  | |  |__| | |  |\   |
 \______| \______/  |_______/    |__|  \______| |__| \__|
cosign: A tool for Container Signing, Verification and Storage in an OCI registry.

GitVersion:    1.13.1
GitCommit:     d1c6336475b4be26bb7fb52d97f56ea0a1767f9f
GitTreeState:  "clean"
BuildDate:     2022-10-17T18:00:05Z
GoVersion:     go1.19.2
Compiler:      gc
Platform:      linux/amd64
```

Now that it is installed, we can get started.

### Creating our signing keys

The first thing we need to do when we want to use Cosign to sign artefacts is to create a key. This is simple enough using the command line.

```
cosign generate-key-pair
```

This creates two files in the directory you run this command - a private and public key. We now use these keys to sign and verify stuff, including container images and other files we might want to upload to our OCI registry.

**Verifying the Cosign binaries**

Before we begin, as we are going to be using Cosign to create keys, sign and verify the various artefacts we work with, we should see how we can use the tool to validate the binaries themselves. We do that easily enough in the following way.
```
$ COSIGN_EXPERIMENTAL=1 cosign verify-blob --cert https://github.com/sigstore/cosign/releases/download/v1.13.1/cosign-linux-amd64-keyless.pem --signature https://github.com/sigstore/cosign/releases/download/v1.13.1/cosign-linux-amd64-keyless.sig https://github.com/sigstore/cosign/releases/download/v1.13.1/cosign-linux-amd64
```    
<wait 2-3 minutes>
```
tlog entry verified with uuid: 22d81bc3f72849e2974d3258f69ca1107aca1c9e71fdfa8c2a76bf536e938e1a index: 5296330
Verified OK
```
We can repeat with the other tools (rekor, fulcio) as needed. But this looks good, our Cosign is legit and so we can proceed with confidence.

**Signing a container image in Amazon ECR**

I have a sample Docker file that I want to use to test out the signing/verification process. Here is my Docker file, which should create a very lightweight image.

```
FROM alpine
CMD ["echo", "Hello, Cosign!"]
```

I am going to build locally and the push up to Amazon Elastic Container Registry (ECR). From the Amazon ECR registry I have created a public repository, and this has provided me with a link (public.ecr.aws/a4b5h6u6) which I will use to login via the command line:

```
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/a4b5h6u6

WARNING! Your password will be stored unencrypted in /home/ubuntu/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
```
I go to where Dockerfile is located and then run

```
docker build -t os-security .
Sending build context to Docker daemon  2.048kB
Step 1/2 : FROM alpine
 ---> 0ac33e5f5afa
Step 2/2 : CMD ["echo", "Hello, Cosign!"]
 ---> Using cache
 ---> 4518fa66e15d
Successfully built 4518fa66e15d
Successfully tagged os-security:latest

docker tag os-security:latest public.ecr.aws/a4b5h6u6/os-security:latest
```

I can see that I have created a local container image, which I can test/run via "docker run public.ecr.aws/a4b5h6u6/os-security" and it should just display "Hello, Cosign!"

```
public.ecr.aws/a4b5h6u6/os-security          latest     4518fa66e15d   24 hours ago    5.57MB
```

Now I am going to push this to Amazon ECR


```
docker push public.ecr.aws/a4b5h6u6/os-security:latest

docker push public.ecr.aws/a4b5h6u6/os-security:latest
The push refers to repository [public.ecr.aws/a4b5h6u6/os-security]
4fc242d58285: Pushed
latest: digest: sha256:71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8 size: 528
```

So far, all routine. Now lets sign this container image with Cosign

```
cosign sign --key cosign.key public.ecr.aws/a4b5h6u6/os-security
cosign sign --key cosign.key public.ecr.aws/a4b5h6u6/os-security
Enter password for private key:
WARNING: Image reference public.ecr.aws/a4b5h6u6/os-security uses a tag, not a digest, to identify the image to sign.

Pushing signature to: public.ecr.aws/a4b5h6u6/os-security
```

> **Note!** You can use the AWS Console and see the new container image, or you can run the following command (replacing the value of your repository name, mine was called "os-security", so change it to whatever you need):
> 
> ```
> aws ecr-public describe-images --repository-name os-security 
> aws ecr-public describe-repositories --endpoint https://ecr-public.us-east-1.amazonaws.com --region us-east-1
> 

When we look at our ECR repository, we get a new tagged entry.

The next step is to see how we can verify the signature.

```
cosign verify --key cosign.pub public.ecr.aws/a4b5h6u6/os-security


Verification for public.ecr.aws/a4b5h6u6/os-security:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key

[{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8"},"type":"cosign container image signature"},"optional":null}]

```

Congratulations, we have now signed and verified a container on Amazon EMR. However, we have done that using a key we have created and manage locally. The next step is to see how AWS KMS can help us improve this by managing the private key.

**Using KMS to store our Cosign key**

Cosign supports a number of keystores, including AWS KMS. [You can read more here](https://docs.sigstore.dev/cosign/kms_support/).

We will first create a new KMS store for our key using the following command:

```
aws kms create-key --key-usage SIGN_VERIFY --customer-master-key-spec RSA_4096 --description "Dev Cosign Key"

{
    "KeyMetadata": {
        "AWSAccountId": "704533066374",
        "KeyId": "fa679817-b44b-4663-95e3-63dd395b0628",
        "Arn": "arn:aws:kms:eu-west-1:704533066374:key/fa679817-b44b-4663-95e3-63dd395b0628",
        "CreationDate": "2023-01-30T14:47:45.348000+00:00",
        "Enabled": true,
        "Description": "Dev Cosign Key",
        "KeyUsage": "SIGN_VERIFY",
        "KeyState": "Enabled",
        "Origin": "AWS_KMS",
        "KeyManager": "CUSTOMER",
        "CustomerMasterKeySpec": "RSA_4096",
        "SigningAlgorithms": [
            "RSASSA_PKCS1_V1_5_SHA_256",
            "RSASSA_PKCS1_V1_5_SHA_384",
            "RSASSA_PKCS1_V1_5_SHA_512",
            "RSASSA_PSS_SHA_256",
            "RSASSA_PSS_SHA_384",
            "RSASSA_PSS_SHA_512"
        ]
    }
}
```

We create an alias for this new key

```
aws kms create-alias --alias-name alias/devcosign-key  --target-key-id {output of arn from prev. step}

aws kms create-alias --alias-name alias/devcosign-key  --target-key-id arn:aws:kms:eu-west-1:704533066374:key/fa679817-b44b-4663-95e3-63dd395b0628

```

There is no output from the command line, but if you peep into the AWS Console and look at the Customer Keys in KMS, you should see the new key listed.

Now we use this to store our private key when creating a new key pair. We use the same command as before, this time we specify the location of the KMS keystore

```
cosign generate-key-pair --kms awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key
Public key written to cosign.pub
```

We now have a single file (the public) written to the local filesystem. the key is now deployed on AWS KMS.

We can now use that anytime we want to use Cosign by referencing --key with the "awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key" value.

We can repeat the previous container signing, this time using this new private key managed by KMS. It is possible to sign a container image multiple times.

We can use the "-a" option within Cosign to add annotations. Lets say that the developer originally signed the container with their key, and that we now want to sign this with an organisational key. We could use annotations to do that 

```
cosign sign --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key -a organization=signature public.ecr.aws/a4b5h6u6/os-security

Pushing signature to: public.ecr.aws/a4b5h6u6/os-security
```

When you look at Amazon ECR console, you will see that the tag has been updated. We can now verify this, using the following command:


```
cosign verify --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security

Verification for public.ecr.aws/a4b5h6u6/os-security:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key

[{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8"},"type":"cosign container image signature"},"optional":{"organization":"signature"}}]
```
This has verified ok. You will also notice that the annotation has come through, and we now have an organisational signature listed.

**Signing other artefacts**

In our modern application landscape, we often have other artefacts we might want to sign. How does Cosign help you here? Well the good news is that Cosign can sign, upload and, verify other development artefacts you create. Let us take a quick look at an example.

First, we will create a dummy text file.

```
echo "hello, Cosign" > artifact
```

We can use Cosign to sign and verify this file using the following command:

```
cosign sign-blob --key ../cosign/cosign.key artifact

Using payload from: artifact
Enter password for private key:
MEYCIQC+26KphIN+O5q2VNz23tnmcAakOB+TpiqObXFyqNBBzQIhANwPuhl1srSZn+s+3PDliaWma+BlyMk9WXNXnWOwHzw+
```

The important bit here is the output, this is the signature. That output needs to be saved so you can validate/verify the signature. So how do we validate an artefact that its not been tampered with? By using that output signature as input to the verify option of the tool, we can use Cosign to let us know if the signature matches.

```
cosign verify-blob --key ../cosign/cosign.pub --signature MEYCIQC+26KphIN+O5q2VNz23tnmcAakOB+TpiqObXFyqNBBzQIhANwPuhl1srSZn+s+3PDliaWma+BlyMk9WXNXnWOwHzw+ artifact

Verified OK
```

**Signing and Pushing non Container image assets**

How can we combine the fact we can sign non container image artefacts and store these in an OCI compliant registry like Amazon ECR? Cosign can help us as it provides all the functionality to do this.

We can upload these assets using the "cosign upload blob" command, here is an example. I am taking that text file I created, and using this to upload to Amazon ECR.

```
cosign upload blob -f artifact public.ecr.aws/a4b5h6u6/os-security:file-artifact

Uploading file from [artifact] to [public.ecr.aws/a4b5h6u6/os-security:file-artifact] with media type [text/plain]
File [artifact] is available directly at [public.ecr.aws/v2/a4b5h6u6/os-security/blobs/sha256:dcf8ff807eca6986c0131b7134509a28091a48ff808331f8492b95aa4c146e5f]
Uploaded image to:
public.ecr.aws/a4b5h6u6/os-security@sha256:1957141ce0d6c158e6c50a71d6e310bdc7c1a3b7115b4f75346fdb06b4618819

```
Once uploaded, we can use Cosign to sign it using the following command.

```
cosign sign --key ../../cosign/cosign.key public.ecr.aws/a4b5h6u6/os-security:file-artifact
Enter password for private key:
Pushing signature to: public.ecr.aws/a4b5h6u6/os-security
```
and finally, we can use Cosign to verify

```
cosign verify --key ../../cosign/cosign.pub public.ecr.aws/a4b5h6u6/os-security:file-artifact 

Verification for public.ecr.aws/a4b5h6u6/os-security:file-artifact --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key

[{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:1957141ce0d6c158e6c50a71d6e310bdc7c1a3b7115b4f75346fdb06b4618819"},"type":"cosign container image signature"},"optional":null}]
```

**Using SGET**

As part of the Cosign project, include the sget command for safer, automatic verification of signatures and integration with our binary transparency log, Rekor.

> **Note!** I did notice a warning about this tool being depreacated, so not sure what the longer term alternative will be.

You will need to install this. This is how I did this (the process took about 5 minutes)

```
go install github.com/sigstore/cosign/cmd/sget@latest

sget version

------------------------
  ____     ____   _____   _____
 / ___|   / ___| | ____| |_   _|
 \___ \  | |  _  |  _|     | |
  ___) | | |_| | | |___    | |
 |____/   \____| |_____|   |_|
sget: sget [--key <key reference>] <image reference>

GitVersion:    v1.13.1
GitCommit:     unknown
GitTreeState:  unknown
BuildDate:     unknown
GoVersion:     go1.18.1
Compiler:      gc
Platform:      linux/amd64
```

We can now run the command to grab the contents of the signed file.

```
sget public.ecr.aws/a4b5h6u6/os-security:file-artifact@sha256:1957141ce0d6c158e6c50a71d6e310bdc7c1a3b7115b4f75346fdb06b4618819

-------- NOTICE --------
The sget tool in the cosign repo is deprecated, and will be removed in a future release.

If you're interested in fetching content from an OCI registry or from an arbitrary URLs, please see: https://github.com/sigstore/sget.
------------------------
hello, cosign

```

If you try and just grab the file without the digest, like the following

```
sget public.ecr.aws/a4b5h6u6/os-security:file-artifact
main.go:65: error during command execution: public key must be specified when fetching by tag, you must fetch by digest or supply a public key
```
It will warn you that you need to provide a public key. We can do that by adding the --key

```
sget --key ../../cosign/cosign.pub public.ecr.aws/a4b5h6u6/os-security:file-artifact


Verification for public.ecr.aws/a4b5h6u6/os-security:file-artifact --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key
{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:1957141ce0d6c158e6c50a71d6e310bdc7c1a3b7115b4f75346fdb06b4618819"},"type":"cosign container image signature"},"optional":null}
hello, cosign
```

Finally, we can use the key we stored in KMS in a previous step to do this. I create a new text file called "artifact-kms" with some text.

```
cosign upload blob -f artifact-kms public.ecr.aws/a4b5h6u6/os-security:file-artifact-kms

File [artifact-kms] is available directly at [public.ecr.aws/v2/a4b5h6u6/os-security/blobs/sha256:0aeb40949fcdafed807602f4994638e9f77a230261f9e6780e2dc1f6b9ed786e]
Uploaded image to:
public.ecr.aws/a4b5h6u6/os-security@sha256:db30ea13a4f0c702be4a1265cffd3d248c664ccb410deb6e0d8e563ea50db8d2
```
Now we sign it

```
cosign sign --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security:file-artifact-kms

Pushing signature to: public.ecr.aws/a4b5h6u6/os-security
```

Finally, we can verify this

```
cosign verify --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security:file-artifact-kms

Verification for public.ecr.aws/a4b5h6u6/os-security:file-artifact-kms --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key

[{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:db30ea13a4f0c702be4a1265cffd3d248c664ccb410deb6e0d8e563ea50db8d2"},"type":"cosign container image signature"},"optional":null}]
```

> **Using ORAS**
> 
> As a side note, if you want to more easily work with non container image artefacts in your Amazon ECR repository you can use the [OCI registry client](https://oras.land/cli/). This makes it easy to upload additional artefacts to our OCI compliant container registry (like Amazon ECR)
>
>```
> oras push public.ecr.aws/a4b5h6u6/os-security:file artifact
> Exists    dcf8ff807eca artifact
> Pushed public.ecr.aws/a4b5h6u6/os-security:file
> Digest: sha256:4bfb24333db7194391002874a086b4453429279b83bb584773ce871917beae84
> 
> oras pull -o tmp public.ecr.aws/a4b5h6u6/os-security:file
> Downloading dcf8ff807eca artifact
> Downloaded  dcf8ff807eca artifact
> Pulled public.ecr.aws/a4b5h6u6/os-security:file
> Digest: sha256:4bfb24333db7194391002874a086b4453429279b83bb584773ce871917beae84
> 
> ```

**Hacking our Container**

Now that we have covered the basics, lets put this together to show what would happen if someone had somehow managed to push an updated (hacked) container image onto your repository.

We modify our Dockerfile, and change the text so that it outputs something like "I've been hacked".

```
FROM alpine
CMD ["echo", "Hello, Cosign! - Hacked!"]
```

We then build, tag, push, and then test it to make sure its running our new "hacked" container image.

```
docker build -t os-security .
docker tag os-security:latest public.ecr.aws/a4b5h6u6/os-security
docker push public.ecr.aws/a4b5h6u6/os-security:latest
docker run public.ecr.aws/a4b5h6u6/os-security

Hello, Cosign! - Hacked
```

What happens now if we use Cosign to validate this image?

```
cosign verify --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security:latest
Error: no matching signatures:

main.go:62: error during command execution: no matching signatures:
```

As we can see, Cosign has correctly identified the imposter container image. As part of a workflow, you could incorporate this to make sure what you are getting is what you expect.

**Conclusion**

In this short blog post, I wanted to share a few recipes of how you can use Sigstore Cosign to sign and verify both container images, but also other artefacts such as files/binaries. I also looked at how you can use Amazon ECR and AWS KMS as the target repository and private key store for Cosign.

You can check out and explore the Cosign tool [here](https://docs.sigstore.dev/cosign/overview/). Watch out for future posts where I cover the other Sigstore tools.


### Troubleshooting

If you get the following error message

**403 Forbidden**
```
Uploading file from [artifact] to [public.ecr.aws/a4b5h6u6/os-security:file-artifact] with media type [text/plain]
Error: HEAD https://public.ecr.aws/v2/a4b5h6u6/os-security/blobs/sha256:54771f5abaaeab4a1919c5af90c639f784847741183d5b66ece6307fab8e0f45: unexpected status code 403 Forbidden (HEAD responses have no body, use GET for details)
main.go:62: error during command execution: HEAD https://public.ecr.aws/v2/a4b5h6u6/os-security/blobs/sha256:54771f5abaaeab4a1919c5af90c639f784847741183d5b66ece6307fab8e0f45: unexpected status code 403 Forbidden (HEAD responses have no body, use GET for details)
```

Make sure that you are:

* Logged into Amazon ECR - see the post for how to do this
* If using the aws cli (specifically, aws ecr-public), make sure that you are pointed to us-east-1

**Cosign not installing on Ubuntu**

If you get this error

```
Remote error from secret service: org.freedesktop.Secret.Error.IsLocked: Cannot create an item in a locked collection
Error saving credentials: error storing credentials - err: exit status 1, out: `Cannot create an item in a locked collection`
```

try this which should fix the problem (running on Ubuntu 18.04LTS)

```
sudo apt install gnupg2 pass
```

**References and additional blog posts**

In the process of trying to make sense of how to get started with Cosign, I read a number of helpful blog posts, tutorials, and reference sites. I am including these here as they were all very helpful. I would encourage you all to take a look too.


* https://medium.com/@slimm609/secure-image-signing-with-cosign-and-aws-kms-82bc25d7fdae
* https://aws.amazon.com/blogs/opensource/supply-chain-security-on-amazon-elastic-kubernetes-service-amazon-eks-using-aws-key-management-service-aws-kms-kyverno-and-cosign/
* https://www.youtube.com/watch?v=HLb1Q086u6M
* https://www.chainguard.dev/unchained/cosign-verify-ecs
* https://github.com/chainguard-dev/cosign-ecs-verify
* https://www.linkedin.com/pulse/artifact-digital-signing-verifying-sigstore-cosign-chirravuri/
* https://toddysm.com/2022/10/27/implementing-containers-secure-supply-chain-with-sigstore-part-1-signing-with-existing-keys/
* https://www.techbeatly.com/sigstore-securing-my-software-with-a-new-standard/
