---
categories: []
consumed_apis: []
description: OpenAI's Chat Completions API for generating conversational responses using GPT models. Given a list of messages comprising a conversation, the model returns a response. Supports text generation, function calling, structured outputs, vision inputs, and streaming.
layout: capability
name: ChatGPT Chat Completions API
operations:
- description: Chatgpt Create Chat Completion
  method: POST
  name: createchatcompletion
  path: /chat/completions
personas: []
provider_name: ChatGPT
provider_slug: chatgpt
search_terms:
- agents
- openai
- embeddings
- language model
- chatgpt
- chatgpt create chat completion
- gpt-5
- fine-tuning
- ai
- api
- realtime
- gpt-4
- createchatcompletion
slug: chatgpt-capability
source_filename: chatgpt-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ChatGPT Chat Completions API\n  description: OpenAI's Chat Completions API for generating conversational responses using GPT models. Given a list of messages\n    comprising a conversation, the model returns a response. Supports text generation, function calling, structured outputs,\n    vision inputs, and streaming.\n  tags:\n  - Chatgpt\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chatgpt\n    baseUri: https://api.openai.com/v1\n    description: ChatGPT Chat Completions API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHATGPT_TOKEN}}'\n    resources:\n    - name: chat-completions\n      path: /chat/completions\n      operations:\n      - name: createchatcompletion\n        method: POST\n        description: Chatgpt Create Chat Completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chatgpt-rest\n    description: REST adapter for ChatGPT Chat Completions API.\n    resources:\n    - path: /chat/completions\n      name: createchatcompletion\n      operations:\n      - method: POST\n        name: createchatcompletion\n        description: Chatgpt Create Chat Completion\n        call: chatgpt.createchatcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chatgpt-mcp\n    transport: http\n    description: MCP adapter for ChatGPT Chat Completions API for AI agent use.\n    tools:\n    - name: createchatcompletion\n      description: Chatgpt Create Chat Completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chatgpt.createchatcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHATGPT_TOKEN:\
  \ CHATGPT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chatgpt/refs/heads/main/capabilities/chatgpt-capability.yaml
tags:
- Chatgpt
- API
tools:
- description: Chatgpt Create Chat Completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchatcompletion
---
