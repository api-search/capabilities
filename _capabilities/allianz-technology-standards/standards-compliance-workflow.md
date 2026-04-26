---
consumed_apis:
- allianz-technology-standards
description: Workflow capability for architects and developers querying Allianz technology standards and checking API compliance against documented guidelines.
layout: capability
name: Allianz Standards Compliance Workflow
operations:
- description: List technology standards
  method: GET
  name: list-standards
  path: /v1/standards
- description: Get standard definition
  method: GET
  name: get-standard
  path: /v1/standards/{standard_id}
- description: Check API compliance
  method: POST
  name: check-compliance
  path: /v1/compliance/check
- description: Get pagination standard
  method: GET
  name: get-pagination-guidelines
  path: /v1/guidelines/pagination
personas: []
provider_name: Allianz Technology Standards
provider_slug: allianz-technology-standards
search_terms:
- api design
- best practices
- Enterprise Architect
- get pagination guidelines
- defining and maintaining allianz technology standards
- technology standards
- 'get allianz rest api pagination standard: pagesize, page, totalrequired parameters and response headers'
- compliance checking
- checking and enforcing compliance with api design standards
- get pagination standard
- enterprise architecture
- guidelines
- API Developer
- list all allianz technology standards categorized by api-design, backend, architecture, security, and testing
- list standards
- governance
- get the full rules and definition of a specific allianz technology standard
- openapi
- individual standard detail
- check compliance
- list technology standards
- check api compliance
- get technology standard
- team responsible for enforcing allianz api and technology standards across engineering teams
- standards catalog
- developer building apis on the allianz platform who needs to comply with technology standards
- check an openapi specification for compliance with allianz technology standards and get violations
- software development
- query standards and check api compliance for architects and developers
- get standard
- pagination guidelines
- architect responsible for allianz technology standards governance and enforcement
- compliance
- get standard definition
- Platform Governance Team
- 'get allianz webhook implementation standard: technical/functional types, https, ip whitelisting requirements'
- get webhook standard
slug: standards-compliance-workflow
tags:
- Technology Standards
- API Design
- Compliance
- Enterprise Architecture
- Governance
tools:
- description: List all Allianz technology standards categorized by api-design, backend, architecture, security, and testing
  hints:
    openWorld: false
    readOnly: true
  name: list-technology-standards
- description: Get the full rules and definition of a specific Allianz technology standard
  hints:
    openWorld: false
    readOnly: true
  name: get-technology-standard
- description: Check an OpenAPI specification for compliance with Allianz technology standards and get violations
  hints:
    openWorld: false
    readOnly: true
  name: check-api-compliance
- description: 'Get Allianz REST API pagination standard: pageSize, page, totalRequired parameters and response headers'
  hints:
    openWorld: false
    readOnly: true
  name: get-pagination-standard
- description: 'Get Allianz webhook implementation standard: technical/functional types, HTTPS, IP whitelisting requirements'
  hints:
    openWorld: false
    readOnly: true
  name: get-webhook-standard
---
