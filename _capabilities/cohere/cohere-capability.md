---
categories: []
consumed_apis: []
description: The Cohere Chat API enables developers to integrate large language model text generation capabilities into their applications through a conversational interface. It supports multi-turn conversations, tool use with JSON schema definitions, retrieval-augmented generation, and streaming responses. The API is available via the v2 endpoint and works with Cohere's Command family of models.
layout: capability
name: Cohere Chat API
operations:
- description: Chat with a Cohere model
  method: POST
  name: chat
  path: /v2/chat
- description: Chat with streaming response
  method: POST
  name: chatstream
  path: /v2/chat/stream
personas: []
provider_name: cohere
provider_slug: cohere
search_terms:
- chat with a cohere model
- chat with streaming response
- cohere
- api
- chatstream
- chat
slug: cohere-capability
source_filename: cohere-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cohere Chat API\n  description: The Cohere Chat API enables developers to integrate large language model text generation capabilities into\n    their applications through a conversational interface. It supports multi-turn conversations, tool use with JSON schema\n    definitions, retrieval-augmented generation, and streaming responses. The API is available via the v2 endpoint and works\n    with Cohere's Command family of models.\n  tags:\n  - Cohere\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cohere\n    baseUri: https://api.cohere.com\n    description: Cohere Chat API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{COHERE_TOKEN}}'\n    resources:\n    - name: v2-chat\n      path: /v2/chat\n      operations:\n      - name: chat\n        method: POST\n        description: Chat with a Cohere model\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-chat-stream\n      path: /v2/chat/stream\n      operations:\n      - name: chatstream\n        method: POST\n        description: Chat with streaming response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cohere-rest\n    description: REST adapter for Cohere Chat API.\n    resources:\n    - path: /v2/chat\n      name: chat\n      operations:\n      - method: POST\n        name: chat\n        description: Chat with a Cohere model\n        call: cohere.chat\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/chat/stream\n      name: chatstream\n      operations:\n      - method: POST\n        name: chatstream\n        description: Chat with streaming response\n        call: cohere.chatstream\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cohere-mcp\n    transport: http\n    description: MCP adapter for Cohere Chat API for AI agent use.\n    tools:\n    - name: chat\n      description: Chat with a Cohere model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cohere.chat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chatstream\n      description: Chat with streaming response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cohere.chatstream\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    COHERE_TOKEN: COHERE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cohere/refs/heads/main/capabilities/cohere-capability.yaml
tags:
- Cohere
- API
tools:
- description: Chat with a Cohere model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chat
- description: Chat with streaming response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chatstream
---
