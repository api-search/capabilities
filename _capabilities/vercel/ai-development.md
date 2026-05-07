---
categories: []
consumed_apis: []
description: Unified workflow capability for AI-powered application development using Vercel's AI platform. Enables developers and AI agents to generate full-stack web applications via v0, query and compare AI models via the AI Gateway, and create text embeddings for semantic search and retrieval applications. Designed for developers building AI-native applications on the Vercel platform.
layout: capability
name: Vercel AI Development Platform
operations:
- description: List all AI models available across providers
  method: GET
  name: list-models
  path: /v1/models
- description: Create a chat completion using any model
  method: POST
  name: create-completion
  path: /v1/completions
- description: Create text embeddings
  method: POST
  name: create-embedding
  path: /v1/embeddings
- description: Generate a full-stack web app from a prompt
  method: POST
  name: generate-app
  path: /v1/apps
- description: Get generated app code and preview
  method: GET
  name: get-app
  path: /v1/apps/{chatId}
- description: Iterate on a generated app with follow-up instructions
  method: POST
  name: iterate-app
  path: /v1/apps/{chatId}
personas: []
provider_name: Vercel
provider_slug: vercel
search_terms:
- generate web app
- create completion
- iterate app
- ai models available via vercel ai gateway
- ai gateway
- llm
- ai
- vercel
- ai chat completions via unified gateway
- gateways
- get generated app code and preview
- create text embeddings for semantic search or retrieval using any embedding model
- get app
- generate a full-stack next.js web application from a natural language description using v0
- create embedding
- chat with model
- generate app
- list all ai models available across providers
- create a chat completion using any model
- generate a full-stack web app from a prompt
- developer tools
- observability
- text embeddings for semantic search
- ai gateways
- manage generated applications
- code generation
- list models
- list ai models
- get the code files and preview url for a v0 generated application
- create text embeddings
- ai-generated web applications via v0
- list all ai models available via the vercel ai gateway (anthropic, openai, google, meta, mistral, and more)
- iterate on a generated app with follow-up instructions
- iterate web app
- get generated app
- refine a v0 generated application with follow-up instructions (e.g., add dark mode, fix responsive layout, add authentication)
- send a chat completion request to any ai model via the vercel ai gateway
slug: ai-development
source_filename: ai-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vercel AI Development Platform\n  description: Unified workflow capability for AI-powered application development using Vercel's AI platform. Enables developers\n    and AI agents to generate full-stack web applications via v0, query and compare AI models via the AI Gateway, and create\n    text embeddings for semantic search and retrieval applications. Designed for developers building AI-native applications\n    on the Vercel platform.\n  tags:\n  - Vercel\n  - AI\n  - Code Generation\n  - LLM\n  - AI Gateway\n  - Developer Tools\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AI_GATEWAY_API_KEY: AI_GATEWAY_API_KEY\n    V0_API_KEY: V0_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vercel-ai-gateway\n    baseUri: https://ai-gateway.vercel.sh\n    description: Vercel AI Gateway — unified LLM API across providers\n    authentication:\n      type: bearer\n      token: '{{AI_GATEWAY_API_KEY}}'\n\
  \    resources:\n    - name: models\n      path: /v1/models\n      description: Available AI models\n      operations:\n      - name: list-models\n        method: GET\n        description: List all available AI models across all providers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat-completions\n      path: /v1/chat/completions\n      description: Chat completions across AI providers\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Create a chat completion using any model via the AI Gateway\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            stream: '{{tools.stream}}'\n\
  \            temperature: '{{tools.temperature}}'\n            max_tokens: '{{tools.max_tokens}}'\n    - name: embeddings\n      path: /v1/embeddings\n      description: Text embeddings\n      operations:\n      - name: create-embedding\n        method: POST\n        description: Create text embeddings using any embedding model\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n  - type: http\n    namespace: vercel-v0\n    baseUri: https://v0.dev/api\n    description: Vercel v0 AI-powered app generation API\n    authentication:\n      type: bearer\n      token: '{{V0_API_KEY}}'\n    resources:\n    - name: chat\n      path: /v1/chat\n      description: AI app generation chat sessions\n      operations:\n      - name: create-chat\n        method: POST\n \
  \       description: Generate a web app from a natural language prompt\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            system: '{{tools.system}}'\n    - name: chat-by-id\n      path: /v1/chat/{chatId}\n      description: Individual chat session management\n      operations:\n      - name: get-chat\n        method: GET\n        description: Get details for an existing v0 chat session\n        inputParameters:\n        - name: chatId\n          in: path\n          type: string\n          required: true\n          description: Chat session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: continue-chat\n        method: POST\n        description: Continue an existing chat session with\
  \ a follow-up message\n        inputParameters:\n        - name: chatId\n          in: path\n          type: string\n          required: true\n          description: Chat session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vercel-ai-dev-api\n    description: Unified REST API for AI-powered app development on Vercel.\n    resources:\n    - path: /v1/models\n      name: models\n      description: AI models available via Vercel AI Gateway\n      operations:\n      - method: GET\n        name: list-models\n        description: List all AI models available across providers\n        call: vercel-ai-gateway.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/completions\n      name: completions\n      description:\
  \ AI chat completions via unified gateway\n      operations:\n      - method: POST\n        name: create-completion\n        description: Create a chat completion using any model\n        call: vercel-ai-gateway.create-chat-completion\n        with:\n          model: rest.model\n          messages: rest.messages\n          temperature: rest.temperature\n          max_tokens: rest.max_tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Text embeddings for semantic search\n      operations:\n      - method: POST\n        name: create-embedding\n        description: Create text embeddings\n        call: vercel-ai-gateway.create-embedding\n        with:\n          model: rest.model\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps\n      name: apps\n      description: AI-generated web applications via v0\n      operations:\n\
  \      - method: POST\n        name: generate-app\n        description: Generate a full-stack web app from a prompt\n        call: vercel-v0.create-chat\n        with:\n          message: rest.message\n          system: rest.system\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps/{chatId}\n      name: app-by-id\n      description: Manage generated applications\n      operations:\n      - method: GET\n        name: get-app\n        description: Get generated app code and preview\n        call: vercel-v0.get-chat\n        with:\n          chatId: rest.chatId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: iterate-app\n        description: Iterate on a generated app with follow-up instructions\n        call: vercel-v0.continue-chat\n        with:\n          chatId: rest.chatId\n          message: rest.message\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: vercel-ai-dev-mcp\n    transport: http\n    description: MCP server for AI-assisted web development on the Vercel platform.\n    tools:\n    - name: list-ai-models\n      description: List all AI models available via the Vercel AI Gateway (Anthropic, OpenAI, Google, Meta, Mistral, and more)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vercel-ai-gateway.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chat-with-model\n      description: Send a chat completion request to any AI model via the Vercel AI Gateway\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vercel-ai-gateway.create-chat-completion\n      with:\n        model: tools.model\n        messages: tools.messages\n        temperature: tools.temperature\n        max_tokens: tools.max_tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-embedding\n\
  \      description: Create text embeddings for semantic search or retrieval using any embedding model\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vercel-ai-gateway.create-embedding\n      with:\n        model: tools.model\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-web-app\n      description: Generate a full-stack Next.js web application from a natural language description using v0\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vercel-v0.create-chat\n      with:\n        message: tools.message\n        system: tools.system\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-generated-app\n      description: Get the code files and preview URL for a v0 generated application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vercel-v0.get-chat\n      with:\n        chatId: tools.chatId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: iterate-web-app\n      description: Refine a v0 generated application with follow-up instructions (e.g., add dark mode, fix responsive layout,\n        add authentication)\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vercel-v0.continue-chat\n      with:\n        chatId: tools.chatId\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vercel/refs/heads/main/capabilities/ai-development.yaml
tags:
- Vercel
- AI
- Code Generation
- LLM
- AI Gateway
- Developer Tools
tools:
- description: List all AI models available via the Vercel AI Gateway (Anthropic, OpenAI, Google, Meta, Mistral, and more)
  hints:
    idempotent: true
    readOnly: true
  name: list-ai-models
- description: Send a chat completion request to any AI model via the Vercel AI Gateway
  hints:
    openWorld: true
    readOnly: true
  name: chat-with-model
- description: Create text embeddings for semantic search or retrieval using any embedding model
  hints:
    idempotent: true
    readOnly: true
  name: create-embedding
- description: Generate a full-stack Next.js web application from a natural language description using v0
  hints:
    idempotent: false
    readOnly: false
  name: generate-web-app
- description: Get the code files and preview URL for a v0 generated application
  hints:
    idempotent: true
    readOnly: true
  name: get-generated-app
- description: Refine a v0 generated application with follow-up instructions (e.g., add dark mode, fix responsive layout, add authentication)
  hints:
    idempotent: false
    readOnly: false
  name: iterate-web-app
---
