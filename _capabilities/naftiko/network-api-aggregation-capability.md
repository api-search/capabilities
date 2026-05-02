---
categories: []
consumed_apis: []
description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
layout: capability
name: Network Api Aggregation Capability
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
- a capability over network apis (ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as mcp.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: network-api-aggregation-capability
source_filename: network-api-aggregation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Network Api Aggregation Capability\n  description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: network-api-aggregation-capability-rest\n    description: REST API for Network Api Aggregation Capability.\n    resources:\n    - name: example\n  \
  \    path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: network-api-aggregation-capability-mcp\n    description: MCP server exposing Network Api Aggregation Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: network-api-aggregation-capability-skills\n    description: Agent Skill bundle for Network Api Aggregation Capability.\n    skills:\n    - name: network-api-aggregation-capability\n      description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status)\
  \ exposing carrier-grade governed reads as MCP.\n      location: file:///opt/naftiko/skills/network-api-aggregation-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.\n        from:\n          sourceNamespace: network-api-aggregation-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/network-api-aggregation-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
  hints:
    readOnly: true
  name: example
---
