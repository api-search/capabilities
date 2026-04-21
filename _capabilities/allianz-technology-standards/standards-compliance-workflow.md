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
- Enterprise Architect
- guidelines
- get standard definition
- pagination guidelines
- checking and enforcing compliance with api design standards
- get standard
- technology standards
- openapi
- list all allianz technology standards categorized by api-design, backend, architecture, security, and testing
- api design
- get webhook standard
- software development
- defining and maintaining allianz technology standards
- best practices
- standards catalog
- query standards and check api compliance for architects and developers
- check api compliance
- get pagination standard
- 'get allianz rest api pagination standard: pagesize, page, totalrequired parameters and response headers'
- Platform Governance Team
- list standards
- architect responsible for allianz technology standards governance and enforcement
- get technology standard
- compliance
- governance
- compliance checking
- API Developer
- get pagination guidelines
- 'get allianz webhook implementation standard: technical/functional types, https, ip whitelisting requirements'
- enterprise architecture
- get the full rules and definition of a specific allianz technology standard
- list technology standards
- check an openapi specification for compliance with allianz technology standards and get violations
- individual standard detail
- check compliance
- developer building apis on the allianz platform who needs to comply with technology standards
- team responsible for enforcing allianz api and technology standards across engineering teams
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
