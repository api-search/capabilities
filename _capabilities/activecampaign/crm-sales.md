---
categories:
- crm-sales
consumed_apis: []
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
- company account management
- list all sales deals in activecampaign crm
- crm, pipeline management, and revenue operations
- tracks deals, manages accounts, and uses crm features
- list accounts
- cross-channel contact engagement and personalization
- sales automation
- create a new deal
- crm
- customer experience
- manage sales pipeline, deals, accounts, and tasks
- create a new account
- create account
- list all company accounts in activecampaign crm
- email, sms, and multi-channel marketing automation
- accounts
- list all accounts
- Marketing Manager
- Growth Engineer
- create a new company account in activecampaign crm
- Sales Representative
- deals
- create a new sales deal in activecampaign crm
- get deal
- Revenue Operations
- create deal
- sales
- orchestrate contact journeys, campaigns, automations, and list management
- Account Manager
- list all deals
- Email Marketer
- list deals
- builds integrations, automation workflows, and uses the api directly
- sales deal management
- retrieve a specific deal by id
- marketing automation
- activecampaign
- email marketing
slug: crm-sales
source_filename: crm-sales.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ActiveCampaign CRM and Sales\n  description: Workflow capability for CRM and sales pipeline management including deals, accounts, tasks, and pipeline stages.\n    Used by sales teams and revenue operations to track and advance deals.\n  tags:\n  - ActiveCampaign\n  - CRM\n  - Sales\n  - Deals\n  - Accounts\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACTIVECAMPAIGN_API_TOKEN: ACTIVECAMPAIGN_API_TOKEN\n    ACTIVECAMPAIGN_API_URL: ACTIVECAMPAIGN_API_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: activecampaign-v3\n    baseUri: https://{yourAccountName}.api-us1.com/api/3\n    description: ActiveCampaign REST API v3\n    authentication:\n      type: apikey\n      key: Api-Token\n      value: '{{ACTIVECAMPAIGN_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: contacts\n      path: /contacts\n      description: Manage contacts - the center of all ActiveCampaign activity\n\
  \      operations:\n      - name: list-contacts\n        method: GET\n        description: List, search, and filter contacts\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter contacts by email\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n         \
  \   contact: '{{tools.contact}}'\n      - name: get-contact\n        method: GET\n        description: Retrieve a contact by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PUT\n        description: Update a contact\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-contact\n        method: DELETE\n        description: Delete a contact\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sync-contact\n        method: POST\n        description: Sync a contact's data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deals\n      path: /deals\n      description: Manage sales deals and pipeline\n      operations:\n      - name: list-deals\n        method: GET\n        description: List all deals\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ create-deal\n        method: POST\n        description: Create a new deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deal\n        method: GET\n        description: Retrieve a deal by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deal\n        method: PUT\n        description: Update a deal\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      description: Manage company\
  \ accounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: Retrieve all accounts\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Retrieve an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: automations\n      path: /automations\n      description: Manage marketing automations\n      operations:\n      - name: list-automations\n        method: GET\n        description: List all automations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /campaigns\n      description: Manage email campaigns\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List all campaigns\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /lists\n      description: Manage contact lists\n      operations:\n      - name: list-lists\n        method: GET\n        description:\
  \ Retrieve all lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-list\n        method: POST\n        description: Create a new list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Manage contact tags\n      operations:\n      - name: list-tags\n        method: GET\n        description: List all tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag\n        method: POST\n        description: Create a new tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Manage event webhooks\n      operations:\n      - name:\
  \ list-webhooks\n        method: GET\n        description: List all webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: crm-sales-api\n    description: Unified REST API for CRM and sales pipeline workflows.\n    resources:\n    - path: /v1/deals\n      name: deals\n      description: Sales deal management\n      operations:\n      - method: GET\n        name: list-deals\n        description: List all deals\n        call: activecampaign-v3.list-deals\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deal\n        description: Create a new deal\n        call: activecampaign-v3.create-deal\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Company account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accounts\n        call: activecampaign-v3.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new account\n        call: activecampaign-v3.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: crm-sales-mcp\n    transport: http\n    description: MCP server for AI-assisted CRM and sales pipeline management.\n    tools:\n    - name: list-deals\n      description: List all sales deals in ActiveCampaign CRM\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-deals\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-deal\n      description: Create a new sales deal in ActiveCampaign CRM\n      hints:\n        readOnly: false\n        destructive: false\n      call: activecampaign-v3.create-deal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deal\n      description: Retrieve a specific deal by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: activecampaign-v3.get-deal\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List all company accounts in ActiveCampaign CRM\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-account\n      description: Create a new company account in ActiveCampaign CRM\n      hints:\n        readOnly: false\n\
  \        destructive: false\n      call: activecampaign-v3.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
