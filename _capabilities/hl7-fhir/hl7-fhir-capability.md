---
categories: []
consumed_apis: []
description: HL7 FHIR R4 (v4.0.1) RESTful API for healthcare data exchange. Provides access to patient demographics, clinical observations, conditions, medications, encounters, care plans, and diagnostic reports. Implements the FHIR REST specification including CRUD operations, search parameters, history, and batch/ transaction bundles. SMART on FHIR OAuth 2.0 authorization required.
layout: capability
name: HL7 FHIR R4 Healthcare API
operations:
- description: Search patients
  method: GET
  name: searchpatient
  path: /Patient
- description: Create a patient
  method: POST
  name: createpatient
  path: /Patient
- description: Read a patient
  method: GET
  name: readpatient
  path: /Patient/{id}
- description: Update a patient
  method: PUT
  name: updatepatient
  path: /Patient/{id}
- description: Search observations
  method: GET
  name: searchobservation
  path: /Observation
- description: Read an observation
  method: GET
  name: readobservation
  path: /Observation/{id}
- description: Search conditions
  method: GET
  name: searchcondition
  path: /Condition
- description: Search medication requests
  method: GET
  name: searchmedicationrequest
  path: /MedicationRequest
- description: Search encounters
  method: GET
  name: searchencounter
  path: /Encounter
- description: Process batch or transaction
  method: POST
  name: processbatch
  path: /
- description: Get server capability statement
  method: GET
  name: getcapabilitystatement
  path: /metadata
personas: []
provider_name: HL7 FHIR
provider_slug: hl7-fhir
search_terms:
- searchpatient
- fhir
- processbatch
- clinical
- process batch or transaction
- searchmedicationrequest
- search patients
- search observations
- search encounters
- hl7
- readpatient
- updatepatient
- searchobservation
- healthcare
- getcapabilitystatement
- searchcondition
- read a patient
- create a patient
- update a patient
- api
- interoperability
- searchencounter
- createpatient
- search conditions
- get server capability statement
- readobservation
- search medication requests
- read an observation
slug: hl7-fhir-capability
source_filename: hl7-fhir-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HL7 FHIR R4 Healthcare API\n  description: HL7 FHIR R4 (v4.0.1) RESTful API for healthcare data exchange. Provides access to patient demographics, clinical\n    observations, conditions, medications, encounters, care plans, and diagnostic reports. Implements the FHIR REST specification\n    including CRUD operations, search parameters, history, and batch/ transaction bundles. SMART on FHIR OAuth 2.0 authorization\n    required.\n  tags:\n  - Hl7\n  - Fhir\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hl7-fhir\n    baseUri: https://fhir-server.example.com/fhir/R4\n    description: HL7 FHIR R4 Healthcare API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HL7_FHIR_TOKEN}}'\n    resources:\n    - name: patient\n      path: /Patient\n      operations:\n      - name: searchpatient\n        method: GET\n        description: Search patients\n        inputParameters:\n\
  \        - name: _id\n          in: query\n          type: string\n          description: Logical id of the patient\n        - name: identifier\n          in: query\n          type: string\n          description: Patient identifier (e.g., \"http://hospital.example.org/patients|12345\")\n        - name: family\n          in: query\n          type: string\n          description: A portion of the family name of the patient\n        - name: given\n          in: query\n          type: string\n          description: A portion of the given name of the patient\n        - name: birthdate\n          in: query\n          type: string\n          description: The patient's date of birth (e.g., \"1990-01-15\" or \"ge1990\")\n        - name: gender\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n          description: Number of results per page\n        - name: _sort\n          in: query\n          type: string\n          description:\
  \ Sort criteria (e.g., \"family,-birthdate\")\n        - name: _include\n          in: query\n          type: string\n          description: Include related resources (e.g., \"Patient:general-practitioner\")\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpatient\n        method: POST\n        description: Create a patient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id\n      path: /Patient/{id}\n      operations:\n      - name: readpatient\n        method: GET\n        description: Read a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Logical ID of the patient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updatepatient\n        method: PUT\n        description: Update a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observation\n      path: /Observation\n      operations:\n      - name: searchobservation\n        method: GET\n        description: Search observations\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Patient reference (e.g., \"Patient/123\")\n        - name: category\n          in: query\n          type: string\n          description: Observation category (vital-signs, laboratory, social-history, etc.)\n        - name: code\n          in: query\n          type: string\n          description: LOINC code or system|code (e.g., \"8302-2\" for body height)\n        - name: date\n\
  \          in: query\n          type: string\n          description: Observation date filter (e.g., \"ge2024-01-01\")\n        - name: status\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n        - name: _sort\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observation-id\n      path: /Observation/{id}\n      operations:\n      - name: readobservation\n        method: GET\n        description: Read an observation\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /Condition\n      operations:\n      - name: searchcondition\n        method: GET\n        description:\
  \ Search conditions\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Patient reference\n        - name: clinical-status\n          in: query\n          type: string\n        - name: code\n          in: query\n          type: string\n          description: ICD-10 or SNOMED CT code\n        - name: category\n          in: query\n          type: string\n        - name: onset-date\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medicationrequest\n      path: /MedicationRequest\n      operations:\n      - name: searchmedicationrequest\n        method: GET\n        description: Search medication requests\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required:\
  \ true\n        - name: status\n          in: query\n          type: string\n        - name: medication\n          in: query\n          type: string\n        - name: authoredon\n          in: query\n          type: string\n        - name: _count\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encounter\n      path: /Encounter\n      operations:\n      - name: searchencounter\n        method: GET\n        description: Search encounters\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: class\n          in: query\n          type: string\n          description: Encounter class code (AMB, IMP, EMER, etc.)\n        - name: date\n          in: query\n          type: string\n        - name: _count\n          in: query\n        \
  \  type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource\n      path: /\n      operations:\n      - name: processbatch\n        method: POST\n        description: Process batch or transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: getcapabilitystatement\n        method: GET\n        description: Get server capability statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hl7-fhir-rest\n    description: REST adapter for HL7 FHIR R4 Healthcare API.\n    resources:\n    - path: /Patient\n      name: searchpatient\n      operations:\n      - method: GET\n        name: searchpatient\n\
  \        description: Search patients\n        call: hl7-fhir.searchpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient\n      name: createpatient\n      operations:\n      - method: POST\n        name: createpatient\n        description: Create a patient\n        call: hl7-fhir.createpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: readpatient\n      operations:\n      - method: GET\n        name: readpatient\n        description: Read a patient\n        call: hl7-fhir.readpatient\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: updatepatient\n      operations:\n      - method: PUT\n        name: updatepatient\n        description: Update a patient\n        call: hl7-fhir.updatepatient\n        with:\n          id: rest.id\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /Observation\n      name: searchobservation\n      operations:\n      - method: GET\n        name: searchobservation\n        description: Search observations\n        call: hl7-fhir.searchobservation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Observation/{id}\n      name: readobservation\n      operations:\n      - method: GET\n        name: readobservation\n        description: Read an observation\n        call: hl7-fhir.readobservation\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Condition\n      name: searchcondition\n      operations:\n      - method: GET\n        name: searchcondition\n        description: Search conditions\n        call: hl7-fhir.searchcondition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MedicationRequest\n      name: searchmedicationrequest\n\
  \      operations:\n      - method: GET\n        name: searchmedicationrequest\n        description: Search medication requests\n        call: hl7-fhir.searchmedicationrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Encounter\n      name: searchencounter\n      operations:\n      - method: GET\n        name: searchencounter\n        description: Search encounters\n        call: hl7-fhir.searchencounter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /\n      name: processbatch\n      operations:\n      - method: POST\n        name: processbatch\n        description: Process batch or transaction\n        call: hl7-fhir.processbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata\n      name: getcapabilitystatement\n      operations:\n      - method: GET\n        name: getcapabilitystatement\n        description: Get server capability statement\n       \
  \ call: hl7-fhir.getcapabilitystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hl7-fhir-mcp\n    transport: http\n    description: MCP adapter for HL7 FHIR R4 Healthcare API for AI agent use.\n    tools:\n    - name: searchpatient\n      description: Search patients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.searchpatient\n      with:\n        _id: tools._id\n        identifier: tools.identifier\n        family: tools.family\n        given: tools.given\n        birthdate: tools.birthdate\n        gender: tools.gender\n        _count: tools._count\n        _sort: tools._sort\n        _include: tools._include\n      inputParameters:\n      - name: _id\n        type: string\n        description: Logical id of the patient\n      - name: identifier\n        type: string\n        description: Patient identifier (e.g., \"http://hospital.example.org/patients|12345\"\
  )\n      - name: family\n        type: string\n        description: A portion of the family name of the patient\n      - name: given\n        type: string\n        description: A portion of the given name of the patient\n      - name: birthdate\n        type: string\n        description: The patient's date of birth (e.g., \"1990-01-15\" or \"ge1990\")\n      - name: gender\n        type: string\n        description: gender\n      - name: _count\n        type: integer\n        description: Number of results per page\n      - name: _sort\n        type: string\n        description: Sort criteria (e.g., \"family,-birthdate\")\n      - name: _include\n        type: string\n        description: Include related resources (e.g., \"Patient:general-practitioner\")\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpatient\n      description: Create a patient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ hl7-fhir.createpatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readpatient\n      description: Read a patient\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.readpatient\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Logical ID of the patient\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepatient\n      description: Update a patient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.updatepatient\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchobservation\n      description: Search observations\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.searchobservation\n      with:\n        patient: tools.patient\n        category: tools.category\n        code: tools.code\n        date: tools.date\n        status: tools.status\n        _count: tools._count\n        _sort: tools._sort\n      inputParameters:\n      - name: patient\n        type: string\n        description: Patient reference (e.g., \"Patient/123\")\n      - name: category\n        type: string\n        description: Observation category (vital-signs, laboratory, social-history, etc.)\n      - name: code\n        type: string\n        description: LOINC code or system|code (e.g., \"8302-2\" for body height)\n      - name: date\n        type: string\n        description: Observation date filter (e.g., \"ge2024-01-01\")\n      - name: status\n        type: string\n        description: status\n      - name: _count\n        type: integer\n        description: _count\n\
  \      - name: _sort\n        type: string\n        description: _sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readobservation\n      description: Read an observation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.readobservation\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcondition\n      description: Search conditions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.searchcondition\n      with:\n        patient: tools.patient\n        clinical-status: tools.clinical-status\n        code: tools.code\n        category: tools.category\n        onset-date: tools.onset-date\n        _count: tools._count\n      inputParameters:\n  \
  \    - name: patient\n        type: string\n        description: Patient reference\n      - name: clinical-status\n        type: string\n        description: clinical-status\n      - name: code\n        type: string\n        description: ICD-10 or SNOMED CT code\n      - name: category\n        type: string\n        description: category\n      - name: onset-date\n        type: string\n        description: onset-date\n      - name: _count\n        type: integer\n        description: _count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmedicationrequest\n      description: Search medication requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.searchmedicationrequest\n      with:\n        patient: tools.patient\n        status: tools.status\n        medication: tools.medication\n        authoredon: tools.authoredon\n        _count: tools._count\n      inputParameters:\n      - name:\
  \ patient\n        type: string\n        description: patient\n        required: true\n      - name: status\n        type: string\n        description: status\n      - name: medication\n        type: string\n        description: medication\n      - name: authoredon\n        type: string\n        description: authoredon\n      - name: _count\n        type: integer\n        description: _count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchencounter\n      description: Search encounters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.searchencounter\n      with:\n        patient: tools.patient\n        status: tools.status\n        class: tools.class\n        date: tools.date\n        _count: tools._count\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: status\n        type: string\n        description: status\n      -\
  \ name: class\n        type: string\n        description: Encounter class code (AMB, IMP, EMER, etc.)\n      - name: date\n        type: string\n        description: date\n      - name: _count\n        type: integer\n        description: _count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: processbatch\n      description: Process batch or transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hl7-fhir.processbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcapabilitystatement\n      description: Get server capability statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hl7-fhir.getcapabilitystatement\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HL7_FHIR_TOKEN: HL7_FHIR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hl7-fhir/refs/heads/main/capabilities/hl7-fhir-capability.yaml
tags:
- Hl7
- Fhir
- API
tools:
- description: Search patients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpatient
- description: Create a patient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpatient
- description: Read a patient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readpatient
- description: Update a patient
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepatient
- description: Search observations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchobservation
- description: Read an observation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readobservation
- description: Search conditions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcondition
- description: Search medication requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmedicationrequest
- description: Search encounters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchencounter
- description: Process batch or transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: processbatch
- description: Get server capability statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilitystatement
---
