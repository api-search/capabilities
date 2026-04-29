---
api_specs:
- filename: activecampaign-v3.json
  format: json
  label: activecampaign-v3
  slug: activecampaign-v3
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/activecampaign/refs/heads/main/openapi/activecampaign-v3.json
categories:
- customer-engagement
consumed_apis:
- activecampaign-v3
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
- list campaigns
- list contact lists
- customer experience
- sync contact
- Revenue Operations
- crm, pipeline management, and revenue operations
- campaigns
- list all contact lists in activecampaign
- list all marketing automations in activecampaign
- list all email campaigns in activecampaign
- contact lifecycle management
- create a new contact tag in activecampaign
- list all contact lists
- crm
- sales automation
- orchestrate contact journeys, campaigns, automations, and list management
- contact tag management
- contacts
- email campaign management
- marketing automation
- list all campaigns
- create a new contact in activecampaign
- email marketing
- list contacts
- manage sales pipeline, deals, accounts, and tasks
- create tag
- list lists
- list automations
- list all automations
- sync a contact's data to activecampaign, creating or updating as needed
- list all tags
- Sales Representative
- list and search contacts
- builds integrations, automation workflows, and uses the api directly
- email, sms, and multi-channel marketing automation
- activecampaign
- marketing automation workflows
- tracks deals, manages accounts, and uses crm features
- Email Marketer
- create a new contact
- list all contact tags in activecampaign
- manages email campaigns, automations, and contact segmentation
- cross-channel contact engagement and personalization
- create list
- Marketing Manager
- Account Manager
- Growth Engineer
- contact list management
- create contact
- create a new contact list
- list tags
- list and search activecampaign contacts by email, name, or other criteria
slug: marketing-automation
source_filename: marketing-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ActiveCampaign Marketing Automation\"\n  description: \"Unified workflow capability for marketing automation, contact management, campaign execution, and list segmentation. Used by marketing teams and growth engineers to orchestrate multi-channel customer journeys.\"\n  tags:\n    - ActiveCampaign\n    - Marketing Automation\n    - Email Marketing\n    - Contacts\n    - Campaigns\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACTIVECAMPAIGN_API_TOKEN: ACTIVECAMPAIGN_API_TOKEN\n      ACTIVECAMPAIGN_API_URL: ACTIVECAMPAIGN_API_URL\n\ncapability:\n  consumes:\n    - import: activecampaign-v3\n      location: ./shared/activecampaign-v3.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: marketing-automation-api\n      description: \"Unified REST API for marketing automation workflows.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n\
  \          description: \"Contact lifecycle management\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List and search contacts\"\n              call: \"activecampaign-v3.list-contacts\"\n              with:\n                email: \"rest.email\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Create a new contact\"\n              call: \"activecampaign-v3.create-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Email campaign management\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"\
  List all campaigns\"\n              call: \"activecampaign-v3.list-campaigns\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/automations\n          name: automations\n          description: \"Marketing automation workflows\"\n          operations:\n            - method: GET\n              name: list-automations\n              description: \"List all automations\"\n              call: \"activecampaign-v3.list-automations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lists\n          name: lists\n          description: \"Contact list management\"\n          operations:\n            - method: GET\n              name: list-lists\n              description: \"List all contact lists\"\n              call: \"activecampaign-v3.list-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    \
  \        - method: POST\n              name: create-list\n              description: \"Create a new contact list\"\n              call: \"activecampaign-v3.create-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tags\n          name: tags\n          description: \"Contact tag management\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List all tags\"\n              call: \"activecampaign-v3.list-tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: marketing-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted marketing automation with ActiveCampaign.\"\n      tools:\n        - name: list-contacts\n          description: \"List and search ActiveCampaign contacts by email, name, or other criteria\"\n      \
  \    hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-contacts\"\n          with:\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new contact in ActiveCampaign\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"activecampaign-v3.create-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sync-contact\n          description: \"Sync a contact's data to ActiveCampaign, creating or updating as needed\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"activecampaign-v3.sync-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: list-campaigns\n          description: \"List all email campaigns in ActiveCampaign\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-campaigns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-automations\n          description: \"List all marketing automations in ActiveCampaign\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-automations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contact-lists\n          description: \"List all contact lists in ActiveCampaign\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n        \
  \  description: \"List all contact tags in ActiveCampaign\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activecampaign-v3.list-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-tag\n          description: \"Create a new contact tag in ActiveCampaign\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"activecampaign-v3.create-tag\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
