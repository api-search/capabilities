---
categories: []
consumed_apis: []
description: Workflow capability for AI/LLM operations via TrueFoundry's AI Gateway. Combines chat completions, embeddings, image generation, content moderation, and document reranking into a unified AI operations workflow. Used by AI engineers, data scientists, and application developers building LLM-powered applications on TrueFoundry's enterprise platform.
layout: capability
name: TrueFoundry LLM Operations
operations:
- description: Generate chat completion from any supported model
  method: POST
  name: create-chat-completion
  path: /v1/chat/completions
- description: Generate vector embeddings
  method: POST
  name: create-embeddings
  path: /v1/embeddings
- description: Generate images from text prompts
  method: POST
  name: generate-images
  path: /v1/images/generations
- description: Check content for policy violations
  method: POST
  name: create-moderation
  path: /v1/moderations
- description: Rerank documents by query relevance
  method: POST
  name: rerank-documents
  path: /v1/rerank
- description: List all available models
  method: GET
  name: list-models
  path: /v1/models
- description: Create a batch job
  method: POST
  name: create-batch
  path: /v1/batches
- description: List uploaded files
  method: GET
  name: list-files
  path: /v1/files
personas: []
provider_name: TrueFoundry
provider_slug: truefoundry
search_terms:
- reranking
- check text content for policy violations
- content moderation
- text embedding generation
- ai gateway
- generate images from text prompts using ai image models
- generate a chat completion using any model available in truefoundry ai gateway (gpt-4o, claude, gemini, mistral, etc.). supports streaming, tool calling, and all openai-compatible parameters.
- llm
- chat completions
- generate vector embeddings
- generate chat completion from any supported model
- rerank documents
- create batch
- list all llm models available in truefoundry ai gateway
- ai image generation
- image generation
- generate vector embeddings for text. used for semantic search, rag pipelines, and similarity comparisons across 1000+ embedding models.
- ai platform
- truefoundry
- rerank a list of documents by their relevance to a query. used in rag pipelines to improve retrieval quality.
- moderate content
- rerank documents by query relevance
- document reranking
- kubernetes
- list all available models
- embeddings
- mlops
- check content for policy violations
- create moderation
- list models
- list files
- generate images
- create a batch job
- chat completion
- chat completion for llm conversations
- enterprise ai
- list uploaded files
- create embeddings
- available model catalog
- create chat completion
- file management
- batch request management
- create a batch job for async processing of multiple llm requests
- list files uploaded to truefoundry
- generate images from text prompts
- llm gateway
slug: llm-operations
source_filename: llm-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TrueFoundry LLM Operations\n  description: Workflow capability for AI/LLM operations via TrueFoundry's AI Gateway. Combines chat completions, embeddings,\n    image generation, content moderation, and document reranking into a unified AI operations workflow. Used by AI engineers,\n    data scientists, and application developers building LLM-powered applications on TrueFoundry's enterprise platform.\n  tags:\n  - TrueFoundry\n  - AI Gateway\n  - LLM\n  - Chat Completions\n  - Embeddings\n  - Image Generation\n  - Content Moderation\n  - Reranking\n  - MLOps\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUEFOUNDRY_API_KEY: TRUEFOUNDRY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tfy-gateway\n    baseUri: https://app.truefoundry.com/api/llm\n    description: TrueFoundry AI Gateway - OpenAI-compatible LLM proxy\n    authentication:\n      type: bearer\n      token: '{{TRUEFOUNDRY_API_KEY}}'\n\
  \    resources:\n    - name: chat\n      path: /chat/completions\n      description: Chat completions for LLM conversations\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Generate chat completion using any supported model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            temperature: '{{tools.temperature}}'\n            max_tokens: '{{tools.max_tokens}}'\n            stream: '{{tools.stream}}'\n    - name: embeddings\n      path: /embeddings\n      description: Text embedding generation\n      operations:\n      - name: create-embeddings\n        method: POST\n        description: Generate vector embeddings for text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n    - name: images-generations\n      path: /images/generations\n      description: AI image generation\n      operations:\n      - name: generate-images\n        method: POST\n        description: Generate images from text prompts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n            n: '{{tools.n}}'\n            size: '{{tools.size}}'\n    - name: moderations\n      path: /moderations\n      description: Content moderation\n      operations:\n      - name: create-moderation\n        method: POST\n        description: Check content for policy violations\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            model: '{{tools.model}}'\n    - name: models\n      path: /models\n      description: Available model listing\n      operations:\n      - name: list-models\n        method: GET\n        description: List all available models in the gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rerank\n      path: /rerank\n      description: Document reranking for search\n      operations:\n      - name: rerank-documents\n        method: POST\n        description: Rerank documents by relevance to a query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n           \
  \ query: '{{tools.query}}'\n            documents: '{{tools.documents}}'\n            top_n: '{{tools.top_n}}'\n    - name: files\n      path: /files\n      description: File management\n      operations:\n      - name: list-files\n        method: GET\n        description: List uploaded files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batches\n      path: /batches\n      description: Batch request processing\n      operations:\n      - name: create-batch\n        method: POST\n        description: Create a batch of API requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            input_file_id: '{{tools.input_file_id}}'\n            endpoint: '{{tools.endpoint}}'\n            completion_window: '{{tools.completion_window}}'\n  exposes:\n  - type: rest\n\
  \    port: 8080\n    namespace: truefoundry-llm-api\n    description: Unified REST API for LLM operations via TrueFoundry AI Gateway.\n    resources:\n    - path: /v1/chat/completions\n      name: chat-completions\n      description: Chat completion for LLM conversations\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Generate chat completion from any supported model\n        call: tfy-gateway.create-chat-completion\n        with:\n          model: rest.model\n          messages: rest.messages\n          temperature: rest.temperature\n          max_tokens: rest.max_tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Text embedding generation\n      operations:\n      - method: POST\n        name: create-embeddings\n        description: Generate vector embeddings\n        call: tfy-gateway.create-embeddings\n        with:\n          model:\
  \ rest.model\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/generations\n      name: image-generations\n      description: AI image generation\n      operations:\n      - method: POST\n        name: generate-images\n        description: Generate images from text prompts\n        call: tfy-gateway.generate-images\n        with:\n          model: rest.model\n          prompt: rest.prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/moderations\n      name: moderations\n      description: Content moderation\n      operations:\n      - method: POST\n        name: create-moderation\n        description: Check content for policy violations\n        call: tfy-gateway.create-moderation\n        with:\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rerank\n      name: rerank\n      description: Document\
  \ reranking\n      operations:\n      - method: POST\n        name: rerank-documents\n        description: Rerank documents by query relevance\n        call: tfy-gateway.rerank-documents\n        with:\n          model: rest.model\n          query: rest.query\n          documents: rest.documents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Available model catalog\n      operations:\n      - method: GET\n        name: list-models\n        description: List all available models\n        call: tfy-gateway.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batches\n      name: batches\n      description: Batch request management\n      operations:\n      - method: POST\n        name: create-batch\n        description: Create a batch job\n        call: tfy-gateway.create-batch\n        with:\n          input_file_id: rest.input_file_id\n          endpoint:\
  \ rest.endpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files\n      name: files\n      description: File management\n      operations:\n      - method: GET\n        name: list-files\n        description: List uploaded files\n        call: tfy-gateway.list-files\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: truefoundry-llm-mcp\n    transport: http\n    description: MCP server for AI-assisted LLM operations via TrueFoundry.\n    tools:\n    - name: chat-completion\n      description: Generate a chat completion using any model available in TrueFoundry AI Gateway (GPT-4o, Claude, Gemini,\n        Mistral, etc.). Supports streaming, tool calling, and all OpenAI-compatible parameters.\n      hints:\n        readOnly: false\n        openWorld: true\n      call: tfy-gateway.create-chat-completion\n      with:\n        model: tools.model\n        messages: tools.messages\n\
  \        temperature: tools.temperature\n        max_tokens: tools.max_tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-embeddings\n      description: Generate vector embeddings for text. Used for semantic search, RAG pipelines, and similarity comparisons\n        across 1000+ embedding models.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tfy-gateway.create-embeddings\n      with:\n        model: tools.model\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-images\n      description: Generate images from text prompts using AI image models\n      hints:\n        readOnly: false\n      call: tfy-gateway.generate-images\n      with:\n        model: tools.model\n        prompt: tools.prompt\n        n: tools.n\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moderate-content\n      description:\
  \ Check text content for policy violations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tfy-gateway.create-moderation\n      with:\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rerank-documents\n      description: Rerank a list of documents by their relevance to a query. Used in RAG pipelines to improve retrieval quality.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tfy-gateway.rerank-documents\n      with:\n        model: tools.model\n        query: tools.query\n        documents: tools.documents\n        top_n: tools.top_n\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List all LLM models available in TrueFoundry AI Gateway\n      hints:\n        readOnly: true\n      call: tfy-gateway.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-batch\n  \
  \    description: Create a batch job for async processing of multiple LLM requests\n      hints:\n        readOnly: false\n      call: tfy-gateway.create-batch\n      with:\n        input_file_id: tools.input_file_id\n        endpoint: tools.endpoint\n        completion_window: tools.completion_window\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-files\n      description: List files uploaded to TrueFoundry\n      hints:\n        readOnly: true\n      call: tfy-gateway.list-files\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/truefoundry/refs/heads/main/capabilities/llm-operations.yaml
tags:
- TrueFoundry
- AI Gateway
- LLM
- Chat Completions
- Embeddings
- Image Generation
- Content Moderation
- Reranking
- MLOps
tools:
- description: Generate a chat completion using any model available in TrueFoundry AI Gateway (GPT-4o, Claude, Gemini, Mistral, etc.). Supports streaming, tool calling, and all OpenAI-compatible parameters.
  hints:
    openWorld: true
    readOnly: false
  name: chat-completion
- description: Generate vector embeddings for text. Used for semantic search, RAG pipelines, and similarity comparisons across 1000+ embedding models.
  hints:
    idempotent: true
    readOnly: true
  name: create-embeddings
- description: Generate images from text prompts using AI image models
  hints:
    readOnly: false
  name: generate-images
- description: Check text content for policy violations
  hints:
    idempotent: true
    readOnly: true
  name: moderate-content
- description: Rerank a list of documents by their relevance to a query. Used in RAG pipelines to improve retrieval quality.
  hints:
    idempotent: true
    readOnly: true
  name: rerank-documents
- description: List all LLM models available in TrueFoundry AI Gateway
  hints:
    readOnly: true
  name: list-models
- description: Create a batch job for async processing of multiple LLM requests
  hints:
    readOnly: false
  name: create-batch
- description: List files uploaded to TrueFoundry
  hints:
    readOnly: true
  name: list-files
---
