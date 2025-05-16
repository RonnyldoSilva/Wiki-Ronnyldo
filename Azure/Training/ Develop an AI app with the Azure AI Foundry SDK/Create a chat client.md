
# Building a Client App for Azure AI Model Inference Deployments

When you have deployed models to the Azure AI model inference service, you can use the Azure AI Foundry SDK to write code that creates a `ChatCompletionsClient` object, which you can then use to chat with a deployed model. 

One of the benefits of using this model deployment type is that you can easily switch between deployed models by changing one parameter in your code (the model deployment name), making it a great way to test against multiple models while developing an app.

## Sample Python Code

The following Python code sample uses a `ChatCompletionsClient` object to chat with a model deployment named `phi-4-model`.

```python
from azure.ai.projects import AIProjectClient
from azure.identity import DefaultAzureCredential
from azure.ai.inference.models import SystemMessage, UserMessage

try:
    # Initialize the project client
    project_connection_string = "<region>.api.azureml.ms;<project_id>;<hub_name>;<project_name>"
    project_client = AIProjectClient.from_connection_string(
        credential=DefaultAzureCredential(),
        conn_str=project_connection_string,
    )

    # Get a chat client
    chat = project_client.inference.get_chat_completions_client()

    # Get a chat completion based on a user-provided prompt
    user_prompt = input("Enter a question:")

    response = chat.complete(
        model="phi-4-model",
        messages=[
            SystemMessage("You are a helpful AI assistant that answers questions."),
            UserMessage(user_prompt)
        ],
    )
    print(response.choices[0].message.content)

except Exception as ex:
    print(ex)
```

## Prerequisites

Ensure the following packages are installed:

```bash
pip install azure-ai-inference
```

The `ChatCompletionsClient` class is part of the Azure AI Inference library.

# Building a client app for Azure OpenAI service deployments

When you have deployed models to the Azure OpenAI service, you can use the AIProjectConnection to connect to the Azure OpenAI service resource in your project and then use the Azure OpenAI SDK to chat with your models.

In the Azure AI Foundry SDK for Python, the AIProjectClient class provides a get_azure_openai_client() method that you can use to create an Azure OpenAI client object. You can then use the classes and methods defined in the Azure OpenAI SDK to consume a model deployed to the Azure OpenAI service.

The following Python code sample uses the Azure AI Foundry and Azure OpenAI SDKs to chat with a model deployment named `gpt-4-model`.

```python
from azure.ai.projects import AIProjectClient
from azure.identity import DefaultAzureCredential
import openai


try:
    # Initialize the project client
    project_connection_string = "<region>.api.azureml.ms;<project_id>;<hub_name>;<project_name>"
    project_client = AIProjectClient.from_connection_string(
        credential=DefaultAzureCredential(),
        conn_str=project_connection_string,
    )

    ## Get an Azure OpenAI chat client
    openai_client = project_client.inference.get_azure_openai_client(api_version="2024-06-01")

    # Get a chat completion based on a user-provided prompt
    user_prompt = input("Enter a question:")
    response = openai_client.chat.completions.create(
        model="gpt-4-model",
        messages=[
            {"role": "system", "content": "You are a helpful AI assistant that answers questions."},
            {"role": "user", "content": user_prompt},
        ]
    )
    print(response.choices[0].message.content)

except Exception as ex:
    print(ex)
```

## Prerequisites

Ensure the following packages are installed:

```bash
pip install openai
```
