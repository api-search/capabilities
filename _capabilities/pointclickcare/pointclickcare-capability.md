---
categories: []
consumed_apis: []
description: PointClickCare provides EHR and care coordination APIs for long-term and post-acute care (LTPAC) facilities. APIs enable access to resident records, medication administration records, clinical assessments, care plans, and facility data for skilled nursing facilities (SNFs) and senior living communities.
layout: capability
name: PointClickCare Long-Term Care EHR API
operations:
- description: List residents/patients
  method: GET
  name: listpatients
  path: /patients
- description: Get a resident/patient
  method: GET
  name: getpatient
  path: /patients/{patientId}
- description: Get patient vitals
  method: GET
  name: getpatientvitals
  path: /patients/{patientId}/vitals
- description: Get patient medication orders
  method: GET
  name: getpatientmedications
  path: /patients/{patientId}/medications
- description: Get medication administration records
  method: GET
  name: getpatientmar
  path: /patients/{patientId}/medications/mar
- description: List patient assessments
  method: GET
  name: listpatientassessments
  path: /patients/{patientId}/assessments
- description: Get patient diagnoses
  method: GET
  name: getpatientdiagnoses
  path: /patients/{patientId}/diagnoses
- description: List facilities
  method: GET
  name: listfacilities
  path: /facilities
personas: []
provider_name: PointClickCare
provider_slug: pointclickcare
search_terms:
- listpatients
- fhir
- listfacilities
- get a resident/patient
- get patient medication orders
- get patient diagnoses
- getpatientdiagnoses
- healthcare
- list facilities
- getpatientmedications
- get patient vitals
- getpatientvitals
- api
- get medication administration records
- interoperability
- getpatient
- senior care
- ehr
- list residents/patients
- list patient assessments
- post-acute care
- listpatientassessments
- pointclickcare
- long-term care
- getpatientmar
slug: pointclickcare-capability
source_filename: pointclickcare-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PointClickCare Long-Term Care EHR API\n  description: PointClickCare provides EHR and care coordination APIs for long-term and post-acute care (LTPAC) facilities.\n    APIs enable access to resident records, medication administration records, clinical assessments, care plans, and facility\n    data for skilled nursing facilities (SNFs) and senior living communities.\n  tags:\n  - Pointclickcare\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pointclickcare\n    baseUri: https://api.pointclickcare.com/v2\n    description: PointClickCare Long-Term Care EHR API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{POINTCLICKCARE_TOKEN}}'\n    resources:\n    - name: patients\n      path: /patients\n      operations:\n      - name: listpatients\n        method: GET\n        description: List residents/patients\n        inputParameters:\n        - name: facilityId\n\
  \          in: query\n          type: string\n          required: true\n          description: Facility identifier\n        - name: status\n          in: query\n          type: string\n          description: Filter by admission status\n        - name: unitId\n          in: query\n          type: string\n          description: Filter by unit/floor\n        - name: updatedSince\n          in: query\n          type: string\n          description: Return only records updated after this timestamp\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid\n      path: /patients/{patientId}\n      operations:\n      - name: getpatient\n        method: GET\n        description: Get a resident/patient\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid-vitals\n      path: /patients/{patientId}/vitals\n      operations:\n      - name: getpatientvitals\n        method: GET\n        description: Get patient vitals\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: vitalType\n          in: query\n          type: string\n          description: Filter by vital type\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid-medications\n      path: /patients/{patientId}/medications\n      operations:\n      - name: getpatientmedications\n        method: GET\n        description: Get patient medication orders\n        inputParameters:\n        -\
  \ name: status\n          in: query\n          type: string\n          description: Filter by order status\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid-medications-mar\n      path: /patients/{patientId}/medications/mar\n      operations:\n      - name: getpatientmar\n        method: GET\n        description: Get medication administration records\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n        - name: endDate\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid-assessments\n   \
  \   path: /patients/{patientId}/assessments\n      operations:\n      - name: listpatientassessments\n        method: GET\n        description: List patient assessments\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Filter by assessment type\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients-patientid-diagnoses\n      path: /patients/{patientId}/diagnoses\n      operations:\n      - name: getpatientdiagnoses\n        method: GET\n        description: Get patient diagnoses\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: facilities\n      path: /facilities\n      operations:\n      - name: listfacilities\n        method: GET\n        description: List facilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pointclickcare-rest\n    description: REST adapter for PointClickCare Long-Term Care EHR API.\n    resources:\n    - path: /patients\n      name: listpatients\n      operations:\n      - method: GET\n        name: listpatients\n        description: List residents/patients\n        call: pointclickcare.listpatients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patients/{patientId}\n      name: getpatient\n      operations:\n      - method: GET\n        name: getpatient\n        description: Get a resident/patient\n        call: pointclickcare.getpatient\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /patients/{patientId}/vitals\n      name: getpatientvitals\n      operations:\n      - method: GET\n        name: getpatientvitals\n        description: Get patient vitals\n        call: pointclickcare.getpatientvitals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patients/{patientId}/medications\n      name: getpatientmedications\n      operations:\n      - method: GET\n        name: getpatientmedications\n        description: Get patient medication orders\n        call: pointclickcare.getpatientmedications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patients/{patientId}/medications/mar\n      name: getpatientmar\n      operations:\n      - method: GET\n        name: getpatientmar\n        description: Get medication administration records\n        call: pointclickcare.getpatientmar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /patients/{patientId}/assessments\n      name: listpatientassessments\n      operations:\n      - method: GET\n        name: listpatientassessments\n        description: List patient assessments\n        call: pointclickcare.listpatientassessments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patients/{patientId}/diagnoses\n      name: getpatientdiagnoses\n      operations:\n      - method: GET\n        name: getpatientdiagnoses\n        description: Get patient diagnoses\n        call: pointclickcare.getpatientdiagnoses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities\n      name: listfacilities\n      operations:\n      - method: GET\n        name: listfacilities\n        description: List facilities\n        call: pointclickcare.listfacilities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pointclickcare-mcp\n    transport:\
  \ http\n    description: MCP adapter for PointClickCare Long-Term Care EHR API for AI agent use.\n    tools:\n    - name: listpatients\n      description: List residents/patients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.listpatients\n      with:\n        facilityId: tools.facilityId\n        status: tools.status\n        unitId: tools.unitId\n        updatedSince: tools.updatedSince\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: facilityId\n        type: string\n        description: Facility identifier\n        required: true\n      - name: status\n        type: string\n        description: Filter by admission status\n      - name: unitId\n        type: string\n        description: Filter by unit/floor\n      - name: updatedSince\n        type: string\n        description: Return only records updated after this timestamp\n      - name: offset\n        type: integer\n\
  \        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatient\n      description: Get a resident/patient\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.getpatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientvitals\n      description: Get patient vitals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.getpatientvitals\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        vitalType: tools.vitalType\n        limit: tools.limit\n      inputParameters:\n      - name: startDate\n        type: string\n        description: startDate\n      - name: endDate\n        type: string\n        description: endDate\n      - name: vitalType\n        type:\
  \ string\n        description: Filter by vital type\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientmedications\n      description: Get patient medication orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.getpatientmedications\n      with:\n        status: tools.status\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by order status\n      - name: startDate\n        type: string\n        description: startDate\n      - name: endDate\n        type: string\n        description: endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientmar\n      description: Get medication administration records\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: pointclickcare.getpatientmar\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: startDate\n        type: string\n        description: startDate\n        required: true\n      - name: endDate\n        type: string\n        description: endDate\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpatientassessments\n      description: List patient assessments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.listpatientassessments\n      with:\n        type: tools.type\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: type\n        type: string\n        description: Filter by assessment type\n      - name: startDate\n        type: string\n        description: startDate\n      - name: endDate\n\
  \        type: string\n        description: endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatientdiagnoses\n      description: Get patient diagnoses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.getpatientdiagnoses\n      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfacilities\n      description: List facilities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pointclickcare.listfacilities\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    POINTCLICKCARE_TOKEN: POINTCLICKCARE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pointclickcare/refs/heads/main/capabilities/pointclickcare-capability.yaml
tags:
- Pointclickcare
- API
tools:
- description: List residents/patients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpatients
- description: Get a resident/patient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatient
- description: Get patient vitals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientvitals
- description: Get patient medication orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientmedications
- description: Get medication administration records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientmar
- description: List patient assessments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpatientassessments
- description: Get patient diagnoses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatientdiagnoses
- description: List facilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilities
---
