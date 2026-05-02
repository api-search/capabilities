---
categories: []
consumed_apis: []
description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating the deterministic flow end-to-end.
layout: capability
name: Deterministic Sdk Pipeline Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
- a capability where the spec is the source of truth for both the engine runtime and the downstream sdk pipeline, demonstrating the deterministic flow end-to-end.
slug: deterministic-sdk-pipeline-capability
source_filename: deterministic-sdk-pipeline-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Sdk Pipeline Capability\n  description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating the deterministic flow end-to-end.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-sdk-pipeline-capability-rest\n    description: REST API for Deterministic Sdk Pipeline Capability.\n    resources:\n    - name: example\n   \
  \   path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-sdk-pipeline-capability-mcp\n    description: MCP server exposing Deterministic Sdk Pipeline Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating the deterministic flow end-to-end.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-sdk-pipeline-capability-skills\n    description: Agent Skill bundle for Deterministic Sdk Pipeline Capability.\n    skills:\n    - name: deterministic-sdk-pipeline-capability\n      description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating\
  \ the deterministic flow end-to-end.\n      location: file:///opt/naftiko/skills/deterministic-sdk-pipeline-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating the deterministic flow end-to-end.\n        from:\n          sourceNamespace: deterministic-sdk-pipeline-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-sdk-pipeline-capability.yaml
tags:
- Naftiko
tools:
- description: A capability where the spec is the source of truth for both the engine runtime and the downstream SDK pipeline, demonstrating the deterministic flow end-to-end.
  hints:
    readOnly: true
  name: example
---
