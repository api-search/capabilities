---
categories: []
consumed_apis: []
description: A FinOps capability over AWS + Azure + GCP cost APIs producing a cross-platform AI-spend rollup for FinOps agents.
layout: capability
name: Finops Ai Cross Platform Cost Capability
operations:
- description: ''
  method: GET
  name: get-ai-spend-rollup
  path: /ai-spend
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get aws cost
- spec-driven integration
- get ai spend rollup
- get azure cost
- finops
- mcp
- multi-cloud
- capabilities
- get gcp billing
- naftiko
- api integration
- governance
- ai
slug: finops-ai-cross-platform-cost-capability
source_filename: finops-ai-cross-platform-cost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Finops Ai Cross Platform Cost Capability\n  description: A FinOps capability over AWS + Azure + GCP cost APIs producing a cross-platform AI-spend rollup for FinOps agents.\n  tags: [Naftiko, FinOps, Multi-Cloud]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: aws-env\n  keys: {AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY, AWS_REGION: AWS_REGION}\n- namespace: azure-env\n  keys: {AZURE_TOKEN: AZURE_TOKEN, AZURE_SUBSCRIPTION: AZURE_SUBSCRIPTION}\n- namespace: gcp-env\n  keys: {GCP_TOKEN: GCP_TOKEN, GCP_PROJECT: GCP_PROJECT}\ncapability:\n  consumes:\n  - namespace: aws-cost\n    type: http\n    baseUri: https://ce.{{AWS_REGION}}.amazonaws.com\n    authentication: {type: aws-sig-v4, accessKeyId: '{{AWS_ACCESS_KEY_ID}}', secretKey: '{{AWS_SECRET_ACCESS_KEY}}', region: '{{AWS_REGION}}', service: ce}\n    resources:\n    - {name: cost-and-usage, path: /, operations: [{name: get-cost-and-usage,\
  \ method: POST, description: AWS Cost Explorer GetCostAndUsage.}]}\n  - namespace: azure-cost\n    type: http\n    baseUri: https://management.azure.com\n    authentication: {type: bearer, token: '{{AZURE_TOKEN}}'}\n    resources:\n    - name: cost-management\n      path: '/subscriptions/{{AZURE_SUBSCRIPTION}}/providers/Microsoft.CostManagement/query'\n      operations: [{name: query-azure-costs, method: POST}]\n  - namespace: gcp-billing\n    type: http\n    baseUri: https://cloudbilling.googleapis.com\n    authentication: {type: bearer, token: '{{GCP_TOKEN}}'}\n    resources:\n    - {name: projects, path: '/v1/projects/{{GCP_PROJECT}}/billingInfo', operations: [{name: get-billing-info, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: finops-ai-cross-platform-cost-capability-rest\n    description: REST surface for cross-platform AI-spend rollup.\n    resources:\n    - {name: ai-spend, path: /ai-spend, operations: [{method: GET, name: get-ai-spend-rollup,\
  \ call: aws-cost.get-cost-and-usage}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: finops-ai-cross-platform-cost-capability-mcp\n    description: MCP for FinOps AI-spend rollup.\n    tools:\n    - {name: get-aws-cost, hints: {readOnly: true}, call: aws-cost.get-cost-and-usage}\n    - {name: get-azure-cost, hints: {readOnly: true}, call: azure-cost.query-azure-costs}\n    - {name: get-gcp-billing, hints: {readOnly: true}, call: gcp-billing.get-billing-info}\n    - {name: get-ai-spend-rollup, hints: {readOnly: true}, call: aws-cost.get-cost-and-usage}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: finops-ai-cross-platform-cost-capability-skills\n    description: Skill for FinOps AI-spend.\n    skills:\n    - name: finops-ai-cross-platform-cost-capability\n      description: Cross-platform AI-spend FinOps.\n      location: file:///opt/naftiko/skills/finops-ai-cross-platform-cost-capability\n      allowed-tools: get-aws-cost,get-azure-cost,get-gcp-billing,get-ai-spend-rollup\n\
  \      tools:\n      - {name: get-aws-cost, from: {sourceNamespace: finops-ai-cross-platform-cost-capability-mcp, action: get-aws-cost}}\n      - {name: get-azure-cost, from: {sourceNamespace: finops-ai-cross-platform-cost-capability-mcp, action: get-azure-cost}}\n      - {name: get-gcp-billing, from: {sourceNamespace: finops-ai-cross-platform-cost-capability-mcp, action: get-gcp-billing}}\n      - {name: get-ai-spend-rollup, from: {sourceNamespace: finops-ai-cross-platform-cost-capability-mcp, action: get-ai-spend-rollup}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/finops-ai-cross-platform-cost-capability.yaml
tags:
- Naftiko
- FinOps
- Multi-Cloud
tools:
- description: ''
  hints:
    readOnly: true
  name: get-aws-cost
- description: ''
  hints:
    readOnly: true
  name: get-azure-cost
- description: ''
  hints:
    readOnly: true
  name: get-gcp-billing
- description: ''
  hints:
    readOnly: true
  name: get-ai-spend-rollup
---
