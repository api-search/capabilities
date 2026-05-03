---
categories: []
consumed_apis: []
description: Composable capability collection that wraps a representative client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
layout: capability
name: Api As Digital Product Collection
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- composable capability collection that wraps a representative client api as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: api-as-digital-product-collection
source_filename: api-as-digital-product-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api As Digital Product Collection\n  description: Composable capability collection that wraps a representative client API as a \"digital product,\" with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-as-digital-product-collection-rest\n    description: REST API for Api As Digital Product Collection.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-as-digital-product-collection-mcp\n    description: MCP server exposing Api As Digital Product Collection for AI agents.\n    tools:\n    - name: example\n      description: Composable capability collection that wraps a representative client API as a \"digital product,\" with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-as-digital-product-collection-skills\n    description: Agent Skill bundle for Api As Digital Product Collection.\n    skills:\n    - name: api-as-digital-product-collection\n      description: Composable capability collection that\
  \ wraps a representative client API as a \"digital product,\" with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.\n      location: file:///opt/naftiko/skills/api-as-digital-product-collection\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Composable capability collection that wraps a representative client API as a \"digital product,\" with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.\n        from:\n          sourceNamespace: api-as-digital-product-collection-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-as-digital-product-collection.yaml
tags:
- Naftiko
tools:
- description: Composable capability collection that wraps a representative client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
  hints:
    readOnly: true
  name: example
---
