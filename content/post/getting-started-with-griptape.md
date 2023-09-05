---
title: 'Getting gnarly with AI - a quick look at Griptape, an enterprise ready alternative to LangChain'
date: '2023-09-05'
tags : [ Griptape, Amazon SageMaker, LLMs, Falcon7b, OpenAI,]

---

## Getting started with Griptape

**Getting gnarly with AI**

When I was much much younger, I was known to (very occasionally) drop an ollie, kick-turn, or very occasionally dare a drop in on my trusty skateboard. Thanks to the grip tape, my shoes would stick to the board, and gave me the confidence I could try these tricks. I was always grateful to that grip tape and who knew all these years later, I would become re-aquatinted with it (albeit in a different form!)

Last week I had a quick call with the folks behind [Griptape](https://aws-oss.beachgeek.co.uk/37t), an Apache 2.0 licenced open source project that hopes to empower developers to build a new generation of applications powered by the capabilities of large language models. It looks super interesting, and for folks who are already exploring this space, the way that I was thinking of Griptape is as a more production ready version of LangChain.

Enough of an introduction, in this post I am going to take a quick look at Griptape, and show you how you can get it up and running to interact with the Falcon-7b large language model, deployed on Amazon SageMaker.

What you will need:

* An AWS Account with the right level of access (Admin equiv)
* An OpenAI API key - if you do not have one, don't worry, as we will also be using Falcon7b which does not require an API key
* Code for this post can be found in the [GitHub repo](https://github.com/094459/griptape-hello-world)

Lets get stuck in.

**Setting up our AWS Cloud9 environment**

The Griptape tutorial shows you how you can get started with VSCode. I am a big fan and user of this, but when it comes to working with data and machine learning technologies, I tend to work on my AWS Cloud 9 environment as I can scale up performance and capacity as I needed (my Macbook is not quite as shiny as it once was!). The first thing I did was to create my AWS Cloud9 environment, and setup a few dependencies (updating Python to run 3.10, [check out the script I use here](https://aws-oss.beachgeek.co.uk/37p)). Griptape requires version 3.9 or newer of Python (as of writing, but check the docs), so I should be good to go.

The first thing I always do when working with a new Python project, is to create a fresh virtual environment. It makes your life so much easier.

```
python -m venv griptape
cd griptape/
source bin/activate
(griptape) $

```

As we are going to be testing this with OpenAI, we now need to configure our API access. We will create a .env file and add our key that way (replacing the XXXX with your own OpenAI key) and install python-dotenv to make it easier to use.

```
pip install python-dotenv
touch .env
echo 'OPENAI_API_KEY="xxxxxxxxxxxx" ' > .env
```

The final step is to install the griptape Python library

```
pip install griptape
```

Don't worry if you see a lot of additional Python libraries installed. This is the output I got (your may vary, but you get the idea)

```
Installing collected packages: tokenizers, stringcase, stopit, sortedcontainers, safetensors, pytz, python-decouple, graphlib, backports-datetime-fromisoformat, asn1crypto, zipp, websocket-client, urllib3, tzlocal, typing-extensions, tqdm, tomlkit, tld, tenacity, sniffio, six, rpds-py, regex, pyyaml, PyPDF2, pyjwt, pygments, pycryptodomex, pycparser, platformdirs, packaging, oscrypto, numpy, multidict, mdurl, MarkupSafe, lxml, loguru, langcodes, jmespath, idna, h11, greenlet, fsspec, frozenlist, fastavro, exceptiongroup, dnspython, distro, contextlib2, click, charset-normalizer, certifi, backoff, attrs, async-timeout, yarl, uvicorn, sqlalchemy, schema, requests, referencing, redis, python-dateutil, pymongo, pydantic, marshmallow, markdown-it-py, justext, jinja2, importlib_metadata, filelock, courlan, cffi, anyio, aiosignal, tiktoken, starlette, sqlalchemy-redshift, rich, pinecone-client, marshmallow-enum, marqo, jsonschema-specifications, huggingface-hub, httpcore, docker, dateparser, cryptography, botocore, aiohttp, transformers, s3transfer, pyOpenSSL, openai, jsonschema, httpx, htmldate, fastapi, cohere, trafilatura, snowflake-connector-python, boto3, anthropic, snowflake-sqlalchemy, griptape
Successfully installed MarkupSafe-2.1.3 PyPDF2-3.0.1 aiohttp-3.8.5 aiosignal-1.3.1 anthropic-0.3.11 anyio-3.7.1 asn1crypto-1.5.1 async-timeout-4.0.3 attrs-23.1.0 backoff-2.2.1 backports-datetime-fromisoformat-2.0.0 boto3-1.28.40 botocore-1.31.40 certifi-2023.7.22 cffi-1.15.1 charset-normalizer-3.2.0 click-8.1.7 cohere-4.21 contextlib2-21.6.0 courlan-0.9.3 cryptography-41.0.3 dateparser-1.1.8 distro-1.8.0 dnspython-2.4.2 docker-6.1.3 exceptiongroup-1.1.3 fastapi-0.103.1 fastavro-1.8.2 filelock-3.12.3 frozenlist-1.4.0 fsspec-2023.9.0 graphlib-0.9.5 greenlet-2.0.2 griptape-0.15.3 h11-0.14.0 htmldate-1.5.0 httpcore-0.17.3 httpx-0.24.1 huggingface-hub-0.16.4 idna-3.4 importlib_metadata-6.8.0 jinja2-3.1.2 jmespath-1.0.1 jsonschema-4.19.0 jsonschema-specifications-2023.7.1 justext-3.0.0 langcodes-3.3.0 loguru-0.7.1 lxml-4.9.3 markdown-it-py-3.0.0 marqo-1.2.4 marshmallow-3.20.1 marshmallow-enum-1.5.1 mdurl-0.1.2 multidict-6.0.4 numpy-1.25.2 openai-0.28.0 oscrypto-1.3.0 packaging-23.1 pinecone-client-2.2.2 platformdirs-3.8.1 pyOpenSSL-23.2.0 pycparser-2.21 pycryptodomex-3.18.0 pydantic-1.10.12 pygments-2.16.1 pyjwt-2.8.0 pymongo-4.5.0 python-dateutil-2.8.2 python-decouple-3.8 pytz-2023.3 pyyaml-6.0.1 redis-4.6.0 referencing-0.30.2 regex-2023.8.8 requests-2.31.0 rich-13.5.2 rpds-py-0.10.2 s3transfer-0.6.2 safetensors-0.3.3 schema-0.7.5 six-1.16.0 sniffio-1.3.0 snowflake-connector-python-3.1.1 snowflake-sqlalchemy-1.5.0 sortedcontainers-2.4.0 sqlalchemy-1.4.49 sqlalchemy-redshift-0.8.14 starlette-0.27.0 stopit-1.1.2 stringcase-1.2.0 tenacity-8.2.3 tiktoken-0.4.0 tld-0.13 tokenizers-0.13.3 tomlkit-0.12.1 tqdm-4.66.1 trafilatura-1.6.1 transformers-4.32.1 typing-extensions-4.7.1 tzlocal-5.0.1 urllib3-1.26.16 uvicorn-0.23.2 websocket-client-1.6.2 yarl-1.9.2 zipp-3.16.2
```

This now looks good, so we can now get stuck in and try it out.

**Hello World**

Before we move onto more advanced topics, lets make sure that we can Griptape to do something quickly for us. The tutorial shows you how you can use it to ask OpenAI a prompt, so lets try that.


Griptape uses the concept of Agents as a way of running tasks. One such task might be to communicate with Large Language Models (LLM's), although Agents also do other things too.

```
from griptape.structures import Agent

load_dotenv() # Load the environment variables

# Create the Agent
agent = Agent()

# Run the agent
agent.run("Can you tell me what griptape is?")
```

We can see here that we have only added a few lines of code. We have used the Agent class in the Griptape library, and then got it to run a prompt against our configured LLM (which at the moment is OpenAI, which is configured via the .env). When we run this python command we get the following:

```
[09/04/23 16:21:21] INFO     Task 7c75ca4912a74e628695d29b50678e23                                                                                                                                                                                                                      
                             Input: Can you tell me what griptape is?                                                                                                                                                                                                                   
WARNING:root:<RetryCallState 140256866511328: attempt #1; slept for 0.0; last result: failed (InvalidRequestError The model `gpt-4` does not exist or you do not have access to it. Learn more: https://help.openai.com/en/articles/7102672-how-can-i-access-gpt-4.)>
WARNING:root:<RetryCallState 140256866511328: attempt #2; slept for 2.0; last result: failed (InvalidRequestError The model `gpt-4` does not exist or you do not have access to it. Learn more: https://help.openai.com/en/articles/7102672-how-can-i-access-gpt-4.)>

```

Ok, so this is not what I was expecting. My OpenAI account does not currently support calls to gpt-4, which is the default being used by Griptape. A quick [look at the documentation here](https://aws-oss.beachgeek.co.uk/37q) provides me with I hope, the answer. Lets update our code.

```
from dotenv import load_dotenv

load_dotenv()

from griptape.drivers import OpenAiChatPromptDriver
from griptape.structures import Agent

agent = Agent(
    prompt_driver=OpenAiChatPromptDriver(
        model="gpt-3.5-turbo"
    )
)

agent.run(
    "Can you tell me what griptape is?"
)

```

And now we get some output

```
[09/04/23 17:25:13] INFO     Task 04a64a6156f84767a5abc3a47a649515                                                                                                                                                                                                                      
                             Input: Can you tell me what griptape is?                                                                                                                                                                                                                   
[09/04/23 17:25:18] INFO     Task 04a64a6156f84767a5abc3a47a649515                                                                                                                                                                                                                      
                             Answer: Of course! Griptape is a type of adhesive material that is applied to the top surface of a skateboard or a longboard deck. It provides traction and grip for the rider's feet, helping them maintain control and stability while riding. Griptape  
                             is usually made of a layer of sandpaper-like material with a sticky backing that adheres to the deck. It's an essential component for skateboarders and longboarders to ensure a secure footing while performing tricks or cruising. Is there anything else
                             you'd like to know about?  
```

We can improve that by changing the prompt to "based on https://www.griptape.ai/, tell me what Griptape is" and running this again

```
[09/04/23 17:28:23] INFO     Task 38051d0336204eb0aa12f8ac64a76023                                                                                                                                                                                                                      
                             Input: based on https://www.griptape.ai/, tell me what Griptape is                                                                                                                                                                                         
[09/04/23 17:28:28] INFO     Task 38051d0336204eb0aa12f8ac64a76023                                                                                                                                                                                                                      
                             Answer: Griptape is an AI-powered conversational assistant that aims to provide a friendly and helpful experience. It can assist with a wide range of tasks, such as answering questions, providing information, and engaging in casual conversation.      
                             Griptape is designed to be intuitive and user-friendly, making it easy for anyone to interact with. Whether you need assistance with a specific topic or simply want to have a friendly chat, Griptape is here to help! 
```

In only a few lines of code, we have managed to get up and running with our LLM.

**Using Griptape on our own LLMs**

What if we wanted to use Griptape with a different LLM, for example Falcon7b?

First lets deploy Falcon7b as an endpoint on Amazon SageMaker. We can create a Python script to do this. We create a file called "deploy_falcon.py" which contains the following code:

```
import json
import boto3
import time
from sagemaker.huggingface import get_huggingface_llm_image_uri
from sagemaker.huggingface import HuggingFaceModel

# get image from huggingface
llm_image = get_huggingface_llm_image_uri(
  "huggingface",
  version="0.8.2"
)

assume_role_policy_document = json.dumps({
    "Version": "2012-10-17",
    "Statement": [
        {
        "Effect": "Allow",
        "Principal": {
            "Service": [
                "sagemaker.amazonaws.com",
                "ecs.amazonaws.com"
            ]
        },
        "Action": "sts:AssumeRole"
        }
    ]
})

SAGEMAKER_IAM_ROLE_NAME = 'Sagemaker-Endpoint-Creation-Role'
SAGEMAKER_ENDPOINT_NAME = "huggingface-pytorch-sagemaker-endpoint"

def get_iam_role(role_name=SAGEMAKER_IAM_ROLE_NAME):
    iam_client = boto3.client('iam')

    try: 
        role = iam_client.get_role(RoleName=role_name)
        role_arn = role['Role']['Arn']
        print(f"Role {role_arn} found!")
        return role_arn
    
    except:
        role_arn = iam_client.create_role(
            RoleName=SAGEMAKER_IAM_ROLE_NAME,
            AssumeRolePolicyDocument=assume_role_policy_document
            )['Role']['Arn']

        time.sleep(10) # give the policy some time to properly create

        response = iam_client.attach_role_policy(
            PolicyArn='arn:aws:iam::aws:policy/AmazonSageMakerFullAccess',
            RoleName=SAGEMAKER_IAM_ROLE_NAME,
        )
        print(f"Creating {role_arn}")
        time.sleep(20) # give iam time to let the role create
        return role_arn


# Define Model and Endpoint configuration parameter

health_check_timeout = 300
trust_remote_code = True

# Create sagemaker endpoint, default values are flan t5 xxl in a g5.8xl instance
def create_endpoint_from_HF_image(hf_model_id, instance_type="ml.g5.8xlarge", endpoint_name=SAGEMAKER_ENDPOINT_NAME, number_of_gpu=1):
    sagemaker_client = boto3.client('sagemaker')

    try: # check if endpoint already existst
        sagemaker_client.describe_endpoint(EndpointName=SAGEMAKER_ENDPOINT_NAME)
        print(f"Endpoint with name {SAGEMAKER_ENDPOINT_NAME} found!")
        return
    
    except:
        print(f"Creating endpoint with model{hf_model_id} on {instance_type}...")

        # create HuggingFaceModel with the image uri
        llm_model = HuggingFaceModel(
            role=get_iam_role(),
            image_uri=llm_image,
            env={
                'HF_MODEL_ID': hf_model_id,
                'SM_NUM_GPUS': json.dumps(number_of_gpu),
                'HF_MODEL_TRUST_REMOTE_CODE': json.dumps(trust_remote_code)
            }
        )

        # Deploy model to an endpoint
        # https://sagemaker.readthedocs.io/en/stable/api/inference/model.html#sagemaker.model.Model.deploy
        llm = llm_model.deploy(
            endpoint_name=endpoint_name,
            initial_instance_count=1,
            instance_type=instance_type,
            # volume_size=400, # If using an instance with local SSD storage, volume_size must be None, e.g. p4 but not p3
            container_startup_health_check_timeout=health_check_timeout  # 10 minutes to be able to load the model
        )

        print(f"\nEndpoint created ({endpoint_name})")


create_endpoint_from_HF_image(hf_model_id="tiiuae/falcon-7b-instruct")

```

When we run this, it takes about 5 mins to complete

```
python deploy-falcon7b.py 
Creating endpoint with modeltiiuae/falcon-7b-instruct on ml.g5.8xlarge...
Role arn:aws:iam::xxxxxxx:role/Sagemaker-Endpoint-Creation-Role found!
-----------!
Endpoint created (huggingface-pytorch-sagemaker-endpoint)
```

If we look at the docs, we can see that [Prompt Drivers](https://docs.griptape.ai/griptape-framework/structures/prompt-drivers/) section of the docs for Griptape show us how to interact with different LLMs. When we look at this, we do not see Amazon SageMaker listed. (as of Sep, 23 dear future reader).

From the docs we can see the format of how Griptape Prompt Drivers work, and if we look at the project [source code](https://github.com/griptape-ai/griptape/blob/main/griptape/drivers/prompt_model/sagemaker_falcon_prompt_model_driver.py) we can see code for Falcon, so there is hope yet!

I was running version 0.15.3, and when I looked at the files deployed (by exploring in my site-packages) I could see that these classes where not there. I thought I would build the library from source and update my local installation so I could grab these updated Prompt Drivers.

```
git clone https://github.com/griptape-ai/griptape.git upstream-griptape
cd upstream-griptape
pip install poetry
poetry build
cd dist
pip uninstall griptape
pip install griptape-0.15.3-py3-none-any.whl
```
I now had an up to date version of Griptape up and running, so now lets configure the new Prompt Driver!

I updated my hello-world code to use the SageMakerPromptDriver. When using this you also have to specify an additional class, currently this is either SageMakerFalconPromptModelDriver or SageMakerLlamaPromptModelDriver. As I have deployed Falcon7b,  SageMakerFalconPromptModelDriver is what I needed. This was the finished code.

```
from dotenv import load_dotenv

load_dotenv()

import boto3
from griptape.drivers import AmazonSageMakerPromptDriver
from griptape.drivers import SageMakerFalconPromptModelDriver

from griptape.structures import Agent

agent = Agent(
    prompt_driver=AmazonSageMakerPromptDriver(
        model="huggingface-pytorch-sagemaker-endpoint",
        session=boto3.Session(region_name="eu-west-1"),
        prompt_model_driver_type=SageMakerFalconPromptModelDriver,
    )
)

agent.run(
    "based on https://www.griptape.ai/, tell me what Griptape is"
)
```

When I ran this, I got the following error:

```
python hello-falcon.py 
[09/05/23 09:49:54] INFO     Task 1a09fbdeeea1427a89db8f9aa6a23a24                                                                                                                                                                                                             
                             Input: based on https://www.griptape.ai/, tell me what Griptape is                                                                                                                                                                                
WARNING:root:<RetryCallState 140509363345568: attempt #1; slept for 0.0; last result: failed (ModelError An error occurred (ModelError) when calling the InvokeEndpoint operation: Received client error (422) from primary with message "{"error":"Input validation error: `inputs` tokens + `max_new_tokens` must be <= 1512. Given: 30 `inputs` tokens and 4060 `max_new_tokens`","error_type":"validation"}". See https://eu-west-1.console.aws.amazon.com/cloudwatch/home?region=eu-west-1#logEventViewer:group=/aws/sagemaker/Endpoints/huggingface-pytorch-sagemaker-endpoint in account 704533066374 for more information.)>
```

Taking a look at the source code (this is why we all love open source right!), we can see the current SageMakerFalconPromptModelDriver source code has the following two things I might need to change.

```
class SageMakerFalconPromptModelDriver(BasePromptModelDriver):
    DEFAULT_MAX_TOKENS = 2048

    tokenizer: BaseTokenizer = field(
        default=Factory(
            lambda self: HuggingFaceTokenizer(
                tokenizer=AutoTokenizer.from_pretrained(
                    "tiiuae/falcon-40b",
                    model_max_length=self.prompt_driver.max_tokens
                    if self.prompt_driver.max_tokens else self.DEFAULT_MAX_TOKENS
                )
            ),
            takes_self=True
        ),
        kw_only=True
    )
```
The first is the actual model being used. I have deployed the "tiiuae/falcon-7b-instruct" model as I do not really want to deploy the full falcon40b model for a hello-world application. The second, is that the max tokens for this is currently set to 2048. I updated the code as follows:

```
class SageMakerFalconPromptModelDriver(BasePromptModelDriver):
    DEFAULT_MAX_TOKENS = 1024

    tokenizer: BaseTokenizer = field(
        default=Factory(
            lambda self: HuggingFaceTokenizer(
                tokenizer=AutoTokenizer.from_pretrained(
                    "tiiuae/falcon-7b-instruct",
                    model_max_length=self.prompt_driver.max_tokens
                    if self.prompt_driver.max_tokens else self.DEFAULT_MAX_TOKENS
                )
            ),
            takes_self=True
        ),
        kw_only=True
    )
```

And then rebuilt Griptape from source, uninstalled and then installed this updated version. When I go to re-run the script, we now get success

```
python hello-falcon.py 
Downloading (…)okenizer_config.json: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 220/220 [00:00<00:00, 1.11MB/s]
Downloading (…)/main/tokenizer.json: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 2.73M/2.73M [00:00<00:00, 37.1MB/s]
Downloading (…)cial_tokens_map.json: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 281/281 [00:00<00:00, 1.41MB/s]
[09/05/23 09:54:05] INFO     Task f694b0ee9e874d0293a71aa50db373d4                                                                                                                                                                                                             
                             Input: based on https://www.griptape.ai/, tell me what Griptape is                                                                                                                                                                                
[09/05/23 09:54:07] INFO     Task f694b0ee9e874d0293a71aa50db373d4                                                                                                                                                                                                             
                             Output: Act like a friendly conversational assistant.                                                                                                                                                                                             
                             User: based on https://www.griptape.ai/, tell me what Griptape is.                                                                                                                           
                             Assistant: Griptape is a tool that helps you stay on top of the latest news and trends in the tech industry. It's a great way to stay informed and get insights on the latest developments in the tech world.                                     
                             User   
```

We have successfully got Griptape interacting with our Falcon7b LLM deployed on Amazon SageMaker.


**Next Steps**

In this short blog post, I introduce a new open source tool that makes it easy for developers to get started in building applications that leverage the power of large language models. I have only scratched the surface though, and there are many more features that Griptape has that I am planning to explore. Griptape is a fast evolving open source project, so make sure you check out the [repo here](https://aws-oss.beachgeek.co.uk/37u) - if you like what you see, why not get involved.

Why not take a look at [Griptape](https://aws-oss.beachgeek.co.uk/37t) for yourself. [Griptape](https://aws-oss.beachgeek.co.uk/37t) has some [great tutorials](https://aws-oss.beachgeek.co.uk/37s) and getting started content, and using AWS Cloud9 makes it super easy to try. I really like the combination of text and video which makes it easy to follow along. Why not check it out for yourselves.

Before you disappear, please make sure you read the next section. In this demo/walk through, we provisioned some resources that you do not really want to leave up and running.

**Clean up**

It is really important before you finish that you shut down the SageMaker endpoint that we created as part of deploying Falcon7b. If you do not do this, you will continue to generate costs on your AWS bill.

We create our Python script called "cleanup_falcon.py" - you will notice that we are using the same names defined in the deploy script, so if you do change the deploy script you must make sure that you update this script as well.

```
import boto3
from botocore.exceptions import ClientError

SAGEMAKER_IAM_ROLE_NAME = 'Sagemaker-Endpoint-Creation-Role'
SAGEMAKER_ENDPOINT_NAME = "huggingface-pytorch-sagemaker-endpoint"

sagemaker_client = boto3.client('sagemaker')
iam = boto3.client('iam')


try:
    # verify endpoint exists
    endpoint = sagemaker_client.describe_endpoint(EndpointName=SAGEMAKER_ENDPOINT_NAME)

    print(f"Endpoint {endpoint['EndpointName']} found, shutting down")

    try: # delete both endpoint and configuration
        sagemaker_client.delete_endpoint(
            EndpointName=SAGEMAKER_ENDPOINT_NAME
        )
        sagemaker_client.delete_endpoint_config(
            EndpointConfigName=SAGEMAKER_ENDPOINT_NAME
        )
        print(f"Endpoint {SAGEMAKER_ENDPOINT_NAME} shut down")
    except ClientError as e:
        print(e)
except:
    print(f"Endpoint {SAGEMAKER_ENDPOINT_NAME} does not exist in account {boto3.client('sts').get_caller_identity().get('Account')}")
    
# delete IAM role created

role_name=SAGEMAKER_IAM_ROLE_NAME
try:
    for item in iam.list_attached_role_policies(RoleName=role_name)['AttachedPolicies']:
        policy_arn = item['PolicyArn']
        iam.detach_role_policy(RoleName=role_name, PolicyArn=policy_arn)
        print(f"Detached policy {policy_arn}")
    for item in iam.list_role_policies(RoleName=role_name)['PolicyNames']:
        policy_name = item
        iam.delete_role_policy(RoleName=role_name, PolicyName=policy_name)
        print(f"Deleted inline policy {policy_name}")
    iam.delete_role(RoleName=role_name)
    print(f"Deleted role {role_name}")
except ClientError as e:
        print(e)
```

I then used the script I talked about in [this blog post](https://aws-oss.beachgeek.co.uk/37r) to remove any models that were created. I have not included that here as there is the possibiity of accidently deleting real models you might care about. Check the script and then modify before you run it to remove just the models created during the falcon_deploy script. 

**Help!**

As always, the fun part of putting these blog posts together is when it all goes wrong and you need to figure out how to fix it. I like to inlcude these in my blog posts, as often when folk have issues, searching on the error messages might help you find a fix.

*Changing the default gpt-4 model*

When I first got my code up and running and tried to run this, I got the following error:

```
Input: Can you tell me what griptape is?                                                                                                                                                                                                                   
WARNING:root:<RetryCallState 140256866511328: attempt #1; slept for 0.0; last result: failed (InvalidRequestError The model `gpt-4` does not exist or you do not have access to it. Learn more: https://help.openai.com/en/articles/7102672-how-can-i-access-gpt-4.)
```
It turns out that I had not been using OpenAI enough, so had not made the required minimum payments to qualify for gpt-4. The link shows you how you can resolve this by setting up a payment plan. It was odd because I already had a payment plan, and it was not providing me with the options on the way page. In the end I had to look through the documentation to figure a way of changing the default model being called by Griptape (gpt-4) which is what I documented above. 


*AWS Cloud 9 errors*

If you run into the following error when trying to deploy the Falcon7b model using the Python code

```
botocore.errorfactory.NoSuchEntityException: An error occurred (NoSuchEntity) when calling the GetRole operation: The role with name Sagemaker-Endpoint-Creation-Role cannot be found.


botocore.exceptions.ClientError: An error occurred (InvalidClientTokenId) when calling the CreateRole operation: The security token included in the request is invalid
```
The fix is to disable the default behaviour of AWS Cloud9 in managing temporary credentials (you can disable this via the Preferences > AWS Settings, and then disable the "AWS managed temporary credentials"). Once you have done this, you will then need to configure AWS credentials (using aws configure). Once completed, I reverted back to AWS Cloud9 managing temporary credentials.