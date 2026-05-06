---
categories: []
consumed_apis: []
description: Workflow capability for accessing UnitedHealthcare member health data through FHIR R4 Interoperability APIs mandated by CMS. Enables patient portals, health apps, and care coordination tools to retrieve claims history, coverage details, and provider directory information. Supports CMS-9115-F Patient Access rule compliance and Da Vinci PDex Provider Directory implementation.
layout: capability
name: UnitedHealthcare Patient Data Access
operations:
- description: Get FHIR Patient resource.
  method: GET
  name: get-patient
  path: /v1/patient/{id}
- description: List EOB claims history.
  method: GET
  name: list-eobs
  path: /v1/claims-history
- description: List coverage.
  method: GET
  name: list-coverage
  path: /v1/coverage
- description: Search providers.
  method: GET
  name: list-practitioners
  path: /v1/providers
personas: []
provider_name: UnitedHealthcare
provider_slug: unitedhealthcare
search_terms:
- fhir
- get fhir patient resource.
- retrieve a member's claims history as fhir explanationofbenefit resources including service dates, amounts billed, and payment status.
- get claims history
- eligibility
- health data exchange
- health app developer
- list eobs
- healthcare provider
- clinical staff coordinating prior authorization requests and tracking approval status
- provider directory
- healthcare
- list practitioners
- billing specialist
- get member demographics
- fhir-based patient data access workflow for claims history, coverage, and provider directory
- coverage details.
- healthcare provider workflow for eligibility, claims, prior authorization, and provider directory
- developer building patient-facing applications using fhir interoperability apis
- get a member's unitedhealthcare insurance coverage details including plan name, effective dates, and benefit periods.
- list coverage
- claims submission, eligibility verification, and payment management workflows
- health insurance
- get insurance coverage
- patient demographics.
- care management professional accessing member health history for care coordination
- list eob claims history.
- physician or clinical staff verifying eligibility and managing prior authorizations at point of care
- find in network providers
- provider directory search.
- search unitedhealthcare's fhir provider directory for in-network physicians and organizations by name, specialty, or state.
- prior auth coordinator
- unitedhealthcare
- patient
- care coordinator
- list coverage.
- search providers.
- fhir-based interoperability for health information exchange
- unitedhealthcare member accessing their health data through patient portals or apps
- prior authorization, provider directory, and point-of-care clinical support
- medical billing staff managing claim submission, status inquiry, and revenue cycle workflows
- claims
- get patient
- patient access
- fhir explanationofbenefit claims history.
- cms interoperability
- member-facing health data access and patient portal integration
- retrieve unitedhealthcare member demographics from the fhir patient resource.
slug: patient-data-access
source_filename: patient-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UnitedHealthcare Patient Data Access\n  description: Workflow capability for accessing UnitedHealthcare member health data through FHIR R4 Interoperability APIs\n    mandated by CMS. Enables patient portals, health apps, and care coordination tools to retrieve claims history, coverage\n    details, and provider directory information. Supports CMS-9115-F Patient Access rule compliance and Da Vinci PDex Provider\n    Directory implementation.\n  tags:\n  - UnitedHealthcare\n  - FHIR\n  - Patient Access\n  - CMS Interoperability\n  - Provider Directory\n  - Health Data Exchange\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UHC_FHIR_TOKEN: UHC_FHIR_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uhc-fhir\n    baseUri: https://api.uhc.com/fhir/R4\n    description: UnitedHealthcare FHIR R4 Interoperability API.\n    authentication:\n      type: bearer\n      token: '{{UHC_FHIR_TOKEN}}'\n\
  \    resources:\n    - name: patient\n      path: /Patient/{id}\n      description: FHIR Patient resource.\n      operations:\n      - name: get-patient\n        method: GET\n        description: Retrieve FHIR Patient demographics for a member.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: explanation-of-benefit\n      path: /ExplanationOfBenefit\n      description: FHIR ExplanationOfBenefit resources.\n      operations:\n      - name: list-eobs\n        method: GET\n        description: List ExplanationOfBenefit (claims) for a patient.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: Patient resource ID.\n        - name: _lastUpdated\n   \
  \       in: query\n          type: string\n          required: false\n          description: Filter by last updated date.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Claim type filter.\n        - name: _count\n          in: query\n          type: string\n          required: false\n          description: Max results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage\n      path: /Coverage\n      description: FHIR Coverage resources.\n      operations:\n      - name: list-coverage\n        method: GET\n        description: List Coverage resources for a patient.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: Patient resource ID.\n        - name: status\n          in: query\n          type: string\n          required: false\n\
  \          description: Coverage status filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: practitioner\n      path: /Practitioner\n      description: FHIR Practitioner resources.\n      operations:\n      - name: list-practitioners\n        method: GET\n        description: Search provider directory for practitioners.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Provider name search.\n        - name: specialty\n          in: query\n          type: string\n          required: false\n          description: Specialty taxonomy code.\n        - name: address-state\n          in: query\n          type: string\n          required: false\n          description: State filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8081\n    namespace: patient-data-access-api\n    description: Unified REST API for UnitedHealthcare FHIR patient data access.\n    resources:\n    - path: /v1/patient/{id}\n      name: patient\n      description: Patient demographics.\n      operations:\n      - method: GET\n        name: get-patient\n        description: Get FHIR Patient resource.\n        call: uhc-fhir.get-patient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims-history\n      name: claims-history\n      description: FHIR ExplanationOfBenefit claims history.\n      operations:\n      - method: GET\n        name: list-eobs\n        description: List EOB claims history.\n        call: uhc-fhir.list-eobs\n        with:\n          patient: rest.patient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/coverage\n      name: coverage\n      description: Coverage details.\n      operations:\n  \
  \    - method: GET\n        name: list-coverage\n        description: List coverage.\n        call: uhc-fhir.list-coverage\n        with:\n          patient: rest.patient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/providers\n      name: providers\n      description: Provider directory search.\n      operations:\n      - method: GET\n        name: list-practitioners\n        description: Search providers.\n        call: uhc-fhir.list-practitioners\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: patient-data-access-mcp\n    transport: http\n    description: MCP server for AI-assisted UnitedHealthcare FHIR patient data access.\n    tools:\n    - name: get-member-demographics\n      description: Retrieve UnitedHealthcare member demographics from the FHIR Patient resource.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uhc-fhir.get-patient\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claims-history\n      description: Retrieve a member's claims history as FHIR ExplanationOfBenefit resources including service dates, amounts\n        billed, and payment status.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uhc-fhir.list-eobs\n      with:\n        patient: tools.patientId\n        type: tools.claimType\n        _lastUpdated: tools.lastUpdated\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-insurance-coverage\n      description: Get a member's UnitedHealthcare insurance coverage details including plan name, effective dates, and benefit\n        periods.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uhc-fhir.list-coverage\n      with:\n        patient: tools.patientId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-in-network-providers\n\
  \      description: Search UnitedHealthcare's FHIR Provider Directory for in-network physicians and organizations by name,\n        specialty, or state.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uhc-fhir.list-practitioners\n      with:\n        name: tools.providerName\n        specialty: tools.specialty\n        address-state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unitedhealthcare/refs/heads/main/capabilities/patient-data-access.yaml
tags:
- UnitedHealthcare
- FHIR
- Patient Access
- CMS Interoperability
- Provider Directory
- Health Data Exchange
tools:
- description: Retrieve UnitedHealthcare member demographics from the FHIR Patient resource.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-demographics
- description: Retrieve a member's claims history as FHIR ExplanationOfBenefit resources including service dates, amounts billed, and payment status.
  hints:
    openWorld: false
    readOnly: true
  name: get-claims-history
- description: Get a member's UnitedHealthcare insurance coverage details including plan name, effective dates, and benefit periods.
  hints:
    openWorld: false
    readOnly: true
  name: get-insurance-coverage
- description: Search UnitedHealthcare's FHIR Provider Directory for in-network physicians and organizations by name, specialty, or state.
  hints:
    openWorld: true
    readOnly: true
  name: find-in-network-providers
---
