---
categories: []
consumed_apis:
- uh-fhir
description: Workflow capability for CMS-compliant health data interoperability using UnitedHealth Group FHIR R4 APIs. Enables patient portals, third-party health apps, care management platforms, and provider tools to access member health records, claims history, coverage details, clinical conditions, provider directory, and drug formulary data. Supports CMS-9115-F Patient Access rule and Da Vinci implementation guides for payer data exchange.
layout: capability
name: UnitedHealth Group Health Data Interoperability
operations:
- description: Get member FHIR Patient resource.
  method: GET
  name: get-member
  path: /v1/members/{id}
- description: List member claims as EOBs.
  method: GET
  name: list-member-claims
  path: /v1/members/{id}/claims
- description: Get member coverage details.
  method: GET
  name: get-member-coverage
  path: /v1/members/{id}/coverage
- description: List member conditions.
  method: GET
  name: list-member-conditions
  path: /v1/members/{id}/conditions
- description: Search provider directory.
  method: GET
  name: search-providers
  path: /v1/providers
- description: Search drug formulary.
  method: GET
  name: search-formulary
  path: /v1/formulary
personas: []
provider_name: UnitedHealth Group
provider_slug: unitedhealth
search_terms:
- get member fhir patient resource.
- get member coverage
- search provider directory.
- get insurance coverage
- health data interoperability
- provider
- check drug formulary
- get a member's unitedhealth group insurance coverage including plan name, group number, and benefit period.
- member
- find in network provider
- search providers
- fhir
- developer building fhir-compliant applications using unitedhealth group interoperability apis
- healthcare
- drug formulary.
- retrieve a member's health conditions and diagnoses from unitedhealth group clinical records and claims data.
- member-facing health data access and transparency
- member coverage.
- get member conditions
- claims
- network provider search and directory services
- list member conditions
- get member claims history
- health app developer
- health insurance
- search drug formulary.
- fhir r4 health data interoperability workflow for member access, claims, coverage, conditions, providers, and formulary
- provider using directory and formulary apis for patient care support
- search the unitedhealth group provider directory for in-network physicians, specialists, and organizations by name, npi, specialty, or state.
- retrieve a unitedhealth group member's fhir patient record with demographics and identifiers.
- member demographics.
- list member conditions.
- member conditions.
- care manager
- unitedhealth group
- member accessing their own health data through fhir patient access apis
- list member claims as eobs.
- cms patient access
- cms-mandated fhir r4 data exchange for patient health records and claims
- drug coverage and formulary management
- get member health record
- care management professional accessing member health data for population health and care coordination
- optum
- list member claims
- member claims history.
- provider directory.
- retrieve a member's complete claims history as fhir explanationofbenefit resources including services, diagnoses, and payment details.
- interoperability
- search formulary
- get member
- get member coverage details.
- da vinci
- check unitedhealth group drug formulary coverage tier, prior authorization requirements, and quantity limits for a medication.
slug: health-data-interoperability
source_filename: health-data-interoperability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UnitedHealth Group Health Data Interoperability\"\n  description: >-\n    Workflow capability for CMS-compliant health data interoperability using UnitedHealth\n    Group FHIR R4 APIs. Enables patient portals, third-party health apps, care management\n    platforms, and provider tools to access member health records, claims history, coverage\n    details, clinical conditions, provider directory, and drug formulary data. Supports\n    CMS-9115-F Patient Access rule and Da Vinci implementation guides for payer data\n    exchange.\n  tags:\n    - UnitedHealth Group\n    - Optum\n    - FHIR\n    - Health Data Interoperability\n    - CMS Patient Access\n    - Da Vinci\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UH_FHIR_TOKEN: UH_FHIR_TOKEN\n\ncapability:\n  consumes:\n    - import: uh-fhir\n      location: ./shared/optum-api.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: uh-interoperability-api\n      description: \"Unified REST API for UnitedHealth Group FHIR interoperability.\"\n      resources:\n        - path: /v1/members/{id}\n          name: member\n          description: \"Member demographics.\"\n          operations:\n            - method: GET\n              name: get-member\n              description: \"Get member FHIR Patient resource.\"\n              call: \"uh-fhir.get-patient\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members/{id}/claims\n          name: claims\n          description: \"Member claims history.\"\n          operations:\n            - method: GET\n              name: list-member-claims\n              description: \"List member claims as EOBs.\"\n              call: \"uh-fhir.list-eobs\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/members/{id}/coverage\n          name: coverage\n          description: \"Member coverage.\"\n          operations:\n            - method: GET\n              name: get-member-coverage\n              description: \"Get member coverage details.\"\n              call: \"uh-fhir.list-coverage\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members/{id}/conditions\n          name: conditions\n          description: \"Member conditions.\"\n          operations:\n            - method: GET\n              name: list-member-conditions\n              description: \"List member conditions.\"\n              call: \"uh-fhir.list-conditions\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/providers\n\
  \          name: providers\n          description: \"Provider directory.\"\n          operations:\n            - method: GET\n              name: search-providers\n              description: \"Search provider directory.\"\n              call: \"uh-fhir.list-practitioners\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/formulary\n          name: formulary\n          description: \"Drug formulary.\"\n          operations:\n            - method: GET\n              name: search-formulary\n              description: \"Search drug formulary.\"\n              call: \"uh-fhir.list-formulary\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: uh-interoperability-mcp\n      transport: http\n      description: \"MCP server for AI-assisted UnitedHealth Group FHIR data access.\"\n      tools:\n        - name: get-member-health-record\n\
  \          description: \"Retrieve a UnitedHealth Group member's FHIR Patient record with demographics and identifiers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uh-fhir.get-patient\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-member-claims-history\n          description: \"Retrieve a member's complete claims history as FHIR ExplanationOfBenefit resources including services, diagnoses, and payment details.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uh-fhir.list-eobs\"\n          with:\n            patient: \"tools.memberId\"\n            type: \"tools.claimType\"\n            _lastUpdated: \"tools.since\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-insurance-coverage\n          description: \"Get a member's UnitedHealth Group insurance coverage including\
  \ plan name, group number, and benefit period.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uh-fhir.list-coverage\"\n          with:\n            patient: \"tools.memberId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-member-conditions\n          description: \"Retrieve a member's health conditions and diagnoses from UnitedHealth Group clinical records and claims data.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uh-fhir.list-conditions\"\n          with:\n            patient: \"tools.memberId\"\n            \"clinical-status\": \"tools.clinicalStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-in-network-provider\n          description: \"Search the UnitedHealth Group provider directory for in-network physicians, specialists,\
  \ and organizations by name, NPI, specialty, or state.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uh-fhir.list-practitioners\"\n          with:\n            name: \"tools.providerName\"\n            identifier: \"tools.npi\"\n            specialty: \"tools.specialty\"\n            \"address-state\": \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-drug-formulary\n          description: \"Check UnitedHealth Group drug formulary coverage tier, prior authorization requirements, and quantity limits for a medication.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uh-fhir.list-formulary\"\n          with:\n            code: \"tools.rxnormCode\"\n            drug-name: \"tools.drugName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unitedhealth/refs/heads/main/capabilities/health-data-interoperability.yaml
tags:
- UnitedHealth Group
- Optum
- FHIR
- Health Data Interoperability
- CMS Patient Access
- Da Vinci
tools:
- description: Retrieve a UnitedHealth Group member's FHIR Patient record with demographics and identifiers.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-health-record
- description: Retrieve a member's complete claims history as FHIR ExplanationOfBenefit resources including services, diagnoses, and payment details.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-claims-history
- description: Get a member's UnitedHealth Group insurance coverage including plan name, group number, and benefit period.
  hints:
    openWorld: false
    readOnly: true
  name: get-insurance-coverage
- description: Retrieve a member's health conditions and diagnoses from UnitedHealth Group clinical records and claims data.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-conditions
- description: Search the UnitedHealth Group provider directory for in-network physicians, specialists, and organizations by name, NPI, specialty, or state.
  hints:
    openWorld: true
    readOnly: true
  name: find-in-network-provider
- description: Check UnitedHealth Group drug formulary coverage tier, prior authorization requirements, and quantity limits for a medication.
  hints:
    openWorld: true
    readOnly: true
  name: check-drug-formulary
---
