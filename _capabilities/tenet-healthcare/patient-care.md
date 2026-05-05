---
categories: []
consumed_apis:
- tenet-fhir
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
- hospitals
- clinical observations and test results
- clinical document references
- list active diagnoses and health conditions for a patient
- get patient
- patient medication prescriptions
- list clinical observations (vitals, labs, imaging)
- clinical data
- search appointments across the tenet health network by patient, date, or facility
- search appointments
- list clinical documents (notes, reports, summaries)
- list appointments for a patient
- appointment search
- list patient medication prescriptions
- fhir
- healthcare
- list clinical documents including discharge summaries, notes, and radiology reports
- patient appointments
- patient diagnoses and health conditions
- patient demographic record
- list scheduled appointments for a patient, with optional status and date filters
- get patient demographic and administrative information
- list patient diagnoses and health conditions
- get a patient's demographic and administrative information
- get laboratory test results for a patient
- list current medication prescriptions for a patient
- fortune 500
- ambulatory surgery centers
- list clinical documents
- list medications
- list patient medications
- list observations
- list patient conditions
- search appointments by patient, date, or practitioner
- appointment scheduling
- care coordination
- list vital signs
- get vital sign observations for a patient (blood pressure, heart rate, temperature, etc.)
- list lab results
- list conditions
- list documents
- list patient appointments
- list appointments
- patient care
- revenue cycle management
slug: patient-care
source_filename: patient-care.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tenet Healthcare Patient Care\"\n  description: \"Patient care coordination workflow combining FHIR R4 APIs for patient records, appointment management, clinical data access, and care plan coordination. Used by patient portals, care coordinators, and clinical staff to manage the patient healthcare journey across Tenet Health facilities.\"\n  tags:\n    - Healthcare\n    - Patient Care\n    - FHIR\n    - Appointment Scheduling\n    - Clinical Data\n    - Care Coordination\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TENET_FHIR_TOKEN: TENET_FHIR_TOKEN\n\ncapability:\n  consumes:\n    - import: tenet-fhir\n      location: ./shared/tenet-fhir.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: patient-care-api\n      description: \"Unified REST API for Tenet Healthcare patient care coordination.\"\n      resources:\n        - path: /v1/patients/{patientId}\n\
  \          name: patient\n          description: \"Patient demographic record\"\n          operations:\n            - method: GET\n              name: get-patient\n              description: \"Get patient demographic and administrative information\"\n              call: \"tenet-fhir.get-patient\"\n              with:\n                id: \"rest.patientId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{patientId}/appointments\n          name: appointments\n          description: \"Patient appointments\"\n          operations:\n            - method: GET\n              name: list-appointments\n              description: \"List appointments for a patient\"\n              call: \"tenet-fhir.list-patient-appointments\"\n              with:\n                id: \"rest.patientId\"\n                status: \"rest.status\"\n                date: \"rest.date\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n        - path: /v1/appointments\n          name: appointment-search\n          description: \"Appointment search\"\n          operations:\n            - method: GET\n              name: search-appointments\n              description: \"Search appointments by patient, date, or practitioner\"\n              call: \"tenet-fhir.search-appointments\"\n              with:\n                patient: \"rest.patient\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{patientId}/observations\n          name: observations\n          description: \"Clinical observations and test results\"\n          operations:\n            - method: GET\n              name: list-observations\n              description: \"List clinical observations (vitals, labs, imaging)\"\n              call: \"tenet-fhir.list-patient-observations\"\n   \
  \           with:\n                id: \"rest.patientId\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{patientId}/conditions\n          name: conditions\n          description: \"Patient diagnoses and health conditions\"\n          operations:\n            - method: GET\n              name: list-conditions\n              description: \"List patient diagnoses and health conditions\"\n              call: \"tenet-fhir.list-patient-conditions\"\n              with:\n                id: \"rest.patientId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{patientId}/medications\n          name: medications\n          description: \"Patient medication prescriptions\"\n          operations:\n            - method: GET\n              name: list-medications\n              description:\
  \ \"List patient medication prescriptions\"\n              call: \"tenet-fhir.list-patient-medications\"\n              with:\n                id: \"rest.patientId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{patientId}/documents\n          name: documents\n          description: \"Clinical document references\"\n          operations:\n            - method: GET\n              name: list-documents\n              description: \"List clinical documents (notes, reports, summaries)\"\n              call: \"tenet-fhir.list-patient-documents\"\n              with:\n                id: \"rest.patientId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: patient-care-mcp\n      transport: http\n      description: \"MCP server for AI-assisted patient care coordination\
  \ at Tenet Health.\"\n      tools:\n        - name: get-patient\n          description: \"Get a patient's demographic and administrative information\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.get-patient\"\n          with:\n            id: \"tools.patientId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-patient-appointments\n          description: \"List scheduled appointments for a patient, with optional status and date filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.list-patient-appointments\"\n          with:\n            id: \"tools.patientId\"\n            status: \"tools.status\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-appointments\n          description: \"Search appointments across\
  \ the Tenet Health network by patient, date, or facility\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.search-appointments\"\n          with:\n            patient: \"tools.patient\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vital-signs\n          description: \"Get vital sign observations for a patient (blood pressure, heart rate, temperature, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.list-patient-observations\"\n          with:\n            id: \"tools.patientId\"\n            category: \"vital-signs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-lab-results\n          description: \"Get laboratory test results for a patient\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: false\n          call: \"tenet-fhir.list-patient-observations\"\n          with:\n            id: \"tools.patientId\"\n            category: \"laboratory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-patient-conditions\n          description: \"List active diagnoses and health conditions for a patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.list-patient-conditions\"\n          with:\n            id: \"tools.patientId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-patient-medications\n          description: \"List current medication prescriptions for a patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.list-patient-medications\"\n          with:\n            id: \"tools.patientId\"\n            status: \"active\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clinical-documents\n          description: \"List clinical documents including discharge summaries, notes, and radiology reports\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tenet-fhir.list-patient-documents\"\n          with:\n            id: \"tools.patientId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
