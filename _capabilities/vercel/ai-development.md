---
api_specs:
- filename: vercel-ai-gateway-openapi.yml
  format: yaml
  label: vercel-ai-gateway
  slug: vercel-ai-gateway
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vercel/refs/heads/main/openapi/vercel-ai-gateway-openapi.yml
- filename: vercel-v0-platform-openapi.yml
  format: yaml
  label: vercel-v0
  slug: vercel-v0
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vercel/refs/heads/main/openapi/vercel-v0-platform-openapi.yml
categories: []
consumed_apis:
- vercel-ai-gateway
- vercel-v0
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
- llm
- gateways
- list models
- iterate on a generated app with follow-up instructions
- create text embeddings
- refine a v0 generated application with follow-up instructions (e.g., add dark mode, fix responsive layout, add authentication)
- iterate web app
- chat with model
- get generated app
- ai
- list ai models
- ai-generated web applications via v0
- ai gateways
- create text embeddings for semantic search or retrieval using any embedding model
- observability
- send a chat completion request to any ai model via the vercel ai gateway
- developer tools
- vercel
- generate a full-stack next.js web application from a natural language description using v0
- ai chat completions via unified gateway
- list all ai models available via the vercel ai gateway (anthropic, openai, google, meta, mistral, and more)
- ai models available via vercel ai gateway
- iterate app
- create a chat completion using any model
- create embedding
- ai gateway
- get the code files and preview url for a v0 generated application
- list all ai models available across providers
- text embeddings for semantic search
- generate web app
- get app
- generate a full-stack web app from a prompt
- manage generated applications
- code generation
- get generated app code and preview
- create completion
- generate app
slug: ai-development
source_filename: ai-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vercel AI Development Platform\"\n  description: >-\n    Unified workflow capability for AI-powered application development using Vercel's\n    AI platform. Enables developers and AI agents to generate full-stack web\n    applications via v0, query and compare AI models via the AI Gateway, and create\n    text embeddings for semantic search and retrieval applications. Designed for\n    developers building AI-native applications on the Vercel platform.\n  tags:\n    - Vercel\n    - AI\n    - Code Generation\n    - LLM\n    - AI Gateway\n    - Developer Tools\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      AI_GATEWAY_API_KEY: AI_GATEWAY_API_KEY\n      V0_API_KEY: V0_API_KEY\n\ncapability:\n  consumes:\n    - import: vercel-ai-gateway\n      location: ./shared/vercel-ai-gateway.yaml\n    - import: vercel-v0\n      location: ./shared/vercel-v0-platform.yaml\n\n  exposes:\n    -\
  \ type: rest\n      port: 8080\n      namespace: vercel-ai-dev-api\n      description: \"Unified REST API for AI-powered app development on Vercel.\"\n      resources:\n        - path: /v1/models\n          name: models\n          description: \"AI models available via Vercel AI Gateway\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all AI models available across providers\"\n              call: \"vercel-ai-gateway.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/completions\n          name: completions\n          description: \"AI chat completions via unified gateway\"\n          operations:\n            - method: POST\n              name: create-completion\n              description: \"Create a chat completion using any model\"\n              call: \"vercel-ai-gateway.create-chat-completion\"\n              with:\n          \
  \      model: \"rest.model\"\n                messages: \"rest.messages\"\n                temperature: \"rest.temperature\"\n                max_tokens: \"rest.max_tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Text embeddings for semantic search\"\n          operations:\n            - method: POST\n              name: create-embedding\n              description: \"Create text embeddings\"\n              call: \"vercel-ai-gateway.create-embedding\"\n              with:\n                model: \"rest.model\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apps\n          name: apps\n          description: \"AI-generated web applications via v0\"\n          operations:\n            - method: POST\n              name: generate-app\n\
  \              description: \"Generate a full-stack web app from a prompt\"\n              call: \"vercel-v0.create-chat\"\n              with:\n                message: \"rest.message\"\n                system: \"rest.system\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apps/{chatId}\n          name: app-by-id\n          description: \"Manage generated applications\"\n          operations:\n            - method: GET\n              name: get-app\n              description: \"Get generated app code and preview\"\n              call: \"vercel-v0.get-chat\"\n              with:\n                chatId: \"rest.chatId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: iterate-app\n              description: \"Iterate on a generated app with follow-up instructions\"\n              call: \"vercel-v0.continue-chat\"\n\
  \              with:\n                chatId: \"rest.chatId\"\n                message: \"rest.message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vercel-ai-dev-mcp\n      transport: http\n      description: \"MCP server for AI-assisted web development on the Vercel platform.\"\n      tools:\n        - name: list-ai-models\n          description: \"List all AI models available via the Vercel AI Gateway (Anthropic, OpenAI, Google, Meta, Mistral, and more)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vercel-ai-gateway.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: chat-with-model\n          description: \"Send a chat completion request to any AI model via the Vercel AI Gateway\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"vercel-ai-gateway.create-chat-completion\"\n          with:\n            model: \"tools.model\"\n            messages: \"tools.messages\"\n            temperature: \"tools.temperature\"\n            max_tokens: \"tools.max_tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-embedding\n          description: \"Create text embeddings for semantic search or retrieval using any embedding model\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vercel-ai-gateway.create-embedding\"\n          with:\n            model: \"tools.model\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-web-app\n          description: \"Generate a full-stack Next.js web application from a natural language description using v0\"\n          hints:\n            readOnly: false\n  \
  \          idempotent: false\n          call: \"vercel-v0.create-chat\"\n          with:\n            message: \"tools.message\"\n            system: \"tools.system\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-generated-app\n          description: \"Get the code files and preview URL for a v0 generated application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vercel-v0.get-chat\"\n          with:\n            chatId: \"tools.chatId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: iterate-web-app\n          description: \"Refine a v0 generated application with follow-up instructions (e.g., add dark mode, fix responsive layout, add authentication)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vercel-v0.continue-chat\"\n          with:\n            chatId: \"tools.chatId\"\
  \n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
