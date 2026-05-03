---
categories: []
consumed_apis: []
description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.
layout: capability
name: Apigee 42Crunch Publish Gate Capability
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
- example op
- a capability that wires the apigee + 42 crunch publish pipeline into the naftiko capability publish flow, so capability yamls cannot reach production without passing both gates and emit a per-publish audit record back to api governance layer.
- governance
slug: apigee-42crunch-publish-gate-capability
source_filename: apigee-42crunch-publish-gate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apigee 42crunch Publish Gate Capability\n  description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apigee-42crunch-publish-gate-capability-rest\n    description: REST API\
  \ for Apigee 42crunch Publish Gate Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apigee-42crunch-publish-gate-capability-mcp\n    description: MCP server exposing Apigee 42crunch Publish Gate Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: apigee-42crunch-publish-gate-capability-skills\n    description: Agent Skill bundle for Apigee 42crunch Publish Gate Capability.\n    skills:\n    - name:\
  \ apigee-42crunch-publish-gate-capability\n      description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.\n      location: file:///opt/naftiko/skills/apigee-42crunch-publish-gate-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.\n        from:\n          sourceNamespace: apigee-42crunch-publish-gate-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apigee-42crunch-publish-gate-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.
  hints:
    readOnly: true
  name: example
---
