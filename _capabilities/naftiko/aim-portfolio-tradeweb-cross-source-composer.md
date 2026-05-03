---
categories: []
consumed_apis: []
description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
layout: capability
name: Aim Portfolio Tradeweb Cross Source Composer
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
- a composite capability that joins aim + valuation service (bval) + tradeweb into one shaped portfolio-context object.
- example op
- governance
slug: aim-portfolio-tradeweb-cross-source-composer
source_filename: aim-portfolio-tradeweb-cross-source-composer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aim Portfolio Tradeweb Cross Source Composer\n  description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aim-portfolio-tradeweb-cross-source-composer-rest\n    description: REST API for Aim Portfolio Tradeweb Cross Source Composer.\n    resources:\n    - name: example\n      path: /example\n   \
  \   operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aim-portfolio-tradeweb-cross-source-composer-mcp\n    description: MCP server exposing Aim Portfolio Tradeweb Cross Source Composer for AI agents.\n    tools:\n    - name: example\n      description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aim-portfolio-tradeweb-cross-source-composer-skills\n    description: Agent Skill bundle for Aim Portfolio Tradeweb Cross Source Composer.\n    skills:\n    - name: aim-portfolio-tradeweb-cross-source-composer\n      description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.\n      location: file:///opt/naftiko/skills/aim-portfolio-tradeweb-cross-source-composer\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.\n        from:\n          sourceNamespace: aim-portfolio-tradeweb-cross-source-composer-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aim-portfolio-tradeweb-cross-source-composer.yaml
tags:
- Naftiko
tools:
- description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
  hints:
    readOnly: true
  name: example
---
