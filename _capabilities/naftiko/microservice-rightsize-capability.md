---
categories: []
consumed_apis: []
description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
layout: capability
name: Microservice Rightsize Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- 'implements guide-use-cases #6 (rightsize a set of microservices) as the apidays talking point.'
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: microservice-rightsize-capability
source_filename: microservice-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microservice Rightsize Capability\n  description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microservice-rightsize-capability-rest\n    description: REST API for Microservice Rightsize Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n\
  \        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microservice-rightsize-capability-mcp\n    description: MCP server exposing Microservice Rightsize Capability for AI agents.\n    tools:\n    - name: example\n      description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microservice-rightsize-capability-skills\n    description: Agent Skill bundle for Microservice Rightsize Capability.\n    skills:\n    - name: microservice-rightsize-capability\n      description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'\n      location: file:///opt/naftiko/skills/microservice-rightsize-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'Implements Guide-Use-Cases\
  \ #6 (Rightsize a set of microservices) as the apidays talking point.'\n        from:\n          sourceNamespace: microservice-rightsize-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microservice-rightsize-capability.yaml
tags:
- Naftiko
tools:
- description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
  hints:
    readOnly: true
  name: example
---
