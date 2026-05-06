---
categories: []
consumed_apis: []
description: Trains and deploys custom machine learning models using Google's AutoML technology with transfer learning and neural architecture search.
layout: capability
name: Google Cloud AutoML API
operations:
- description: Google Cloud AutoML List datasets
  method: GET
  name: listdatasets
  path: /projects/{projectId}/locations/{location}/datasets
- description: Google Cloud AutoML Create a dataset
  method: POST
  name: createdataset
  path: /projects/{projectId}/locations/{location}/datasets
- description: Google Cloud AutoML List models
  method: GET
  name: listmodels
  path: /projects/{projectId}/locations/{location}/models
- description: Google Cloud AutoML Create a model
  method: POST
  name: createmodel
  path: /projects/{projectId}/locations/{location}/models
- description: Google Cloud AutoML Get a model
  method: GET
  name: getmodel
  path: /projects/{projectId}/locations/{location}/models/{modelId}
- description: Google Cloud AutoML Delete a model
  method: DELETE
  name: deletemodel
  path: /projects/{projectId}/locations/{location}/models/{modelId}
- description: Google Cloud AutoML Make a prediction
  method: POST
  name: predict
  path: /projects/{projectId}/locations/{location}/models/{modelId}:predict
personas: []
provider_name: Google Cloud AutoML
provider_slug: google-cloud-automl
search_terms:
- google cloud automl get a model
- google cloud automl list models
- custom models
- training
- google cloud automl list datasets
- listdatasets
- cloud
- deletemodel
- google
- createdataset
- getmodel
- google cloud automl create a dataset
- listmodels
- predict
- machine learning
- createmodel
- api
- google cloud automl create a model
- automl
- google cloud automl delete a model
- google cloud
- google cloud automl make a prediction
slug: google-cloud-automl-capability
source_filename: google-cloud-automl-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud AutoML API\n  description: Trains and deploys custom machine learning models using Google's AutoML technology with transfer learning and\n    neural architecture search.\n  tags:\n  - Google\n  - Cloud\n  - Automl\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-automl\n    baseUri: https://automl.googleapis.com/v1\n    description: Google Cloud AutoML API HTTP API.\n    resources:\n    - name: projects-projectid-locations-location-datasets\n      path: /projects/{projectId}/locations/{location}/datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: Google Cloud AutoML List datasets\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdataset\n        method: POST\n        description: Google Cloud AutoML Create a dataset\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-models\n      path: /projects/{projectId}/locations/{location}/models\n      operations:\n      - name: listmodels\n        method: GET\n        description: Google Cloud AutoML List models\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n     \
  \     type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmodel\n        method: POST\n        description: Google Cloud AutoML Create a model\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-models-mod\n      path: /projects/{projectId}/locations/{location}/models/{modelId}\n      operations:\n      - name: getmodel\n        method: GET\n        description: Google Cloud AutoML Get a model\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        - name: modelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description: Google Cloud AutoML Delete a model\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: modelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-models-mod\n      path: /projects/{projectId}/locations/{location}/models/{modelId}:predict\n\
  \      operations:\n      - name: predict\n        method: POST\n        description: Google Cloud AutoML Make a prediction\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: modelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-automl-rest\n    description: REST adapter for Google Cloud AutoML API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: Google Cloud AutoML List datasets\n        call: google-cloud-automl.listdatasets\n        with:\n\
  \          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/datasets\n      name: createdataset\n      operations:\n      - method: POST\n        name: createdataset\n        description: Google Cloud AutoML Create a dataset\n        call: google-cloud-automl.createdataset\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: Google Cloud AutoML List models\n        call: google-cloud-automl.listmodels\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /projects/{projectId}/locations/{location}/models\n      name: createmodel\n      operations:\n      - method: POST\n        name: createmodel\n        description: Google Cloud AutoML Create a model\n        call: google-cloud-automl.createmodel\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/models/{modelId}\n      name: getmodel\n      operations:\n      - method: GET\n        name: getmodel\n        description: Google Cloud AutoML Get a model\n        call: google-cloud-automl.getmodel\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/models/{modelId}\n      name: deletemodel\n      operations:\n      - method: DELETE\n\
  \        name: deletemodel\n        description: Google Cloud AutoML Delete a model\n        call: google-cloud-automl.deletemodel\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/models/{modelId}:predict\n      name: predict\n      operations:\n      - method: POST\n        name: predict\n        description: Google Cloud AutoML Make a prediction\n        call: google-cloud-automl.predict\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-automl-mcp\n    transport: http\n    description: MCP adapter for Google Cloud AutoML API for AI agent use.\n    tools:\n    - name: listdatasets\n    \
  \  description: Google Cloud AutoML List datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-automl.listdatasets\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdataset\n      description: Google Cloud AutoML Create a dataset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-automl.createdataset\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n\
  \      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodels\n      description: Google Cloud AutoML List models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-automl.listmodels\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmodel\n      description: Google Cloud AutoML Create a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-automl.createmodel\n      with:\n      \
  \  projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodel\n      description: Google Cloud AutoML Get a model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-automl.getmodel\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        modelId: tools.modelId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: modelId\n        type: string\n        description: modelId\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: Google Cloud AutoML Delete a model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-automl.deletemodel\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        modelId: tools.modelId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: modelId\n        type: string\n        description: modelId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: predict\n      description: Google Cloud AutoML Make a prediction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-automl.predict\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n        modelId: tools.modelId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: modelId\n        type: string\n        description: modelId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-automl/refs/heads/main/capabilities/google-cloud-automl-capability.yaml
tags:
- Google
- Cloud
- Automl
- API
tools:
- description: Google Cloud AutoML List datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Google Cloud AutoML Create a dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdataset
- description: Google Cloud AutoML List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Google Cloud AutoML Create a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmodel
- description: Google Cloud AutoML Get a model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodel
- description: Google Cloud AutoML Delete a model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Google Cloud AutoML Make a prediction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: predict
---
