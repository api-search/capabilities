---
categories: []
consumed_apis: []
description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
layout: capability
name: Bnp Simcorp Bloomberg Portfolio Deterministic Bridge
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
- a composed capability over simcorp dimension + bloomberg aim that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
- ai
- mcp
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: bnp-simcorp-bloomberg-portfolio-deterministic-bridge
source_filename: bnp-simcorp-bloomberg-portfolio-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Simcorp Bloomberg Portfolio Deterministic Bridge\n  description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-rest\n    description: REST API for Bnp Simcorp Bloomberg Portfolio Deterministic Bridge.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp\n    description: MCP server exposing Bnp Simcorp Bloomberg Portfolio Deterministic Bridge for AI agents.\n    tools:\n    - name: example\n      description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-skills\n    description: Agent Skill bundle for Bnp Simcorp Bloomberg Portfolio Deterministic Bridge.\n    skills:\n    - name: bnp-simcorp-bloomberg-portfolio-deterministic-bridge\n      description: A\
  \ composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.\n      location: file:///opt/naftiko/skills/bnp-simcorp-bloomberg-portfolio-deterministic-bridge\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.\n        from:\n          sourceNamespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-simcorp-bloomberg-portfolio-deterministic-bridge.yaml
tags:
- Naftiko
tools:
- description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
  hints:
    readOnly: true
  name: example
---
