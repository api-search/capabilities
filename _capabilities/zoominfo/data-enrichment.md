---
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
- get the status of a bulk job.
- b2b data
- enrich scoop
- submit a bulk contact search job.
- data
- get org chart data for a company.
- enrich a contact record with zoominfo person data including email, phone, title, and company.
- enrich intent
- zoominfo
- retrieve bulk job results.
- enrich news
- contacts
- lead generation
- submit a bulk company enrichment job.
- get news data for a company.
- get organizational chart data for a company.
- contact database
- get intent signal data for a company.
- enrich company records with zoominfo master data.
- get the results of a completed bulk job.
- bulk search companies
- enrich corporate hierarchy
- retrieve organizational chart data.
- submit a bulk company search job.
- get bulk job status
- enrich ip addresses with company data.
- enrich company
- enrich location
- submit a bulk contact enrichment job.
- sales intelligence
- get company data associated with an ip address.
- enrich a company record with zoominfo firmographic data including revenue, employees, and industry.
- get bulk job results
- get corporate hierarchy data showing parent/subsidiary relationships.
- crm integration
- company data
- check bulk job status.
- b2b
- retrieve news enrichment data.
- enrich company master
- enrich a contact record with zoominfo person data.
- enrich orgchart
- retrieve technology stack data.
- retrieve intent signal enrichment data.
- bulk company search and enrichment.
- bulk enrich companies
- enrich a company record with zoominfo firmographic data.
- enrich ip
- get hashtag data for a contact.
- get corporate hierarchy showing parent/subsidiary relationships.
- retrieve company location data.
- get technology stack data for a company.
- retrieve corporate hierarchy data.
- enrich contact records with zoominfo data.
- get scoop data for a company.
- bulk search contacts
- enrich technology
- bulk contact search and enrichment.
- retrieve scoop enrichment data.
- enrich a company record with zoominfo master company data.
- enrich company records with zoominfo data.
- enrich contact
- bulk enrich contacts
- data enrichment
- enrich hashtags
- marketing intelligence
- retrieve contact hashtag data.
- get location data for a company.
slug: data-enrichment
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
