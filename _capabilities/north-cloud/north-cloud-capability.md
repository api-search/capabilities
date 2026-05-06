---
categories: []
consumed_apis: []
description: The North.Cloud Public API enables programmatic access to push and retrieve cost unit data for FinOps and cloud cost optimization workflows across AWS and GCP. Cost units combine business units and cost identifiers to track metric values over time, supporting unit economics, allocation, and chargeback reporting.
layout: capability
name: North.Cloud Public API
operations:
- description: Retrieve cost unit
  method: GET
  name: getcostunit
  path: /public/cost-units
- description: Update cost unit data
  method: POST
  name: updatecostunit
  path: /public/cost-units
personas: []
provider_name: North.Cloud
provider_slug: north-cloud
search_terms:
- cloud cost management
- cost optimization
- getcostunit
- gcp
- cloud
- update cost unit data
- api
- updatecostunit
- cost units
- retrieve cost unit
- north
- finops
slug: north-cloud-capability
source_filename: north-cloud-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: North.Cloud Public API\n  description: The North.Cloud Public API enables programmatic access to push and retrieve cost unit data for FinOps and cloud\n    cost optimization workflows across AWS and GCP. Cost units combine business units and cost identifiers to track metric\n    values over time, supporting unit economics, allocation, and chargeback reporting.\n  tags:\n  - North\n  - Cloud\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: north-cloud\n    baseUri: https://api.north.cloud\n    description: North.Cloud Public API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{NORTH_CLOUD_TOKEN}}'\n    resources:\n    - name: public-cost-units\n      path: /public/cost-units\n      operations:\n      - name: getcostunit\n        method: GET\n        description: Retrieve cost unit\n        inputParameters:\n\
  \        - name: costUnitId\n          in: query\n          type: string\n          required: true\n          description: Identifier combining business unit and cost unit (for example `bu-123:cu-456`).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecostunit\n        method: POST\n        description: Update cost unit data\n        inputParameters:\n        - name: replace\n          in: query\n          type: boolean\n          description: When true, replaces the cost unit's data set instead of merging.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: north-cloud-rest\n    description: REST adapter for North.Cloud Public API.\n    resources:\n    - path: /public/cost-units\n      name: getcostunit\n      operations:\n      - method: GET\n        name:\
  \ getcostunit\n        description: Retrieve cost unit\n        call: north-cloud.getcostunit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/cost-units\n      name: updatecostunit\n      operations:\n      - method: POST\n        name: updatecostunit\n        description: Update cost unit data\n        call: north-cloud.updatecostunit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: north-cloud-mcp\n    transport: http\n    description: MCP adapter for North.Cloud Public API for AI agent use.\n    tools:\n    - name: getcostunit\n      description: Retrieve cost unit\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: north-cloud.getcostunit\n      with:\n        costUnitId: tools.costUnitId\n      inputParameters:\n      - name: costUnitId\n        type: string\n        description: Identifier combining business unit\
  \ and cost unit (for example `bu-123:cu-456`).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecostunit\n      description: Update cost unit data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: north-cloud.updatecostunit\n      with:\n        replace: tools.replace\n      inputParameters:\n      - name: replace\n        type: boolean\n        description: When true, replaces the cost unit's data set instead of merging.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NORTH_CLOUD_TOKEN: NORTH_CLOUD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/north-cloud/refs/heads/main/capabilities/north-cloud-capability.yaml
tags:
- North
- Cloud
- API
tools:
- description: Retrieve cost unit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcostunit
- description: Update cost unit data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecostunit
---
