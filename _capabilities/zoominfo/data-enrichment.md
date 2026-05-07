---
categories: []
consumed_apis: []
description: Unified capability for B2B data enrichment workflows combining contact, company, org chart, corporate hierarchy, location, technology, intent, and IP enrichment. Used by sales ops, marketing ops, and data teams to enrich CRM and marketing automation records.
layout: capability
name: ZoomInfo Data Enrichment
operations:
- description: Enrich a contact record with ZoomInfo person data.
  method: POST
  name: enrich-contact
  path: /v1/contacts/enrich
- description: Enrich a company record with ZoomInfo firmographic data.
  method: POST
  name: enrich-company
  path: /v1/companies/enrich
- description: Enrich a company record with ZoomInfo master company data.
  method: POST
  name: enrich-company-master
  path: /v1/companies/master-enrich
- description: Get org chart data for a company.
  method: POST
  name: enrich-orgchart
  path: /v1/org-charts
- description: Get corporate hierarchy data showing parent/subsidiary relationships.
  method: POST
  name: enrich-corporate-hierarchy
  path: /v1/corporate-hierarchies
- description: Get location data for a company.
  method: POST
  name: enrich-location
  path: /v1/locations
- description: Get technology stack data for a company.
  method: POST
  name: enrich-technology
  path: /v1/technologies
- description: Get hashtag data for a contact.
  method: POST
  name: enrich-hashtags
  path: /v1/hashtags
- description: Get intent signal data for a company.
  method: POST
  name: enrich-intent
  path: /v1/intent/enrich
- description: Get news data for a company.
  method: POST
  name: enrich-news
  path: /v1/news/enrich
- description: Get scoop data for a company.
  method: POST
  name: enrich-scoop
  path: /v1/scoops/enrich
- description: Get company data associated with an IP address.
  method: POST
  name: enrich-ip
  path: /v1/ip-addresses
- description: Submit a bulk contact search job.
  method: POST
  name: bulk-search-contacts
  path: /v1/bulk/contacts
- description: Submit a bulk contact enrichment job.
  method: POST
  name: bulk-enrich-contacts
  path: /v1/bulk/contacts
- description: Submit a bulk company search job.
  method: POST
  name: bulk-search-companies
  path: /v1/bulk/companies
- description: Submit a bulk company enrichment job.
  method: POST
  name: bulk-enrich-companies
  path: /v1/bulk/companies
- description: Get the status of a bulk job.
  method: GET
  name: get-bulk-job-status
  path: /v1/bulk/jobs/{jobId}/status
- description: Get the results of a completed bulk job.
  method: GET
  name: get-bulk-job-results
  path: /v1/bulk/jobs/{jobId}/results
personas: []
provider_name: ZoomInfo
provider_slug: zoominfo
search_terms:
- enrich news
- submit a bulk company enrichment job.
- get scoop data for a company.
- retrieve corporate hierarchy data.
- crm integration
- enrich ip
- enrich scoop
- check bulk job status.
- submit a bulk contact search job.
- get the status of a bulk job.
- retrieve news enrichment data.
- b2b
- enrich technology
- bulk enrich contacts
- bulk search companies
- bulk contact search and enrichment.
- enrich company records with zoominfo master data.
- get news data for a company.
- enrich contact records with zoominfo data.
- enrich intent
- retrieve technology stack data.
- retrieve scoop enrichment data.
- retrieve intent signal enrichment data.
- enrich company master
- b2b data
- enrich company
- get org chart data for a company.
- get company data associated with an ip address.
- contacts
- enrich corporate hierarchy
- enrich a company record with zoominfo master company data.
- retrieve company location data.
- retrieve bulk job results.
- enrich ip addresses with company data.
- contact database
- enrich a company record with zoominfo firmographic data including revenue, employees, and industry.
- zoominfo
- enrich a company record with zoominfo firmographic data.
- retrieve contact hashtag data.
- get corporate hierarchy showing parent/subsidiary relationships.
- company data
- data enrichment
- enrich contact
- enrich company records with zoominfo data.
- enrich location
- bulk company search and enrichment.
- get intent signal data for a company.
- get bulk job status
- enrich hashtags
- get hashtag data for a contact.
- bulk search contacts
- get organizational chart data for a company.
- sales intelligence
- get bulk job results
- submit a bulk company search job.
- data
- enrich a contact record with zoominfo person data.
- bulk enrich companies
- get location data for a company.
- submit a bulk contact enrichment job.
- lead generation
- get the results of a completed bulk job.
- marketing intelligence
- enrich a contact record with zoominfo person data including email, phone, title, and company.
- retrieve organizational chart data.
- get corporate hierarchy data showing parent/subsidiary relationships.
- get technology stack data for a company.
- enrich orgchart
slug: data-enrichment
source_filename: data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ZoomInfo Data Enrichment\n  description: Unified capability for B2B data enrichment workflows combining contact, company, org chart, corporate hierarchy,\n    location, technology, intent, and IP enrichment. Used by sales ops, marketing ops, and data teams to enrich CRM and marketing\n    automation records.\n  tags:\n  - ZoomInfo\n  - Data Enrichment\n  - CRM Integration\n  - B2B Data\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n    ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: zoominfo\n    baseUri: https://api.zoominfo.com\n    description: ZoomInfo B2B intelligence API for contact, company, intent, news, scoop, and technographic data.\n    authentication:\n      type: bearer\n      token: '{{ZOOMINFO_JWT_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /\n      description: Authentication\
  \ operations for obtaining JWT tokens.\n      operations:\n      - name: authenticate\n        method: POST\n        path: /authenticate\n        description: Return a valid JWT access token by inputting your ZoomInfo username and password.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: contact-search\n      path: /search\n      description: Search and lookup operations for ZoomInfo contacts.\n      operations:\n      - name: search-contacts\n        method: POST\n        path: /contact\n        description: Returns a list of contacts from ZoomInfo's data that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n      - name: get-contact-search-inputs\n        method: GET\n        path: /contact\n        description: Returns the available input fields for contact search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contact-search-outputs\n        method: GET\n        path: /contact\n        description: Returns the available output fields for contact search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-search\n      path: /search\n      description: Search and lookup operations for ZoomInfo companies.\n      operations:\n      - name: search-companies\n        method: POST\n        path: /company\n\
  \        description: Returns a list of companies from ZoomInfo's data that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n      - name: get-company-search-inputs\n        method: GET\n        path: /company\n        description: Returns the available input fields for company search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-company-search-outputs\n        method: GET\n        path: /company\n        description: Returns the available output fields for company search.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: scoop-search\n      path: /search\n      description: Search operations for ZoomInfo scoops (buying signals).\n      operations:\n      - name: search-scoops\n        method: POST\n        path: /scoop\n        description: Returns a list of scoops that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: news-search\n      path: /search\n      description: Search operations for ZoomInfo news.\n      operations:\n      - name: search-news\n        method: POST\n        path: /news\n        description: Returns a list of news articles that meet the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: intent-search\n      path: /search\n      description: Search operations for ZoomInfo intent signals.\n      operations:\n      - name: search-intent\n        method: POST\n        path: /intent\n        description: Returns intent signal data that meets the specified search criteria.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rpp: '{{tools.rpp}}'\n            page: '{{tools.page}}'\n    - name: contact-enrich\n      path: /enrich\n      description: Contact enrichment operations.\n      operations:\n      - name: enrich-contact\n        method: POST\n        path: /contact\n        description: Enriches contact records with\
  \ ZoomInfo data.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.match_person_input}}'\n    - name: company-enrich\n      path: /enrich\n      description: Company enrichment operations.\n      operations:\n      - name: enrich-company\n        method: POST\n        path: /company\n        description: Enriches company records with ZoomInfo data.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchCompanyInput: '{{tools.match_company_input}}'\n      - name: enrich-company-master\n        method: POST\n        path: /company-master\n        description: Enriches company records with ZoomInfo master data.\n        inputParameters:\
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
  \ contacts.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchPersonInput: '{{tools.match_person_input}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-enrichment-api\n    description: Unified REST API for B2B data enrichment workflows.\n    resources:\n    - path: /v1/contacts/enrich\n      name: contact-enrichment\n      description: Enrich contact records with ZoomInfo data.\n      operations:\n      - method: POST\n        name: enrich-contact\n        description: Enrich a contact record with ZoomInfo person data.\n        call: zoominfo.enrich-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies/enrich\n      name: company-enrichment\n      description: Enrich company records with ZoomInfo data.\n      operations:\n      - method:\
  \ POST\n        name: enrich-company\n        description: Enrich a company record with ZoomInfo firmographic data.\n        call: zoominfo.enrich-company\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies/master-enrich\n      name: company-master-enrichment\n      description: Enrich company records with ZoomInfo master data.\n      operations:\n      - method: POST\n        name: enrich-company-master\n        description: Enrich a company record with ZoomInfo master company data.\n        call: zoominfo.enrich-company-master\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/org-charts\n      name: org-charts\n      description: Retrieve organizational chart data.\n      operations:\n      - method: POST\n        name: enrich-orgchart\n        description: Get org chart data for a company.\n        call: zoominfo.enrich-orgchart\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/corporate-hierarchies\n      name: corporate-hierarchies\n      description: Retrieve corporate hierarchy data.\n      operations:\n      - method: POST\n        name: enrich-corporate-hierarchy\n        description: Get corporate hierarchy data showing parent/subsidiary relationships.\n        call: zoominfo.enrich-corporate-hierarchy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Retrieve company location data.\n      operations:\n      - method: POST\n        name: enrich-location\n        description: Get location data for a company.\n        call: zoominfo.enrich-location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/technologies\n      name: technologies\n      description: Retrieve technology stack data.\n      operations:\n      - method: POST\n        name: enrich-technology\n        description: Get technology stack\
  \ data for a company.\n        call: zoominfo.enrich-technology\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hashtags\n      name: hashtags\n      description: Retrieve contact hashtag data.\n      operations:\n      - method: POST\n        name: enrich-hashtags\n        description: Get hashtag data for a contact.\n        call: zoominfo.enrich-hashtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intent/enrich\n      name: intent-enrichment\n      description: Retrieve intent signal enrichment data.\n      operations:\n      - method: POST\n        name: enrich-intent\n        description: Get intent signal data for a company.\n        call: zoominfo.enrich-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/enrich\n      name: news-enrichment\n      description: Retrieve news enrichment data.\n      operations:\n      - method: POST\n       \
  \ name: enrich-news\n        description: Get news data for a company.\n        call: zoominfo.enrich-news\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scoops/enrich\n      name: scoop-enrichment\n      description: Retrieve scoop enrichment data.\n      operations:\n      - method: POST\n        name: enrich-scoop\n        description: Get scoop data for a company.\n        call: zoominfo.enrich-scoop\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ip-addresses\n      name: ip-enrichment\n      description: Enrich IP addresses with company data.\n      operations:\n      - method: POST\n        name: enrich-ip\n        description: Get company data associated with an IP address.\n        call: zoominfo.enrich-ip\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/contacts\n      name: bulk-contact-operations\n      description: Bulk contact search and enrichment.\n\
  \      operations:\n      - method: POST\n        name: bulk-search-contacts\n        description: Submit a bulk contact search job.\n        call: zoominfo.bulk-search-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: bulk-enrich-contacts\n        path: /enrich\n        description: Submit a bulk contact enrichment job.\n        call: zoominfo.bulk-enrich-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/companies\n      name: bulk-company-operations\n      description: Bulk company search and enrichment.\n      operations:\n      - method: POST\n        name: bulk-search-companies\n        description: Submit a bulk company search job.\n        call: zoominfo.bulk-search-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: bulk-enrich-companies\n        path: /enrich\n        description: Submit\
  \ a bulk company enrichment job.\n        call: zoominfo.bulk-enrich-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/jobs/{jobId}/status\n      name: bulk-job-status\n      description: Check bulk job status.\n      operations:\n      - method: GET\n        name: get-bulk-job-status\n        description: Get the status of a bulk job.\n        call: zoominfo.get-bulk-job-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/jobs/{jobId}/results\n      name: bulk-job-results\n      description: Retrieve bulk job results.\n      operations:\n      - method: GET\n        name: get-bulk-job-results\n        description: Get the results of a completed bulk job.\n        call: zoominfo.get-bulk-job-results\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9091\n    namespace: data-enrichment-mcp\n    transport: http\n    description: MCP server for AI-assisted B2B data enrichment.\n    tools:\n    - name: enrich-contact\n      description: Enrich a contact record with ZoomInfo person data including email, phone, title, and company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-company\n      description: Enrich a company record with ZoomInfo firmographic data including revenue, employees, and industry.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-company\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-company-master\n      description: Enrich a company record with ZoomInfo master company data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-company-master\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: enrich-orgchart\n      description: Get organizational chart data for a company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-orgchart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-corporate-hierarchy\n      description: Get corporate hierarchy showing parent/subsidiary relationships.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-corporate-hierarchy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-location\n      description: Get location data for a company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-technology\n      description: Get technology stack data for a company.\n      hints:\n        readOnly: true\n      \
  \  openWorld: true\n      call: zoominfo.enrich-technology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-hashtags\n      description: Get hashtag data for a contact.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-hashtags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-intent\n      description: Get intent signal data for a company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrich-news\n      description: Get news data for a company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoominfo.enrich-news\n \n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/capabilities/data-enrichment.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/capabilities/data-enrichment.yaml
tags:
- ZoomInfo
- Data Enrichment
- CRM Integration
- B2B Data
tools:
- description: Enrich a contact record with ZoomInfo person data including email, phone, title, and company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-contact
- description: Enrich a company record with ZoomInfo firmographic data including revenue, employees, and industry.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-company
- description: Enrich a company record with ZoomInfo master company data.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-company-master
- description: Get organizational chart data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-orgchart
- description: Get corporate hierarchy showing parent/subsidiary relationships.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-corporate-hierarchy
- description: Get location data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-location
- description: Get technology stack data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-technology
- description: Get hashtag data for a contact.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-hashtags
- description: Get intent signal data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-intent
- description: Get news data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-news
- description: Get scoop data for a company.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-scoop
- description: Get company data associated with an IP address.
  hints:
    openWorld: true
    readOnly: true
  name: enrich-ip
- description: Submit a bulk contact search job.
  hints:
    idempotent: false
    readOnly: false
  name: bulk-search-contacts
- description: Submit a bulk company search job.
  hints:
    idempotent: false
    readOnly: false
  name: bulk-search-companies
- description: Submit a bulk contact enrichment job.
  hints:
    idempotent: false
    readOnly: false
  name: bulk-enrich-contacts
- description: Submit a bulk company enrichment job.
  hints:
    idempotent: false
    readOnly: false
  name: bulk-enrich-companies
- description: Get the status of a bulk job.
  hints:
    idempotent: true
    readOnly: true
  name: get-bulk-job-status
- description: Get the results of a completed bulk job.
  hints:
    idempotent: true
    readOnly: true
  name: get-bulk-job-results
---
