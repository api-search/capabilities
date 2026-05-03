---
categories: []
consumed_apis: []
description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
layout: capability
name: Databricks Feature Store Mcp
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
- a capability over azure databricks feature store, exposing typed model-feature retrieval as mcp for the ai assistant flows john is architecting.
- example op
- governance
slug: databricks-feature-store-mcp
source_filename: databricks-feature-store-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Databricks Feature Store Mcp\n  description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: databricks-feature-store-mcp-rest\n    description: REST API for Databricks Feature Store Mcp.\n    resources:\n    - name: example\n      path: /example\n      operations:\n     \
  \ - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: databricks-feature-store-mcp-mcp\n    description: MCP server exposing Databricks Feature Store Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: databricks-feature-store-mcp-skills\n    description: Agent Skill bundle for Databricks Feature Store Mcp.\n    skills:\n    - name: databricks-feature-store-mcp\n      description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.\n      location: file:///opt/naftiko/skills/databricks-feature-store-mcp\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.\n        from:\n          sourceNamespace: databricks-feature-store-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/databricks-feature-store-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
  hints:
    readOnly: true
  name: example
---
