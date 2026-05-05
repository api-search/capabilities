---
api_specs:
- filename: varian-aria-fhir-openapi.yml
  format: yaml
  label: varian-fhir
  slug: varian-fhir
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/varian-medical-systems/refs/heads/main/openapi/varian-aria-fhir-openapi.yml
categories: []
consumed_apis:
- varian-fhir
description: Unified oncology clinical data workflow combining the Varian ARIA FHIR R4 API. Designed for clinical informaticists, oncology application developers, and EHR integration teams accessing patient-level cancer care data including diagnoses, radiation therapy procedures, observations, care plans, and medications.
layout: capability
name: Varian Oncology Clinical Data
operations:
- description: Search for oncology patients by name, MRN, or birth date
  method: GET
  name: search-patients
  path: /v1/patients
- description: Get patient by FHIR resource ID
  method: GET
  name: get-patient
  path: /v1/patients/{id}
- description: Search for patient conditions and cancer diagnoses
  method: GET
  name: search-conditions
  path: /v1/conditions
- description: Search for procedures including radiation therapy treatments
  method: GET
  name: search-procedures
  path: /v1/procedures
- description: Search for clinical observations and lab results
  method: GET
  name: search-observations
  path: /v1/observations
- description: Search for diagnostic reports including pathology
  method: GET
  name: search-diagnostic-reports
  path: /v1/diagnostic-reports
- description: Search for oncology care plans
  method: GET
  name: search-care-plans
  path: /v1/care-plans
- description: Search for medication orders including chemotherapy
  method: GET
  name: search-medication-requests
  path: /v1/medications
personas: []
provider_name: Varian Medical Systems
provider_slug: varian-medical-systems
search_terms:
- cancer diagnoses and clinical conditions
- search diagnostic reports
- search for diagnostic reports including pathology
- get lab results
- labs, vitals, and clinical measurements
- get radiation therapy procedures and treatment history for a patient
- search for procedures including radiation therapy treatments
- get patient
- search for oncology patients in varian aria by name or mrn
- radiation therapy
- get chemotherapy and medication orders for an oncology patient
- clinical data
- search care plans
- search for clinical observations and lab results
- search observations
- get laboratory results and clinical observations for a patient
- search conditions
- get pathology reports
- get treatment plans
- fhir
- healthcare
- search medication requests
- individual patient demographics
- get pathology and diagnostic reports for an oncology patient
- get oncology care plans and treatment plans for a patient
- search for oncology care plans
- search procedures
- search for medication orders including chemotherapy
- radiation therapy and clinical procedures
- oncology patient demographics
- varian
- chemotherapy and medication orders
- oncology treatment care plans
- oncology
- get detailed demographics for a specific oncology patient
- get chemotherapy orders
- pathology and imaging reports
- search patients
- get radiation procedures
- health it
- interoperability
- medical devices
- search for oncology patients by name, mrn, or birth date
- get patient by fhir resource id
- search for patient conditions and cancer diagnoses
- get cancer diagnoses
- get cancer diagnoses and conditions for an oncology patient
slug: oncology-clinical-data
source_filename: oncology-clinical-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Varian Oncology Clinical Data\"\n  description: >-\n    Unified oncology clinical data workflow combining the Varian ARIA FHIR R4 API.\n    Designed for clinical informaticists, oncology application developers, and\n    EHR integration teams accessing patient-level cancer care data including diagnoses,\n    radiation therapy procedures, observations, care plans, and medications.\n  tags:\n    - Varian\n    - Healthcare\n    - Oncology\n    - FHIR\n    - Radiation Therapy\n    - Clinical Data\n    - Interoperability\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VARIAN_FHIR_ACCESS_TOKEN: VARIAN_FHIR_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: varian-fhir\n      location: ./shared/varian-aria-fhir.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: varian-oncology-api\n      description: \"Unified REST API for Varian ARIA oncology clinical data.\"\
  \n      resources:\n        - path: /v1/patients\n          name: patients\n          description: \"Oncology patient demographics\"\n          operations:\n            - method: GET\n              name: search-patients\n              description: \"Search for oncology patients by name, MRN, or birth date\"\n              call: \"varian-fhir.search-patients\"\n              with:\n                identifier: \"rest.identifier\"\n                family: \"rest.family\"\n                _count: \"rest._count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patients/{id}\n          name: patient-detail\n          description: \"Individual patient demographics\"\n          operations:\n            - method: GET\n              name: get-patient\n              description: \"Get patient by FHIR resource ID\"\n              call: \"varian-fhir.get-patient\"\n              with:\n                id: \"rest.id\"\n     \
  \         outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/conditions\n          name: conditions\n          description: \"Cancer diagnoses and clinical conditions\"\n          operations:\n            - method: GET\n              name: search-conditions\n              description: \"Search for patient conditions and cancer diagnoses\"\n              call: \"varian-fhir.search-conditions\"\n              with:\n                patient: \"rest.patient\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/procedures\n          name: procedures\n          description: \"Radiation therapy and clinical procedures\"\n          operations:\n            - method: GET\n              name: search-procedures\n              description: \"Search for procedures including radiation therapy treatments\"\n              call: \"varian-fhir.search-procedures\"\
  \n              with:\n                patient: \"rest.patient\"\n                date: \"rest.date\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/observations\n          name: observations\n          description: \"Labs, vitals, and clinical measurements\"\n          operations:\n            - method: GET\n              name: search-observations\n              description: \"Search for clinical observations and lab results\"\n              call: \"varian-fhir.search-observations\"\n              with:\n                patient: \"rest.patient\"\n                code: \"rest.code\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/diagnostic-reports\n          name: diagnostic-reports\n          description: \"Pathology and imaging reports\"\n          operations:\n\
  \            - method: GET\n              name: search-diagnostic-reports\n              description: \"Search for diagnostic reports including pathology\"\n              call: \"varian-fhir.search-diagnostic-reports\"\n              with:\n                patient: \"rest.patient\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/care-plans\n          name: care-plans\n          description: \"Oncology treatment care plans\"\n          operations:\n            - method: GET\n              name: search-care-plans\n              description: \"Search for oncology care plans\"\n              call: \"varian-fhir.search-care-plans\"\n              with:\n                patient: \"rest.patient\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/medications\n          name:\
  \ medications\n          description: \"Chemotherapy and medication orders\"\n          operations:\n            - method: GET\n              name: search-medication-requests\n              description: \"Search for medication orders including chemotherapy\"\n              call: \"varian-fhir.search-medication-requests\"\n              with:\n                patient: \"rest.patient\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: varian-oncology-mcp\n      transport: http\n      description: \"MCP server for AI-assisted oncology clinical data access from Varian ARIA.\"\n      tools:\n        - name: search-patients\n          description: \"Search for oncology patients in Varian ARIA by name or MRN\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-patients\"\n          with:\n\
  \            identifier: \"tools.identifier\"\n            family: \"tools.family\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-patient\n          description: \"Get detailed demographics for a specific oncology patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.get-patient\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cancer-diagnoses\n          description: \"Get cancer diagnoses and conditions for an oncology patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-conditions\"\n          with:\n            patient: \"tools.patient\"\n            code: \"tools.code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-radiation-procedures\n\
  \          description: \"Get radiation therapy procedures and treatment history for a patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-procedures\"\n          with:\n            patient: \"tools.patient\"\n            date: \"tools.date\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-lab-results\n          description: \"Get laboratory results and clinical observations for a patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-observations\"\n          with:\n            patient: \"tools.patient\"\n            code: \"tools.code\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pathology-reports\n          description: \"Get pathology and\
  \ diagnostic reports for an oncology patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-diagnostic-reports\"\n          with:\n            patient: \"tools.patient\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-treatment-plans\n          description: \"Get oncology care plans and treatment plans for a patient\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varian-fhir.search-care-plans\"\n          with:\n            patient: \"tools.patient\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-chemotherapy-orders\n          description: \"Get chemotherapy and medication orders for an oncology patient\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"varian-fhir.search-medication-requests\"\n          with:\n            patient: \"tools.patient\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/varian-medical-systems/refs/heads/main/capabilities/oncology-clinical-data.yaml
tags:
- Varian
- Healthcare
- Oncology
- FHIR
- Radiation Therapy
- Clinical Data
- Interoperability
tools:
- description: Search for oncology patients in Varian ARIA by name or MRN
  hints:
    openWorld: false
    readOnly: true
  name: search-patients
- description: Get detailed demographics for a specific oncology patient
  hints:
    openWorld: false
    readOnly: true
  name: get-patient
- description: Get cancer diagnoses and conditions for an oncology patient
  hints:
    openWorld: false
    readOnly: true
  name: get-cancer-diagnoses
- description: Get radiation therapy procedures and treatment history for a patient
  hints:
    openWorld: false
    readOnly: true
  name: get-radiation-procedures
- description: Get laboratory results and clinical observations for a patient
  hints:
    openWorld: false
    readOnly: true
  name: get-lab-results
- description: Get pathology and diagnostic reports for an oncology patient
  hints:
    openWorld: false
    readOnly: true
  name: get-pathology-reports
- description: Get oncology care plans and treatment plans for a patient
  hints:
    openWorld: false
    readOnly: true
  name: get-treatment-plans
- description: Get chemotherapy and medication orders for an oncology patient
  hints:
    openWorld: false
    readOnly: true
  name: get-chemotherapy-orders
---
