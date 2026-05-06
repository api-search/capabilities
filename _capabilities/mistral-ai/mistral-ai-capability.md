---
categories: []
consumed_apis: []
description: The Mistral AI Agents API provides a dedicated framework for building agentic applications. It complements the Chat Completion API by enabling AI agents to handle complex tasks, maintain context across interactions, and coordinate multiple actions. Developers can create agents with specific configurations, tools, and instructions, making it suitable for enterprise-grade agentic platforms and multi-step workflow automation.
layout: capability
name: Mistral AI Agents API
operations:
- description: Create agent completion
  method: POST
  name: createagentcompletion
  path: /agents/completions
personas: []
provider_name: Mistral AI
provider_slug: mistral-ai
search_terms:
- batch processing
- large language models
- agents
- fine-tuning
- mistral
- api
- ocr
- embeddings
- ai
- createagentcompletion
- create agent completion
- artificial intelligence
- chat
slug: mistral-ai-capability
source_filename: mistral-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mistral AI Agents API\n  description: The Mistral AI Agents API provides a dedicated framework for building agentic applications. It complements\n    the Chat Completion API by enabling AI agents to handle complex tasks, maintain context across interactions, and coordinate\n    multiple actions. Developers can create agents with specific configurations, tools, and instructions, making it suitable\n    for enterprise-grade agentic platforms and multi-step workflow automation.\n  tags:\n  - Mistral\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mistral-ai\n    baseUri: https://api.mistral.ai/v1\n    description: Mistral AI Agents API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MISTRAL_AI_TOKEN}}'\n    resources:\n    - name: agents-completions\n      path: /agents/completions\n      operations:\n      - name: createagentcompletion\n   \
  \     method: POST\n        description: Create agent completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mistral-ai-rest\n    description: REST adapter for Mistral AI Agents API.\n    resources:\n    - path: /agents/completions\n      name: createagentcompletion\n      operations:\n      - method: POST\n        name: createagentcompletion\n        description: Create agent completion\n        call: mistral-ai.createagentcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mistral-ai-mcp\n    transport: http\n    description: MCP adapter for Mistral AI Agents API for AI agent use.\n    tools:\n    - name: createagentcompletion\n      description: Create agent completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: mistral-ai.createagentcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MISTRAL_AI_TOKEN: MISTRAL_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mistral-ai/refs/heads/main/capabilities/mistral-ai-capability.yaml
tags:
- Mistral
- Ai
- API
tools:
- description: Create agent completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagentcompletion
---
