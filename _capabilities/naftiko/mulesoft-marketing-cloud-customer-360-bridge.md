---
categories: []
consumed_apis: []
description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.
layout: capability
name: Mulesoft Marketing Cloud Customer 360 Bridge
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
- capabilities
- a composed customer-360 capability over + mulesoft + marketing cloud that returns one shaped agent context object.
- example op
- governance
slug: mulesoft-marketing-cloud-customer-360-bridge
source_filename: mulesoft-marketing-cloud-customer-360-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mulesoft Marketing Cloud Customer 360 Bridge\n  description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-rest\n    description: REST API for Mulesoft Marketing Cloud Customer 360 Bridge.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-mcp\n    description: MCP server exposing Mulesoft Marketing Cloud Customer 360 Bridge for AI agents.\n    tools:\n    - name: example\n      description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-skills\n    description: Agent Skill bundle for Mulesoft Marketing Cloud Customer 360 Bridge.\n    skills:\n    - name: mulesoft-marketing-cloud-customer-360-bridge\n      description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.\n      location: file:///opt/naftiko/skills/mulesoft-marketing-cloud-customer-360-bridge\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.\n        from:\n          sourceNamespace: mulesoft-marketing-cloud-customer-360-bridge-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mulesoft-marketing-cloud-customer-360-bridge.yaml
tags:
- Naftiko
tools:
- description: A composed Customer-360 capability over + MuleSoft + Marketing Cloud that returns one shaped agent context object.
  hints:
    readOnly: true
  name: example
---
