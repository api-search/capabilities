---
categories: []
consumed_apis: []
description: Provides programmatic access to build, deploy, and manage machine learning models, run predictions, manage datasets, and orchestrate ML pipelines on Google Cloud.
layout: capability
name: Google Vertex AI API
operations:
- description: Google Vertex AI List models
  method: GET
  name: listmodels
  path: /projects/{project}/locations/{location}/models
- description: Google Vertex AI Get a model
  method: GET
  name: getmodel
  path: /projects/{project}/locations/{location}/models/{model}
- description: Google Vertex AI Delete a model
  method: DELETE
  name: deletemodel
  path: /projects/{project}/locations/{location}/models/{model}
- description: Google Vertex AI List endpoints
  method: GET
  name: listendpoints
  path: /projects/{project}/locations/{location}/endpoints
- description: Google Vertex AI Create an endpoint
  method: POST
  name: createendpoint
  path: /projects/{project}/locations/{location}/endpoints
- description: Google Vertex AI Run a prediction
  method: POST
  name: predict
  path: /projects/{project}/locations/{location}/endpoints/{endpoint}:predict
- description: Google Vertex AI List datasets
  method: GET
  name: listdatasets
  path: /projects/{project}/locations/{location}/datasets
- description: Google Vertex AI List training pipelines
  method: GET
  name: listtrainingpipelines
  path: /projects/{project}/locations/{location}/trainingPipelines
personas: []
provider_name: Google Vertex AI
provider_slug: google-vertex-ai
search_terms:
- createendpoint
- listdatasets
- vertex
- google vertex ai list endpoints
- ai
- api
- google vertex ai get a model
- listendpoints
- google vertex ai list datasets
- artificial intelligence
- google
- deletemodel
- getmodel
- machine learning
- listmodels
- google vertex ai run a prediction
- generative ai
- google vertex ai list models
- ml models
- google vertex ai list training pipelines
- predict
- listtrainingpipelines
- google vertex ai delete a model
- google vertex ai create an endpoint
- google cloud
slug: google-vertex-ai-capability
source_filename: google-vertex-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Vertex AI API\n  description: Provides programmatic access to build, deploy, and manage machine learning models, run predictions, manage\n    datasets, and orchestrate ML pipelines on Google Cloud.\n  tags:\n  - Google\n  - Vertex\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-vertex-ai\n    baseUri: https://us-central1-aiplatform.googleapis.com/v1\n    description: Google Vertex AI API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_VERTEX_AI_TOKEN}}'\n    resources:\n    - name: projects-project-locations-location-models\n      path: /projects/{project}/locations/{location}/models\n      operations:\n      - name: listmodels\n        method: GET\n        description: Google Vertex AI List models\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-models-model\n      path: /projects/{project}/locations/{location}/models/{model}\n      operations:\n      - name: getmodel\n        method: GET\n        description: Google Vertex AI Get a model\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description: Google Vertex AI Delete\
  \ a model\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-endpoints\n      path: /projects/{project}/locations/{location}/endpoints\n      operations:\n      - name: listendpoints\n        method: GET\n        description: Google Vertex AI List endpoints\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: createendpoint\n        method: POST\n        description: Google Vertex AI Create an endpoint\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-endpoints-en\n      path: /projects/{project}/locations/{location}/endpoints/{endpoint}:predict\n      operations:\n      - name: predict\n        method: POST\n        description: Google Vertex AI Run a prediction\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: endpoint\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-datasets\n      path: /projects/{project}/locations/{location}/datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: Google Vertex AI List datasets\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-trainingpipe\n      path: /projects/{project}/locations/{location}/trainingPipelines\n      operations:\n      - name: listtrainingpipelines\n        method: GET\n    \
  \    description: Google Vertex AI List training pipelines\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-vertex-ai-rest\n    description: REST adapter for Google Vertex AI API.\n    resources:\n    - path: /projects/{project}/locations/{location}/models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: Google Vertex AI List models\n        call: google-vertex-ai.listmodels\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/models/{model}\n\
  \      name: getmodel\n      operations:\n      - method: GET\n        name: getmodel\n        description: Google Vertex AI Get a model\n        call: google-vertex-ai.getmodel\n        with:\n          project: rest.project\n          location: rest.location\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/models/{model}\n      name: deletemodel\n      operations:\n      - method: DELETE\n        name: deletemodel\n        description: Google Vertex AI Delete a model\n        call: google-vertex-ai.deletemodel\n        with:\n          project: rest.project\n          location: rest.location\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/endpoints\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: Google\
  \ Vertex AI List endpoints\n        call: google-vertex-ai.listendpoints\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/endpoints\n      name: createendpoint\n      operations:\n      - method: POST\n        name: createendpoint\n        description: Google Vertex AI Create an endpoint\n        call: google-vertex-ai.createendpoint\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/endpoints/{endpoint}:predict\n      name: predict\n      operations:\n      - method: POST\n        name: predict\n        description: Google Vertex AI Run a prediction\n        call: google-vertex-ai.predict\n        with:\n          project: rest.project\n          location: rest.location\n\
  \          endpoint: rest.endpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: Google Vertex AI List datasets\n        call: google-vertex-ai.listdatasets\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/trainingPipelines\n      name: listtrainingpipelines\n      operations:\n      - method: GET\n        name: listtrainingpipelines\n        description: Google Vertex AI List training pipelines\n        call: google-vertex-ai.listtrainingpipelines\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: google-vertex-ai-mcp\n    transport: http\n    description: MCP adapter for Google Vertex AI API for AI agent use.\n    tools:\n    - name: listmodels\n      description: Google Vertex AI List models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-vertex-ai.listmodels\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodel\n      description: Google Vertex AI Get a model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-vertex-ai.getmodel\n      with:\n        project: tools.project\n        location: tools.location\n\
  \        model: tools.model\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: model\n        type: string\n        description: model\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: Google Vertex AI Delete a model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-vertex-ai.deletemodel\n      with:\n        project: tools.project\n        location: tools.location\n        model: tools.model\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: model\n        type: string\n\
  \        description: model\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listendpoints\n      description: Google Vertex AI List endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-vertex-ai.listendpoints\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createendpoint\n      description: Google Vertex AI Create an endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-vertex-ai.createendpoint\n      with:\n        project: tools.project\n        location: tools.location\n\
  \      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: predict\n      description: Google Vertex AI Run a prediction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-vertex-ai.predict\n      with:\n        project: tools.project\n        location: tools.location\n        endpoint: tools.endpoint\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: endpoint\n        type: string\n        description: endpoint\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listdatasets\n      description: Google Vertex AI List datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-vertex-ai.listdatasets\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtrainingpipelines\n      description: Google Vertex AI List training pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-vertex-ai.listtrainingpipelines\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n\
  \        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_VERTEX_AI_TOKEN: GOOGLE_VERTEX_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-vertex-ai/refs/heads/main/capabilities/google-vertex-ai-capability.yaml
tags:
- Google
- Vertex
- Ai
- API
tools:
- description: Google Vertex AI List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Google Vertex AI Get a model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodel
- description: Google Vertex AI Delete a model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Google Vertex AI List endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Google Vertex AI Create an endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createendpoint
- description: Google Vertex AI Run a prediction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: predict
- description: Google Vertex AI List datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Google Vertex AI List training pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrainingpipelines
---
