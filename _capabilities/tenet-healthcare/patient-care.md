---
categories: []
consumed_apis: []
description: Patient care coordination workflow combining FHIR R4 APIs for patient records, appointment management, clinical data access, and care plan coordination. Used by patient portals, care coordinators, and clinical staff to manage the patient healthcare journey across Tenet Health facilities.
layout: capability
name: Tenet Healthcare Patient Care
operations:
- description: Get patient demographic and administrative information
  method: GET
  name: get-patient
  path: /v1/patients/{patientId}
- description: List appointments for a patient
  method: GET
  name: list-appointments
  path: /v1/patients/{patientId}/appointments
- description: Search appointments by patient, date, or practitioner
  method: GET
  name: search-appointments
  path: /v1/appointments
- description: List clinical observations (vitals, labs, imaging)
  method: GET
  name: list-observations
  path: /v1/patients/{patientId}/observations
- description: List patient diagnoses and health conditions
  method: GET
  name: list-conditions
  path: /v1/patients/{patientId}/conditions
- description: List patient medication prescriptions
  method: GET
  name: list-medications
  path: /v1/patients/{patientId}/medications
- description: List clinical documents (notes, reports, summaries)
  method: GET
  name: list-documents
  path: /v1/patients/{patientId}/documents
personas: []
provider_name: Tenet Healthcare
provider_slug: tenet-healthcare
search_terms:
- list patient appointments
- patient diagnoses and health conditions
- care coordination
- get patient
- list patient conditions
- appointment search
- hospitals
- search appointments across the tenet health network by patient, date, or facility
- list observations
- fhir
- list scheduled appointments for a patient, with optional status and date filters
- patient care
- clinical document references
- healthcare
- revenue cycle management
- get a patient's demographic and administrative information
- list appointments
- clinical observations and test results
- search appointments
- list patient medication prescriptions
- list lab results
- clinical data
- get vital sign observations for a patient (blood pressure, heart rate, temperature, etc.)
- ambulatory surgery centers
- appointment scheduling
- patient medication prescriptions
- search appointments by patient, date, or practitioner
- list appointments for a patient
- list medications
- patient demographic record
- list conditions
- list clinical documents including discharge summaries, notes, and radiology reports
- patient appointments
- get laboratory test results for a patient
- list patient diagnoses and health conditions
- list documents
- get patient demographic and administrative information
- list clinical documents (notes, reports, summaries)
- list current medication prescriptions for a patient
- list clinical documents
- list vital signs
- list clinical observations (vitals, labs, imaging)
- list active diagnoses and health conditions for a patient
- fortune 500
- list patient medications
slug: patient-care
source_filename: patient-care.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tenet Healthcare Patient Care\n  description: Patient care coordination workflow combining FHIR R4 APIs for patient records, appointment management, clinical\n    data access, and care plan coordination. Used by patient portals, care coordinators, and clinical staff to manage the\n    patient healthcare journey across Tenet Health facilities.\n  tags:\n  - Healthcare\n  - Patient Care\n  - FHIR\n  - Appointment Scheduling\n  - Clinical Data\n  - Care Coordination\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TENET_FHIR_TOKEN: TENET_FHIR_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tenet-fhir\n    baseUri: https://api.tenethealth.com/fhir/r4\n    description: Tenet Healthcare FHIR R4 API\n    authentication:\n      type: bearer\n      token: '{{TENET_FHIR_TOKEN}}'\n    resources:\n    - name: patient\n      path: /Patient/{id}\n      description: Patient demographic information\n\
  \      operations:\n      - name: get-patient\n        method: GET\n        description: Get patient record\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-appointments\n      path: /Patient/{id}/Appointment\n      description: Patient appointments\n      operations:\n      - name: list-patient-appointments\n        method: GET\n        description: List appointments for a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Appointment status filter\n        - name: date\n          in: query\n\
  \          type: string\n          required: false\n          description: Date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appointments\n      path: /Appointment\n      description: Appointment search\n      operations:\n      - name: search-appointments\n        method: GET\n        description: Search appointments\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: false\n          description: Patient reference\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Status filter\n        - name: _count\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-observations\n\
  \      path: /Patient/{id}/Observation\n      description: Patient clinical observations\n      operations:\n      - name: list-patient-observations\n        method: GET\n        description: List clinical observations for a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Observation category (vital-signs, laboratory)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-conditions\n      path: /Patient/{id}/Condition\n      description: Patient diagnoses and conditions\n      operations:\n      - name: list-patient-conditions\n        method: GET\n        description: List conditions for a patient\n        inputParameters:\n        - name: id\n     \
  \     in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        - name: clinical-status\n          in: query\n          type: string\n          required: false\n          description: Condition status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-medications\n      path: /Patient/{id}/MedicationRequest\n      description: Patient medication requests\n      operations:\n      - name: list-patient-medications\n        method: GET\n        description: List medications for a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Medication status filter\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-documents\n      path: /Patient/{id}/DocumentReference\n      description: Patient clinical documents\n      operations:\n      - name: list-patient-documents\n        method: GET\n        description: List clinical document references for a patient\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Patient FHIR resource ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: patient-care-api\n    description: Unified REST API for Tenet Healthcare patient care coordination.\n    resources:\n    - path: /v1/patients/{patientId}\n      name: patient\n      description: Patient demographic record\n      operations:\n      - method: GET\n        name: get-patient\n\
  \        description: Get patient demographic and administrative information\n        call: tenet-fhir.get-patient\n        with:\n          id: rest.patientId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patients/{patientId}/appointments\n      name: appointments\n      description: Patient appointments\n      operations:\n      - method: GET\n        name: list-appointments\n        description: List appointments for a patient\n        call: tenet-fhir.list-patient-appointments\n        with:\n          id: rest.patientId\n          status: rest.status\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/appointments\n      name: appointment-search\n      description: Appointment search\n      operations:\n      - method: GET\n        name: search-appointments\n        description: Search appointments by patient, date, or practitioner\n        call: tenet-fhir.search-appointments\n\
  \        with:\n          patient: rest.patient\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patients/{patientId}/observations\n      name: observations\n      description: Clinical observations and test results\n      operations:\n      - method: GET\n        name: list-observations\n        description: List clinical observations (vitals, labs, imaging)\n        call: tenet-fhir.list-patient-observations\n        with:\n          id: rest.patientId\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patients/{patientId}/conditions\n      name: conditions\n      description: Patient diagnoses and health conditions\n      operations:\n      - method: GET\n        name: list-conditions\n        description: List patient diagnoses and health conditions\n        call: tenet-fhir.list-patient-conditions\n        with:\n          id: rest.patientId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patients/{patientId}/medications\n      name: medications\n      description: Patient medication prescriptions\n      operations:\n      - method: GET\n        name: list-medications\n        description: List patient medication prescriptions\n        call: tenet-fhir.list-patient-medications\n        with:\n          id: rest.patientId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patients/{patientId}/documents\n      name: documents\n      description: Clinical document references\n      operations:\n      - method: GET\n        name: list-documents\n        description: List clinical documents (notes, reports, summaries)\n        call: tenet-fhir.list-patient-documents\n        with:\n          id: rest.patientId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: patient-care-mcp\n    transport: http\n    description: MCP server for AI-assisted patient care coordination at Tenet Health.\n    tools:\n    - name: get-patient\n      description: Get a patient's demographic and administrative information\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.get-patient\n      with:\n        id: tools.patientId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-patient-appointments\n      description: List scheduled appointments for a patient, with optional status and date filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-appointments\n      with:\n        id: tools.patientId\n        status: tools.status\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-appointments\n      description: Search appointments across the Tenet Health network by patient,\
  \ date, or facility\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.search-appointments\n      with:\n        patient: tools.patient\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vital-signs\n      description: Get vital sign observations for a patient (blood pressure, heart rate, temperature, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-observations\n      with:\n        id: tools.patientId\n        category: vital-signs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lab-results\n      description: Get laboratory test results for a patient\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-observations\n      with:\n        id: tools.patientId\n        category: laboratory\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: list-patient-conditions\n      description: List active diagnoses and health conditions for a patient\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-conditions\n      with:\n        id: tools.patientId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-patient-medications\n      description: List current medication prescriptions for a patient\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-medications\n      with:\n        id: tools.patientId\n        status: active\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clinical-documents\n      description: List clinical documents including discharge summaries, notes, and radiology reports\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tenet-fhir.list-patient-documents\n      with:\n        id: tools.patientId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tenet-healthcare/refs/heads/main/capabilities/patient-care.yaml
tags:
- Healthcare
- Patient Care
- FHIR
- Appointment Scheduling
- Clinical Data
- Care Coordination
tools:
- description: Get a patient's demographic and administrative information
  hints:
    openWorld: false
    readOnly: true
  name: get-patient
- description: List scheduled appointments for a patient, with optional status and date filters
  hints:
    openWorld: false
    readOnly: true
  name: list-patient-appointments
- description: Search appointments across the Tenet Health network by patient, date, or facility
  hints:
    openWorld: false
    readOnly: true
  name: search-appointments
- description: Get vital sign observations for a patient (blood pressure, heart rate, temperature, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-vital-signs
- description: Get laboratory test results for a patient
  hints:
    openWorld: false
    readOnly: true
  name: list-lab-results
- description: List active diagnoses and health conditions for a patient
  hints:
    openWorld: false
    readOnly: true
  name: list-patient-conditions
- description: List current medication prescriptions for a patient
  hints:
    openWorld: false
    readOnly: true
  name: list-patient-medications
- description: List clinical documents including discharge summaries, notes, and radiology reports
  hints:
    openWorld: false
    readOnly: true
  name: list-clinical-documents
---
