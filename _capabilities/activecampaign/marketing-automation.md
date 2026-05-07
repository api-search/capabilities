---
categories:
- customer-engagement
consumed_apis: []
description: Unified workflow capability for marketing automation, contact management, campaign execution, and list segmentation. Used by marketing teams and growth engineers to orchestrate multi-channel customer journeys.
layout: capability
name: ActiveCampaign Marketing Automation
operations:
- description: List and search contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: List all campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: List all automations
  method: GET
  name: list-automations
  path: /v1/automations
- description: List all contact lists
  method: GET
  name: list-lists
  path: /v1/lists
- description: Create a new contact list
  method: POST
  name: create-list
  path: /v1/lists
- description: List all tags
  method: GET
  name: list-tags
  path: /v1/tags
personas: []
provider_name: ActiveCampaign
provider_slug: activecampaign
search_terms:
- list and search activecampaign contacts by email, name, or other criteria
- manages email campaigns, automations, and contact segmentation
- create a new contact tag in activecampaign
- contact lifecycle management
- create a new contact
- list tags
- create list
- crm, pipeline management, and revenue operations
- list all campaigns
- tracks deals, manages accounts, and uses crm features
- list contact lists
- create contact
- list all contact lists
- cross-channel contact engagement and personalization
- create a new contact list
- email campaign management
- list automations
- contact tag management
- sync contact
- list all contact tags in activecampaign
- contact list management
- manage sales pipeline, deals, accounts, and tasks
- contacts
- list campaigns
- crm
- sales automation
- customer experience
- list all marketing automations in activecampaign
- create a new contact in activecampaign
- email, sms, and multi-channel marketing automation
- list contacts
- Marketing Manager
- campaigns
- Growth Engineer
- list lists
- list all tags
- Sales Representative
- list all contact lists in activecampaign
- Revenue Operations
- orchestrate contact journeys, campaigns, automations, and list management
- create tag
- Account Manager
- marketing automation workflows
- Email Marketer
- builds integrations, automation workflows, and uses the api directly
- sync a contact's data to activecampaign, creating or updating as needed
- list all email campaigns in activecampaign
- marketing automation
- list and search contacts
- list all automations
- activecampaign
- email marketing
slug: marketing-automation
source_filename: marketing-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ActiveCampaign Marketing Automation\n  description: Unified workflow capability for marketing automation, contact management, campaign execution, and list segmentation.\n    Used by marketing teams and growth engineers to orchestrate multi-channel customer journeys.\n  tags:\n  - ActiveCampaign\n  - Marketing Automation\n  - Email Marketing\n  - Contacts\n  - Campaigns\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACTIVECAMPAIGN_API_TOKEN: ACTIVECAMPAIGN_API_TOKEN\n    ACTIVECAMPAIGN_API_URL: ACTIVECAMPAIGN_API_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: activecampaign-v3\n    baseUri: https://{yourAccountName}.api-us1.com/api/3\n    description: ActiveCampaign REST API v3\n    authentication:\n      type: apikey\n      key: Api-Token\n      value: '{{ACTIVECAMPAIGN_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: contacts\n      path: /contacts\n      description:\
  \ Manage contacts - the center of all ActiveCampaign activity\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List, search, and filter contacts\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter contacts by email\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \       body:\n          type: json\n          data:\n            contact: '{{tools.contact}}'\n      - name: get-contact\n        method: GET\n        description: Retrieve a contact by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PUT\n        description: Update a contact\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-contact\n        method: DELETE\n        description: Delete a contact\n        inputParameters:\n        - name: id\n          in: path\n   \
  \       type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sync-contact\n        method: POST\n        description: Sync a contact's data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deals\n      path: /deals\n      description: Manage sales deals and pipeline\n      operations:\n      - name: list-deals\n        method: GET\n        description: List all deals\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-deal\n        method: POST\n        description: Create a new deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deal\n        method: GET\n        description: Retrieve a deal by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deal\n        method: PUT\n        description: Update a deal\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: accounts\n      path: /accounts\n      description: Manage company accounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: Retrieve all accounts\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Retrieve an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: automations\n      path: /automations\n      description: Manage marketing automations\n      operations:\n      - name: list-automations\n        method: GET\n        description: List all automations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /campaigns\n      description: Manage email campaigns\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List all campaigns\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /lists\n      description: Manage contact lists\n      operations:\n\
  \      - name: list-lists\n        method: GET\n        description: Retrieve all lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-list\n        method: POST\n        description: Create a new list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Manage contact tags\n      operations:\n      - name: list-tags\n        method: GET\n        description: List all tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag\n        method: POST\n        description: Create a new tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n   \
  \   description: Manage event webhooks\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marketing-automation-api\n    description: Unified REST API for marketing automation workflows.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Contact lifecycle management\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List and search contacts\n        call: activecampaign-v3.list-contacts\n        with:\n          email: rest.email\n          limit: rest.limit\n\
  \          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create a new contact\n        call: activecampaign-v3.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name: campaigns\n      description: Email campaign management\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List all campaigns\n        call: activecampaign-v3.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/automations\n      name: automations\n      description: Marketing automation workflows\n      operations:\n      - method: GET\n        name: list-automations\n        description: List all automations\n        call: activecampaign-v3.list-automations\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /v1/lists\n      name: lists\n      description: Contact list management\n      operations:\n      - method: GET\n        name: list-lists\n        description: List all contact lists\n        call: activecampaign-v3.list-lists\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-list\n        description: Create a new contact list\n        call: activecampaign-v3.create-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Contact tag management\n      operations:\n      - method: GET\n        name: list-tags\n        description: List all tags\n        call: activecampaign-v3.list-tags\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marketing-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted marketing automation with ActiveCampaign.\n\
  \    tools:\n    - name: list-contacts\n      description: List and search ActiveCampaign contacts by email, name, or other criteria\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-contacts\n      with:\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact in ActiveCampaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: activecampaign-v3.create-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-contact\n      description: Sync a contact's data to ActiveCampaign, creating or updating as needed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: activecampaign-v3.sync-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-campaigns\n  \
  \    description: List all email campaigns in ActiveCampaign\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-automations\n      description: List all marketing automations in ActiveCampaign\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-automations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contact-lists\n      description: List all contact lists in ActiveCampaign\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-lists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: List all contact tags in ActiveCampaign\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activecampaign-v3.list-tags\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: create-tag\n      description: Create a new contact tag in ActiveCampaign\n      hints:\n        readOnly: false\n        destructive: false\n      call: activecampaign-v3.create-tag\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/activecampaign/refs/heads/main/capabilities/marketing-automation.yaml
tags:
- ActiveCampaign
- Marketing Automation
- Email Marketing
- Contacts
- Campaigns
tools:
- description: List and search ActiveCampaign contacts by email, name, or other criteria
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Create a new contact in ActiveCampaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-contact
- description: Sync a contact's data to ActiveCampaign, creating or updating as needed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-contact
- description: List all email campaigns in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: List all marketing automations in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-automations
- description: List all contact lists in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-contact-lists
- description: List all contact tags in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: Create a new contact tag in ActiveCampaign
  hints:
    destructive: false
    readOnly: false
  name: create-tag
---
