---
title: 'Using Amazon CodeWhisperer as my scripting sidekick'
date: '2023-09-04'
tags : [ python, AWS CodeWhisperer, Amazon SageMaker]

---

How are you using these new AI coding assistants like Amazon CodeWhisperer? I want to share a quick story about how I am finding some success with using these tools, which I hope will encourage you to experiment for yourselves.

As I work on new projects, demos, blog posts, I often need to do supporting activities such as creating or cleaning up AWS environments, which I sometimes do by hand but mostly do via the AWS CLI or via Python scripts and boto3. I am working on a some demos to show how you can use tools like Griptape, which is a Python framework for AI workflows and pipelines which you can think of as an enterprise grade alternative to LangChain. I needed to delete a bunch of resources in my Amazon Sagemaker environment that I had forgotten to clean up. I had a few hundred SageMaker Models that were really distracting me as I love to have clean environments when I start writing new content.

Typically I might just use the console to clean these up, but there were just too many so I decided to write a quick script to do this. In my VSCode I have Amazon CodeWispherer enabled via the AWS Toolkit (check out [this video](https://aws-oss.beachgeek.co.uk/37n) if you want to learn how). I thought I would try and use it to create a script to help me automate this.

I created a new file called "cleanup-sagemaker-models.py" and in the first line I wrote

```
# create a python function that takes in a parameter and then iteratively deletes sagemaker models using that parameter as a search string
```

When I hit enter, Amazon CodeWhisperer offered my some code. I was not happy with the first choice, so I hit the right arrow key on my keyboard, which instructs Amazon CodeWhisperer to give me some different code. The second choice was exactly what I was looking for. Here is the code:

> **Note!** Do not use this script yourself unless you understand what it will do - this deletes permanently Amazon SageMaker models

```
import boto3
def delete_sagemaker_models(model_name_prefix):
    sagemaker_client = boto3.client('sagemaker')

    try:
        models = sagemaker_client.list_models(
            NameContains=model_name_prefix,
            SortBy='CreationTime',
            SortOrder='Descending'
        )
        for model in models['Models']:
            sagemaker_client.delete_model(ModelName=model['ModelName'])
            print(f"Deleted model {model['ModelName']}")

    except Exception as e:
        print(e)
        print("No models found")
        return
    
    print("Done")

# delete_sagemaker_models("test-model-")
```

I had to press return a few times during this, Amazon CodeWhisperer did not provide this in one go. If you find that it brings back some code and then stops, it is work hitting return until the code stops coming.

The only thing I had to do is now call this with the search prefixes I wanted to delete, which in my case was


```
delete_sagemaker_models("sagemaker-sklearn-automl")
```

I saved this file and then run it.

```
python cleanup-sagemaker-models.py
Deleted model sagemaker-sklearn-automl-2021-05-26-17-53-18-718
Deleted model sagemaker-sklearn-automl-2021-05-26-17-52-59-126
Deleted model sagemaker-sklearn-automl-2021-05-26-17-45-54-363
Deleted model sagemaker-sklearn-automl-2021-05-26-17-45-48-622
Deleted model sagemaker-sklearn-automl-2021-05-26-17-45-42-967
Deleted model sagemaker-sklearn-automl-2021-05-26-17-45-38-859
Done
```

I re-ran the script a few times, changing the search prefix until it had successfully removed all the old SageMaker models.

**Improving the script**

When I ran the script, I realised it was only bringing back the first page of models as they appear in the Amazon SageMaker console. I explored the "[sagemaker_client.list_models](https://aws-oss.beachgeek.co.uk/37o)" documentation in boto3 and noticed there was a "MaxResults=" parameter that could be set. I could set this myself, and this would have improved the script. But maybe I can see if Amazon CodeWhisperer can do this for me.

I deleted the script, and the tried again, this time using this comment

```
# create a python function that takes in a parameter and then iteratively deletes the first 50 sagemaker models using that parameter as a search string
```

This provided different code to the first script

```
# create a python function that takes in a parameter and then iteratively deletes the first 50 sagemaker models using that parameter as a search string
import boto3
def delete_sagemaker_models(model_name_prefix):
    sagemaker_client = boto3.client('sagemaker')

    # get all models that start with the model_name_prefix
    models = sagemaker_client.list_models(
        NameContains=model_name_prefix,
        SortBy='CreationTime',
        SortOrder='Descending'
    )

    # delete the first 50 models
    for model in models['Models'][:50]:
        sagemaker_client.delete_model(ModelName=model['ModelName'])
        print(f"Deleted model {model['ModelName']}")

delete_sagemaker_models('test-model-')
```

I updated ran the script and this time it went through and removed all instances of the models without having to re-run the script. Success!

**How will you use Amazon CodeWhisperer?**

Thank you Amazon CodeWhisperer, you are going to be a very handy side kick that will make tasks like this, a walk in the park. As I hope this quick example shows, you do need to evaluate the code that is generated, and it might not always do what you think it will do, so it is important to review and understand the code. As in the example above, whilst the initial script worked great, I had to re-run it a few times. It was simple enough to update to fix, but it is also something that I could have addressed if my initial prompt was better. This is something that I am learning to get better at. 

I would be interested to hear how you are using tools like Amazon CodeWhisperer to make your lives easier. Please share via the comments or reach out to me directly.