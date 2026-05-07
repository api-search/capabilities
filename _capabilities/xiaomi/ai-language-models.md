---
categories: []
consumed_apis: []
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
- list mimo models
- available mimo models.
- chat completions
- list all available xiaomi mimo ai models.
- mobile
- cloud storage
- generate a response from xiaomi mimo ai models (mimo-v2.5-pro, mimo-v2-flash, etc.).
- artificial intelligence
- chat completion generation.
- machine learning
- language models
- iot
- smart home
- list available xiaomi mimo ai models.
- consumer electronics
- list models
- chat completion
- create a chat completion using xiaomi mimo models.
- create chat completion
- xiaomi
slug: ai-language-models
source_filename: ai-language-models.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Xiaomi AI Language Models\n  description: Capability for integrating Xiaomi MiMo large language models into applications. Provides access to reasoning,\n    coding, multimodal, and text-to-speech AI capabilities via an OpenAI-compatible API.\n  tags:\n  - Xiaomi\n  - Artificial Intelligence\n  - Language Models\n  - Chat Completions\n  - Machine Learning\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    XIAOMI_MIMO_API_KEY: XIAOMI_MIMO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: xiaomi-mimo-api\n    baseUri: https://api.xiaomimimo.com\n    description: Xiaomi MiMo AI API for chat completions.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{XIAOMI_MIMO_API_KEY}}'\n      placement: header\n    resources:\n    - name: chat-completions\n      path: /v1/chat/completions\n      description: Chat completion generation.\n      operations:\n      - name:\
  \ create-chat-completion\n        method: POST\n        description: Creates a chat completion from the specified MiMo model.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            temperature: '{{tools.temperature}}'\n            max_tokens: '{{tools.max_tokens}}'\n            stream: '{{tools.stream}}'\n    - name: models\n      path: /v1/models\n      description: Available MiMo AI models.\n      operations:\n      - name: list-models\n        method: GET\n        description: Returns a list of available MiMo AI models.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: xiaomi-ai-api\n\
  \    description: Unified REST API for Xiaomi MiMo AI language model interactions.\n    resources:\n    - path: /v1/chat/completions\n      name: chat-completions\n      description: Chat completion generation.\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Create a chat completion using Xiaomi MiMo models.\n        call: xiaomi-mimo-api.create-chat-completion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Available MiMo models.\n      operations:\n      - method: GET\n        name: list-models\n        description: List available Xiaomi MiMo AI models.\n        call: xiaomi-mimo-api.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: xiaomi-ai-mcp\n    transport: http\n    description: MCP server for AI-assisted integration with Xiaomi MiMo language models.\n   \
  \ tools:\n    - name: chat-completion\n      description: Generate a response from Xiaomi MiMo AI models (mimo-v2.5-pro, mimo-v2-flash, etc.).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: xiaomi-mimo-api.create-chat-completion\n      with:\n        model: tools.model\n        messages: tools.messages\n        temperature: tools.temperature\n        max_tokens: tools.max_tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mimo-models\n      description: List all available Xiaomi MiMo AI models.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xiaomi-mimo-api.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
