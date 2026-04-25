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
- get pagination guidelines
- standards catalog
- get standard definition
- compliance checking
- Enterprise Architect
- list all allianz technology standards categorized by api-design, backend, architecture, security, and testing
- 'get allianz rest api pagination standard: pagesize, page, totalrequired parameters and response headers'
- individual standard detail
- pagination guidelines
- compliance
- list technology standards
- software development
- openapi
- enterprise architecture
- check api compliance
- api design
- get webhook standard
- Platform Governance Team
- checking and enforcing compliance with api design standards
- governance
- 'get allianz webhook implementation standard: technical/functional types, https, ip whitelisting requirements'
- check an openapi specification for compliance with allianz technology standards and get violations
- check compliance
- guidelines
- get pagination standard
- best practices
- API Developer
- developer building apis on the allianz platform who needs to comply with technology standards
- list standards
- get standard
- team responsible for enforcing allianz api and technology standards across engineering teams
- defining and maintaining allianz technology standards
- architect responsible for allianz technology standards governance and enforcement
- get the full rules and definition of a specific allianz technology standard
- get technology standard
- technology standards
- query standards and check api compliance for architects and developers
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
