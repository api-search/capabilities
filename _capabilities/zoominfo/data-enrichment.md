---
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
- lead generation
- bulk enrich contacts
- enrich ip addresses with company data.
- sales intelligence
- submit a bulk contact enrichment job.
- b2b data
- zoominfo
- check bulk job status.
- get corporate hierarchy data showing parent/subsidiary relationships.
- bulk search contacts
- get the results of a completed bulk job.
- get corporate hierarchy showing parent/subsidiary relationships.
- enrich a company record with zoominfo firmographic data.
- enrich location
- bulk contact search and enrichment.
- marketing intelligence
- retrieve intent signal enrichment data.
- get intent signal data for a company.
- enrich a contact record with zoominfo person data including email, phone, title, and company.
- retrieve organizational chart data.
- get news data for a company.
- enrich company records with zoominfo master data.
- data enrichment
- retrieve news enrichment data.
- get org chart data for a company.
- enrich scoop
- enrich contact
- retrieve corporate hierarchy data.
- enrich intent
- submit a bulk company enrichment job.
- get organizational chart data for a company.
- enrich company records with zoominfo data.
- enrich technology
- get hashtag data for a contact.
- enrich corporate hierarchy
- retrieve contact hashtag data.
- enrich hashtags
- submit a bulk company search job.
- b2b
- get scoop data for a company.
- crm integration
- enrich company master
- get technology stack data for a company.
- retrieve bulk job results.
- retrieve technology stack data.
- enrich a company record with zoominfo firmographic data including revenue, employees, and industry.
- submit a bulk contact search job.
- get the status of a bulk job.
- bulk search companies
- retrieve scoop enrichment data.
- enrich news
- bulk company search and enrichment.
- company data
- enrich a company record with zoominfo master company data.
- get company data associated with an ip address.
- bulk enrich companies
- get bulk job status
- data
- contact database
- enrich contact records with zoominfo data.
- enrich orgchart
- retrieve company location data.
- get bulk job results
- enrich company
- enrich ip
- get location data for a company.
- contacts
- enrich a contact record with zoominfo person data.
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
