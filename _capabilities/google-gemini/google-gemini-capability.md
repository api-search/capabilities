---
categories: []
consumed_apis: []
description: Google's Gemini API provides access to generative AI models for text generation, multimodal understanding, and embedding creation. The API supports text, image, audio, and video inputs with configurable safety settings, generation parameters, and tool use capabilities.
layout: capability
name: Google Gemini API
operations:
- description: Google Gemini Generates a model response given an input GenerateContentRequest. Refer to the text generation guide for detailed usage information. Input capabilities differ between models, including tuned models.
  method: POST
  name: generatecontent
  path: /models/{model}:generateContent
- description: Google Gemini Generates a streamed response from the model given an input GenerateContentRequest. Returns a stream of GenerateContentResponse chunks using server-sent events.
  method: POST
  name: streamgeneratecontent
  path: /models/{model}:streamGenerateContent
- description: Google Gemini Generates a text embedding vector from the input Content using the specified Gemini Embedding model.
  method: POST
  name: embedcontent
  path: /models/{model}:embedContent
personas: []
provider_name: Google Gemini
provider_slug: google-gemini
search_terms:
- google gemini generates a text embedding vector from the input content using the specified gemini embedding model.
- agentic ai
- google gemini generates a streamed response from the model given an input generatecontentrequest. returns a stream of generatecontentresponse chunks using server-sent events.
- embeddings
- machine learning
- multimodal
- artificial intelligence
- code generation
- google
- generative ai
- google gemini generates a model response given an input generatecontentrequest. refer to the text generation guide for detailed usage information. input capabilities differ between models, including tuned models.
- embedcontent
- gemini
- generatecontent
- api
- streamgeneratecontent
- llm
- image generation
slug: google-gemini-capability
source_filename: google-gemini-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Gemini API\n  description: Google's Gemini API provides access to generative AI models for text generation, multimodal understanding,\n    and embedding creation. The API supports text, image, audio, and video inputs with configurable safety settings, generation\n    parameters, and tool use capabilities.\n  tags:\n  - Google\n  - Gemini\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-gemini\n    baseUri: https://generativelanguage.googleapis.com/v1beta\n    description: Google Gemini API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_GEMINI_TOKEN}}'\n    resources:\n    - name: models-model-generatecontent\n      path: /models/{model}:generateContent\n      operations:\n      - name: generatecontent\n        method: POST\n        description: Google Gemini Generates a model response given an\
  \ input GenerateContentRequest. Refer to the text generation\n          guide for detailed usage information. Input capabilities differ between models, including tuned models.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: 'The name of the Model to use for generating the completion. Format: models/{model}. Example: models/gemini-2.0-flash.'\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-model-streamgeneratecontent\n      path: /models/{model}:streamGenerateContent\n      operations:\n      - name: streamgeneratecontent\n        method: POST\n        description: Google Gemini Generates a streamed response from the model given an input GenerateContentRequest.\
  \ Returns\n          a stream of GenerateContentResponse chunks using server-sent events.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: 'The name of the Model to use for generating the completion. Format: models/{model}. Example: models/gemini-2.0-flash.'\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        - name: alt\n          in: query\n          type: string\n          description: Set to 'sse' for server-sent events streaming.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-model-embedcontent\n      path: /models/{model}:embedContent\n      operations:\n      - name: embedcontent\n        method: POST\n        description: Google Gemini Generates a text embedding vector from the input Content\
  \ using the specified Gemini Embedding\n          model.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: 'The model name to use for embedding. Format: models/{model}. Example: models/gemini-embedding-001.'\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-gemini-rest\n    description: REST adapter for Google Gemini API.\n    resources:\n    - path: /models/{model}:generateContent\n      name: generatecontent\n      operations:\n      - method: POST\n        name: generatecontent\n        description: Google Gemini Generates a model response given an input GenerateContentRequest. Refer to the text generation\n\
  \          guide for detailed usage information. Input capabilities differ between models, including tuned models.\n        call: google-gemini.generatecontent\n        with:\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{model}:streamGenerateContent\n      name: streamgeneratecontent\n      operations:\n      - method: POST\n        name: streamgeneratecontent\n        description: Google Gemini Generates a streamed response from the model given an input GenerateContentRequest. Returns\n          a stream of GenerateContentResponse chunks using server-sent events.\n        call: google-gemini.streamgeneratecontent\n        with:\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{model}:embedContent\n      name: embedcontent\n      operations:\n      - method: POST\n        name: embedcontent\n        description: Google Gemini Generates\
  \ a text embedding vector from the input Content using the specified Gemini Embedding\n          model.\n        call: google-gemini.embedcontent\n        with:\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-gemini-mcp\n    transport: http\n    description: MCP adapter for Google Gemini API for AI agent use.\n    tools:\n    - name: generatecontent\n      description: Google Gemini Generates a model response given an input GenerateContentRequest. Refer to the text generation\n        guide for detailed usage information. Input capabilities differ between models, including tuned models.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gemini.generatecontent\n      with:\n        model: tools.model\n        key: tools.key\n      inputParameters:\n      - name: model\n        type: string\n        description: 'The name\
  \ of the Model to use for generating the completion. Format: models/{model}. Example: models/gemini-2.0-flash.'\n        required: true\n      - name: key\n        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamgeneratecontent\n      description: Google Gemini Generates a streamed response from the model given an input GenerateContentRequest. Returns\n        a stream of GenerateContentResponse chunks using server-sent events.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gemini.streamgeneratecontent\n      with:\n        model: tools.model\n        key: tools.key\n        alt: tools.alt\n      inputParameters:\n      - name: model\n        type: string\n        description: 'The name of the Model to use for generating the completion. Format: models/{model}. Example: models/gemini-2.0-flash.'\n\
  \        required: true\n      - name: key\n        type: string\n        description: API key for authentication.\n        required: true\n      - name: alt\n        type: string\n        description: Set to 'sse' for server-sent events streaming.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: embedcontent\n      description: Google Gemini Generates a text embedding vector from the input Content using the specified Gemini Embedding\n        model.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gemini.embedcontent\n      with:\n        model: tools.model\n        key: tools.key\n      inputParameters:\n      - name: model\n        type: string\n        description: 'The model name to use for embedding. Format: models/{model}. Example: models/gemini-embedding-001.'\n        required: true\n      - name: key\n        type: string\n        description: API key for authentication.\n       \
  \ required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_GEMINI_TOKEN: GOOGLE_GEMINI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-gemini/refs/heads/main/capabilities/google-gemini-capability.yaml
tags:
- Google
- Gemini
- API
tools:
- description: Google Gemini Generates a model response given an input GenerateContentRequest. Refer to the text generation guide for detailed usage information. Input capabilities differ between models, including tuned models.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatecontent
- description: Google Gemini Generates a streamed response from the model given an input GenerateContentRequest. Returns a stream of GenerateContentResponse chunks using server-sent events.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: streamgeneratecontent
- description: Google Gemini Generates a text embedding vector from the input Content using the specified Gemini Embedding model.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: embedcontent
---
