---
categories: []
consumed_apis: []
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
- list member conditions.
- fhir
- get member coverage
- drug formulary.
- care manager
- member
- search providers
- retrieve a unitedhealth group member's fhir patient record with demographics and identifiers.
- care management professional accessing member health data for population health and care coordination
- member conditions.
- get member fhir patient resource.
- provider
- get a member's unitedhealth group insurance coverage including plan name, group number, and benefit period.
- health app developer
- get member coverage details.
- get member health record
- cms-mandated fhir r4 data exchange for patient health records and claims
- network provider search and directory services
- retrieve a member's complete claims history as fhir explanationofbenefit resources including services, diagnoses, and payment details.
- healthcare
- list member conditions
- developer building fhir-compliant applications using unitedhealth group interoperability apis
- member demographics.
- health insurance
- get insurance coverage
- unitedhealth group
- optum
- provider directory.
- cms patient access
- da vinci
- search the unitedhealth group provider directory for in-network physicians, specialists, and organizations by name, npi, specialty, or state.
- get member
- find in network provider
- fhir r4 health data interoperability workflow for member access, claims, coverage, conditions, providers, and formulary
- drug coverage and formulary management
- interoperability
- get member claims history
- search provider directory.
- search drug formulary.
- search formulary
- list member claims as eobs.
- member accessing their own health data through fhir patient access apis
- provider using directory and formulary apis for patient care support
- member coverage.
- health data interoperability
- member-facing health data access and transparency
- check drug formulary
- claims
- list member claims
- member claims history.
- retrieve a member's health conditions and diagnoses from unitedhealth group clinical records and claims data.
- get member conditions
- check unitedhealth group drug formulary coverage tier, prior authorization requirements, and quantity limits for a medication.
slug: health-data-interoperability
source_filename: health-data-interoperability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UnitedHealth Group Health Data Interoperability\n  description: Workflow capability for CMS-compliant health data interoperability using UnitedHealth Group FHIR R4 APIs. Enables\n    patient portals, third-party health apps, care management platforms, and provider tools to access member health records,\n    claims history, coverage details, clinical conditions, provider directory, and drug formulary data. Supports CMS-9115-F\n    Patient Access rule and Da Vinci implementation guides for payer data exchange.\n  tags:\n  - UnitedHealth Group\n  - Optum\n  - FHIR\n  - Health Data Interoperability\n  - CMS Patient Access\n  - Da Vinci\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UH_FHIR_TOKEN: UH_FHIR_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uh-fhir\n    baseUri: https://api.uhc.com/fhir/R4\n    description: UnitedHealth Group FHIR R4 Interoperability API.\n    authentication:\n\
  \      type: bearer\n      token: '{{UH_FHIR_TOKEN}}'\n    resources:\n    - name: patient\n      path: /Patient/{id}\n      description: FHIR Patient resource.\n      operations:\n      - name: get-patient\n        method: GET\n        description: Retrieve FHIR Patient demographics for a member.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: explanation-of-benefit\n      path: /ExplanationOfBenefit\n      description: FHIR ExplanationOfBenefit resources.\n      operations:\n      - name: list-eobs\n        method: GET\n        description: List claims as ExplanationOfBenefit for a patient.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: Patient\
  \ ID.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Claim type filter.\n        - name: _lastUpdated\n          in: query\n          type: string\n          required: false\n          description: Date filter.\n        - name: _count\n          in: query\n          type: string\n          required: false\n          description: Max results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage\n      path: /Coverage\n      description: FHIR Coverage resources.\n      operations:\n      - name: list-coverage\n        method: GET\n        description: List insurance coverage for a patient.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: Patient ID.\n        - name: status\n          in: query\n          type: string\n         \
  \ required: false\n          description: Coverage status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /Condition\n      description: FHIR Condition resources.\n      operations:\n      - name: list-conditions\n        method: GET\n        description: List health conditions for a patient.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: Patient ID.\n        - name: clinical-status\n          in: query\n          type: string\n          required: false\n          description: Clinical status filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: practitioner\n      path: /Practitioner\n      description: FHIR Practitioner provider directory.\n      operations:\n      - name: list-practitioners\n\
  \        method: GET\n        description: Search provider directory for practitioners.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Provider name.\n        - name: identifier\n          in: query\n          type: string\n          required: false\n          description: NPI.\n        - name: specialty\n          in: query\n          type: string\n          required: false\n          description: Specialty code.\n        - name: address-state\n          in: query\n          type: string\n          required: false\n          description: State filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: formulary\n      path: /MedicationKnowledge\n      description: FHIR Drug Formulary.\n      operations:\n      - name: list-formulary\n        method: GET\n        description: Search drug formulary coverage.\n\
  \        inputParameters:\n        - name: code\n          in: query\n          type: string\n          required: false\n          description: RxNorm drug code.\n        - name: drug-name\n          in: query\n          type: string\n          required: false\n          description: Drug name.\n        - name: tier\n          in: query\n          type: string\n          required: false\n          description: Formulary tier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uh-interoperability-api\n    description: Unified REST API for UnitedHealth Group FHIR interoperability.\n    resources:\n    - path: /v1/members/{id}\n      name: member\n      description: Member demographics.\n      operations:\n      - method: GET\n        name: get-member\n        description: Get member FHIR Patient resource.\n        call: uh-fhir.get-patient\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/claims\n      name: claims\n      description: Member claims history.\n      operations:\n      - method: GET\n        name: list-member-claims\n        description: List member claims as EOBs.\n        call: uh-fhir.list-eobs\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/coverage\n      name: coverage\n      description: Member coverage.\n      operations:\n      - method: GET\n        name: get-member-coverage\n        description: Get member coverage details.\n        call: uh-fhir.list-coverage\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/conditions\n      name: conditions\n      description: Member conditions.\n      operations:\n      - method: GET\n        name: list-member-conditions\n        description:\
  \ List member conditions.\n        call: uh-fhir.list-conditions\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/providers\n      name: providers\n      description: Provider directory.\n      operations:\n      - method: GET\n        name: search-providers\n        description: Search provider directory.\n        call: uh-fhir.list-practitioners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/formulary\n      name: formulary\n      description: Drug formulary.\n      operations:\n      - method: GET\n        name: search-formulary\n        description: Search drug formulary.\n        call: uh-fhir.list-formulary\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: uh-interoperability-mcp\n    transport: http\n    description: MCP server for AI-assisted UnitedHealth Group FHIR data access.\n\
  \    tools:\n    - name: get-member-health-record\n      description: Retrieve a UnitedHealth Group member's FHIR Patient record with demographics and identifiers.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uh-fhir.get-patient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-claims-history\n      description: Retrieve a member's complete claims history as FHIR ExplanationOfBenefit resources including services,\n        diagnoses, and payment details.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uh-fhir.list-eobs\n      with:\n        patient: tools.memberId\n        type: tools.claimType\n        _lastUpdated: tools.since\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-insurance-coverage\n      description: Get a member's UnitedHealth Group insurance coverage including plan name, group number, and benefit period.\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: uh-fhir.list-coverage\n      with:\n        patient: tools.memberId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-conditions\n      description: Retrieve a member's health conditions and diagnoses from UnitedHealth Group clinical records and claims\n        data.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uh-fhir.list-conditions\n      with:\n        patient: tools.memberId\n        clinical-status: tools.clinicalStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-in-network-provider\n      description: Search the UnitedHealth Group provider directory for in-network physicians, specialists, and organizations\n        by name, NPI, specialty, or state.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uh-fhir.list-practitioners\n      with:\n        name: tools.providerName\n\
  \        identifier: tools.npi\n        specialty: tools.specialty\n        address-state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-drug-formulary\n      description: Check UnitedHealth Group drug formulary coverage tier, prior authorization requirements, and quantity limits\n        for a medication.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uh-fhir.list-formulary\n      with:\n        code: tools.rxnormCode\n        drug-name: tools.drugName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
