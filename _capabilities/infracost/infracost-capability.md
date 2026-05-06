---
categories: []
consumed_apis: []
description: The Infracost Cloud Pricing API provides programmatic access to cloud cost estimation for Terraform plans. The Plan JSON API exposes breakdown and diff endpoints used by the Infracost CLI and CI/CD integrations to surface cost breakdowns and changes directly inside pull requests.
layout: capability
name: Infracost Cloud Pricing API
operations:
- description: Generate Cost Breakdown
  method: POST
  name: generatebreakdown
  path: /breakdown
- description: Generate Cost Diff
  method: POST
  name: generatediff
  path: /diff
personas: []
provider_name: Infracost
provider_slug: infracost
search_terms:
- infracost
- generatebreakdown
- cloud cost
- api
- generatediff
- terraform
- infrastructure
- finops
- generate cost breakdown
- generate cost diff
slug: infracost-capability
source_filename: infracost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Infracost Cloud Pricing API\n  description: The Infracost Cloud Pricing API provides programmatic access to cloud cost estimation for Terraform plans.\n    The Plan JSON API exposes breakdown and diff endpoints used by the Infracost CLI and CI/CD integrations to surface cost\n    breakdowns and changes directly inside pull requests.\n  tags:\n  - Infracost\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: infracost\n    baseUri: https://pricing.api.infracost.io\n    description: Infracost Cloud Pricing API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{INFRACOST_TOKEN}}'\n    resources:\n    - name: breakdown\n      path: /breakdown\n      operations:\n      - name: generatebreakdown\n        method: POST\n        description: Generate Cost Breakdown\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: diff\n      path: /diff\n      operations:\n      - name: generatediff\n        method: POST\n        description: Generate Cost Diff\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infracost-rest\n    description: REST adapter for Infracost Cloud Pricing API.\n    resources:\n    - path: /breakdown\n      name: generatebreakdown\n      operations:\n      - method: POST\n        name: generatebreakdown\n        description: Generate Cost Breakdown\n        call: infracost.generatebreakdown\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /diff\n      name: generatediff\n      operations:\n      - method: POST\n        name: generatediff\n        description: Generate Cost Diff\n        call: infracost.generatediff\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: infracost-mcp\n    transport: http\n    description: MCP adapter for Infracost Cloud Pricing API for AI agent use.\n    tools:\n    - name: generatebreakdown\n      description: Generate Cost Breakdown\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infracost.generatebreakdown\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatediff\n      description: Generate Cost Diff\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infracost.generatediff\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INFRACOST_TOKEN: INFRACOST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/infracost/refs/heads/main/capabilities/infracost-capability.yaml
tags:
- Infracost
- API
tools:
- description: Generate Cost Breakdown
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatebreakdown
- description: Generate Cost Diff
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatediff
---
