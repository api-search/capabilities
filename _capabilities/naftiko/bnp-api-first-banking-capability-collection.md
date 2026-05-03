---
categories: []
consumed_apis: []
description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
layout: capability
name: Bnp Api First Banking Capability Collection
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
- a bnp-paribas-flavored api-first capability collection wrapping representative banking apis, exposed rest + mcp, governance-tagged for banking compliance.
- example op
- governance
slug: bnp-api-first-banking-capability-collection
source_filename: bnp-api-first-banking-capability-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Api First Banking Capability Collection\n  description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-api-first-banking-capability-collection-rest\n    description: REST API for Bnp Api First Banking Capability Collection.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-api-first-banking-capability-collection-mcp\n    description: MCP server exposing Bnp Api First Banking Capability Collection for AI agents.\n    tools:\n    - name: example\n      description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-api-first-banking-capability-collection-skills\n    description: Agent Skill bundle for Bnp Api First Banking Capability Collection.\n    skills:\n    - name: bnp-api-first-banking-capability-collection\n      description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs,\
  \ exposed REST + MCP, governance-tagged for banking compliance.\n      location: file:///opt/naftiko/skills/bnp-api-first-banking-capability-collection\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.\n        from:\n          sourceNamespace: bnp-api-first-banking-capability-collection-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-api-first-banking-capability-collection.yaml
tags:
- Naftiko
tools:
- description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
  hints:
    readOnly: true
  name: example
---
