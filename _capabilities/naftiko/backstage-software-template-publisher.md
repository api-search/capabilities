---
categories: []
consumed_apis: []
description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
layout: capability
name: Backstage Software Template Publisher
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
- api integration
- spec-driven integration
- publishes the naftiko spec-driven integration backstage template into a backstage catalog daniel can demo at apidays munich.
- capabilities
- example op
- governance
slug: backstage-software-template-publisher
source_filename: backstage-software-template-publisher.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Software Template Publisher\n  description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-software-template-publisher-rest\n    description: REST API for Backstage Software Template Publisher.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-software-template-publisher-mcp\n    description: MCP server exposing Backstage Software Template Publisher for AI agents.\n    tools:\n    - name: example\n      description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-software-template-publisher-skills\n    description: Agent Skill bundle for Backstage Software Template Publisher.\n    skills:\n    - name: backstage-software-template-publisher\n      description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.\n      location: file:///opt/naftiko/skills/backstage-software-template-publisher\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.\n        from:\n          sourceNamespace: backstage-software-template-publisher-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-software-template-publisher.yaml
tags:
- Naftiko
tools:
- description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
  hints:
    readOnly: true
  name: example
---
