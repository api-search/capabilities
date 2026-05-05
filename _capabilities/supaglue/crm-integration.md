---
categories: []
consumed_apis:
- supaglue-mgmt
- supaglue-crm
description: Unified workflow capability for building CRM product integrations using Supaglue. Combines the Management API for configuring customer connections and sync settings with the Unified CRM API for reading and writing CRM data (accounts, contacts, leads, opportunities) across Salesforce, HubSpot, Pipedrive, and 15+ other providers. Used by B2B SaaS developers building native CRM integrations into their product.
layout: capability
name: Supaglue CRM Integration
operations:
- description: List all customers using integrations
  method: GET
  name: list-customers
  path: /v1/customers
- description: List provider connections for a customer
  method: GET
  name: list-connections
  path: /v1/customers/{customer_id}/connections
- description: Create OAuth magic link for customer authentication
  method: POST
  name: create-magic-link
  path: /v1/magic-links
- description: Trigger a data sync
  method: POST
  name: trigger-sync
  path: /v1/syncs/trigger
- description: List sync run history
  method: GET
  name: list-sync-runs
  path: /v1/sync-runs
- description: List CRM accounts
  method: GET
  name: list-accounts
  path: /v1/crm/accounts
- description: Create a CRM account
  method: POST
  name: create-account
  path: /v1/crm/accounts
- description: List CRM contacts
  method: GET
  name: list-contacts
  path: /v1/crm/contacts
- description: Create a CRM contact
  method: POST
  name: create-contact
  path: /v1/crm/contacts
- description: Search CRM contacts by criteria
  method: POST
  name: search-contacts
  path: /v1/crm/contacts/search
- description: List CRM leads
  method: GET
  name: list-leads
  path: /v1/crm/leads
- description: Create a CRM lead
  method: POST
  name: create-lead
  path: /v1/crm/leads
- description: List CRM opportunities
  method: GET
  name: list-opportunities
  path: /v1/crm/opportunities
- description: Create a CRM opportunity
  method: POST
  name: create-opportunity
  path: /v1/crm/opportunities
personas: []
provider_name: Supaglue
provider_slug: supaglue
search_terms:
- crm leads
- create lead
- create a new contact in the customer's crm
- generate a magic link for customer oauth authentication to a crm provider
- list connections
- crm accounts
- search crm contacts by criteria
- list crm accounts from the provider for a customer
- list customers
- crm contacts
- sync control
- list crm leads
- list all customers using integrations
- list accounts
- create contact
- create a crm lead
- list sync run history
- search for crm contacts matching filter criteria
- search contacts
- crm opportunities
- open source
- create a crm contact
- list contacts from the customer's crm
- crm contact search
- hubspot
- manage integration customers
- create account
- list crm accounts
- list provider connections for a customer
- trigger a crm data sync for a customer connection
- view crm sync run history and status
- sales engagement
- list all customers using supaglue integrations
- list crm opportunities
- list sync runs
- sync history
- customer crm connections
- list crm contacts
- create a crm opportunity
- supaglue
- list leads
- create or update a customer in the supaglue platform
- list crm provider connections for a customer
- create a new lead in the customer's crm
- create a new opportunity in the customer's crm
- integrations
- salesforce
- create oauth magic link for customer authentication
- list leads from the customer's crm
- unified api
- create opportunity
- list contacts
- crm
- upsert customer
- trigger a data sync
- create a new account in the customer's crm
- oauth authentication links
- hris
- create a crm account
- list opportunities from the customer's crm
- trigger sync
- list opportunities
- create magic link
slug: crm-integration
source_filename: crm-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Supaglue CRM Integration\"\n  description: >-\n    Unified workflow capability for building CRM product integrations using\n    Supaglue. Combines the Management API for configuring customer connections\n    and sync settings with the Unified CRM API for reading and writing CRM data\n    (accounts, contacts, leads, opportunities) across Salesforce, HubSpot,\n    Pipedrive, and 15+ other providers. Used by B2B SaaS developers building\n    native CRM integrations into their product.\n  tags:\n    - Supaglue\n    - CRM\n    - Integrations\n    - Salesforce\n    - HubSpot\n    - Unified API\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SUPAGLUE_API_KEY: SUPAGLUE_API_KEY\n\ncapability:\n  consumes:\n    - import: supaglue-mgmt\n      location: ./shared/management-api.yaml\n    - import: supaglue-crm\n      location: ./shared/crm-api.yaml\n\n  exposes:\n    - type: rest\n    \
  \  port: 8080\n      namespace: supaglue-crm-integration-api\n      description: \"Unified REST API for Supaglue CRM integration management and data access.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"Manage integration customers\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all customers using integrations\"\n              call: \"supaglue-mgmt.list-customers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/customers/{customer_id}/connections\n          name: connections\n          description: \"Customer CRM connections\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List provider connections for a customer\"\n              call: \"supaglue-mgmt.list-connections\"\n              with:\n                customer_id:\
  \ \"rest.customer_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/magic-links\n          name: magic-links\n          description: \"OAuth authentication links\"\n          operations:\n            - method: POST\n              name: create-magic-link\n              description: \"Create OAuth magic link for customer authentication\"\n              call: \"supaglue-mgmt.create-magic-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/syncs/trigger\n          name: sync-trigger\n          description: \"Sync control\"\n          operations:\n            - method: POST\n              name: trigger-sync\n              description: \"Trigger a data sync\"\n              call: \"supaglue-mgmt.trigger-sync\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sync-runs\n  \
  \        name: sync-runs\n          description: \"Sync history\"\n          operations:\n            - method: GET\n              name: list-sync-runs\n              description: \"List sync run history\"\n              call: \"supaglue-mgmt.list-sync-runs\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/crm/accounts\n          name: accounts\n          description: \"CRM accounts\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List CRM accounts\"\n              call: \"supaglue-crm.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a CRM account\"\n              call: \"supaglue-crm.create-account\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n        - path: /v1/crm/contacts\n          name: contacts\n          description: \"CRM contacts\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List CRM contacts\"\n              call: \"supaglue-crm.list-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Create a CRM contact\"\n              call: \"supaglue-crm.create-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crm/contacts/search\n          name: contact-search\n          description: \"CRM contact search\"\n          operations:\n            - method: POST\n              name: search-contacts\n              description: \"Search CRM contacts by criteria\"\n              call: \"supaglue-crm.search-contacts\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crm/leads\n          name: leads\n          description: \"CRM leads\"\n          operations:\n            - method: GET\n              name: list-leads\n              description: \"List CRM leads\"\n              call: \"supaglue-crm.list-leads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lead\n              description: \"Create a CRM lead\"\n              call: \"supaglue-crm.create-lead\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crm/opportunities\n          name: opportunities\n          description: \"CRM opportunities\"\n          operations:\n            - method: GET\n              name: list-opportunities\n              description: \"List CRM opportunities\"\n     \
  \         call: \"supaglue-crm.list-opportunities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-opportunity\n              description: \"Create a CRM opportunity\"\n              call: \"supaglue-crm.create-opportunity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: supaglue-crm-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CRM integration management and data access.\"\n      tools:\n        - name: list-customers\n          description: \"List all customers using Supaglue integrations\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-mgmt.list-customers\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: upsert-customer\n\
  \          description: \"Create or update a customer in the Supaglue platform\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-mgmt.upsert-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n            name: \"tools.name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List CRM provider connections for a customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-mgmt.list-connections\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-magic-link\n          description: \"Generate a magic link for customer OAuth authentication to a CRM provider\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n          call: \"supaglue-mgmt.create-magic-link\"\n          with:\n            customer_id: \"tools.customer_id\"\n            provider_name: \"tools.provider_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-sync\n          description: \"Trigger a CRM data sync for a customer connection\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-mgmt.trigger-sync\"\n          with:\n            customer_id: \"tools.customer_id\"\n            provider_name: \"tools.provider_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sync-runs\n          description: \"View CRM sync run history and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-mgmt.list-sync-runs\"\n          outputParameters:\n            - type:\
  \ array\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List CRM accounts from the provider for a customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-crm.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new account in the customer's CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-crm.create-account\"\n          with:\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contacts\n          description: \"List contacts from the customer's CRM\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-crm.list-contacts\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new contact in the customer's CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-crm.create-contact\"\n          with:\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-contacts\n          description: \"Search for CRM contacts matching filter criteria\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-crm.search-contacts\"\n          with:\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leads\n          description: \"List leads from the customer's CRM\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-crm.list-leads\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lead\n          description: \"Create a new lead in the customer's CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-crm.create-lead\"\n          with:\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-opportunities\n          description: \"List opportunities from the customer's CRM\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supaglue-crm.list-opportunities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-opportunity\n          description: \"Create a new opportunity in the customer's CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supaglue-crm.create-opportunity\"\
  \n          with:\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/supaglue/refs/heads/main/capabilities/crm-integration.yaml
tags:
- Supaglue
- CRM
- Integrations
- Salesforce
- HubSpot
- Unified API
tools:
- description: List all customers using Supaglue integrations
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Create or update a customer in the Supaglue platform
  hints:
    destructive: false
    readOnly: false
  name: upsert-customer
- description: List CRM provider connections for a customer
  hints:
    openWorld: false
    readOnly: true
  name: list-connections
- description: Generate a magic link for customer OAuth authentication to a CRM provider
  hints:
    destructive: false
    readOnly: false
  name: create-magic-link
- description: Trigger a CRM data sync for a customer connection
  hints:
    destructive: false
    readOnly: false
  name: trigger-sync
- description: View CRM sync run history and status
  hints:
    openWorld: false
    readOnly: true
  name: list-sync-runs
- description: List CRM accounts from the provider for a customer
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Create a new account in the customer's CRM
  hints:
    destructive: false
    readOnly: false
  name: create-account
- description: List contacts from the customer's CRM
  hints:
    openWorld: false
    readOnly: true
  name: list-contacts
- description: Create a new contact in the customer's CRM
  hints:
    destructive: false
    readOnly: false
  name: create-contact
- description: Search for CRM contacts matching filter criteria
  hints:
    openWorld: false
    readOnly: true
  name: search-contacts
- description: List leads from the customer's CRM
  hints:
    openWorld: false
    readOnly: true
  name: list-leads
- description: Create a new lead in the customer's CRM
  hints:
    destructive: false
    readOnly: false
  name: create-lead
- description: List opportunities from the customer's CRM
  hints:
    openWorld: false
    readOnly: true
  name: list-opportunities
- description: Create a new opportunity in the customer's CRM
  hints:
    destructive: false
    readOnly: false
  name: create-opportunity
---
