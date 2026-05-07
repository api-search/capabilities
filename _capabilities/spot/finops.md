---
categories:
- payments
consumed_apis: []
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
- containers
- get azure savings analysis
- get unused aws reserved instances
- list billing accounts
- billing list account families
- list commitment plans
- get aws savings analysis
- get cost analysis
- billing
- autoscaling
- billing accounts
- list aws savings plans
- cost optimization
- cloud commitment plans
- eco list commitment plans aws
- eco get savings analysis gcp
- eco list savings plans aws
- list billing engine accounts
- eco list reserved instances aws
- spot instances
- list gcp commitment plans
- spot
- billing get cost analysis
- list aws reserved instances
- list billing account families
- get a specific aws commitment plan
- eco get unused ris aws
- kubernetes
- eco get commitment analysis aws
- get savings analysis
- list spot accounts for context
- list aws commitment plans
- billing list accounts
- get aws commitment analysis
- get gcp savings analysis
- cloud infrastructure
- cost analysis
- savings analysis
- eco get savings analysis azure
- eco list commitment plans azure
- list azure commitment plans
- get billing cost analysis
- admin list accounts
- eco list commitment plans gcp
- eco get commitment plan aws
- eco get savings analysis aws
- finops
slug: finops
source_filename: finops.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spot FinOps\n  description: Unified workflow for cloud financial operations combining commitment management (Eco), billing analytics (Billing\n    Engine), and cost optimization. Used by FinOps teams, cloud finance analysts, and platform administrators.\n  tags:\n  - Spot\n  - FinOps\n  - Cost Optimization\n  - Billing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPOT_API_TOKEN: SPOT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spot-eco\n    baseUri: https://api.spotinst.io\n    description: Spot Eco API\n    authentication:\n      type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: commitments-aws\n      path: /eco/aws\n      description: AWS commitment management\n      operations:\n      - name: list-commitment-plans-aws\n        method: GET\n        description: List AWS commitment plans\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-commitment-plan-aws\n        method: GET\n        description: Get an AWS commitment plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-unused-ris-aws\n        method: GET\n        description: Get unused AWS reserved instances\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-savings-plans-aws\n        method: GET\n        description: List AWS savings plans\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: list-reserved-instances-aws\n        method: GET\n        description: List AWS reserved instances\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-savings-analysis-aws\n        method: GET\n        description: Get AWS savings analysis\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-commitment-analysis-aws\n        method: GET\n        description: Get AWS commitment analysis\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commitments-azure\n      path: /eco/azure\n      description: Azure commitment management\n      operations:\n      - name: list-commitment-plans-azure\n        method:\
  \ GET\n        description: List Azure commitment plans\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-savings-analysis-azure\n        method: GET\n        description: Get Azure savings analysis\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commitments-gcp\n      path: /eco/gcp\n      description: GCP commitment management\n      operations:\n      - name: list-commitment-plans-gcp\n        method: GET\n        description: List GCP commitment plans\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-savings-analysis-gcp\n        method: GET\n        description: Get GCP savings analysis\n        inputParameters: []\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: spot-billing\n    baseUri: https://api.spotinst.io\n    description: Spot Billing Engine API\n    authentication:\n      type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: billing-accounts\n      path: /billing/account\n      description: Manage billing accounts\n      operations:\n      - name: list-billing-accounts\n        method: GET\n        description: List billing engine accounts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setup-billing-engine\n        method: POST\n        description: Set up billing engine\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ validate-billing-setup\n        method: POST\n        description: Validate billing engine setup\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-families\n      path: /billing/accountFamily\n      description: Manage account families\n      operations:\n      - name: create-account-family\n        method: POST\n        description: Create an account family\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-account-families\n        method: GET\n        description: List account families\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account-family\n        method: GET\n        description: Get an account family\n\
  \        inputParameters:\n        - name: familyId\n          in: path\n          type: string\n          required: true\n          description: Account family ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account-family\n        method: PUT\n        description: Update an account family\n        inputParameters:\n        - name: familyId\n          in: path\n          type: string\n          required: true\n          description: Account family ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account-family\n        method: DELETE\n        description: Delete an account family\n        inputParameters:\n        - name: familyId\n          in: path\n          type: string\n          required: true\n          description: Account family ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: cost-analysis\n      path: /billing/costAnalysis\n      description: Cost analysis\n      operations:\n      - name: get-cost-analysis\n        method: GET\n        description: Get cost analysis data\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-intelligence\n      path: /billing/costIntelligence\n      description: Cost intelligence\n      operations:\n      - name: setup-cost-intelligence\n        method: POST\n        description: Set up cost intelligence\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-cost-intelligence\n        method: POST\n        description: Validate cost intelligence setup\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: spot-admin\n    baseUri: https://api.spotinst.io\n    description: Spot Administration API\n    authentication:\n      type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /setup/organization\n      description: Manage Spot organizations\n      operations:\n      - name: create-organization\n        method: POST\n        description: Create a new organization\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description: Delete an organization\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /setup/account\n\
  \      description: Manage Spot accounts\n      operations:\n      - name: create-account\n        method: POST\n        description: Create a new account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-accounts\n        method: GET\n        description: List all accounts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update an account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Delete an account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: users\n      path: /setup/user\n      description: Manage users\n      operations:\n      - name: create-user\n        method: POST\n        description: Create a new user\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-users\n        method: GET\n        description: List organization users\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get a specific user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: update-user-permissions\n        method: PUT\n        description: Update user permissions\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-programmatic-user\n        method: POST\n        description: Create a programmatic API user\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: access-policies\n      path: /setup/access/policy\n      description: Manage access policies\n      operations:\n      - name: create-access-policy\n        method: POST\n        description: Create an access policy\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-access-policies\n        method: GET\n        description: List access policies\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-access-policy\n        method: PUT\n        description: Update an access policy\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-access-policy\n        method: DELETE\n  \
  \      description: Delete an access policy\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-credentials\n      path: /setup/credentials\n      description: Link cloud provider credentials\n      operations:\n      - name: set-aws-credentials\n        method: POST\n        description: Set AWS cloud credentials\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-azure-credentials\n        method: POST\n        description: Set Azure cloud credentials\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-gcp-credentials\n        method: POST\n        description: Set GCP cloud credentials\n        inputParameters: []\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /events/subscription\n      description: Manage event subscriptions\n      operations:\n      - name: create-subscription\n        method: POST\n        description: Create an event subscription\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-subscriptions\n        method: GET\n        description: List event subscriptions\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscription\n        method: DELETE\n        description: Delete an event subscription\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: health\n      path: /healthCheck\n      description: API health check\n      operations:\n      - name: health-check\n        method: GET\n        description: Check API health status\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: spot-finops-api\n    description: Unified REST API for Spot FinOps operations.\n    resources:\n    - path: /v1/commitment-plans\n      name: commitment-plans\n      description: Cloud commitment plans\n      operations:\n      - method: GET\n        name: list-commitment-plans\n        description: List AWS commitment plans\n        call: spot-eco.list-commitment-plans-aws\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/savings-analysis\n      name: savings-analysis\n      description: Savings analysis\n\
  \      operations:\n      - method: GET\n        name: get-savings-analysis\n        description: Get AWS savings analysis\n        call: spot-eco.get-savings-analysis-aws\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-accounts\n      name: billing-accounts\n      description: Billing accounts\n      operations:\n      - method: GET\n        name: list-billing-accounts\n        description: List billing accounts\n        call: spot-billing.list-billing-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-analysis\n      name: cost-analysis\n      description: Cost analysis\n      operations:\n      - method: GET\n        name: get-cost-analysis\n        description: Get cost analysis\n        call: spot-billing.get-cost-analysis\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: spot-finops-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted Spot FinOps operations.\n    tools:\n    - name: eco-list-commitment-plans-aws\n      description: List AWS commitment plans\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spot-eco.list-commitment-plans-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-commitment-plan-aws\n      description: Get a specific AWS commitment plan\n      hints:\n        readOnly: true\n      call: spot-eco.get-commitment-plan-aws\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-savings-analysis-aws\n      description: Get AWS savings analysis\n      hints:\n        readOnly: true\n      call: spot-eco.get-savings-analysis-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-commitment-analysis-aws\n      description: Get AWS commitment analysis\n      hints:\n        readOnly:\
  \ true\n      call: spot-eco.get-commitment-analysis-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-list-savings-plans-aws\n      description: List AWS savings plans\n      hints:\n        readOnly: true\n      call: spot-eco.list-savings-plans-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-list-reserved-instances-aws\n      description: List AWS reserved instances\n      hints:\n        readOnly: true\n      call: spot-eco.list-reserved-instances-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-unused-ris-aws\n      description: Get unused AWS reserved instances\n      hints:\n        readOnly: true\n      call: spot-eco.get-unused-ris-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-list-commitment-plans-azure\n      description: List Azure commitment plans\n      hints:\n        readOnly: true\n      call: spot-eco.list-commitment-plans-azure\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-savings-analysis-azure\n      description: Get Azure savings analysis\n      hints:\n        readOnly: true\n      call: spot-eco.get-savings-analysis-azure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-list-commitment-plans-gcp\n      description: List GCP commitment plans\n      hints:\n        readOnly: true\n      call: spot-eco.list-commitment-plans-gcp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: eco-get-savings-analysis-gcp\n      description: Get GCP savings analysis\n      hints:\n        readOnly: true\n      call: spot-eco.get-savings-analysis-gcp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: billing-list-accounts\n      description: List billing engine accounts\n      hints:\n        readOnly: true\n      call: spot-billing.list-billing-accounts\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: billing-list-account-families\n      description: List billing account families\n      hints:\n        readOnly: true\n      call: spot-billing.list-account-families\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: billing-get-cost-analysis\n      description: Get billing cost analysis\n      hints:\n        readOnly: true\n      call: spot-billing.get-cost-analysis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admin-list-accounts\n      description: List Spot accounts for context\n      hints:\n        readOnly: true\n      call: spot-admin.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
