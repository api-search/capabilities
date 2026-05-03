---
categories: []
consumed_apis: []
description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
layout: capability
name: Backstage Catalog Documentation Capability
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
- a "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via rest + mcp for backstage catalog enrichment.
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: backstage-catalog-documentation-capability
source_filename: backstage-catalog-documentation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Catalog Documentation Capability\n  description: A \"documentation capability\" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-catalog-documentation-capability-rest\n    description: REST API for Backstage Catalog Documentation Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-catalog-documentation-capability-mcp\n    description: MCP server exposing Backstage Catalog Documentation Capability for AI agents.\n    tools:\n    - name: example\n      description: A \"documentation capability\" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-catalog-documentation-capability-skills\n    description: Agent Skill bundle for Backstage Catalog Documentation Capability.\n    skills:\n    - name: backstage-catalog-documentation-capability\n      description: A \"documentation capability\" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog\
  \ enrichment.\n      location: file:///opt/naftiko/skills/backstage-catalog-documentation-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A \"documentation capability\" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.\n        from:\n          sourceNamespace: backstage-catalog-documentation-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-catalog-documentation-capability.yaml
tags:
- Naftiko
tools:
- description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
  hints:
    readOnly: true
  name: example
---
