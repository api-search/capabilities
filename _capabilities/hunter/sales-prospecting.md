---
categories: []
consumed_apis:
- hunter
description: Unified workflow for sales prospecting including email discovery, verification, enrichment, lead management, and outreach campaigns. Used by sales development representatives and marketing teams.
layout: capability
name: Hunter Sales Prospecting
operations:
- description: Search for emails by domain.
  method: GET
  name: domain-search
  path: /v1/domain-search
- description: Find email for a person.
  method: GET
  name: find-email
  path: /v1/email-finder
- description: Verify email deliverability.
  method: GET
  name: verify-email
  path: /v1/email-verifier
- description: List all leads.
  method: GET
  name: list-leads
  path: /v1/leads
- description: Create a lead.
  method: POST
  name: create-lead
  path: /v1/leads
- description: Get lead details.
  method: GET
  name: get-lead
  path: /v1/leads/{id}
- description: Update a lead.
  method: PUT
  name: update-lead
  path: /v1/leads/{id}
- description: Delete a lead.
  method: DELETE
  name: delete-lead
  path: /v1/leads/{id}
- description: Enrich personal data from email.
  method: GET
  name: enrich-email
  path: /v1/enrichment/email
- description: Enrich company data from domain.
  method: GET
  name: enrich-company
  path: /v1/enrichment/company
- description: Discover companies.
  method: GET
  name: discover-companies
  path: /v1/discover
personas: []
provider_name: Hunter
provider_slug: hunter
search_terms:
- lead generation
- verify email deliverability.
- search for emails by domain.
- find email
- update leads list
- find email for a person.
- create a lead.
- list all leads.
- enrich personal data from email.
- discover companies.
- discover companies matching criteria.
- delete a lead.
- get leads list
- create a new lead.
- list campaigns
- hunter
- lead management.
- enrich company
- get lead list details.
- delete a lead list.
- create leads list
- discover companies
- find the most likely email for a person at a company.
- count emails for a domain.
- prospecting
- search for email addresses by domain.
- enrich combined
- enrich email
- get lead details.
- sales prospecting
- create lead
- get combined person and company data.
- delete lead
- list all email campaigns.
- company enrichment.
- verify email
- sales intelligence
- individual lead management.
- verify emails.
- find email addresses.
- delete leads list
- email outreach
- list leads
- get lead
- get account information and usage.
- update a lead list.
- enrich company data from domain.
- enrich personal data from email address.
- search emails by domain.
- update a lead.
- get account
- email
- list all lead lists.
- update lead
- email enrichment.
- create a new lead list.
- count emails
- email verification
- domain search
- list leads lists
- contact discovery
- company discovery.
slug: sales-prospecting
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Hunter Sales Prospecting\"\n  description: \"Unified workflow for sales prospecting including email discovery, verification, enrichment, lead management, and outreach campaigns. Used by sales development representatives and marketing teams.\"\n  tags:\n    - Hunter\n    - Sales Prospecting\n    - Lead Generation\n    - Email Outreach\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUNTER_API_KEY: HUNTER_API_KEY\n\ncapability:\n  consumes:\n    - import: hunter\n      location: ./shared/hunter-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hunter-prospecting-api\n      description: \"Unified REST API for Hunter sales prospecting workflows.\"\n      resources:\n        - path: /v1/domain-search\n          name: domain-search\n          description: \"Search emails by domain.\"\n          operations:\n            - method: GET\n              name:\
  \ domain-search\n              description: \"Search for emails by domain.\"\n              call: \"hunter.domain-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/email-finder\n          name: email-finder\n          description: \"Find email addresses.\"\n          operations:\n            - method: GET\n              name: find-email\n              description: \"Find email for a person.\"\n              call: \"hunter.find-email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/email-verifier\n          name: email-verifier\n          description: \"Verify emails.\"\n          operations:\n            - method: GET\n              name: verify-email\n              description: \"Verify email deliverability.\"\n              call: \"hunter.verify-email\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n        - path: /v1/leads\n          name: leads\n          description: \"Lead management.\"\n          operations:\n            - method: GET\n              name: list-leads\n              description: \"List all leads.\"\n              call: \"hunter.list-leads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lead\n              description: \"Create a lead.\"\n              call: \"hunter.create-lead\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leads/{id}\n          name: lead-details\n          description: \"Individual lead management.\"\n          operations:\n            - method: GET\n              name: get-lead\n              description: \"Get lead details.\"\n              call: \"hunter.get-lead\"\n              with:\n                id: \"rest.id\"\n             \
  \ outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-lead\n              description: \"Update a lead.\"\n              call: \"hunter.update-lead\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-lead\n              description: \"Delete a lead.\"\n              call: \"hunter.delete-lead\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/enrichment/email\n          name: email-enrichment\n          description: \"Email enrichment.\"\n          operations:\n            - method: GET\n              name: enrich-email\n              description: \"Enrich personal data from email.\"\n              call: \"hunter.enrich-email\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/enrichment/company\n          name: company-enrichment\n          description: \"Company enrichment.\"\n          operations:\n            - method: GET\n              name: enrich-company\n              description: \"Enrich company data from domain.\"\n              call: \"hunter.enrich-company\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/discover\n          name: discover\n          description: \"Company discovery.\"\n          operations:\n            - method: GET\n              name: discover-companies\n              description: \"Discover companies.\"\n              call: \"hunter.discover-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: hunter-prospecting-mcp\n \
  \     transport: http\n      description: \"MCP server for AI-assisted Hunter sales prospecting.\"\n      tools:\n        - name: domain-search\n          description: \"Search for email addresses by domain.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hunter.domain-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-email\n          description: \"Find the most likely email for a person at a company.\"\n          hints:\n            readOnly: true\n          call: \"hunter.find-email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-email\n          description: \"Verify email deliverability.\"\n          hints:\n            readOnly: true\n          call: \"hunter.verify-email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: count-emails\n        \
  \  description: \"Count emails for a domain.\"\n          hints:\n            readOnly: true\n          call: \"hunter.count-emails\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Get account information and usage.\"\n          hints:\n            readOnly: true\n          call: \"hunter.get-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leads\n          description: \"List all leads.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hunter.list-leads\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lead\n          description: \"Create a new lead.\"\n          hints:\n            readOnly: false\n          call: \"hunter.create-lead\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-lead\n          description: \"Get lead details.\"\n          hints:\n            readOnly: true\n          call: \"hunter.get-lead\"\n          with:\n            id: \"tools.leadId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-lead\n          description: \"Update a lead.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"hunter.update-lead\"\n          with:\n            id: \"tools.leadId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-lead\n          description: \"Delete a lead.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"hunter.delete-lead\"\n          with:\n            id: \"tools.leadId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leads-lists\n   \
  \       description: \"List all lead lists.\"\n          hints:\n            readOnly: true\n          call: \"hunter.list-leads-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-leads-list\n          description: \"Create a new lead list.\"\n          hints:\n            readOnly: false\n          call: \"hunter.create-leads-list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-leads-list\n          description: \"Get lead list details.\"\n          hints:\n            readOnly: true\n          call: \"hunter.get-leads-list\"\n          with:\n            id: \"tools.listId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-leads-list\n          description: \"Update a lead list.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"hunter.update-leads-list\"\
  \n          with:\n            id: \"tools.listId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-leads-list\n          description: \"Delete a lead list.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"hunter.delete-leads-list\"\n          with:\n            id: \"tools.listId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-companies\n          description: \"Discover companies matching criteria.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hunter.discover-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-email\n          description: \"Enrich personal data from email address.\"\n          hints:\n            readOnly: true\n          call: \"hunter.enrich-email\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: enrich-company\n          description: \"Enrich company data from domain.\"\n          hints:\n            readOnly: true\n          call: \"hunter.enrich-company\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-combined\n          description: \"Get combined person and company data.\"\n          hints:\n            readOnly: true\n          call: \"hunter.enrich-combined\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-campaigns\n          description: \"List all email campaigns.\"\n          hints:\n            readOnly: true\n          call: \"hunter.list-campaigns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hunter/refs/heads/main/capabilities/sales-prospecting.yaml
tags:
- Hunter
- Sales Prospecting
- Lead Generation
- Email Outreach
tools:
- description: Search for email addresses by domain.
  hints:
    openWorld: true
    readOnly: true
  name: domain-search
- description: Find the most likely email for a person at a company.
  hints:
    readOnly: true
  name: find-email
- description: Verify email deliverability.
  hints:
    readOnly: true
  name: verify-email
- description: Count emails for a domain.
  hints:
    readOnly: true
  name: count-emails
- description: Get account information and usage.
  hints:
    readOnly: true
  name: get-account
- description: List all leads.
  hints:
    openWorld: true
    readOnly: true
  name: list-leads
- description: Create a new lead.
  hints:
    readOnly: false
  name: create-lead
- description: Get lead details.
  hints:
    readOnly: true
  name: get-lead
- description: Update a lead.
  hints:
    idempotent: true
    readOnly: false
  name: update-lead
- description: Delete a lead.
  hints:
    destructive: true
    idempotent: true
  name: delete-lead
- description: List all lead lists.
  hints:
    readOnly: true
  name: list-leads-lists
- description: Create a new lead list.
  hints:
    readOnly: false
  name: create-leads-list
- description: Get lead list details.
  hints:
    readOnly: true
  name: get-leads-list
- description: Update a lead list.
  hints:
    idempotent: true
    readOnly: false
  name: update-leads-list
- description: Delete a lead list.
  hints:
    destructive: true
    idempotent: true
  name: delete-leads-list
- description: Discover companies matching criteria.
  hints:
    openWorld: true
    readOnly: true
  name: discover-companies
- description: Enrich personal data from email address.
  hints:
    readOnly: true
  name: enrich-email
- description: Enrich company data from domain.
  hints:
    readOnly: true
  name: enrich-company
- description: Get combined person and company data.
  hints:
    readOnly: true
  name: enrich-combined
- description: List all email campaigns.
  hints:
    readOnly: true
  name: list-campaigns
---
