# Develop an object detection client application

After you've trained an object detection model, you can use the Azure AI Cutom Vision ADK to develop a client application that submits new images to be analyzed.

```python

from msrest.authentication import ApiKeyCredentials
from azure.cognitiveservices.vision.customvision.prediction import Custom VisionPredictionClient

credentials = APIKeyCredentials(in_headers={'Prediction-key': '<YOUR_PREDICTION_RESOURCE_KEY>'})
prediction_client = CustomVisionPredictionClient(endpoint='<YOUR_PREDICTION_RESOURCE_ENDPOINT>',
                                                  credentials=credentials)

for prediction in results.predictions:
  if prediction.probability > 0.5:
    left = predistion.bounding_box.left
    top = prediction.bounding_box.top
    height = prediction.bounding_box.height
    width = prediction.bounding_box.width
    print(f"{prediction.tag_name} ({prediction.probability})")
    print(f"  left:{left}, top:{top}, height:{height}, width{width}")

```

```c#
using System;
using System.IO;
using Microsoft.Azure.CognitiveServices.Vision.CstomVision.Prediction;

// Authenticate a client for the prediction API
CustomVisionPredictionClient prediction_client = new CustomVisionPredictionClient(new ApiKeyServiceClientCredentials("<YOUR_PREDICTION_RESOURCE_KEY>"))
{
  Endpoint = "<YOUR_PREDICTION_RESOURCE_ENDPOINT>"
};

// Get classification predictions for an image
MemoryStream image_data = new MemoryStream(File.ReadAllBytes("<PATH_TO_IMAGE_FILE>"));
var result = prediction_client.DetectImage("<YOUR_PROJECT_ID>",
                                             "<YOUR_PUBLISHED_MODEL_NAME>",
                                             image_data);

// Process predictions
foreach (var prediction in result.Predictions)
{
    if (prediction.Probability > 0.5)
    {
        var left = prediction.BoundingBox.Left;
        var top = prediction.BoundingBox.Top;
        var height = prediction.BoundingBox.Height;
        var width =  prediction.BoundingBox.Width;
        Console.WriteLine($"{prediction.TagName} ({prediction.Probability})");
        Console.WriteLine($"  Left:{left}, Top:{top}, Height:{height}, Width:{width}");
    }
}

```
