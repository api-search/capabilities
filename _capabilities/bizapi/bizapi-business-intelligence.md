---
categories:
- analytics
consumed_apis:
- bizapi
description: Workflow capability for business intelligence and CRM data enrichment using the BizAPI. Enables sales, marketing, and data teams to search and enrich company records with firmographic data including NAICS, SIC, DUNS, employee counts, and corporate hierarchy.
layout: capability
name: BizAPI Business Intelligence
operations:
- description: Search for business entities and retrieve firmographic data.
  method: POST
  name: search-companies
  path: /v1/companies/search
- description: Test company search returning fake firmographic data.
  method: POST
  name: search-companies-test
  path: /v1/companies/search/test
personas: []
provider_name: BizAPI
provider_slug: bizapi
search_terms:
- Sales Representative
- search companies test
- test company search that returns fake firmographic data without consuming api credits. use for development and testing.
- sic
- crm
- crm enrichment
- business intelligence and crm enrichment workflow combining company search and test endpoints
- test search returning fake data without consuming api credits.
- segments and scores prospects using naics, sic, and financial data
- search business entities by name, address, phone, or url.
- integrates bizapi into data pipelines for crm and data warehouse enrichment
- naics
- business intelligence
- Marketing Analyst
- appending firmographic data to crm records for sales and marketing
- test company search returning fake firmographic data.
- company data
- firmographic data
- sales enablement
- Data Engineer
- uses firmographic data to qualify leads and enrich crm account records
- firmographic data retrieval and company lookup
- search companies
- search for business entities and retrieve firmographic data.
- search for business entities and retrieve firmographic data including duns numbers, naics codes, sic codes, employee counts, sales volume, and corporate hierarchy.
slug: bizapi-business-intelligence
source_filename: bizapi-business-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: BizAPI Business Intelligence\n  description: >-\n    Workflow capability for business intelligence and CRM data enrichment using the BizAPI.\n    Enables sales, marketing, and data teams to search and enrich company records with\n    firmographic data including NAICS, SIC, DUNS, employee counts, and corporate hierarchy.\n  tags:\n    - Business Intelligence\n    - CRM Enrichment\n    - Company Data\n    - Firmographic Data\n    - NAICS\n    - Sales Enablement\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BIZAPI_USERNAME: BIZAPI_USERNAME\n      BIZAPI_PASSWORD: BIZAPI_PASSWORD\n\ncapability:\n  consumes:\n    - import: bizapi\n      location: ./shared/bizapi.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bizapi-business-intelligence-api\n      description: Unified REST API for business intelligence and firmographic data enrichment.\n      resources:\n\
  \        - path: /v1/companies/search\n          name: company-search\n          description: Search business entities by name, address, phone, or URL.\n          operations:\n            - method: POST\n              name: search-companies\n              description: Search for business entities and retrieve firmographic data.\n              call: \"bizapi.search-companies\"\n              with:\n                company_name: \"rest.company_name\"\n                street: \"rest.street\"\n                city: \"rest.city\"\n                state: \"rest.state\"\n                zip: \"rest.zip\"\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/companies/search/test\n          name: company-search-test\n          description: Test search returning fake data without consuming API credits.\n          operations:\n            - method: POST\n              name: search-companies-test\n\
  \              description: Test company search returning fake firmographic data.\n              call: \"bizapi.search-companies-test\"\n              with:\n                company_name: \"rest.company_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: bizapi-business-intelligence-mcp\n      transport: http\n      description: MCP server for AI-assisted business intelligence and CRM enrichment workflows.\n      tools:\n        - name: search-companies\n          description: Search for business entities and retrieve firmographic data including DUNS numbers, NAICS codes, SIC codes, employee counts, sales volume, and corporate hierarchy.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bizapi.search-companies\"\n          with:\n            company_name: \"tools.company_name\"\n            street: \"tools.street\"\n            city:\
  \ \"tools.city\"\n            state: \"tools.state\"\n            zip: \"tools.zip\"\n            country: \"tools.country\"\n            phone: \"tools.phone\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-companies-test\n          description: Test company search that returns fake firmographic data without consuming API credits. Use for development and testing.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bizapi.search-companies-test\"\n          with:\n            company_name: \"tools.company_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bizapi/refs/heads/main/capabilities/bizapi-business-intelligence.yaml
tags:
- Business Intelligence
- CRM Enrichment
- Company Data
- Firmographic Data
- NAICS
- Sales Enablement
tools:
- description: Search for business entities and retrieve firmographic data including DUNS numbers, NAICS codes, SIC codes, employee counts, sales volume, and corporate hierarchy.
  hints:
    openWorld: true
    readOnly: true
  name: search-companies
- description: Test company search that returns fake firmographic data without consuming API credits. Use for development and testing.
  hints:
    openWorld: false
    readOnly: true
  name: search-companies-test
---
