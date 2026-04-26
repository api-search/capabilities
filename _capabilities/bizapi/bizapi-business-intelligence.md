---
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
- firmographic data
- business intelligence
- test company search returning fake firmographic data.
- Sales Representative
- search companies test
- search for business entities and retrieve firmographic data including duns numbers, naics codes, sic codes, employee counts, sales volume, and corporate hierarchy.
- crm enrichment
- crm
- test company search that returns fake firmographic data without consuming api credits. use for development and testing.
- Data Engineer
- Marketing Analyst
- integrates bizapi into data pipelines for crm and data warehouse enrichment
- segments and scores prospects using naics, sic, and financial data
- company data
- naics
- uses firmographic data to qualify leads and enrich crm account records
- appending firmographic data to crm records for sales and marketing
- search business entities by name, address, phone, or url.
- sic
- test search returning fake data without consuming api credits.
- business intelligence and crm enrichment workflow combining company search and test endpoints
- firmographic data retrieval and company lookup
- search companies
- search for business entities and retrieve firmographic data.
- sales enablement
slug: bizapi-business-intelligence
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
