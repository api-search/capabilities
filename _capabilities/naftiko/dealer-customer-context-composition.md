---
categories: []
consumed_apis: []
description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
layout: capability
name: Dealer Customer Context Composition
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- naftiko
- a composed capability (capability-consuming-capability) that fans out to dealer + customer apis and returns one shaped context object for the assistant.
- governance
- mcp
- capabilities
- ai
slug: dealer-customer-context-composition
source_filename: dealer-customer-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Dealer Customer Context Composition\n  description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: dealer-customer-context-composition-rest\n    description: REST API for Dealer Customer Context Composition.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: dealer-customer-context-composition-mcp\n    description: MCP server exposing Dealer Customer Context Composition for AI agents.\n    tools:\n    - name: example\n      description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: dealer-customer-context-composition-skills\n    description: Agent Skill bundle for Dealer Customer Context Composition.\n    skills:\n    - name: dealer-customer-context-composition\n      description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.\n\
  \      location: file:///opt/naftiko/skills/dealer-customer-context-composition\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.\n        from:\n          sourceNamespace: dealer-customer-context-composition-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/dealer-customer-context-composition.yaml
tags:
- Naftiko
tools:
- description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
  hints:
    readOnly: true
  name: example
---
