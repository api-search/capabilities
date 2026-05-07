---
categories: []
consumed_apis: []
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
- search intent
- search for contacts matching sales criteria
- intent data
- enrich a company with firmographic data
- enrich a company with firmographic data including revenue and employee count
- contact search
- get intent data for a specific company
- search zoominfo for contacts by job title, company, location, and industry
- search for recent news about target companies
- search zoominfo for companies by industry, revenue, employee count, and tech stack
- b2b
- enrich technology
- search news
- enrich company records
- search and discover companies
- sales prospecting
- enrich intent
- find companies showing buying intent signals in your category
- enrich a contact with verified data
- find companies showing buying intent
- buyer intent signals
- enrich a contact record with verified email, phone, and professional details
- enrich company
- business intelligence scoops
- b2b data
- search and discover contacts
- company search
- contacts
- search for business scoops about companies
- enrich contact records
- contact database
- search for business intelligence scoops about target companies
- zoominfo
- company data
- enrich contact
- search companies
- get org chart to identify decision makers at target company
- sales intelligence
- search contacts
- search for companies matching ideal customer profile
- get technology stack details for a target company
- data
- marketing intelligence
- search scoops
- lead generation
- enrich orgchart
slug: sales-prospecting
source_filename: sales-prospecting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ZoomInfo Sales Prospecting\n  description: Workflow for sales teams to find, qualify, and enrich prospect data. Combines contact search, company search,\n    intent signals, and enrichment for targeted outreach.\n  tags:\n  - ZoomInfo\n  - Sales Prospecting\n  - Lead Generation\n  - Contact Search\n  - Company Search\n  - Intent Data\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n    ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: zoominfo-api\n    baseUri: https://api.zoominfo.com\n    description: ZoomInfo Enterprise API for B2B data intelligence\n    authentication:\n      type: bearer\n      token: '{{ZOOMINFO_JWT_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /\n      description: Authentication operations\n      operations:\n      - name: authenticate\n        method: POST\n        path:\
  \ /authenticate\n        description: ZoomInfo Authenticate\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: contact-search\n      path: /search\n      description: Contact search operations\n      operations:\n      - name: search-contacts\n        method: POST\n        path: /search/contact\n        description: ZoomInfo Contact Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n      - name: contact-search-inputs\n        method: GET\n        path: /lookup/inputfields/contact/search\n        description:\
  \ ZoomInfo Contact Search Inputs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: contact-search-outputs\n        method: GET\n        path: /lookup/outputfields/contact/search\n        description: ZoomInfo Contact Search Outputs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-search\n      path: /search\n      description: Company search operations\n      operations:\n      - name: search-companies\n        method: POST\n        path: /search/company\n        description: ZoomInfo Company Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n\
  \            page: '{{tools.page}}'\n      - name: company-search-inputs\n        method: GET\n        path: /lookup/inputfields/company/search\n        description: ZoomInfo Company Search Inputs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: company-search-outputs\n        method: GET\n        path: /lookup/outputfields/company/search\n        description: ZoomInfo Company Search Outputs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intent-search\n      path: /search\n      description: Intent search operations\n      operations:\n      - name: search-intent\n        method: POST\n        path: /search/intent\n        description: ZoomInfo Intent Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            topicId: '{{tools.topicId}}'\n    - name: scoop-search\n      path: /search\n      description: Scoop search operations\n      operations:\n      - name: search-scoops\n        method: POST\n        path: /search/scoop\n        description: ZoomInfo Scoop Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: news-search\n      path: /search\n      description: News search operations\n      operations:\n      - name: search-news\n        method: POST\n        path: /search/news\n        description: ZoomInfo News Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: contact-enrich\n      path: /enrich\n      description: Contact enrichment operations\n      operations:\n      - name: enrich-contact\n        method: POST\n        path: /enrich/contact\n        description: ZoomInfo Contact Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.matchPersonInput}}'\n    - name: company-enrich\n      path: /enrich\n      description: Company enrichment operations\n      operations:\n      - name: enrich-company\n        method: POST\n        path: /enrich/company\n        description: ZoomInfo Company Enrich\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.matchCompanyInput}}'\n      - name: enrich-company-master\n        method: POST\n        path: /enrich/company-master\n        description: ZoomInfo Company Master Data Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.matchCompanyInput}}'\n      - name: enrich-location\n        method: POST\n        path: /enrich/location\n        description: ZoomInfo Location Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n          \
  \  matchCompanyInput: '{{tools.matchCompanyInput}}'\n    - name: org-structure\n      path: /enrich\n      description: Organizational structure operations\n      operations:\n      - name: enrich-orgchart\n        method: POST\n        path: /enrich/orgchart\n        description: ZoomInfo OrgChart Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n      - name: enrich-corporate-hierarchy\n        method: POST\n        path: /enrich/corporatehierarchy\n        description: ZoomInfo Corporate Hierarchy Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.matchCompanyInput}}'\n\
  \    - name: technology-enrich\n      path: /enrich\n      description: Technology enrichment operations\n      operations:\n      - name: enrich-technology\n        method: POST\n        path: /enrich/tech\n        description: ZoomInfo Technology Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n      - name: enrich-hashtags\n        method: POST\n        path: /enrich/hashtag\n        description: ZoomInfo Hashtags Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n    - name: intent-enrich\n      path: /enrich\n      description: Intent enrichment operations\n  \
  \    operations:\n      - name: enrich-intent\n        method: POST\n        path: /enrich/intent\n        description: ZoomInfo Intent Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n    - name: news-enrich\n      path: /enrich\n      description: News enrichment operations\n      operations:\n      - name: enrich-news\n        method: POST\n        path: /enrich/news\n        description: ZoomInfo News Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n    - name: scoop-enrich\n      path: /enrich\n      description: Scoop enrichment operations\n      operations:\n\
  \      - name: enrich-scoop\n        method: POST\n        path: /enrich/scoop\n        description: ZoomInfo Scoop Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.companyId}}'\n    - name: websights\n      path: /enrich\n      description: WebSights IP enrichment operations\n      operations:\n      - name: enrich-ip\n        method: POST\n        path: /enrich/ip\n        description: ZoomInfo IP Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ipAddress: '{{tools.ipAddress}}'\n    - name: compliance\n      path: /\n      description: Compliance operations\n      operations:\n      - name: check-compliance\n\
  \        method: POST\n        path: /compliance\n        description: ZoomInfo Compliance\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputType: '{{tools.inputType}}'\n    - name: webhooks\n      path: /webhooks\n      description: Webhook management operations\n      operations:\n      - name: get-webhooks\n        method: GET\n        path: /webhooks\n        description: ZoomInfo Get Webhooks\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        path: /webhooks\n        description: ZoomInfo Create Webhook\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data:\n            targetUrl: '{{tools.targetUrl}}'\n      - name: validate-target-url\n        method: POST\n        path: /webhooks/validate\n        description: ZoomInfo Validate Target URL\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetUrl: '{{tools.targetUrl}}'\n    - name: bulk-operations\n      path: /bulk\n      description: Bulk search and enrichment operations\n      operations:\n      - name: bulk-search-contacts\n        method: POST\n        path: /bulk/search/contact\n        description: ZoomInfo Bulk Contact Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n    \
  \        query: '{{tools.query}}'\n      - name: bulk-search-companies\n        method: POST\n        path: /bulk/search/company\n        description: ZoomInfo Bulk Company Search\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n      - name: bulk-enrich-contacts\n        method: POST\n        path: /bulk/enrich/contact\n        description: ZoomInfo Bulk Contact Enrich\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.matchPersonInput}}'\n      - name: bulk-enrich-companies\n        method: POST\n        path: /bulk/enrich/company\n        description: ZoomInfo Bulk Company Enrich\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.matchCompanyInput}}'\n      - name: bulk-job-status\n        method: POST\n        path: /bulk/job/status\n        description: ZoomInfo Bulk Job Status\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n      - name: bulk-job-results\n        method: POST\n        path: /bulk/job/results\n        description: ZoomInfo Bulk Job Results\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n\
  \    - name: lookup\n      path: /lookup\n      description: Lookup reference data operations\n      operations:\n      - name: lookup-company-ranking\n        method: GET\n        path: /lookup/companyranking\n        description: ZoomInfo Company Ranking\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-industries\n        method: GET\n        path: /lookup/industry\n        description: ZoomInfo Industry Codes\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-sic-codes\n        method: GET\n        path: /lookup/siccode\n        description: ZoomInfo SIC Codes\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-naics-codes\n\
  \        method: GET\n        path: /lookup/naicscode\n        description: ZoomInfo NAICS Codes\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-departments\n        method: GET\n        path: /lookup/department\n        description: ZoomInfo Contact Departments\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-tech-categories\n        method: GET\n        path: /lookup/tech/category\n        description: ZoomInfo Tech Categories\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-intent-topics\n        method: GET\n        path: /lookup/intent/topics\n        description: ZoomInfo Intent Topics\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-usage\n        method: GET\n        path: /lookup/usage\n        description: ZoomInfo Usage\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sales-prospecting-api\n    description: Unified REST API for sales prospecting workflows.\n    resources:\n    - path: /v1/contacts/search\n      name: contact-search\n      description: Search and discover contacts\n      operations:\n      - method: POST\n        name: search-contacts\n        description: Search for contacts matching sales criteria\n        call: zoominfo-api.search-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies/search\n      name: company-search\n \
  \     description: Search and discover companies\n      operations:\n      - method: POST\n        name: search-companies\n        description: Search for companies matching ideal customer profile\n        call: zoominfo-api.search-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/enrich\n      name: contact-enrich\n      description: Enrich contact records\n      operations:\n      - method: POST\n        name: enrich-contact\n        description: Enrich a contact with verified data\n        call: zoominfo-api.enrich-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies/enrich\n      name: company-enrich\n      description: Enrich company records\n      operations:\n      - method: POST\n        name: enrich-company\n        description: Enrich a company with firmographic data\n        call: zoominfo-api.enrich-company\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/intent\n      name: intent\n      description: Buyer intent signals\n      operations:\n      - method: POST\n        name: search-intent\n        description: Find companies showing buying intent\n        call: zoominfo-api.search-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scoops\n      name: scoops\n      description: Business intelligence scoops\n      operations:\n      - method: POST\n        name: search-scoops\n        description: Search for business scoops about companies\n        call: zoominfo-api.search-scoops\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sales-prospecting-mcp\n    transport: http\n    description: MCP server for AI-assisted sales prospecting workflows.\n    tools:\n    - name: search-contacts\n      description: Search ZoomInfo for contacts by job title, company, location, and industry\n \
  \     hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.search-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-companies\n      description: Search ZoomInfo for companies by industry, revenue, employee count, and tech stack\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.search-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-contact\n      description: Enrich a contact record with verified email, phone, and professional details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.enrich-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-company\n      description: Enrich a company with firmographic data including revenue and employee count\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.enrich-company\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-intent\n      description: Find companies showing buying intent signals in your category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.search-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-intent\n      description: Get intent data for a specific company\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.enrich-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-scoops\n      description: Search for business intelligence scoops about target companies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.search-scoops\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-technology\n      description: Get technology stack details for a target company\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: zoominfo-api.enrich-technology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-orgchart\n      description: Get org chart to identify decision makers at target company\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.enrich-orgchart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-news\n      description: Search for recent news about target companies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo-api.search-news\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
