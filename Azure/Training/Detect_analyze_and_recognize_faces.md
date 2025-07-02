# Detect and analyze faces

To use the Azure AI Vision Face API, you must provision a resource for the service in an Azure subscription. You can provision Face as a single-service resource, or you can use the Face API in a multi-service Azure AI Services resource; which can be provisioned as a standalone resource or as part of an Azure AI Foundry hub.

To use your resource from a client application you must connect to its endpoint using either key-based authentication or Microsoft Entra AI authentication. When using the REST interface you can provide the authentication key or token in the request header. When using a language-specific SDK (for example, the Python azure-ai-vision-face package or the Microsoft .NET Azure.AI.Vision.Face package), you use a FaceClient object to connect to the service.

```python

from azure.ai.vision.face import FaceClient
from azure.ai.vision.face.models import *
from azure.core.credentials import AzureKeyCredential

face_client = FaceClient (
    endpoint="<YOUR_RESOURCE_ENDPOINT>",
    credential=AzureKeyCredential("YOUR_RESOURCE_KEY"))

```

To detect and analyze faces in an image, you must specify the model-specific features you want the service to return, and then use the client to call the Detect method.

```python

features = [
    FaceAttributeTypeDetection01.HEAD_PODE,
    FaceAttributeTypeDetection01.OCCLUSION,
    FaceAttributeTypeDetection01.ACCESSORIES]

with open("<IMAGE_FILEPATH>", mode="rb") as image_data:
    detected_face = face_client.detect(
        image_content=image_data.read(),
        detection_model=FaceDetectionModel.DETECTION01,
        recognition_model=FaceRecognitionModel.RECOGNITION01,
        return_face_id=True,
        return_face_attributes=features
    )

```

The response from the service dependes on:

- The model specific features requested.
- The number of faces detected in the image.

A response for an image containing a single face might look similar toe the following example:

```json

[
  {
    'fceRectangle': {'top': 174, 'left': 247, 'width': 246, 'height': 246},
    'faceAttributes':
    {
      'headPose': {'putch': 3.7, 'roll': -7.7, 'yaw': -20.9},
      'accessories':
        [
          {'type': 'glasses', 'confidence': 1.0}
        ],
      'occllusion': {'foreheadOccluded': False, 'eyeOccluded': False, 'mouthOccluded': False}
    }
  }
]

```

