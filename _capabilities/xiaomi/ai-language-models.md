---
api_specs:
- filename: xiaomi-mimo-api-openapi.yml
  format: yaml
  label: xiaomi-mimo-api
  slug: xiaomi-mimo-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/xiaomi/refs/heads/main/openapi/xiaomi-mimo-api-openapi.yml
categories: []
consumed_apis:
- xiaomi-mimo-api
description: Capability for integrating Xiaomi MiMo large language models into applications. Provides access to reasoning, coding, multimodal, and text-to-speech AI capabilities via an OpenAI-compatible API.
layout: capability
name: Xiaomi AI Language Models
operations:
- description: Create a chat completion using Xiaomi MiMo models.
  method: POST
  name: create-chat-completion
  path: /v1/chat/completions
- description: List available Xiaomi MiMo AI models.
  method: GET
  name: list-models
  path: /v1/models
personas: []
provider_name: Xiaomi
provider_slug: xiaomi
search_terms:
- list models
- mobile
- create a chat completion using xiaomi mimo models.
- cloud storage
- language models
- list available xiaomi mimo ai models.
- generate a response from xiaomi mimo ai models (mimo-v2.5-pro, mimo-v2-flash, etc.).
- artificial intelligence
- consumer electronics
- chat completion
- chat completions
- available mimo models.
- smart home
- machine learning
- xiaomi
- list all available xiaomi mimo ai models.
- create chat completion
- iot
- chat completion generation.
- list mimo models
slug: ai-language-models
source_filename: ai-language-models.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Xiaomi AI Language Models\"\n  description: \"Capability for integrating Xiaomi MiMo large language models into applications. Provides access to reasoning, coding, multimodal, and text-to-speech AI capabilities via an OpenAI-compatible API.\"\n  tags:\n    - Xiaomi\n    - Artificial Intelligence\n    - Language Models\n    - Chat Completions\n    - Machine Learning\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      XIAOMI_MIMO_API_KEY: XIAOMI_MIMO_API_KEY\n\ncapability:\n  consumes:\n    - import: xiaomi-mimo-api\n      location: ./shared/xiaomi-mimo-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: xiaomi-ai-api\n      description: \"Unified REST API for Xiaomi MiMo AI language model interactions.\"\n      resources:\n        - path: /v1/chat/completions\n          name: chat-completions\n          description: \"Chat completion generation.\"\n    \
  \      operations:\n            - method: POST\n              name: create-chat-completion\n              description: \"Create a chat completion using Xiaomi MiMo models.\"\n              call: \"xiaomi-mimo-api.create-chat-completion\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models\n          name: models\n          description: \"Available MiMo models.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List available Xiaomi MiMo AI models.\"\n              call: \"xiaomi-mimo-api.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: xiaomi-ai-mcp\n      transport: http\n      description: \"MCP server for AI-assisted integration with Xiaomi MiMo language models.\"\n      tools:\n        - name: chat-completion\n          description:\
  \ \"Generate a response from Xiaomi MiMo AI models (mimo-v2.5-pro, mimo-v2-flash, etc.).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"xiaomi-mimo-api.create-chat-completion\"\n          with:\n            model: \"tools.model\"\n            messages: \"tools.messages\"\n            temperature: \"tools.temperature\"\n            max_tokens: \"tools.max_tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-mimo-models\n          description: \"List all available Xiaomi MiMo AI models.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"xiaomi-mimo-api.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/xiaomi/refs/heads/main/capabilities/ai-language-models.yaml
tags:
- Xiaomi
- Artificial Intelligence
- Language Models
- Chat Completions
- Machine Learning
tools:
- description: Generate a response from Xiaomi MiMo AI models (mimo-v2.5-pro, mimo-v2-flash, etc.).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chat-completion
- description: List all available Xiaomi MiMo AI models.
  hints:
    openWorld: false
    readOnly: true
  name: list-mimo-models
---
