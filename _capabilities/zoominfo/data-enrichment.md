---
api_specs:
- filename: zoominfo-openapi.yml
  format: yaml
  label: zoominfo
  slug: zoominfo
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/openapi/zoominfo-openapi.yml
categories: []
consumed_apis:
- zoominfo
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
- enrich corporate hierarchy
- bulk company search and enrichment.
- enrich a company record with zoominfo master company data.
- contact database
- bulk search companies
- retrieve corporate hierarchy data.
- enrich a company record with zoominfo firmographic data including revenue, employees, and industry.
- enrich contact
- retrieve technology stack data.
- enrich company records with zoominfo master data.
- lead generation
- get news data for a company.
- submit a bulk company search job.
- bulk contact search and enrichment.
- submit a bulk contact search job.
- submit a bulk contact enrichment job.
- data
- enrich news
- retrieve bulk job results.
- b2b data
- get company data associated with an ip address.
- retrieve company location data.
- enrich a company record with zoominfo firmographic data.
- enrich a contact record with zoominfo person data.
- retrieve contact hashtag data.
- enrich intent
- data enrichment
- get hashtag data for a contact.
- crm integration
- enrich scoop
- enrich ip
- enrich company
- enrich orgchart
- enrich hashtags
- bulk search contacts
- enrich a contact record with zoominfo person data including email, phone, title, and company.
- bulk enrich companies
- get the results of a completed bulk job.
- b2b
- marketing intelligence
- get the status of a bulk job.
- get technology stack data for a company.
- get corporate hierarchy data showing parent/subsidiary relationships.
- retrieve intent signal enrichment data.
- get scoop data for a company.
- get intent signal data for a company.
- get org chart data for a company.
- get organizational chart data for a company.
- get bulk job status
- submit a bulk company enrichment job.
- contacts
- enrich ip addresses with company data.
- check bulk job status.
- zoominfo
- get corporate hierarchy showing parent/subsidiary relationships.
- bulk enrich contacts
- retrieve organizational chart data.
- enrich company master
- retrieve scoop enrichment data.
- retrieve news enrichment data.
- company data
- enrich contact records with zoominfo data.
- get location data for a company.
- get bulk job results
- enrich technology
- enrich location
- sales intelligence
- enrich company records with zoominfo data.
slug: data-enrichment
source_filename: data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ZoomInfo Data Enrichment\"\n  description: \"Unified capability for B2B data enrichment workflows combining contact, company, org chart, corporate hierarchy, location, technology, intent, and IP enrichment. Used by sales ops, marketing ops, and data teams to enrich CRM and marketing automation records.\"\n  tags:\n    - ZoomInfo\n    - Data Enrichment\n    - CRM Integration\n    - B2B Data\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n      ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\n\ncapability:\n  consumes:\n    - import: zoominfo\n      location: ./shared/zoominfo.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: data-enrichment-api\n      description: \"Unified REST API for B2B data enrichment workflows.\"\n      resources:\n        - path: /v1/contacts/enrich\n          name: contact-enrichment\n          description:\
  \ \"Enrich contact records with ZoomInfo data.\"\n          operations:\n            - method: POST\n              name: enrich-contact\n              description: \"Enrich a contact record with ZoomInfo person data.\"\n              call: \"zoominfo.enrich-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/companies/enrich\n          name: company-enrichment\n          description: \"Enrich company records with ZoomInfo data.\"\n          operations:\n            - method: POST\n              name: enrich-company\n              description: \"Enrich a company record with ZoomInfo firmographic data.\"\n              call: \"zoominfo.enrich-company\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/companies/master-enrich\n          name: company-master-enrichment\n          description: \"Enrich company records with ZoomInfo master data.\"\
  \n          operations:\n            - method: POST\n              name: enrich-company-master\n              description: \"Enrich a company record with ZoomInfo master company data.\"\n              call: \"zoominfo.enrich-company-master\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/org-charts\n          name: org-charts\n          description: \"Retrieve organizational chart data.\"\n          operations:\n            - method: POST\n              name: enrich-orgchart\n              description: \"Get org chart data for a company.\"\n              call: \"zoominfo.enrich-orgchart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/corporate-hierarchies\n          name: corporate-hierarchies\n          description: \"Retrieve corporate hierarchy data.\"\n          operations:\n            - method: POST\n              name: enrich-corporate-hierarchy\n\
  \              description: \"Get corporate hierarchy data showing parent/subsidiary relationships.\"\n              call: \"zoominfo.enrich-corporate-hierarchy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations\n          name: locations\n          description: \"Retrieve company location data.\"\n          operations:\n            - method: POST\n              name: enrich-location\n              description: \"Get location data for a company.\"\n              call: \"zoominfo.enrich-location\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/technologies\n          name: technologies\n          description: \"Retrieve technology stack data.\"\n          operations:\n            - method: POST\n              name: enrich-technology\n              description: \"Get technology stack data for a company.\"\n              call: \"zoominfo.enrich-technology\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hashtags\n          name: hashtags\n          description: \"Retrieve contact hashtag data.\"\n          operations:\n            - method: POST\n              name: enrich-hashtags\n              description: \"Get hashtag data for a contact.\"\n              call: \"zoominfo.enrich-hashtags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/intent/enrich\n          name: intent-enrichment\n          description: \"Retrieve intent signal enrichment data.\"\n          operations:\n            - method: POST\n              name: enrich-intent\n              description: \"Get intent signal data for a company.\"\n              call: \"zoominfo.enrich-intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/news/enrich\n     \
  \     name: news-enrichment\n          description: \"Retrieve news enrichment data.\"\n          operations:\n            - method: POST\n              name: enrich-news\n              description: \"Get news data for a company.\"\n              call: \"zoominfo.enrich-news\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scoops/enrich\n          name: scoop-enrichment\n          description: \"Retrieve scoop enrichment data.\"\n          operations:\n            - method: POST\n              name: enrich-scoop\n              description: \"Get scoop data for a company.\"\n              call: \"zoominfo.enrich-scoop\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ip-addresses\n          name: ip-enrichment\n          description: \"Enrich IP addresses with company data.\"\n          operations:\n            - method: POST\n              name:\
  \ enrich-ip\n              description: \"Get company data associated with an IP address.\"\n              call: \"zoominfo.enrich-ip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk/contacts\n          name: bulk-contact-operations\n          description: \"Bulk contact search and enrichment.\"\n          operations:\n            - method: POST\n              name: bulk-search-contacts\n              description: \"Submit a bulk contact search job.\"\n              call: \"zoominfo.bulk-search-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: bulk-enrich-contacts\n              path: /enrich\n              description: \"Submit a bulk contact enrichment job.\"\n              call: \"zoominfo.bulk-enrich-contacts\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/bulk/companies\n          name: bulk-company-operations\n          description: \"Bulk company search and enrichment.\"\n          operations:\n            - method: POST\n              name: bulk-search-companies\n              description: \"Submit a bulk company search job.\"\n              call: \"zoominfo.bulk-search-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: bulk-enrich-companies\n              path: /enrich\n              description: \"Submit a bulk company enrichment job.\"\n              call: \"zoominfo.bulk-enrich-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk/jobs/{jobId}/status\n          name: bulk-job-status\n          description: \"Check bulk job status.\"\n          operations:\n            - method: GET\n              name: get-bulk-job-status\n\
  \              description: \"Get the status of a bulk job.\"\n              call: \"zoominfo.get-bulk-job-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk/jobs/{jobId}/results\n          name: bulk-job-results\n          description: \"Retrieve bulk job results.\"\n          operations:\n            - method: GET\n              name: get-bulk-job-results\n              description: \"Get the results of a completed bulk job.\"\n              call: \"zoominfo.get-bulk-job-results\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: data-enrichment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted B2B data enrichment.\"\n      tools:\n        - name: enrich-contact\n\
  \          description: \"Enrich a contact record with ZoomInfo person data including email, phone, title, and company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-company\n          description: \"Enrich a company record with ZoomInfo firmographic data including revenue, employees, and industry.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-company\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-company-master\n          description: \"Enrich a company record with ZoomInfo master company data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-company-master\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: enrich-orgchart\n          description: \"Get organizational chart data for a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-orgchart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-corporate-hierarchy\n          description: \"Get corporate hierarchy showing parent/subsidiary relationships.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-corporate-hierarchy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-location\n          description: \"Get location data for a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-location\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: enrich-technology\n          description: \"Get technology stack data for a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-technology\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-hashtags\n          description: \"Get hashtag data for a contact.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-hashtags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-intent\n          description: \"Get intent signal data for a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-news\n          description: \"Get news data for\
  \ a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-news\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-scoop\n          description: \"Get scoop data for a company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-scoop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-ip\n          description: \"Get company data associated with an IP address.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.enrich-ip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-search-contacts\n          description: \"Submit a bulk contact search job.\"\n          hints:\n            readOnly: false\n            idempotent: false\n\
  \          call: \"zoominfo.bulk-search-contacts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-search-companies\n          description: \"Submit a bulk company search job.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zoominfo.bulk-search-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-enrich-contacts\n          description: \"Submit a bulk contact enrichment job.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zoominfo.bulk-enrich-contacts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-enrich-companies\n          description: \"Submit a bulk company enrichment job.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zoominfo.bulk-enrich-companies\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bulk-job-status\n          description: \"Get the status of a bulk job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.get-bulk-job-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bulk-job-results\n          description: \"Get the results of a completed bulk job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.get-bulk-job-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
