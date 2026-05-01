---
categories:
- compliance
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
- list standards
- check compliance
- API Developer
- individual standard detail
- list technology standards
- architect responsible for allianz technology standards governance and enforcement
- check an openapi specification for compliance with allianz technology standards and get violations
- get webhook standard
- defining and maintaining allianz technology standards
- query standards and check api compliance for architects and developers
- pagination guidelines
- Platform Governance Team
- get the full rules and definition of a specific allianz technology standard
- api design
- team responsible for enforcing allianz api and technology standards across engineering teams
- get standard definition
- get pagination standard
- standards catalog
- compliance
- 'get allianz webhook implementation standard: technical/functional types, https, ip whitelisting requirements'
- get pagination guidelines
- enterprise architecture
- developer building apis on the allianz platform who needs to comply with technology standards
- guidelines
- check api compliance
- software development
- governance
- compliance checking
- get technology standard
- openapi
- checking and enforcing compliance with api design standards
- technology standards
- best practices
- 'get allianz rest api pagination standard: pagesize, page, totalrequired parameters and response headers'
- Enterprise Architect
- list all allianz technology standards categorized by api-design, backend, architecture, security, and testing
- get standard
slug: standards-compliance-workflow
source_filename: standards-compliance-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Allianz Standards Compliance Workflow\"\n  description: \"Workflow capability for architects and developers querying Allianz technology standards and checking API compliance against documented guidelines.\"\n  tags:\n    - Technology Standards\n    - API Design\n    - Compliance\n    - Enterprise Architecture\n    - Governance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALLIANZ_STANDARDS_CLIENT_ID: ALLIANZ_STANDARDS_CLIENT_ID\n      ALLIANZ_STANDARDS_CLIENT_SECRET: ALLIANZ_STANDARDS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: allianz-technology-standards\n      location: ./shared/standards-compliance.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: allianz-standards-compliance-api\n      description: \"Unified REST API for Allianz technology standards compliance workflows.\"\n      resources:\n        - path: /v1/standards\n        \
  \  name: standards\n          description: \"Standards catalog\"\n          operations:\n            - method: GET\n              name: list-standards\n              description: \"List technology standards\"\n              call: \"allianz-technology-standards.list-standards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/standards/{standard_id}\n          name: standard-detail\n          description: \"Individual standard detail\"\n          operations:\n            - method: GET\n              name: get-standard\n              description: \"Get standard definition\"\n              call: \"allianz-technology-standards.get-standard\"\n              with:\n                standard_id: \"rest.standard_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compliance/check\n          name: compliance\n          description: \"Compliance checking\"\
  \n          operations:\n            - method: POST\n              name: check-compliance\n              description: \"Check API compliance\"\n              call: \"allianz-technology-standards.check-compliance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/guidelines/pagination\n          name: pagination-guidelines\n          description: \"Pagination guidelines\"\n          operations:\n            - method: GET\n              name: get-pagination-guidelines\n              description: \"Get pagination standard\"\n              call: \"allianz-technology-standards.get-pagination-guidelines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: allianz-standards-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Allianz technology standards compliance.\"\n      tools:\n\
  \        - name: list-technology-standards\n          description: \"List all Allianz technology standards categorized by api-design, backend, architecture, security, and testing\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-technology-standards.list-standards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-technology-standard\n          description: \"Get the full rules and definition of a specific Allianz technology standard\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-technology-standards.get-standard\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-api-compliance\n          description: \"Check an OpenAPI specification for compliance with Allianz technology standards and get violations\"\n          hints:\n            readOnly: true\n \
  \           openWorld: false\n          call: \"allianz-technology-standards.check-compliance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pagination-standard\n          description: \"Get Allianz REST API pagination standard: pageSize, page, totalRequired parameters and response headers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-technology-standards.get-pagination-guidelines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-webhook-standard\n          description: \"Get Allianz webhook implementation standard: technical/functional types, HTTPS, IP whitelisting requirements\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-technology-standards.get-webhook-guidelines\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/allianz-technology-standards/refs/heads/main/capabilities/standards-compliance-workflow.yaml
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
