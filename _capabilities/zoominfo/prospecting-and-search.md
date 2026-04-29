---
categories: []
consumed_apis:
- zoominfo
description: Unified capability for B2B prospecting workflows combining contact search, company search, intent signals, news, and scoops. Used by sales development reps and account executives to identify and prioritize target accounts and contacts.
layout: capability
name: ZoomInfo Prospecting And Search
operations:
- description: Search ZoomInfo contacts by criteria such as job title, company, location, and more.
  method: POST
  name: search-contacts
  path: /v1/contacts
- description: Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.
  method: POST
  name: search-companies
  path: /v1/companies
- description: Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.
  method: POST
  name: search-scoops
  path: /v1/scoops
- description: Search ZoomInfo news for recent company events and announcements.
  method: POST
  name: search-news
  path: /v1/news
- description: Search ZoomInfo intent data to identify companies actively researching topics.
  method: POST
  name: search-intent
  path: /v1/intent
- description: Get available industry code lookup values.
  method: GET
  name: get-industries
  path: /v1/lookups/industries
- description: Get available department lookup values.
  method: GET
  name: get-departments
  path: /v1/lookups/departments
- description: Get available job function lookup values.
  method: GET
  name: get-job-functions
  path: /v1/lookups/job-functions
- description: Get available management level lookup values.
  method: GET
  name: get-management-levels
  path: /v1/lookups/management-levels
- description: Get available revenue range lookup values.
  method: GET
  name: get-revenue-ranges
  path: /v1/lookups/revenue-ranges
- description: Get available intent topic lookup values.
  method: GET
  name: get-intent-topics
  path: /v1/lookups/intent-topics
personas: []
provider_name: ZoomInfo
provider_slug: zoominfo
search_terms:
- search for buying signals and scoops.
- get available job function lookup values.
- reference data for management levels.
- get job functions
- search for buyer intent signals.
- reference data for industry codes.
- search for contacts matching prospecting criteria.
- marketing intelligence
- search intent
- zoominfo
- company data
- search zoominfo intent data to identify companies actively researching topics.
- get available department lookup values.
- get management levels
- contact database
- search zoominfo news for recent company events and announcements.
- lead generation
- get available revenue range lookup values.
- reference data for job functions.
- search zoominfo companies by criteria such as industry, revenue, employee count, and more.
- get revenue ranges
- b2b
- get available industry code lookup values.
- search for company news articles.
- get available intent topic lookup values.
- get departments
- search zoominfo contacts by criteria such as job title, company, location, and more.
- contacts
- search for companies matching prospecting criteria.
- get available department lookup values for filtering contact searches.
- search scoops
- get available job function lookup values for filtering contact searches.
- b2b data
- get available management level lookup values.
- data
- get intent topics
- reference data for contact departments.
- get industries
- reference data for intent topics.
- search news
- search zoominfo scoops for buying signals like funding, expansion, and leadership changes.
- search companies
- reference data for revenue ranges.
- prospecting
- get available industry code lookup values for filtering searches.
- sales intelligence
- search contacts
slug: prospecting-and-search
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ZoomInfo Prospecting And Search\"\n  description: \"Unified capability for B2B prospecting workflows combining contact search, company search, intent signals, news, and scoops. Used by sales development reps and account executives to identify and prioritize target accounts and contacts.\"\n  tags:\n    - ZoomInfo\n    - Prospecting\n    - Sales Intelligence\n    - B2B Data\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n      ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\n\ncapability:\n  consumes:\n    - import: zoominfo\n      location: ./shared/zoominfo.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: prospecting-and-search-api\n      description: \"Unified REST API for B2B prospecting and search workflows.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"Search for\
  \ contacts matching prospecting criteria.\"\n          operations:\n            - method: POST\n              name: search-contacts\n              description: \"Search ZoomInfo contacts by criteria such as job title, company, location, and more.\"\n              call: \"zoominfo.search-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/companies\n          name: companies\n          description: \"Search for companies matching prospecting criteria.\"\n          operations:\n            - method: POST\n              name: search-companies\n              description: \"Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.\"\n              call: \"zoominfo.search-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scoops\n          name: scoops\n          description: \"Search for buying signals\
  \ and scoops.\"\n          operations:\n            - method: POST\n              name: search-scoops\n              description: \"Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.\"\n              call: \"zoominfo.search-scoops\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/news\n          name: news\n          description: \"Search for company news articles.\"\n          operations:\n            - method: POST\n              name: search-news\n              description: \"Search ZoomInfo news for recent company events and announcements.\"\n              call: \"zoominfo.search-news\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/intent\n          name: intent\n          description: \"Search for buyer intent signals.\"\n          operations:\n            - method: POST\n              name: search-intent\n\
  \              description: \"Search ZoomInfo intent data to identify companies actively researching topics.\"\n              call: \"zoominfo.search-intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/industries\n          name: lookup-industries\n          description: \"Reference data for industry codes.\"\n          operations:\n            - method: GET\n              name: get-industries\n              description: \"Get available industry code lookup values.\"\n              call: \"zoominfo.lookup-industry\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/departments\n          name: lookup-departments\n          description: \"Reference data for contact departments.\"\n          operations:\n            - method: GET\n              name: get-departments\n              description: \"Get available department lookup\
  \ values.\"\n              call: \"zoominfo.lookup-department\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/job-functions\n          name: lookup-job-functions\n          description: \"Reference data for job functions.\"\n          operations:\n            - method: GET\n              name: get-job-functions\n              description: \"Get available job function lookup values.\"\n              call: \"zoominfo.lookup-job-function\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/management-levels\n          name: lookup-management-levels\n          description: \"Reference data for management levels.\"\n          operations:\n            - method: GET\n              name: get-management-levels\n              description: \"Get available management level lookup values.\"\n              call: \"zoominfo.lookup-management-levels\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/revenue-ranges\n          name: lookup-revenue-ranges\n          description: \"Reference data for revenue ranges.\"\n          operations:\n            - method: GET\n              name: get-revenue-ranges\n              description: \"Get available revenue range lookup values.\"\n              call: \"zoominfo.lookup-revenue-range\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lookups/intent-topics\n          name: lookup-intent-topics\n          description: \"Reference data for intent topics.\"\n          operations:\n            - method: GET\n              name: get-intent-topics\n              description: \"Get available intent topic lookup values.\"\n              call: \"zoominfo.lookup-intent-topics\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: prospecting-and-search-mcp\n      transport: http\n      description: \"MCP server for AI-assisted B2B prospecting and search.\"\n      tools:\n        - name: search-contacts\n          description: \"Search ZoomInfo contacts by criteria such as job title, company, location, and more.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.search-contacts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-companies\n          description: \"Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.search-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-scoops\n          description:\
  \ \"Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.search-scoops\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-news\n          description: \"Search ZoomInfo news for recent company events and announcements.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.search-news\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-intent\n          description: \"Search ZoomInfo intent data to identify companies actively researching topics.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.search-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-industries\n\
  \          description: \"Get available industry code lookup values for filtering searches.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-industry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-departments\n          description: \"Get available department lookup values for filtering contact searches.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-department\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-functions\n          description: \"Get available job function lookup values for filtering contact searches.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-job-function\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: get-management-levels\n          description: \"Get available management level lookup values.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-management-levels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-revenue-ranges\n          description: \"Get available revenue range lookup values.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-revenue-range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-intent-topics\n          description: \"Get available intent topic lookup values.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-intent-topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/capabilities/prospecting-and-search.yaml
tags:
- ZoomInfo
- Prospecting
- Sales Intelligence
- B2B Data
tools:
- description: Search ZoomInfo contacts by criteria such as job title, company, location, and more.
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.
  hints:
    openWorld: true
    readOnly: true
  name: search-companies
- description: Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.
  hints:
    openWorld: true
    readOnly: true
  name: search-scoops
- description: Search ZoomInfo news for recent company events and announcements.
  hints:
    openWorld: true
    readOnly: true
  name: search-news
- description: Search ZoomInfo intent data to identify companies actively researching topics.
  hints:
    openWorld: true
    readOnly: true
  name: search-intent
- description: Get available industry code lookup values for filtering searches.
  hints:
    idempotent: true
    readOnly: true
  name: get-industries
- description: Get available department lookup values for filtering contact searches.
  hints:
    idempotent: true
    readOnly: true
  name: get-departments
- description: Get available job function lookup values for filtering contact searches.
  hints:
    idempotent: true
    readOnly: true
  name: get-job-functions
- description: Get available management level lookup values.
  hints:
    idempotent: true
    readOnly: true
  name: get-management-levels
- description: Get available revenue range lookup values.
  hints:
    idempotent: true
    readOnly: true
  name: get-revenue-ranges
- description: Get available intent topic lookup values.
  hints:
    idempotent: true
    readOnly: true
  name: get-intent-topics
---
