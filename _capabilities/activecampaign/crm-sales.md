---
api_specs:
- filename: activecampaign-v3.json
  format: json
  label: activecampaign-v3
  slug: activecampaign-v3
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/activecampaign/refs/heads/main/openapi/activecampaign-v3.json
categories:
- crm-sales
consumed_apis:
- activecampaign-v3
description: Workflow capability for CRM and sales pipeline management including deals, accounts, tasks, and pipeline stages. Used by sales teams and revenue operations to track and advance deals.
layout: capability
name: ActiveCampaign CRM and Sales
operations:
- description: List all deals
  method: GET
  name: list-deals
  path: /v1/deals
- description: Create a new deal
  method: POST
  name: create-deal
  path: /v1/deals
- description: List all accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new account
  method: POST
  name: create-account
  path: /v1/accounts
personas: []
provider_name: ActiveCampaign
provider_slug: activecampaign
search_terms:
- manages email campaigns, automations, and contact segmentation
- Account Manager
- Marketing Manager
- email, sms, and multi-channel marketing automation
- get deal
- activecampaign
- builds integrations, automation workflows, and uses the api directly
- Growth Engineer
- tracks deals, manages accounts, and uses crm features
- create a new sales deal in activecampaign crm
- crm
- email marketing
- create a new company account in activecampaign crm
- retrieve a specific deal by id
- Revenue Operations
- create a new account
- customer experience
- create deal
- list accounts
- crm, pipeline management, and revenue operations
- marketing automation
- sales deal management
- list all accounts
- cross-channel contact engagement and personalization
- create account
- sales automation
- Email Marketer
- list all sales deals in activecampaign crm
- manage sales pipeline, deals, accounts, and tasks
- Sales Representative
- company account management
- accounts
- list all deals
- list all company accounts in activecampaign crm
- orchestrate contact journeys, campaigns, automations, and list management
- create a new deal
- list deals
- deals
- sales
slug: crm-sales
source_filename: crm-sales.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ActiveCampaign CRM and Sales\"\n  description: \"Workflow capability for CRM and sales pipeline management including deals, accounts, tasks, and pipeline stages. Used by sales teams and revenue operations to track and advance deals.\"\n  tags:\n    - ActiveCampaign\n    - CRM\n    - Sales\n    - Deals\n    - Accounts\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACTIVECAMPAIGN_API_TOKEN: ACTIVECAMPAIGN_API_TOKEN\n      ACTIVECAMPAIGN_API_URL: ACTIVECAMPAIGN_API_URL\n\ncapability:\n  consumes:\n    - import: activecampaign-v3\n      location: ./shared/activecampaign-v3.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: crm-sales-api\n      description: \"Unified REST API for CRM and sales pipeline workflows.\"\n      resources:\n        - path: /v1/deals\n          name: deals\n          description: \"Sales deal management\"\n          operations:\n\
  \            - method: GET\n              name: list-deals\n              description: \"List all deals\"\n              call: \"activecampaign-v3.list-deals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deal\n              description: \"Create a new deal\"\n              call: \"activecampaign-v3.create-deal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Company account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all accounts\"\n              call: \"activecampaign-v3.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n     \
  \         description: \"Create a new account\"\n              call: \"activecampaign-v3.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: crm-sales-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CRM and sales pipeline management.\"\n      tools:\n        - name: list-deals\n          description: \"List all sales deals in ActiveCampaign CRM\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-deals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-deal\n          description: \"Create a new sales deal in ActiveCampaign CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"activecampaign-v3.create-deal\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-deal\n          description: \"Retrieve a specific deal by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"activecampaign-v3.get-deal\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List all company accounts in ActiveCampaign CRM\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new company account in ActiveCampaign CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"activecampaign-v3.create-account\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/activecampaign/refs/heads/main/capabilities/crm-sales.yaml
tags:
- ActiveCampaign
- CRM
- Sales
- Deals
- Accounts
tools:
- description: List all sales deals in ActiveCampaign CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-deals
- description: Create a new sales deal in ActiveCampaign CRM
  hints:
    destructive: false
    readOnly: false
  name: create-deal
- description: Retrieve a specific deal by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-deal
- description: List all company accounts in ActiveCampaign CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Create a new company account in ActiveCampaign CRM
  hints:
    destructive: false
    readOnly: false
  name: create-account
---
