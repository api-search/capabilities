---
categories: []
consumed_apis: []
description: Ollama provides a REST API for running and managing large language models locally. The API supports text generation, chat completions, embeddings, model management, and streaming responses. It serves as the primary interface for interacting with models running on the Ollama inference engine at localhost:11434.
layout: capability
name: Ollama API
operations:
- description: Ollama Generate a completion
  method: POST
  name: generatecompletion
  path: /api/generate
- description: Ollama Generate a chat completion
  method: POST
  name: generatechatcompletion
  path: /api/chat
- description: Ollama Generate embeddings
  method: POST
  name: generateembeddings
  path: /api/embed
- description: Ollama List local models
  method: GET
  name: listmodels
  path: /api/tags
- description: Ollama Show model information
  method: POST
  name: showmodelinfo
  path: /api/show
- description: Ollama Create a model
  method: POST
  name: createmodel
  path: /api/create
- description: Ollama Copy a model
  method: POST
  name: copymodel
  path: /api/copy
- description: Ollama Pull a model
  method: POST
  name: pullmodel
  path: /api/pull
- description: Ollama Push a model
  method: POST
  name: pushmodel
  path: /api/push
- description: Ollama Delete a model
  method: DELETE
  name: deletemodel
  path: /api/delete
- description: Ollama List running models
  method: GET
  name: listrunningmodels
  path: /api/ps
- description: Ollama Create a blob
  method: POST
  name: createblob
  path: /api/blobs/{digest}
- description: Get Ollama version
  method: GET
  name: getversion
  path: /api/version
personas: []
provider_name: Ollama
provider_slug: ollama
search_terms:
- get ollama version
- generatechatcompletion
- listrunningmodels
- ollama pull a model
- ollama push a model
- ollama list local models
- showmodelinfo
- pushmodel
- pullmodel
- large language models
- ollama generate a completion
- generateembeddings
- deletemodel
- ollama generate a chat completion
- listmodels
- artificial intelligence
- generatecompletion
- createmodel
- ollama delete a model
- api
- getversion
- ollama create a model
- ollama copy a model
- createblob
- models
- copymodel
- ollama show model information
- ollama create a blob
- ollama list running models
- ollama
- ollama generate embeddings
slug: ollama-capability
source_filename: ollama-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ollama API\n  description: Ollama provides a REST API for running and managing large language models locally. The API supports text generation,\n    chat completions, embeddings, model management, and streaming responses. It serves as the primary interface for interacting\n    with models running on the Ollama inference engine at localhost:11434.\n  tags:\n  - Ollama\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ollama\n    baseUri: http://localhost:11434\n    description: Ollama API HTTP API.\n    resources:\n    - name: api-generate\n      path: /api/generate\n      operations:\n      - name: generatecompletion\n        method: POST\n        description: Ollama Generate a completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-chat\n      path: /api/chat\n      operations:\n\
  \      - name: generatechatcompletion\n        method: POST\n        description: Ollama Generate a chat completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-embed\n      path: /api/embed\n      operations:\n      - name: generateembeddings\n        method: POST\n        description: Ollama Generate embeddings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-tags\n      path: /api/tags\n      operations:\n      - name: listmodels\n        method: GET\n        description: Ollama List local models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-show\n      path: /api/show\n      operations:\n      - name: showmodelinfo\n        method: POST\n        description: Ollama Show model information\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-create\n      path: /api/create\n      operations:\n      - name: createmodel\n        method: POST\n        description: Ollama Create a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-copy\n      path: /api/copy\n      operations:\n      - name: copymodel\n        method: POST\n        description: Ollama Copy a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-pull\n      path: /api/pull\n      operations:\n      - name: pullmodel\n        method: POST\n        description: Ollama Pull a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-push\n      path:\
  \ /api/push\n      operations:\n      - name: pushmodel\n        method: POST\n        description: Ollama Push a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-delete\n      path: /api/delete\n      operations:\n      - name: deletemodel\n        method: DELETE\n        description: Ollama Delete a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-ps\n      path: /api/ps\n      operations:\n      - name: listrunningmodels\n        method: GET\n        description: Ollama List running models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-blobs-digest\n      path: /api/blobs/{digest}\n      operations:\n      - name: createblob\n        method: POST\n        description: Ollama Create a blob\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-version\n      path: /api/version\n      operations:\n      - name: getversion\n        method: GET\n        description: Get Ollama version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ollama-rest\n    description: REST adapter for Ollama API.\n    resources:\n    - path: /api/generate\n      name: generatecompletion\n      operations:\n      - method: POST\n        name: generatecompletion\n        description: Ollama Generate a completion\n        call: ollama.generatecompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/chat\n      name: generatechatcompletion\n      operations:\n      - method: POST\n        name: generatechatcompletion\n        description:\
  \ Ollama Generate a chat completion\n        call: ollama.generatechatcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/embed\n      name: generateembeddings\n      operations:\n      - method: POST\n        name: generateembeddings\n        description: Ollama Generate embeddings\n        call: ollama.generateembeddings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/tags\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: Ollama List local models\n        call: ollama.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/show\n      name: showmodelinfo\n      operations:\n      - method: POST\n        name: showmodelinfo\n        description: Ollama Show model information\n        call: ollama.showmodelinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /api/create\n      name: createmodel\n      operations:\n      - method: POST\n        name: createmodel\n        description: Ollama Create a model\n        call: ollama.createmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/copy\n      name: copymodel\n      operations:\n      - method: POST\n        name: copymodel\n        description: Ollama Copy a model\n        call: ollama.copymodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/pull\n      name: pullmodel\n      operations:\n      - method: POST\n        name: pullmodel\n        description: Ollama Pull a model\n        call: ollama.pullmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/push\n      name: pushmodel\n      operations:\n      - method: POST\n        name: pushmodel\n        description: Ollama Push a model\n        call: ollama.pushmodel\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/delete\n      name: deletemodel\n      operations:\n      - method: DELETE\n        name: deletemodel\n        description: Ollama Delete a model\n        call: ollama.deletemodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/ps\n      name: listrunningmodels\n      operations:\n      - method: GET\n        name: listrunningmodels\n        description: Ollama List running models\n        call: ollama.listrunningmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/blobs/{digest}\n      name: createblob\n      operations:\n      - method: POST\n        name: createblob\n        description: Ollama Create a blob\n        call: ollama.createblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/version\n      name: getversion\n      operations:\n      - method: GET\n        name: getversion\n \
  \       description: Get Ollama version\n        call: ollama.getversion\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ollama-mcp\n    transport: http\n    description: MCP adapter for Ollama API for AI agent use.\n    tools:\n    - name: generatecompletion\n      description: Ollama Generate a completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.generatecompletion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatechatcompletion\n      description: Ollama Generate a chat completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.generatechatcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateembeddings\n      description: Ollama Generate embeddings\n      hints:\n        readOnly: false\n  \
  \      destructive: false\n        idempotent: false\n      call: ollama.generateembeddings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodels\n      description: Ollama List local models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ollama.listmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: showmodelinfo\n      description: Ollama Show model information\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.showmodelinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmodel\n      description: Ollama Create a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.createmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copymodel\n      description: Ollama\
  \ Copy a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.copymodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullmodel\n      description: Ollama Pull a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.pullmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pushmodel\n      description: Ollama Push a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.pushmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: Ollama Delete a model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ollama.deletemodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrunningmodels\n\
  \      description: Ollama List running models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ollama.listrunningmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createblob\n      description: Ollama Create a blob\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ollama.createblob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getversion\n      description: Get Ollama version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ollama.getversion\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ollama/refs/heads/main/capabilities/ollama-capability.yaml
tags:
- Ollama
- API
tools:
- description: Ollama Generate a completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatecompletion
- description: Ollama Generate a chat completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatechatcompletion
- description: Ollama Generate embeddings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateembeddings
- description: Ollama List local models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Ollama Show model information
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: showmodelinfo
- description: Ollama Create a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmodel
- description: Ollama Copy a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copymodel
- description: Ollama Pull a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pullmodel
- description: Ollama Push a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushmodel
- description: Ollama Delete a model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Ollama List running models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrunningmodels
- description: Ollama Create a blob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createblob
- description: Get Ollama version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversion
---
