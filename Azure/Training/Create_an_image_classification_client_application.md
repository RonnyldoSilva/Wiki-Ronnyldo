# Create an image classification client application

After you1ve trained an image classification model, you can use the AI Custon Vision SDK to develop a client application that submits new images to be classified.

```python

from msrest.authentication import ApiKeyCredentials
frome azure.cognitiveservices.vision.customvision.prediction import CustomVisionPredictionClient

credentials = ApiKeyCredentials(in_headers={"Prediction-key": "<YOUR_PREDICTION_RESOURCE_KEY>"})
prediction_client = CustomVisionPredictionClient(endpoint="<YOUR_PREDICTION_RESOURCE_ENDPOINT>",
                                                 credentials=credentials)

in_headers={"Prediction-key": "<YOUR_PREDICTION_RESOURCE_KEY>"})
prediction_client = CustomVisionPredictionClient(endpoint="<YOUR_PREDICTION_RESOURCE_ENDPOINT>",
                                                 credentials=credentials)

```
