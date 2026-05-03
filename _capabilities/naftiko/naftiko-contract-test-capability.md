---
categories: []
consumed_apis: []
description: A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.
layout: capability
name: Naftiko Contract Test Capability
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
- a capability where the same yaml drives a mock + the naftiko engine, so dev/test/prod share one artifact.
- naftiko
- governance
- mcp
- capabilities
- ai
slug: naftiko-contract-test-capability
source_filename: naftiko-contract-test-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Naftiko Contract Test Capability\n  description: A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: naftiko-contract-test-capability-rest\n    description: REST API for Naftiko Contract Test Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name:\
  \ example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: naftiko-contract-test-capability-mcp\n    description: MCP server exposing Naftiko Contract Test Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: naftiko-contract-test-capability-skills\n    description: Agent Skill bundle for Naftiko Contract Test Capability.\n    skills:\n    - name: naftiko-contract-test-capability\n      description: A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.\n      location: file:///opt/naftiko/skills/naftiko-contract-test-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description:\
  \ A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.\n        from:\n          sourceNamespace: naftiko-contract-test-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/naftiko-contract-test-capability.yaml
tags:
- Naftiko
tools:
- description: A capability where the same YAML drives a mock + the Naftiko engine, so dev/test/prod share one artifact.
  hints:
    readOnly: true
  name: example
---
