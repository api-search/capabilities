---
categories: []
consumed_apis: []
description: ''
layout: capability
name: African Development Grants
operations: []
personas: []
provider_name: US African Development Foundation
provider_slug: us-african-development-foundation
search_terms:
- researchers and analysts studying usadf grant patterns and development impact
- grants
- african enterprises and ngos seeking usadf funding
- nonprofit
- international development
- economic development
- federal government
- research and tracking workflow for usadf grant awards, recipient organizations, and open funding opportunities for african grassroots enterprises
- journalists and oversight staff monitoring usadf spending
- africa
slug: african-development-grants
source_filename: african-development-grants.yaml
source_heading: Capability Spec
source_yaml: "name: USADF African Development Grants\ndescription: >-\n  Workflow capability for researching, tracking, and analyzing US African\n  Development Foundation (USADF) grant awards and opportunities. Combines\n  grant award data from USASpending with grant opportunity listings from\n  Grants.gov to support development finance research, transparency reporting,\n  and grant opportunity discovery.\nversion: '1.0.0'\nmcp:\n  port: 9080\nrest:\n  port: 8080\npersonas:\n  - name: Development Finance Researcher\n    description: >-\n      Researchers and analysts tracking USADF grant spending, recipient patterns,\n      and program impact across African countries\n  - name: Grant Applicant\n    description: >-\n      African enterprises, cooperatives, and NGOs seeking USADF funding\n      opportunities and eligibility information\n  - name: Transparency Analyst\n    description: >-\n      Journalists, oversight staff, and policy analysts monitoring federal\n      grant award data through\
  \ USASpending transparency tools\ntools:\n  - name: search_usadf_awards\n    description: Search USADF grant awards in the federal awards transparency database\n    operationId: searchAwards\n    api: grants-api\n    parameters:\n      - name: filters\n        description: Award search filters including time period and award type\n      - name: fields\n        description: Fields to include in search results\n      - name: limit\n        description: Number of results per page\n  - name: get_award_details\n    description: Get full details for a specific USADF grant award\n    operationId: getAward\n    api: grants-api\n    parameters:\n      - name: award_id\n        description: USASpending award identifier\n  - name: get_agency_summary\n    description: Get USADF agency award summary for a fiscal year\n    operationId: getAgencyAwards\n    api: grants-api\n    parameters:\n      - name: fiscal_year\n        description: Fiscal year (e.g. 2023)\n  - name: get_recipient_profile\n    description:\
  \ Get profile and award history for a USADF grant recipient\n    operationId: getRecipient\n    api: grants-api\n    parameters:\n      - name: uei\n        description: Unique Entity Identifier of the recipient organization\n  - name: get_spending_by_country\n    description: Get USADF grant spending breakdown by African country\n    operationId: getSpendingByCountry\n    api: grants-api\n    parameters:\n      - name: filters\n        description: Search filters to apply to the geographic breakdown\n      - name: scope\n        description: Geographic scope (recipient_location or place_of_performance)\n  - name: search_grant_opportunities\n    description: Search for open USADF grant opportunities on Grants.gov\n    operationId: searchOpportunities\n    api: grant-opportunities-api\n    parameters:\n      - name: oppStatus\n        description: Opportunity status (posted, closed, archived, forecasted)\n      - name: keyword\n        description: Keyword to search in opportunity title\
  \ and description\n  - name: get_opportunity_details\n    description: Get full details for a specific USADF grant opportunity\n    operationId: getOpportunity\n    api: grant-opportunities-api\n    parameters:\n      - name: opportunityId\n        description: Grants.gov opportunity identifier\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-african-development-foundation/refs/heads/main/capabilities/african-development-grants.yaml
tags: []
tools: []
---
