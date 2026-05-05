---
categories: []
consumed_apis:
- unified-crm
description: Unified sales and CRM workflow combining contacts, companies, deals, and activities across 47+ CRM integrations including Salesforce, HubSpot, Pipedrive, and Zoho. Used by revenue operations teams, sales developers, and CRM integrators building cross-platform sales tooling.
layout: capability
name: Unified.to Sales and CRM
operations:
- description: List contacts from a CRM integration
  method: GET
  name: list-crm-contacts
  path: /v1/crm/{connection_id}/contacts
- description: Create a new contact in a CRM integration
  method: POST
  name: create-crm-contact
  path: /v1/crm/{connection_id}/contacts
- description: List companies from a CRM integration
  method: GET
  name: list-crm-companies
  path: /v1/crm/{connection_id}/companies
- description: List deals from a CRM integration
  method: GET
  name: list-crm-deals
  path: /v1/crm/{connection_id}/deals
- description: Create a new deal in a CRM integration
  method: POST
  name: create-crm-deal
  path: /v1/crm/{connection_id}/deals
personas: []
provider_name: Unified.to
provider_slug: unified-to
search_terms:
- list contacts from a crm integration
- create a new deal in a crm integration
- CRM Integrator
- developers building hr workflows, employee onboarding, and recruiting automation
- list companies from a crm integration
- deals
- create a new contact in a crm integration
- list companies from a connected crm integration
- create crm deal
- crm contact, company, and deal management across 47+ integrations
- list contacts from a connected crm integration (salesforce, hubspot, pipedrive, etc.)
- crm company management across all integrations
- developers building invoicing automation, expense management, and accounting sync
- crm contact management across all integrations
- list crm contacts
- People Operations Engineer
- unified.to
- developers building sales tools, crm sync, and revenue reporting integrations
- integrations
- list deals and opportunities from a connected crm integration
- list deals from a crm integration
- unified api
- crm
- crm deal and opportunity management
- create crm contact
- Revenue Operations Developer
- Finance Operations Engineer
- sales
- HR Technology Developer
- create a new contact in a connected crm integration
- create a new deal or opportunity in a connected crm integration
- list crm companies
- hris and ats management across 296+ hr and recruiting integrations
- Fintech Developer
- contacts
- list crm deals
- accounting, invoicing, and payment management across 41+ integrations
slug: sales-and-crm
source_filename: sales-and-crm.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unified.to Sales and CRM\"\n  description: >-\n    Unified sales and CRM workflow combining contacts, companies, deals, and activities\n    across 47+ CRM integrations including Salesforce, HubSpot, Pipedrive, and Zoho.\n    Used by revenue operations teams, sales developers, and CRM integrators building\n    cross-platform sales tooling.\n  tags:\n    - Unified.to\n    - CRM\n    - Sales\n    - Contacts\n    - Deals\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\n\ncapability:\n  consumes:\n    - import: unified-crm\n      location: ./shared/crm-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unified-sales-crm-api\n      description: \"Unified REST API for sales and CRM data across 47+ integrations.\"\n      resources:\n        - path: /v1/crm/{connection_id}/contacts\n          name: contacts\n         \
  \ description: \"CRM contact management across all integrations\"\n          operations:\n            - method: GET\n              name: list-crm-contacts\n              description: \"List contacts from a CRM integration\"\n              call: \"unified-crm.list-crm-contacts\"\n              with:\n                connection_id: \"rest.connection_id\"\n                query: \"rest.query\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-crm-contact\n              description: \"Create a new contact in a CRM integration\"\n              call: \"unified-crm.create-crm-contact\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/crm/{connection_id}/companies\n\
  \          name: companies\n          description: \"CRM company management across all integrations\"\n          operations:\n            - method: GET\n              name: list-crm-companies\n              description: \"List companies from a CRM integration\"\n              call: \"unified-crm.list-crm-companies\"\n              with:\n                connection_id: \"rest.connection_id\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/crm/{connection_id}/deals\n          name: deals\n          description: \"CRM deal and opportunity management\"\n          operations:\n            - method: GET\n              name: list-crm-deals\n              description: \"List deals from a CRM integration\"\n              call: \"unified-crm.list-crm-deals\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-crm-deal\n              description: \"Create a new deal in a CRM integration\"\n              call: \"unified-crm.create-crm-deal\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: unified-sales-crm-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sales and CRM operations across 47+ integrations.\"\n      tools:\n        - name: list-crm-contacts\n          description: \"List contacts from a connected CRM integration (Salesforce, HubSpot, Pipedrive, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-crm.list-crm-contacts\"\n          with:\n            connection_id: \"tools.connection_id\"\n            query: \"tools.query\"\
  \n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-crm-contact\n          description: \"Create a new contact in a connected CRM integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unified-crm.create-crm-contact\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-crm-companies\n          description: \"List companies from a connected CRM integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-crm.list-crm-companies\"\n          with:\n            connection_id: \"tools.connection_id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: list-crm-deals\n          description: \"List deals and opportunities from a connected CRM integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-crm.list-crm-deals\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-crm-deal\n          description: \"Create a new deal or opportunity in a connected CRM integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unified-crm.create-crm-deal\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unified-to/refs/heads/main/capabilities/sales-and-crm.yaml
tags:
- Unified.to
- CRM
- Sales
- Contacts
- Deals
tools:
- description: List contacts from a connected CRM integration (Salesforce, HubSpot, Pipedrive, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-contacts
- description: Create a new contact in a connected CRM integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-crm-contact
- description: List companies from a connected CRM integration
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-companies
- description: List deals and opportunities from a connected CRM integration
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-deals
- description: Create a new deal or opportunity in a connected CRM integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-crm-deal
---
