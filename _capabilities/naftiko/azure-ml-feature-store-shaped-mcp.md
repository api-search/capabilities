---
categories: []
consumed_apis: []
description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
layout: capability
name: Azure Ml Feature Store Shaped Mcp
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
- a capability over azure machine learning feature store endpoints that returns typed, shaped feature payloads for an ai/ml pipeline agent.
- capabilities
- example op
- governance
slug: azure-ml-feature-store-shaped-mcp
source_filename: azure-ml-feature-store-shaped-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Azure Ml Feature Store Shaped Mcp\n  description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: azure-ml-feature-store-shaped-mcp-rest\n    description: REST API for Azure Ml Feature Store Shaped Mcp.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: azure-ml-feature-store-shaped-mcp-mcp\n    description: MCP server exposing Azure Ml Feature Store Shaped Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: azure-ml-feature-store-shaped-mcp-skills\n    description: Agent Skill bundle for Azure Ml Feature Store Shaped Mcp.\n    skills:\n    - name: azure-ml-feature-store-shaped-mcp\n      description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.\n      location: file:///opt/naftiko/skills/azure-ml-feature-store-shaped-mcp\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.\n        from:\n          sourceNamespace: azure-ml-feature-store-shaped-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/azure-ml-feature-store-shaped-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
  hints:
    readOnly: true
  name: example
---
