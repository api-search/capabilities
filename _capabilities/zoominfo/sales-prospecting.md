---
categories: []
consumed_apis:
- zoominfo-api
description: Workflow for sales teams to find, qualify, and enrich prospect data. Combines contact search, company search, intent signals, and enrichment for targeted outreach.
layout: capability
name: ZoomInfo Sales Prospecting
operations:
- description: Search for contacts matching sales criteria
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: Search for companies matching ideal customer profile
  method: POST
  name: search-companies
  path: /v1/companies/search
- description: Enrich a contact with verified data
  method: POST
  name: enrich-contact
  path: /v1/contacts/enrich
- description: Enrich a company with firmographic data
  method: POST
  name: enrich-company
  path: /v1/companies/enrich
- description: Find companies showing buying intent
  method: POST
  name: search-intent
  path: /v1/intent
- description: Search for business scoops about companies
  method: POST
  name: search-scoops
  path: /v1/scoops
personas: []
provider_name: ZoomInfo
provider_slug: zoominfo
search_terms:
- enrich a contact record with verified email, phone, and professional details
- search and discover contacts
- enrich contact records
- intent data
- contacts
- b2b
- enrich a contact with verified data
- company search
- business intelligence scoops
- enrich company
- search zoominfo for contacts by job title, company, location, and industry
- buyer intent signals
- lead generation
- get technology stack details for a target company
- search intent
- search for contacts matching sales criteria
- search companies
- search scoops
- search for business scoops about companies
- enrich contact
- enrich a company with firmographic data including revenue and employee count
- zoominfo
- get org chart to identify decision makers at target company
- find companies showing buying intent
- contact database
- find companies showing buying intent signals in your category
- search news
- sales intelligence
- enrich a company with firmographic data
- company data
- marketing intelligence
- search for business intelligence scoops about target companies
- search contacts
- b2b data
- search for companies matching ideal customer profile
- contact search
- search for recent news about target companies
- sales prospecting
- get intent data for a specific company
- enrich intent
- data
- enrich orgchart
- search and discover companies
- search zoominfo for companies by industry, revenue, employee count, and tech stack
- enrich company records
- enrich technology
slug: sales-prospecting
source_filename: sales-prospecting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ZoomInfo Sales Prospecting\"\n  description: \"Workflow for sales teams to find, qualify, and enrich prospect data. Combines contact search, company search, intent signals, and enrichment for targeted outreach.\"\n  tags:\n    - ZoomInfo\n    - Sales Prospecting\n    - Lead Generation\n    - Contact Search\n    - Company Search\n    - Intent Data\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n      ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\n\ncapability:\n  consumes:\n    - import: zoominfo-api\n      location: ./shared/zoominfo-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sales-prospecting-api\n      description: \"Unified REST API for sales prospecting workflows.\"\n      resources:\n        - path: /v1/contacts/search\n          name: contact-search\n          description: \"Search and discover contacts\"\n\
  \          operations:\n            - method: POST\n              name: search-contacts\n              description: \"Search for contacts matching sales criteria\"\n              call: \"zoominfo-api.search-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/companies/search\n          name: company-search\n          description: \"Search and discover companies\"\n          operations:\n            - method: POST\n              name: search-companies\n              description: \"Search for companies matching ideal customer profile\"\n              call: \"zoominfo-api.search-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/enrich\n          name: contact-enrich\n          description: \"Enrich contact records\"\n          operations:\n            - method: POST\n              name: enrich-contact\n            \
  \  description: \"Enrich a contact with verified data\"\n              call: \"zoominfo-api.enrich-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/companies/enrich\n          name: company-enrich\n          description: \"Enrich company records\"\n          operations:\n            - method: POST\n              name: enrich-company\n              description: \"Enrich a company with firmographic data\"\n              call: \"zoominfo-api.enrich-company\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/intent\n          name: intent\n          description: \"Buyer intent signals\"\n          operations:\n            - method: POST\n              name: search-intent\n              description: \"Find companies showing buying intent\"\n              call: \"zoominfo-api.search-intent\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scoops\n          name: scoops\n          description: \"Business intelligence scoops\"\n          operations:\n            - method: POST\n              name: search-scoops\n              description: \"Search for business scoops about companies\"\n              call: \"zoominfo-api.search-scoops\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sales-prospecting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sales prospecting workflows.\"\n      tools:\n        - name: search-contacts\n          description: \"Search ZoomInfo for contacts by job title, company, location, and industry\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.search-contacts\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n\n        - name: search-companies\n          description: \"Search ZoomInfo for companies by industry, revenue, employee count, and tech stack\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.search-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-contact\n          description: \"Enrich a contact record with verified email, phone, and professional details\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.enrich-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-company\n          description: \"Enrich a company with firmographic data including revenue and employee count\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.enrich-company\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-intent\n          description: \"Find companies showing buying intent signals in your category\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.search-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-intent\n          description: \"Get intent data for a specific company\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.enrich-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-scoops\n          description: \"Search for business intelligence scoops about target companies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.search-scoops\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-technology\n          description: \"Get technology stack details for a target company\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.enrich-technology\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-orgchart\n          description: \"Get org chart to identify decision makers at target company\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.enrich-orgchart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-news\n          description: \"Search for recent news about target companies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo-api.search-news\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/capabilities/sales-prospecting.yaml
tags:
- ZoomInfo
- Sales Prospecting
- Lead Generation
- Contact Search
- Company Search
- Intent Data
tools:
- description: Search ZoomInfo for contacts by job title, company, location, and industry
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: Search ZoomInfo for companies by industry, revenue, employee count, and tech stack
  hints:
    openWorld: true
    readOnly: true
  name: search-companies
- description: Enrich a contact record with verified email, phone, and professional details
  hints:
    openWorld: true
    readOnly: true
  name: enrich-contact
- description: Enrich a company with firmographic data including revenue and employee count
  hints:
    openWorld: true
    readOnly: true
  name: enrich-company
- description: Find companies showing buying intent signals in your category
  hints:
    openWorld: true
    readOnly: true
  name: search-intent
- description: Get intent data for a specific company
  hints:
    openWorld: true
    readOnly: true
  name: enrich-intent
- description: Search for business intelligence scoops about target companies
  hints:
    openWorld: true
    readOnly: true
  name: search-scoops
- description: Get technology stack details for a target company
  hints:
    openWorld: true
    readOnly: true
  name: enrich-technology
- description: Get org chart to identify decision makers at target company
  hints:
    openWorld: true
    readOnly: true
  name: enrich-orgchart
- description: Search for recent news about target companies
  hints:
    openWorld: true
    readOnly: true
  name: search-news
---
