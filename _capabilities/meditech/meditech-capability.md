---
categories: []
consumed_apis: []
description: Meditech Expanse FHIR API enables standards-based interoperability for sharing patient data across healthcare systems. Supports TEFCA-aligned data exchange through the Traverse Exchange national network, connecting over 700 facilities across 41 US states. Built on HL7 FHIR R4 standards.
layout: capability
name: Meditech Expanse FHIR R4 API
operations:
- description: Get FHIR Capability Statement
  method: GET
  name: getcapabilitystatement
  path: /metadata
- description: Search patients
  method: GET
  name: searchpatients
  path: /Patient
- description: Get patient by ID
  method: GET
  name: getpatient
  path: /Patient/{id}
- description: Get patient observations (vital signs, lab results)
  method: GET
  name: getpatientobservations
  path: /Patient/{id}/Observation
- description: Get patient conditions (problem list, diagnoses)
  method: GET
  name: getpatientconditions
  path: /Patient/{id}/Condition
- description: Get patient medication requests
  method: GET
  name: getpatientmedications
  path: /Patient/{id}/MedicationRequest
- description: Get patient allergies and intolerances
  method: GET
  name: getpatientallergies
  path: /Patient/{id}/AllergyIntolerance
- description: Get patient encounters
  method: GET
  name: getpatientencounters
  path: /Patient/{id}/Encounter
- description: Get patient diagnostic reports
  method: GET
  name: getpatientdiagnosticreports
  path: /Patient/{id}/DiagnosticReport
- description: Get all patient data (Patient $everything)
  method: GET
  name: getpatienteverything
  path: /Patient/{id}/$everything
personas: []
provider_name: meditech
provider_slug: meditech
search_terms:
- get patient medication requests
- get patient encounters
- getpatienteverything
- getcapabilitystatement
- api
- get fhir capability statement
- get patient observations (vital signs, lab results)
- searchpatients
- search patients
- get patient by id
- get patient diagnostic reports
- meditech
- getpatientobservations
- get patient allergies and intolerances
- getpatientencounters
- get all patient data (patient $everything)
- getpatientallergies
- getpatientdiagnosticreports
- getpatientconditions
- get patient conditions (problem list, diagnoses)
- getpatientmedications
- getpatient
slug: meditech-capability
source_filename: meditech-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Meditech Expanse FHIR R4 API\n  description: Meditech Expanse FHIR API enables standards-based interoperability for sharing patient data across healthcare\n    systems. Supports TEFCA-aligned data exchange through the Traverse Exchange national network, connecting over 700 facilities\n    across 41 US states. Built on HL7 FHIR R4 standards.\n  tags:\n  - Meditech\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: meditech\n    baseUri: https://yourhospital.meditech.com/fhir/r4\n    description: Meditech Expanse FHIR R4 API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MEDITECH_TOKEN}}'\n    resources:\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: getcapabilitystatement\n        method: GET\n        description: Get FHIR Capability Statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: patient\n      path: /Patient\n      operations:\n      - name: searchpatients\n        method: GET\n        description: Search patients\n        inputParameters:\n        - name: identifier\n          in: query\n          type: string\n          description: MRN or other identifier (e.g., identifier=MR|12345)\n        - name: family\n          in: query\n          type: string\n        - name: given\n          in: query\n          type: string\n        - name: birthdate\n          in: query\n          type: string\n          description: FHIR date parameter (e.g., birthdate=1980-01-01)\n        - name: gender\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n        - name: _format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ patient-id\n      path: /Patient/{id}\n      operations:\n      - name: getpatient\n        method: GET\n        description: Get patient by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-observation\n      path: /Patient/{id}/Observation\n      operations:\n      - name: getpatientobservations\n        method: GET\n        description: Get patient observations (vital signs, lab results)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: category\n          in: query\n          type: string\n          description: Filter by category (vital-signs, laboratory, imaging, etc.)\n        - name: code\n          in: query\n          type: string\n          description: LOINC code filter\n  \
  \      - name: date\n          in: query\n          type: string\n          description: Date range (e.g., date=ge2024-01-01&date=le2024-12-31)\n        - name: _count\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-condition\n      path: /Patient/{id}/Condition\n      operations:\n      - name: getpatientconditions\n        method: GET\n        description: Get patient conditions (problem list, diagnoses)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: clinical-status\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n          description: problem-list-item or encounter-diagnosis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: patient-id-medicationrequest\n      path: /Patient/{id}/MedicationRequest\n      operations:\n      - name: getpatientmedications\n        method: GET\n        description: Get patient medication requests\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n        - name: intent\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-allergyintolerance\n      path: /Patient/{id}/AllergyIntolerance\n      operations:\n      - name: getpatientallergies\n        method: GET\n        description: Get patient allergies and intolerances\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: clinical-status\n       \
  \   in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-encounter\n      path: /Patient/{id}/Encounter\n      operations:\n      - name: getpatientencounters\n        method: GET\n        description: Get patient encounters\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n        - name: date\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-diagnosticreport\n      path: /Patient/{id}/DiagnosticReport\n      operations:\n      - name: getpatientdiagnosticreports\n        method: GET\n        description: Get\
  \ patient diagnostic reports\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: category\n          in: query\n          type: string\n          description: LAB, RAD, etc.\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-everything\n      path: /Patient/{id}/$everything\n      operations:\n      - name: getpatienteverything\n        method: GET\n        description: Get all patient data (Patient $everything)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: meditech-rest\n    description: REST adapter for Meditech Expanse FHIR R4 API.\n    resources:\n    - path: /metadata\n      name: getcapabilitystatement\n      operations:\n      - method: GET\n        name: getcapabilitystatement\n        description: Get FHIR Capability Statement\n        call: meditech.getcapabilitystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient\n      name: searchpatients\n      operations:\n      - method: GET\n        name: searchpatients\n        description: Search patients\n        call: meditech.searchpatients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: getpatient\n      operations:\n      - method: GET\n        name: getpatient\n        description: Get patient by ID\n        call: meditech.getpatient\n        with:\n          id:\
  \ rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/Observation\n      name: getpatientobservations\n      operations:\n      - method: GET\n        name: getpatientobservations\n        description: Get patient observations (vital signs, lab results)\n        call: meditech.getpatientobservations\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/Condition\n      name: getpatientconditions\n      operations:\n      - method: GET\n        name: getpatientconditions\n        description: Get patient conditions (problem list, diagnoses)\n        call: meditech.getpatientconditions\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/MedicationRequest\n      name: getpatientmedications\n      operations:\n      - method: GET\n        name: getpatientmedications\n\
  \        description: Get patient medication requests\n        call: meditech.getpatientmedications\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/AllergyIntolerance\n      name: getpatientallergies\n      operations:\n      - method: GET\n        name: getpatientallergies\n        description: Get patient allergies and intolerances\n        call: meditech.getpatientallergies\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/Encounter\n      name: getpatientencounters\n      operations:\n      - method: GET\n        name: getpatientencounters\n        description: Get patient encounters\n        call: meditech.getpatientencounters\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/DiagnosticReport\n      name: getpatientdiagnosticreports\n\
  \      operations:\n      - method: GET\n        name: getpatientdiagnosticreports\n        description: Get patient diagnostic reports\n        call: meditech.getpatientdiagnosticreports\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/$everything\n      name: getpatienteverything\n      operations:\n      - method: GET\n        name: getpatienteverything\n        description: Get all patient data (Patient $everything)\n        call: meditech.getpatienteverything\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: meditech-mcp\n    transport: http\n    description: MCP adapter for Meditech Expanse FHIR R4 API for AI agent use.\n    tools:\n    - name: getcapabilitystatement\n      description: Get FHIR Capability Statement\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: meditech.getcapabilitystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpatients\n      description: Search patients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.searchpatients\n      with:\n        identifier: tools.identifier\n        family: tools.family\n        given: tools.given\n        birthdate: tools.birthdate\n        gender: tools.gender\n        _count: tools._count\n        _format: tools._format\n      inputParameters:\n      - name: identifier\n        type: string\n        description: MRN or other identifier (e.g., identifier=MR|12345)\n      - name: family\n        type: string\n        description: family\n      - name: given\n        type: string\n        description: given\n      - name: birthdate\n        type: string\n        description: FHIR date parameter (e.g., birthdate=1980-01-01)\n      - name: gender\n\
  \        type: string\n        description: gender\n      - name: _count\n        type: integer\n        description: _count\n      - name: _format\n        type: string\n        description: _format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatient\n      description: Get patient by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatient\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientobservations\n      description: Get patient observations (vital signs, lab results)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientobservations\n      with:\n        id: tools.id\n        category: tools.category\n        code:\
  \ tools.code\n        date: tools.date\n        _count: tools._count\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: category\n        type: string\n        description: Filter by category (vital-signs, laboratory, imaging, etc.)\n      - name: code\n        type: string\n        description: LOINC code filter\n      - name: date\n        type: string\n        description: Date range (e.g., date=ge2024-01-01&date=le2024-12-31)\n      - name: _count\n        type: integer\n        description: _count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientconditions\n      description: Get patient conditions (problem list, diagnoses)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientconditions\n      with:\n        id: tools.id\n        clinical-status: tools.clinical-status\n        category: tools.category\n\
  \      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: clinical-status\n        type: string\n        description: clinical-status\n      - name: category\n        type: string\n        description: problem-list-item or encounter-diagnosis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientmedications\n      description: Get patient medication requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientmedications\n      with:\n        id: tools.id\n        status: tools.status\n        intent: tools.intent\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: status\n        type: string\n        description: status\n      - name: intent\n        type: string\n        description: intent\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getpatientallergies\n      description: Get patient allergies and intolerances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientallergies\n      with:\n        id: tools.id\n        clinical-status: tools.clinical-status\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: clinical-status\n        type: string\n        description: clinical-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientencounters\n      description: Get patient encounters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientencounters\n      with:\n        id: tools.id\n        status: tools.status\n        date: tools.date\n        _count: tools._count\n      inputParameters:\n      - name: id\n        type: string\n\
  \        description: id\n        required: true\n      - name: status\n        type: string\n        description: status\n      - name: date\n        type: string\n        description: date\n      - name: _count\n        type: integer\n        description: _count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientdiagnosticreports\n      description: Get patient diagnostic reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatientdiagnosticreports\n      with:\n        id: tools.id\n        category: tools.category\n        date: tools.date\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: category\n        type: string\n        description: LAB, RAD, etc.\n      - name: date\n        type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: getpatienteverything\n      description: Get all patient data (Patient $everything)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meditech.getpatienteverything\n      with:\n        id: tools.id\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MEDITECH_TOKEN: MEDITECH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/meditech/refs/heads/main/capabilities/meditech-capability.yaml
tags:
- Meditech
- API
tools:
- description: Get FHIR Capability Statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilitystatement
- description: Search patients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpatients
- description: Get patient by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatient
- description: Get patient observations (vital signs, lab results)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientobservations
- description: Get patient conditions (problem list, diagnoses)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientconditions
- description: Get patient medication requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientmedications
- description: Get patient allergies and intolerances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientallergies
- description: Get patient encounters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientencounters
- description: Get patient diagnostic reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientdiagnosticreports
- description: Get all patient data (Patient $everything)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatienteverything
---
