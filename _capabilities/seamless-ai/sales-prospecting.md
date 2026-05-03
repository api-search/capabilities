---
categories: []
consumed_apis:
- seamless-contacts
- seamless-companies
description: Unified sales prospecting capability combining Seamless.AI contact and company APIs for end-to-end B2B prospecting workflows. Enables sales teams to search and discover target contacts, enrich CRM records, research company firmographics, and track job-change signals for warm outreach opportunities.
layout: capability
name: Seamless.AI Sales Prospecting
operations:
- description: Search contacts by name, company, title, and location
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: Enrich contact with emails and phone numbers
  method: POST
  name: enrich-contact
  path: /v1/contacts/enrich
- description: List contacts with recent job changes
  method: GET
  name: list-job-changes
  path: /v1/contacts/job-changes
- description: Search companies by name, domain, or industry
  method: POST
  name: search-companies
  path: /v1/companies/search
- description: Enrich company with revenue, employees, and tech stack
  method: POST
  name: enrich-company
  path: /v1/companies/enrich
personas: []
provider_name: Seamless.AI
provider_slug: seamless-ai
search_terms:
- sales intelligence
- enrich contact with emails and phone numbers
- search companies
- research contact
- enrich company records with firmographic data
- search contacts by name, company, title, and location
- search for b2b contacts by name, company, title, or location to build prospect lists
- enrich an existing company record with verified firmographic data
- search for target companies by name, domain, industry, size, or location
- research company
- get full company profile with firmographics, revenue, employee count, and technology stack
- get full contact profile with verified emails, direct dials, and job history
- enrich an existing contact in your crm with missing emails, phones, and titles
- crm enrichment
- search for companies
- b2b
- search companies by name, domain, or industry
- lead generation
- enrich contact records with verified data
- list job changes
- search for b2b contacts
- enrich contact
- enrich company with revenue, employees, and tech stack
- enrich company
- list contacts with recent job changes
- job change intelligence for warm outreach
- prospecting
- search contacts
- identify warm prospects who have recently changed jobs for timely outreach
- contact data
slug: sales-prospecting
source_filename: sales-prospecting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Seamless.AI Sales Prospecting\"\n  description: >-\n    Unified sales prospecting capability combining Seamless.AI contact and company APIs\n    for end-to-end B2B prospecting workflows. Enables sales teams to search and discover\n    target contacts, enrich CRM records, research company firmographics, and track\n    job-change signals for warm outreach opportunities.\n  tags:\n    - Sales Intelligence\n    - B2B\n    - Prospecting\n    - CRM Enrichment\n    - Lead Generation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEAMLESS_AI_API_KEY: SEAMLESS_AI_API_KEY\n\ncapability:\n  consumes:\n    - import: seamless-contacts\n      location: ./shared/contacts.yaml\n    - import: seamless-companies\n      location: ./shared/companies.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sales-prospecting-api\n      description: \"Unified REST API for B2B sales\
  \ prospecting with Seamless.AI.\"\n      resources:\n        - path: /v1/contacts/search\n          name: contact-search\n          description: \"Search for B2B contacts\"\n          operations:\n            - method: POST\n              name: search-contacts\n              description: \"Search contacts by name, company, title, and location\"\n              call: \"seamless-contacts.search-contacts\"\n              with:\n                name: \"rest.name\"\n                company: \"rest.company\"\n                title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/enrich\n          name: contact-enrichment\n          description: \"Enrich contact records with verified data\"\n          operations:\n            - method: POST\n              name: enrich-contact\n              description: \"Enrich contact with emails and phone numbers\"\n              call: \"seamless-contacts.enrich-contact\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/job-changes\n          name: job-changes\n          description: \"Job change intelligence for warm outreach\"\n          operations:\n            - method: GET\n              name: list-job-changes\n              description: \"List contacts with recent job changes\"\n              call: \"seamless-contacts.list-job-changes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/companies/search\n          name: company-search\n          description: \"Search for companies\"\n          operations:\n            - method: POST\n              name: search-companies\n              description: \"Search companies by name, domain, or industry\"\n              call: \"seamless-companies.search-companies\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/companies/enrich\n          name: company-enrichment\n          description: \"Enrich company records with firmographic data\"\n          operations:\n            - method: POST\n              name: enrich-company\n              description: \"Enrich company with revenue, employees, and tech stack\"\n              call: \"seamless-companies.enrich-company\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sales-prospecting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted B2B sales prospecting with Seamless.AI.\"\n      tools:\n        - name: search-contacts\n          description: \"Search for B2B contacts by name, company, title, or location to build prospect lists\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-contacts.search-contacts\"\n          with:\n        \
  \    name: \"tools.name\"\n            company: \"tools.company\"\n            title: \"tools.title\"\n            location: \"tools.location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: research-contact\n          description: \"Get full contact profile with verified emails, direct dials, and job history\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-contacts.research-contact\"\n          with:\n            searchResultId: \"tools.searchResultId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-contact\n          description: \"Enrich an existing contact in your CRM with missing emails, phones, and titles\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-contacts.enrich-contact\"\n          with:\n            email: \"tools.email\"\n            name:\
  \ \"tools.name\"\n            company: \"tools.company\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-job-changes\n          description: \"Identify warm prospects who have recently changed jobs for timely outreach\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seamless-contacts.list-job-changes\"\n          with:\n            days: \"tools.days\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-companies\n          description: \"Search for target companies by name, domain, industry, size, or location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-companies.search-companies\"\n          with:\n            name: \"tools.name\"\n            domain: \"tools.domain\"\n            industry: \"tools.industry\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: research-company\n          description: \"Get full company profile with firmographics, revenue, employee count, and technology stack\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-companies.research-company\"\n          with:\n            searchResultId: \"tools.searchResultId\"\n            domain: \"tools.domain\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enrich-company\n          description: \"Enrich an existing company record with verified firmographic data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seamless-companies.enrich-company\"\n          with:\n            domain: \"tools.domain\"\n            companyName: \"tools.companyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/seamless-ai/refs/heads/main/capabilities/sales-prospecting.yaml
tags:
- Sales Intelligence
- B2B
- Prospecting
- CRM Enrichment
- Lead Generation
tools:
- description: Search for B2B contacts by name, company, title, or location to build prospect lists
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: Get full contact profile with verified emails, direct dials, and job history
  hints:
    openWorld: true
    readOnly: true
  name: research-contact
- description: Enrich an existing contact in your CRM with missing emails, phones, and titles
  hints:
    openWorld: true
    readOnly: true
  name: enrich-contact
- description: Identify warm prospects who have recently changed jobs for timely outreach
  hints:
    openWorld: false
    readOnly: true
  name: list-job-changes
- description: Search for target companies by name, domain, industry, size, or location
  hints:
    openWorld: true
    readOnly: true
  name: search-companies
- description: Get full company profile with firmographics, revenue, employee count, and technology stack
  hints:
    openWorld: true
    readOnly: true
  name: research-company
- description: Enrich an existing company record with verified firmographic data
  hints:
    openWorld: true
    readOnly: true
  name: enrich-company
---
