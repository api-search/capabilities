---
categories: []
consumed_apis: []
description: A capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
layout: capability
name: Bloomberg Tradeweb Cross Source Deterministic Bridge
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
- a capability that joins a market-data shape with bloomberg + tradeweb sample inputs and returns a deterministic, schema-strict output for an ai risk reviewer.
- example op
- governance
slug: bloomberg-tradeweb-cross-source-deterministic-bridge
source_filename: bloomberg-tradeweb-cross-source-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bloomberg Tradeweb Cross Source Deterministic Bridge\n  description: A capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-rest\n    description: REST API for Bloomberg Tradeweb Cross Source Deterministic Bridge.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-mcp\n    description: MCP server exposing Bloomberg Tradeweb Cross Source Deterministic Bridge for AI agents.\n    tools:\n    - name: example\n      description: A capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-skills\n    description: Agent Skill bundle for Bloomberg Tradeweb Cross Source Deterministic Bridge.\n    skills:\n    - name: bloomberg-tradeweb-cross-source-deterministic-bridge\n      description: A\
  \ capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.\n      location: file:///opt/naftiko/skills/bloomberg-tradeweb-cross-source-deterministic-bridge\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.\n        from:\n          sourceNamespace: bloomberg-tradeweb-cross-source-deterministic-bridge-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bloomberg-tradeweb-cross-source-deterministic-bridge.yaml
tags:
- Naftiko
tools:
- description: A capability that joins a market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
  hints:
    readOnly: true
  name: example
---
