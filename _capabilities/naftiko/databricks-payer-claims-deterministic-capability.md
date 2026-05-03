---
categories: []
consumed_apis: []
description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
layout: capability
name: Databricks Payer Claims Deterministic Capability
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
- a capability over azure databricks-hosted claims data, exposing read-only deterministic mcp tools with hipaa-shaped governance + pii detection.
- ai
- mcp
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: databricks-payer-claims-deterministic-capability
source_filename: databricks-payer-claims-deterministic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Databricks Payer Claims Deterministic Capability\n  description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: databricks-payer-claims-deterministic-capability-rest\n    description: REST API for Databricks Payer Claims Deterministic Capability.\n    resources:\n    - name:\
  \ example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: databricks-payer-claims-deterministic-capability-mcp\n    description: MCP server exposing Databricks Payer Claims Deterministic Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: databricks-payer-claims-deterministic-capability-skills\n    description: Agent Skill bundle for Databricks Payer Claims Deterministic Capability.\n    skills:\n    - name: databricks-payer-claims-deterministic-capability\n      description: A capability over Azure Databricks-hosted claims data, exposing\
  \ read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.\n      location: file:///opt/naftiko/skills/databricks-payer-claims-deterministic-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.\n        from:\n          sourceNamespace: databricks-payer-claims-deterministic-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/databricks-payer-claims-deterministic-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
  hints:
    readOnly: true
  name: example
---
