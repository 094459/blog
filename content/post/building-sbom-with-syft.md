---
title: 'Building a software bill of materials (SBOM) using open source tools'
date: '2023-02-01'
tags: [Amazon ECR, Cosign, Sigstore, syft, SBOM]
---


This is the second post exploring how you can use open source tools to help you build a stronger defence against common software supply chain attacks. In this blog post, I look at syft, an open source CLI tool and Go library for generating a Software Bill of Materials (SBOM) from container images and filesystems. We will use examples and build on the previous post, Getting hands on with Sigstore Cosign on AWS.

This blog post is not intended to cover the broader topics around supply chain security. I will cover that in separate posts and talks. This is intended to dive deeper into the tools and explore how you put into practice some of the concepts.

**Installation**

Installing [syft](https://github.com/anchore/syft) is pretty straight forward. On any Linux/Mac environment you can run the following command to install

```
curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b /usr/local/bin
```


When we do "syft version" we should see something like

```
syft version
Application:        syft
Version:            0.69.0
JsonSchemaVersion:  6.2.0
BuildDate:          2023-01-30T19:00:28Z
GitCommit:          b81c9805dcc9bf25dad7659fd9c2bbf7dd3f3d90
GitDescription:     v0.69.0
Platform:           darwin/amd64
GoVersion:          go1.18.10
Compiler:           gc
```

We can now run this tool

```
syft public.ecr.aws/a4b5h6u6/os-security:latest

ubuntu@ub18:~$ syft public.ecr.aws/a4b5h6u6/os-security:latest
 ✔ Loaded image
 ✔ Parsed image
 ✔ Cataloged packages      [15 packages]
NAME                    VERSION      TYPE
alpine-baselayout       3.2.0-r18    apk
alpine-keys             2.4-r1       apk
apk-tools               2.12.7-r3    apk
busybox                 1.34.1       binary
busybox                 1.34.1-r5    apk
ca-certificates-bundle  20211220-r0  apk
libc-utils              0.7.2-r3     apk
libcrypto1.1            1.1.1n-r0    apk
libretls                3.3.4-r3     apk
libssl1.1               1.1.1n-r0    apk
musl                    1.2.2-r7     apk
musl-utils              1.2.2-r7     apk
scanelf                 1.3.3-r0     apk
ssl_client              1.34.1-r5    apk
zlib                    1.2.12-r0    apk
```

What just happened? syft has produced a report of all the packages it has found in our container image that we have pushed to Amazon ECR.

The default is to only include the software in this layer of the container image (the squashed version). You can re-run the command to include software from all image layers in the SBOM, regardless of its presence in the final image.

```
syft public.ecr.aws/a4b5h6u6/os-security:latest --scope all-layers
```

>
> **Note!** In this particular example, there will not be any difference as we have not created any additional layers)
> 

**SPDX and CycloneDX**

When creating SBOM, there are different file formats in which you can export the data and share with interested parties. Two common formats are Software Package Data Exchange (SPDX) and CycloneDX.

SPDX is an open standard for communicating software bill of material information, including provenance, license, security, and other related information. SPDX reduces redundant work by providing common formats for organisations and communities to share important data, thereby streamlining and improving compliance, security, and dependability.

CycloneDX is a lightweight software bill of materials (SBOM) standard designed for use in application security contexts and supply chain component analysis. CycloneDX SBOM describes the entire stack for which software runs. Including operating systems, containers, firmware, applications, libraries, frameworks, files, services, and optionally, hardware.

syft allows you to export its findings in either format using a "-o spdx-json or -o cyclonedx-json". We can try this on our sample container image. You can then pipe this to a file by appending "={filename}"

```
syft public.ecr.aws/a4b5h6u6/os-security:latest -o spdx-json=os-security-sbom.spdx.json

 ✔ Loaded image
 ✔ Parsed image
 ✔ Cataloged packages
```

You should now have a file called "os-security-sbom.spdx.json" (or if you used a different name, whatever that was) created. When you look at it, you will see something like:

```
{
 "spdxVersion": "SPDX-2.3",
 "dataLicense": "CC0-1.0",
 "SPDXID": "SPDXRef-DOCUMENT",
 "name": "public.ecr.aws/a4b5h6u6/os-security:latest",
 "documentNamespace": "https://anchore.com/syft/image/public.ecr.aws/a4b5h6u6/os-security-latest-4f52976d-8c05-46a5-8699-1af2a26378f3",
 "creationInfo": {
  "licenseListVersion": "3.19",
  "creators": [
   "Organization: Anchore, Inc",
   "Tool: syft-0.69.0"
  ],
  "created": "2023-01-31T18:09:28Z"
 },
 "packages": [
  {
   "name": "alpine-baselayout",
   "SPDXID": "SPDXRef-Package-apk-alpine-baselayout-e262e1d42d26b294",
   "versionInfo": "3.2.0-r18",
   "originator": "Person: Natanael Copa \u003cncopa@alpinelinux.org\u003e",
   "downloadLocation": "https://git.alpinelinux.org/cgit/aports/tree/main/alpine-baselayout",
   "sourceInfo": "acquired package info from APK DB: /lib/apk/db/installed",
   "licenseConcluded": "GPL-2.0-only",
   "licenseDeclared": "GPL-2.0-only",
   "copyrightText": "NOASSERTION",
   "description": "Alpine base dir structure and init scripts",
   "externalRefs": [
    {
```
(only a small portion of the file)

**Signing our SBOM**

We will first upload our SBOM to our Amazon ECR repo and then we will sign it using the Sigstore Cosign tool. To upload we use the following command:

```
cosign attach sbom --sbom os-security-sbom.spdx.json public.ecr.aws/a4b5h6u6/os-security:latest
```

We get an error when we do this

```
WARNING: Attaching SBOMs this way does not sign them. If you want to sign them, use 'cosign attest --predicate os-security-sbom.spdx.json --key <key path>' or 'cosign sign --key <key path> --attachment sbom <image uri>'.
Uploading SBOM file for [public.ecr.aws/a4b5h6u6/os-security:latest] to [public.ecr.aws/a4b5h6u6/os-security:sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom] with mediaType [spdx+json].
Error: PUT https://public.ecr.aws/v2/a4b5h6u6/os-security/manifests/sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom: UNSUPPORTED: Invalid parameter at 'ImageManifest' failed to satisfy constraint: 'Invalid JSON syntax'
main.go:62: error during command execution: PUT https://public.ecr.aws/v2/a4b5h6u6/os-security/manifests/sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom: UNSUPPORTED: Invalid parameter at 'ImageManifest' failed to satisfy constraint: 'Invalid JSON syntax'
```

When looking at the help, I thought this would be resolved using the following additional command line switches

```
cosign attach sbom --sbom os-security-sbom.spdx.json --input-format json --type spdx public.ecr.aws/a4b5h6u6/os-security:latest
```

But this did not work. If anyone reading has figured out how to do this, would love to hear from you. I re-ran the syft command to output plan spdx text file

```
syft public.ecr.aws/a4b5h6u6/os-security:latest -o spdx=os-security-sbom.spdx
```

And this time when I re-ran the command, it was successful.

```
cosign attach sbom --sbom os-security-sbom.spdx -type spdx public.ecr.aws/a4b5h6u6/os-security:latest
WARNING: Attaching SBOMs this way does not sign them. If you want to sign them, use 'cosign attest --predicate os-security-sbom.spdx --key <key path>' or 'cosign sign --key <key path> --attachment sbom <image uri>'.
Uploading SBOM file for [public.ecr.aws/a4b5h6u6/os-security:latest] to [public.ecr.aws/a4b5h6u6/os-security:sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom] with mediaType [text/spdx].
```

We now have the unsigned sbom in the Amazon ECR repo. We can now sign this, using the the sha256 digest that was output in the previous step. We will use the private key stored in KMS.

```
cosign sign --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security:sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom

Pushing signature to: public.ecr.aws/a4b5h6u6/os-security
```

We can now verify with the following command.

```
cosign verify --key awskms:///arn:aws:kms:eu-west-1:704533066374:alias/devcosign-key public.ecr.aws/a4b5h6u6/os-security:sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom

Verification for public.ecr.aws/a4b5h6u6/os-security:sha256-71debfa41689f10918bd5d5b4265d12892a190e5eb8f688fe9a26fb0298f77c8.sbom --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - The signatures were verified against the specified public key

[{"critical":{"identity":{"docker-reference":"public.ecr.aws/a4b5h6u6/os-security"},"image":{"docker-manifest-digest":"sha256:b6fdec6ba5103faab3a5f5a356d53a69bc33c50fb2f475c2bd429b4d47135bcd"},"type":"cosign container image signature"},"optional":null}]

```

We now have attached and signed a SBOM to our container image.

**Conclusion**

In this short blog post, I covered how you can use the open source tool syft to create a SBOM and then sign and attach this with your container image on Amazon ECR. You can use these building blocks within your automated build pipelines to help catalog and provide visibility into the open source software components you are using. One thing you should be thinking about is that an SBOM in itself does not provide you with much. It is a small piece of a bigger solution that you should be thinking about. I will be exploring this space in future posts. 

I would love the hear more from readers about what your biggest pain points and frustrations when you work with open source is. Please complete [this very short survey](https://pulse.buildon.aws/survey/PJRTOUMK), as this would help me massively. (All responses are anonymous) 

You can check out and explore the syft tool [here](https://github.com/anchore/syft). 