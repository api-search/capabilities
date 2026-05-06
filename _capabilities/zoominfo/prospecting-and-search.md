---
categories: []
consumed_apis: []
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
- company data
- reference data for management levels.
- get job functions
- search contacts
- get available industry code lookup values.
- search companies
- get available intent topic lookup values.
- search for buyer intent signals.
- get available revenue range lookup values.
- contacts
- get departments
- reference data for revenue ranges.
- search for company news articles.
- search zoominfo companies by criteria such as industry, revenue, employee count, and more.
- search intent
- search news
- search for buying signals and scoops.
- search zoominfo contacts by criteria such as job title, company, location, and more.
- get management levels
- get available management level lookup values.
- b2b
- reference data for intent topics.
- zoominfo
- get industries
- search zoominfo intent data to identify companies actively researching topics.
- reference data for industry codes.
- contact database
- prospecting
- get available department lookup values.
- get available industry code lookup values for filtering searches.
- sales intelligence
- get available department lookup values for filtering contact searches.
- b2b data
- get available job function lookup values for filtering contact searches.
- search for contacts matching prospecting criteria.
- search for companies matching prospecting criteria.
- get revenue ranges
- reference data for contact departments.
- lead generation
- data
- get intent topics
- reference data for job functions.
- search zoominfo scoops for buying signals like funding, expansion, and leadership changes.
- marketing intelligence
- search zoominfo news for recent company events and announcements.
- search scoops
- get available job function lookup values.
slug: prospecting-and-search
source_filename: prospecting-and-search.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ZoomInfo Prospecting And Search\n  description: Unified capability for B2B prospecting workflows combining contact search, company search, intent signals,\n    news, and scoops. Used by sales development reps and account executives to identify and prioritize target accounts and\n    contacts.\n  tags:\n  - ZoomInfo\n  - Prospecting\n  - Sales Intelligence\n  - B2B Data\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n    ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: zoominfo\n    baseUri: https://api.zoominfo.com\n    description: ZoomInfo B2B intelligence API for contact, company, intent, news, scoop, and technographic data.\n    authentication:\n      type: bearer\n      token: '{{ZOOMINFO_JWT_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /\n      description: Authentication operations for\
  \ obtaining JWT tokens.\n      operations:\n      - name: authenticate\n        method: POST\n        path: /authenticate\n        description: Return a valid JWT access token by inputting your ZoomInfo username and password.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: contact-search\n      path: /search\n      description: Search and lookup operations for ZoomInfo contacts.\n      operations:\n      - name: search-contacts\n        method: POST\n        path: /contact\n        description: Returns a list of contacts from ZoomInfo's data that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n      - name: get-contact-search-inputs\n        method: GET\n        path: /contact\n        description: Returns the available input fields for contact search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contact-search-outputs\n        method: GET\n        path: /contact\n        description: Returns the available output fields for contact search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-search\n      path: /search\n      description: Search and lookup operations for ZoomInfo companies.\n      operations:\n      - name: search-companies\n        method: POST\n        path: /company\n        description:\
  \ Returns a list of companies from ZoomInfo's data that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n      - name: get-company-search-inputs\n        method: GET\n        path: /company\n        description: Returns the available input fields for company search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-company-search-outputs\n        method: GET\n        path: /company\n        description: Returns the available output fields for company search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: scoop-search\n      path: /search\n      description: Search operations for ZoomInfo scoops (buying signals).\n      operations:\n      - name: search-scoops\n        method: POST\n        path: /scoop\n        description: Returns a list of scoops that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: news-search\n      path: /search\n      description: Search operations for ZoomInfo news.\n      operations:\n      - name: search-news\n        method: POST\n        path: /news\n        description: Returns a list of news articles that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: intent-search\n      path: /search\n      description: Search operations for ZoomInfo intent signals.\n      operations:\n      - name: search-intent\n        method: POST\n        path: /intent\n        description: Returns intent signal data that meets the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: contact-enrich\n      path: /enrich\n      description: Contact enrichment operations.\n      operations:\n      - name: enrich-contact\n        method: POST\n        path: /contact\n        description: Enriches contact records with ZoomInfo\
  \ data.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.match_person_input}}'\n    - name: company-enrich\n      path: /enrich\n      description: Company enrichment operations.\n      operations:\n      - name: enrich-company\n        method: POST\n        path: /company\n        description: Enriches company records with ZoomInfo data.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.match_company_input}}'\n      - name: enrich-company-master\n        method: POST\n        path: /company-master\n        description: Enriches company records with ZoomInfo master data.\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.match_company_input}}'\n    - name: orgchart-enrich\n      path: /enrich\n      description: Org chart enrichment operations.\n      operations:\n      - name: enrich-orgchart\n        method: POST\n        path: /orgchart\n        description: Returns org chart data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: hierarchy-enrich\n      path: /enrich\n      description: Corporate hierarchy enrichment operations.\n      operations:\n      - name: enrich-corporate-hierarchy\n        method: POST\n        path: /corporatehierarchy\n\
  \        description: Returns corporate hierarchy data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: location-enrich\n      path: /enrich\n      description: Company location enrichment operations.\n      operations:\n      - name: enrich-location\n        method: POST\n        path: /location\n        description: Returns location data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: technology-enrich\n      path: /enrich\n      description: Technology stack enrichment operations.\n      operations:\n\
  \      - name: enrich-technology\n        method: POST\n        path: /tech\n        description: Returns technology stack data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: hashtag-enrich\n      path: /enrich\n      description: Hashtag enrichment operations.\n      operations:\n      - name: enrich-hashtags\n        method: POST\n        path: /hashtag\n        description: Returns hashtag data for contacts.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            personId: '{{tools.person_id}}'\n    - name: intent-enrich\n      path: /enrich\n      description: Intent signal\
  \ enrichment operations.\n      operations:\n      - name: enrich-intent\n        method: POST\n        path: /intent\n        description: Returns intent signal data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: news-enrich\n      path: /enrich\n      description: News enrichment operations.\n      operations:\n      - name: enrich-news\n        method: POST\n        path: /news\n        description: Returns news data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: scoop-enrich\n      path: /enrich\n\
  \      description: Scoop enrichment operations.\n      operations:\n      - name: enrich-scoop\n        method: POST\n        path: /scoop\n        description: Returns scoop data for a specified company.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyId: '{{tools.company_id}}'\n    - name: ip-enrich\n      path: /enrich\n      description: IP address enrichment operations.\n      operations:\n      - name: enrich-ip\n        method: POST\n        path: /ip\n        description: Returns company data associated with a given IP address.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ipAddress: '{{tools.ip_address}}'\n    - name: lookup\n\
  \      path: /lookup\n      description: Lookup reference data operations.\n      operations:\n      - name: lookup-company-ranking\n        method: GET\n        path: /companyranking\n        description: Returns company ranking lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-continent\n        method: GET\n        path: /continent\n        description: Returns continent lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-country\n        method: GET\n        path: /country\n        description: Returns country lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-state\n\
  \        method: GET\n        path: /state\n        description: Returns state lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-department\n        method: GET\n        path: /department\n        description: Returns contact department lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-employee-count\n        method: GET\n        path: /employeecount\n        description: Returns employee count range lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-sic-codes\n        method: GET\n        path: /siccode\n        description: Returns SIC code lookup values.\n      \
  \  inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-naics-codes\n        method: GET\n        path: /naicscode\n        description: Returns NAICS code lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-industry\n        method: GET\n        path: /industry\n        description: Returns industry code lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-job-title-hierarchy\n        method: GET\n        path: /jobtitlehierarchy\n        description: Returns job title hierarchy lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: lookup-job-function\n        method: GET\n        path: /jobfunction\n        description: Returns job function lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-metro-area\n        method: GET\n        path: /metroarea\n        description: Returns metro area lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-revenue-range\n        method: GET\n        path: /revenuerange\n        description: Returns revenue range lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-scoop-topics\n        method: GET\n\
  \        path: /scooptopic\n        description: Returns scoop topic lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-company-type\n        method: GET\n        path: /companytype\n        description: Returns company type lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-management-levels\n        method: GET\n        path: /managementLevel\n        description: Returns management level lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-tech-categories\n        method: GET\n        path: /tech/category\n        description: Returns technology category lookup values.\n\
  \        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-tech-vendors\n        method: GET\n        path: /tech/vendor\n        description: Returns technology vendor lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-tech-products\n        method: GET\n        path: /tech/product\n        description: Returns technology product lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-intent-topics\n        method: GET\n        path: /intent/topics\n        description: Returns intent topic lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: lookup-news-categories\n        method: GET\n        path: /news/categories\n        description: Returns news category lookup values.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lookup-usage\n        method: GET\n        path: /usage\n        description: Returns API usage data.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Webhook management operations.\n      operations:\n      - name: create-webhook\n        method: POST\n        path: /\n        description: Creates a new webhook subscription.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetUrl: '{{tools.target_url}}'\n            subscriptionType: '{{tools.subscription_type}}'\n      - name: list-webhooks\n        method: GET\n        path: /\n        description: Returns a list of all webhooks.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-webhook\n        method: PUT\n        path: /{webhookId}\n        description: Updates an existing webhook subscription.\n        inputParameters:\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: The webhook ID to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetUrl:\
  \ '{{tools.target_url}}'\n      - name: delete-webhook\n        method: DELETE\n        path: /{webhookId}\n        description: Deletes a webhook subscription.\n        inputParameters:\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: The webhook ID to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-target-url\n        method: POST\n        path: /validate\n        description: Validates a webhook target URL.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetUrl: '{{tools.target_url}}'\n      - name: get-subscription-types\n        method: GET\n        path: /subscriptiontypes\n        description: Returns the available webhook subscription\
  \ types.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk\n      path: /bulk\n      description: Bulk search and enrichment operations.\n      operations:\n      - name: bulk-search-contacts\n        method: POST\n        path: /search/contact\n        description: Submits a bulk contact search job.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputData: '{{tools.input_data}}'\n      - name: bulk-search-companies\n        method: POST\n        path: /search/company\n        description: Submits a bulk company search job.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            inputData: '{{tools.input_data}}'\n      - name: bulk-enrich-contacts\n        method: POST\n        path: /enrich/contact\n        description: Submits a bulk contact enrichment job.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputData: '{{tools.input_data}}'\n      - name: bulk-enrich-companies\n        method: POST\n        path: /enrich/company\n        description: Submits a bulk company enrichment job.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputData: '{{tools.input_data}}'\n      - name: get-bulk-job-status\n        method: GET\n        path: /job/status\n        description:\
  \ Returns the status of a bulk job.\n        inputParameters:\n        - name: jobId\n          in: query\n          type: string\n          required: true\n          description: The bulk job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bulk-job-results\n        method: GET\n        path: /job/results\n        description: Returns the results of a completed bulk job.\n        inputParameters:\n        - name: jobId\n          in: query\n          type: string\n          required: true\n          description: The bulk job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance\n      path: /compliance\n      description: Compliance operations.\n      operations:\n      - name: check-compliance\n        method: POST\n        path: /\n        description: Returns compliance data for specified\
  \ contacts.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.match_person_input}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: prospecting-and-search-api\n    description: Unified REST API for B2B prospecting and search workflows.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Search for contacts matching prospecting criteria.\n      operations:\n      - method: POST\n        name: search-contacts\n        description: Search ZoomInfo contacts by criteria such as job title, company, location, and more.\n        call: zoominfo.search-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies\n      name: companies\n      description: Search for companies matching prospecting criteria.\n\
  \      operations:\n      - method: POST\n        name: search-companies\n        description: Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.\n        call: zoominfo.search-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scoops\n      name: scoops\n      description: Search for buying signals and scoops.\n      operations:\n      - method: POST\n        name: search-scoops\n        description: Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.\n        call: zoominfo.search-scoops\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news\n      name: news\n      description: Search for company news articles.\n      operations:\n      - method: POST\n        name: search-news\n        description: Search ZoomInfo news for recent company events and announcements.\n        call: zoominfo.search-news\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/intent\n      name: intent\n      description: Search for buyer intent signals.\n      operations:\n      - method: POST\n        name: search-intent\n        description: Search ZoomInfo intent data to identify companies actively researching topics.\n        call: zoominfo.search-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/industries\n      name: lookup-industries\n      description: Reference data for industry codes.\n      operations:\n      - method: GET\n        name: get-industries\n        description: Get available industry code lookup values.\n        call: zoominfo.lookup-industry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/departments\n      name: lookup-departments\n      description: Reference data for contact departments.\n      operations:\n      - method: GET\n        name: get-departments\n\
  \        description: Get available department lookup values.\n        call: zoominfo.lookup-department\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/job-functions\n      name: lookup-job-functions\n      description: Reference data for job functions.\n      operations:\n      - method: GET\n        name: get-job-functions\n        description: Get available job function lookup values.\n        call: zoominfo.lookup-job-function\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/management-levels\n      name: lookup-management-levels\n      description: Reference data for management levels.\n      operations:\n      - method: GET\n        name: get-management-levels\n        description: Get available management level lookup values.\n        call: zoominfo.lookup-management-levels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/revenue-ranges\n\
  \      name: lookup-revenue-ranges\n      description: Reference data for revenue ranges.\n      operations:\n      - method: GET\n        name: get-revenue-ranges\n        description: Get available revenue range lookup values.\n        call: zoominfo.lookup-revenue-range\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lookups/intent-topics\n      name: lookup-intent-topics\n      description: Reference data for intent topics.\n      operations:\n      - method: GET\n        name: get-intent-topics\n        description: Get available intent topic lookup values.\n        call: zoominfo.lookup-intent-topics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prospecting-and-search-mcp\n    transport: http\n    description: MCP server for AI-assisted B2B prospecting and search.\n    tools:\n    - name: search-contacts\n      description: Search ZoomInfo contacts by criteria such\
  \ as job title, company, location, and more.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.search-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-companies\n      description: Search ZoomInfo companies by criteria such as industry, revenue, employee count, and more.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.search-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-scoops\n      description: Search ZoomInfo scoops for buying signals like funding, expansion, and leadership changes.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.search-scoops\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-news\n      description: Search ZoomInfo news for recent company events and announcements.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: zoominfo.search-news\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-intent\n      description: Search ZoomInfo intent data to identify companies actively researching topics.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.search-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-industries\n      description: Get available industry code lookup values for filtering searches.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-industry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-departments\n      description: Get available department lookup values for filtering contact searches.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-department\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-functions\n\
  \      description: Get available job function lookup values for filtering contact searches.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-job-function\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-management-levels\n      description: Get available management level lookup values.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-management-levels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-revenue-ranges\n      description: Get available revenue range lookup values.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-revenue-range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intent-topics\n      description: Get available intent topic lookup values.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: zoominfo.lookup-intent-topics\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
