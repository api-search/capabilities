---
categories:
- payments
consumed_apis:
- spot-eco
- spot-billing
- spot-admin
description: Unified workflow for cloud financial operations combining commitment management (Eco), billing analytics (Billing Engine), and cost optimization. Used by FinOps teams, cloud finance analysts, and platform administrators.
layout: capability
name: Spot FinOps
operations:
- description: List AWS commitment plans
  method: GET
  name: list-commitment-plans
  path: /v1/commitment-plans
- description: Get AWS savings analysis
  method: GET
  name: get-savings-analysis
  path: /v1/savings-analysis
- description: List billing accounts
  method: GET
  name: list-billing-accounts
  path: /v1/billing-accounts
- description: Get cost analysis
  method: GET
  name: get-cost-analysis
  path: /v1/cost-analysis
personas: []
provider_name: Spot
provider_slug: spot
search_terms:
- billing list account families
- cloud commitment plans
- kubernetes
- get aws savings analysis
- cost analysis
- get a specific aws commitment plan
- billing list accounts
- eco get commitment analysis aws
- autoscaling
- cloud infrastructure
- get aws commitment analysis
- get cost analysis
- list spot accounts for context
- list aws reserved instances
- eco list savings plans aws
- eco get unused ris aws
- eco list commitment plans aws
- list gcp commitment plans
- eco list commitment plans azure
- spot
- list billing engine accounts
- billing accounts
- get savings analysis
- list billing account families
- eco get savings analysis azure
- get gcp savings analysis
- eco list commitment plans gcp
- billing get cost analysis
- list aws savings plans
- billing
- containers
- list azure commitment plans
- get billing cost analysis
- eco list reserved instances aws
- admin list accounts
- list aws commitment plans
- eco get commitment plan aws
- cost optimization
- list commitment plans
- finops
- savings analysis
- get azure savings analysis
- list billing accounts
- eco get savings analysis aws
- get unused aws reserved instances
- eco get savings analysis gcp
- spot instances
slug: finops
source_filename: finops.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spot FinOps\"\n  description: \"Unified workflow for cloud financial operations combining commitment management (Eco), billing analytics (Billing Engine), and cost optimization. Used by FinOps teams, cloud finance analysts, and platform administrators.\"\n  tags:\n    - Spot\n    - FinOps\n    - Cost Optimization\n    - Billing\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPOT_API_TOKEN: SPOT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: spot-eco\n      location: ./shared/eco.yaml\n    - import: spot-billing\n      location: ./shared/billing-engine.yaml\n    - import: spot-admin\n      location: ./shared/administration.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: spot-finops-api\n      description: \"Unified REST API for Spot FinOps operations.\"\n      resources:\n        - path: /v1/commitment-plans\n          name: commitment-plans\n\
  \          description: \"Cloud commitment plans\"\n          operations:\n            - method: GET\n              name: list-commitment-plans\n              description: \"List AWS commitment plans\"\n              call: \"spot-eco.list-commitment-plans-aws\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/savings-analysis\n          name: savings-analysis\n          description: \"Savings analysis\"\n          operations:\n            - method: GET\n              name: get-savings-analysis\n              description: \"Get AWS savings analysis\"\n              call: \"spot-eco.get-savings-analysis-aws\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-accounts\n          name: billing-accounts\n          description: \"Billing accounts\"\n          operations:\n            - method: GET\n              name: list-billing-accounts\n \
  \             description: \"List billing accounts\"\n              call: \"spot-billing.list-billing-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cost-analysis\n          name: cost-analysis\n          description: \"Cost analysis\"\n          operations:\n            - method: GET\n              name: get-cost-analysis\n              description: \"Get cost analysis\"\n              call: \"spot-billing.get-cost-analysis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: spot-finops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spot FinOps operations.\"\n      tools:\n        - name: eco-list-commitment-plans-aws\n          description: \"List AWS commitment plans\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spot-eco.list-commitment-plans-aws\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-commitment-plan-aws\n          description: \"Get a specific AWS commitment plan\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-commitment-plan-aws\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-savings-analysis-aws\n          description: \"Get AWS savings analysis\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-savings-analysis-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-commitment-analysis-aws\n          description: \"Get AWS commitment analysis\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-commitment-analysis-aws\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: eco-list-savings-plans-aws\n          description: \"List AWS savings plans\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.list-savings-plans-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-list-reserved-instances-aws\n          description: \"List AWS reserved instances\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.list-reserved-instances-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-unused-ris-aws\n          description: \"Get unused AWS reserved instances\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-unused-ris-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-list-commitment-plans-azure\n          description: \"List Azure commitment plans\"\n  \
  \        hints:\n            readOnly: true\n          call: \"spot-eco.list-commitment-plans-azure\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-savings-analysis-azure\n          description: \"Get Azure savings analysis\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-savings-analysis-azure\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-list-commitment-plans-gcp\n          description: \"List GCP commitment plans\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.list-commitment-plans-gcp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: eco-get-savings-analysis-gcp\n          description: \"Get GCP savings analysis\"\n          hints:\n            readOnly: true\n          call: \"spot-eco.get-savings-analysis-gcp\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: billing-list-accounts\n          description: \"List billing engine accounts\"\n          hints:\n            readOnly: true\n          call: \"spot-billing.list-billing-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: billing-list-account-families\n          description: \"List billing account families\"\n          hints:\n            readOnly: true\n          call: \"spot-billing.list-account-families\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: billing-get-cost-analysis\n          description: \"Get billing cost analysis\"\n          hints:\n            readOnly: true\n          call: \"spot-billing.get-cost-analysis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: admin-list-accounts\n          description: \"List Spot accounts\
  \ for context\"\n          hints:\n            readOnly: true\n          call: \"spot-admin.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spot/refs/heads/main/capabilities/finops.yaml
tags:
- Spot
- FinOps
- Cost Optimization
- Billing
tools:
- description: List AWS commitment plans
  hints:
    openWorld: true
    readOnly: true
  name: eco-list-commitment-plans-aws
- description: Get a specific AWS commitment plan
  hints:
    readOnly: true
  name: eco-get-commitment-plan-aws
- description: Get AWS savings analysis
  hints:
    readOnly: true
  name: eco-get-savings-analysis-aws
- description: Get AWS commitment analysis
  hints:
    readOnly: true
  name: eco-get-commitment-analysis-aws
- description: List AWS savings plans
  hints:
    readOnly: true
  name: eco-list-savings-plans-aws
- description: List AWS reserved instances
  hints:
    readOnly: true
  name: eco-list-reserved-instances-aws
- description: Get unused AWS reserved instances
  hints:
    readOnly: true
  name: eco-get-unused-ris-aws
- description: List Azure commitment plans
  hints:
    readOnly: true
  name: eco-list-commitment-plans-azure
- description: Get Azure savings analysis
  hints:
    readOnly: true
  name: eco-get-savings-analysis-azure
- description: List GCP commitment plans
  hints:
    readOnly: true
  name: eco-list-commitment-plans-gcp
- description: Get GCP savings analysis
  hints:
    readOnly: true
  name: eco-get-savings-analysis-gcp
- description: List billing engine accounts
  hints:
    readOnly: true
  name: billing-list-accounts
- description: List billing account families
  hints:
    readOnly: true
  name: billing-list-account-families
- description: Get billing cost analysis
  hints:
    readOnly: true
  name: billing-get-cost-analysis
- description: List Spot accounts for context
  hints:
    readOnly: true
  name: admin-list-accounts
---
