## Building a client app for Azure AI model inference deployments

When you have deployed models to the Azure AI model inference service, you can use the Azure AI Foundry SDK to write code that creates a ChatCompletionsClient object, which you can then use to chat with a deployed model. One of the benefits of using this model deployment type is that you can easily switch between deployed models by changing one parameter in your code (the model deployment name), making it a great way to test against multiple models while developing an app.

The following Python code sample uses a ChatCompletionsClient object to chat with a model deployment named phi-4-model.

´´´python
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

    ## Get a chat client
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
´´´

The ChatCompletionsClient class uses Azure AI Inference library. In addition to the azure-ai-projects and azure-identity packages discussed previously, the sample code shown here assumes that the azure-ai-inference package has been installed:

`pip install azure-ai-inference`

