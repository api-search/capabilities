---
categories: []
consumed_apis: []
description: Agent completions API for building AI agents that can handle complex tasks, maintain context, coordinate multiple actions, and use tools including function calling. Agents are created and configured via the Mistral platform and invoked through this API.
layout: capability
name: Mistral AI Agents API
operations:
- description: Mistral AI Create an agent completion
  method: POST
  name: createagentcompletion
  path: /agents/completions
personas: []
provider_name: Mistral AI
provider_slug: mistral
search_terms:
- mistral ai create an agent completion
- createagentcompletion
- mistral
- api
slug: mistral-capability
source_filename: mistral-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mistral AI Agents API\n  description: Agent completions API for building AI agents that can handle complex tasks, maintain context, coordinate multiple\n    actions, and use tools including function calling. Agents are created and configured via the Mistral platform and invoked\n    through this API.\n  tags:\n  - Mistral\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mistral\n    baseUri: https://api.mistral.ai/v1\n    description: Mistral AI Agents API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MISTRAL_TOKEN}}'\n    resources:\n    - name: agents-completions\n      path: /agents/completions\n      operations:\n      - name: createagentcompletion\n        method: POST\n        description: Mistral AI Create an agent completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mistral-rest\n    description: REST adapter for Mistral AI Agents API.\n    resources:\n    - path: /agents/completions\n      name: createagentcompletion\n      operations:\n      - method: POST\n        name: createagentcompletion\n        description: Mistral AI Create an agent completion\n        call: mistral.createagentcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mistral-mcp\n    transport: http\n    description: MCP adapter for Mistral AI Agents API for AI agent use.\n    tools:\n    - name: createagentcompletion\n      description: Mistral AI Create an agent completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mistral.createagentcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MISTRAL_TOKEN:\
  \ MISTRAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mistral/refs/heads/main/capabilities/mistral-capability.yaml
tags:
- Mistral
- API
tools:
- description: Mistral AI Create an agent completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagentcompletion
---
