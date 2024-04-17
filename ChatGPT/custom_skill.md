# Custom Skill

## Create a custom skill

Your custom skill must implement the expected schema for input and output data that is expected by skills in an Azure AI Search skillset.

### Input Schema

The input schema for a custom skill defines a JSON structure containing a record for each document to be processed. Each document has a unique identifier, and a data payload with one or more inputs, like this:

```json
{
    "values": [
      {
        "recordId": "<unique_identifier>",
        "data":
           {
             "<input1_name>":  "<input1_value>",
             "<input2_name>": "<input2_value>",
             ...
           }
      },
      {
        "recordId": "<unique_identifier>",
        "data":
           {
             "<input1_name>":  "<input1_value>",
             "<input2_name>": "<input2_value>",
             ...
           }
      },
      ...
    ]
}
```
### Output schema

The schema for the results returned by your custom skill reflects the input schema. It is assumed that the output contains a record for each input record, with either the results produced by the skill or details of any errors that occurred.

```json
{
    "values": [
      {
        "recordId": "<unique_identifier_from_input>",
        "data":
           {
             "<output1_name>":  "<output1_value>",
              ...
           },
         "errors": [...],
         "warnings": [...]
      },
      {
        "recordId": "< unique_identifier_from_input>",
        "data":
           {
             "<output1_name>":  "<output1_value>",
              ...
           },
         "errors": [...],
         "warnings": [...]
      },
      ...
    ]
}
```

## Add a custom skill to a skillset

To integrate a custom skill into your indexing solution, you must add a skill for it to a skillset using the Custom.WebApiSkill skill type.

The skill definition must:

- Specify the URI to your web API endpoint, including parameters and headers if necessary.
- Set the context to specify at which point in the document hierarchy the skill should be called
- Assign input values, usually from existing document fields
- Store output in a new field, optionally specifying a target field name (otherwise the output name is used)

```json
{
    "skills": [
      ...,
      {
        "@odata.type": "#Microsoft.Skills.Custom.WebApiSkill",
        "description": "<custom skill description>",
        "uri": "https://<web_api_endpoint>?<params>",
        "httpHeaders": {
            "<header_name>": "<header_value>"
        },
        "context": "/document/<where_to_apply_skill>",
        "inputs": [
          {
            "name": "<input1_name>",
            "source": "/document/<path_to_input_field>"
          }
        ],
        "outputs": [
          {
            "name": "<output1_name>",
            "targetName": "<optional_field_name>"
          }
        ]
      }
  ]
}
```
