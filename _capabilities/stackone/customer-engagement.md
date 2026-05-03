---
categories: []
consumed_apis:
- stackone
description: Unified workflow capability for customer-facing operations using StackOne's unified APIs. Combines CRM (contacts, accounts, lists) and Marketing (campaigns, email/push/omni-channel templates) for managing customer relationships and multi-channel communications across platforms. Designed for marketing teams, CRM administrators, and AI agents automating customer outreach.
layout: capability
name: StackOne Customer Engagement
operations:
- description: List CRM contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: List marketing campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
personas: []
provider_name: StackOne
provider_slug: stackone
search_terms:
- marketing
- list contacts from the connected crm system (salesforce, hubspot, etc.)
- proxy a custom request to any connected provider api
- crm contacts
- integrations
- proxy request
- campaigns
- create a new contact
- marketing campaigns
- create a new contact in the connected crm system
- customer engagement
- unified api
- list marketing campaigns from the connected platform (mailchimp, braze, etc.)
- list marketing campaigns
- create contact
- ipaas
- list contacts
- list crm contacts
- crm
- list campaigns
slug: customer-engagement
source_filename: customer-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StackOne Customer Engagement\"\n  description: >-\n    Unified workflow capability for customer-facing operations using StackOne's\n    unified APIs. Combines CRM (contacts, accounts, lists) and Marketing\n    (campaigns, email/push/omni-channel templates) for managing customer\n    relationships and multi-channel communications across platforms.\n    Designed for marketing teams, CRM administrators, and AI agents\n    automating customer outreach.\n  tags:\n    - CRM\n    - Marketing\n    - Customer Engagement\n    - Unified API\n    - Campaigns\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACKONE_API_KEY: STACKONE_API_KEY\n\ncapability:\n  consumes:\n    - import: stackone\n      location: ./shared/stackone-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: stackone-engagement-api\n      description: \"Unified REST API for CRM and marketing operations.\"\
  \n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"CRM contacts\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List CRM contacts\"\n              call: \"stackone.list-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Create a new contact\"\n              call: \"stackone.create-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Marketing campaigns\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List marketing campaigns\"\n              call: \"stackone.list-campaigns\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: stackone-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CRM and marketing operations.\"\n      tools:\n        - name: list-contacts\n          description: \"List contacts from the connected CRM system (Salesforce, HubSpot, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackone.list-contacts\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-contact\n          description: \"Create a new contact in the connected CRM system\"\n          hints:\n            readOnly: false\n          call: \"stackone.create-contact\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n\n        - name: list-campaigns\n          description: \"List marketing campaigns from the connected platform (Mailchimp, Braze, etc.)\"\n          hints:\n            readOnly: true\n          call: \"stackone.list-campaigns\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: proxy-request\n          description: \"Proxy a custom request to any connected provider API\"\n          hints:\n            readOnly: false\n          call: \"stackone.proxy-request\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stackone/refs/heads/main/capabilities/customer-engagement.yaml
tags:
- CRM
- Marketing
- Customer Engagement
- Unified API
- Campaigns
tools:
- description: List contacts from the connected CRM system (Salesforce, HubSpot, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Create a new contact in the connected CRM system
  hints:
    readOnly: false
  name: create-contact
- description: List marketing campaigns from the connected platform (Mailchimp, Braze, etc.)
  hints:
    readOnly: true
  name: list-campaigns
- description: Proxy a custom request to any connected provider API
  hints:
    readOnly: false
  name: proxy-request
---
