---
categories: []
consumed_apis: []
description: HL7 FHIR R4 (4.0.1) REST API exposed by CharmHealth EHR conforming to the US Core 3.1.1 Implementation Guide. Supports SMART on FHIR authorization for patient-facing apps, provider-facing apps, and backend services. Resource paths follow FHIR conventions and accept standard FHIR search parameters.
layout: capability
name: CharmHealth FHIR API
operations:
- description: Get FHIR CapabilityStatement
  method: GET
  name: getcapabilitystatement
  path: /metadata
- description: Read Patient
  method: GET
  name: readpatient
  path: /Patient/{id}
- description: Search Patient
  method: GET
  name: searchpatient
  path: /Patient
- description: Search AllergyIntolerance
  method: GET
  name: searchallergyintolerance
  path: /AllergyIntolerance
- description: Search Condition
  method: GET
  name: searchcondition
  path: /Condition
- description: Search Encounter
  method: GET
  name: searchencounter
  path: /Encounter
- description: Search Observation
  method: GET
  name: searchobservation
  path: /Observation
- description: Search MedicationRequest
  method: GET
  name: searchmedicationrequest
  path: /MedicationRequest
- description: Search Immunization
  method: GET
  name: searchimmunization
  path: /Immunization
- description: Search CarePlan
  method: GET
  name: searchcareplan
  path: /CarePlan
- description: Search CareTeam
  method: GET
  name: searchcareteam
  path: /CareTeam
- description: Search DocumentReference
  method: GET
  name: searchdocumentreference
  path: /DocumentReference
- description: Search Practitioner
  method: GET
  name: searchpractitioner
  path: /Practitioner
- description: Search Organization
  method: GET
  name: searchorganization
  path: /Organization
- description: Search Appointment
  method: GET
  name: searchappointment
  path: /Appointment
personas: []
provider_name: CharmHealth
provider_slug: charmhealth
search_terms:
- searchcondition
- getcapabilitystatement
- ehr
- patient engagement
- api
- patients
- searchpatient
- searchmedicationrequest
- searchcareteam
- searchorganization
- emr
- search observation
- search documentreference
- us core
- fhir
- search practitioner
- search appointment
- search encounter
- search allergyintolerance
- searchencounter
- healthcare
- searchimmunization
- search careplan
- smart on fhir
- search organization
- searchallergyintolerance
- hl7
- charmhealth
- searchcareplan
- searchdocumentreference
- read patient
- searchobservation
- readpatient
- search immunization
- get fhir capabilitystatement
- searchpractitioner
- search medicationrequest
- search patient
- search condition
- searchappointment
- search careteam
slug: charmhealth-capability
source_filename: charmhealth-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CharmHealth FHIR API\n  description: HL7 FHIR R4 (4.0.1) REST API exposed by CharmHealth EHR conforming to the US Core 3.1.1 Implementation Guide.\n    Supports SMART on FHIR authorization for patient-facing apps, provider-facing apps, and backend services. Resource paths\n    follow FHIR conventions and accept standard FHIR search parameters.\n  tags:\n  - Charmhealth\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: charmhealth\n    baseUri: https://ehr2.charmtracker.com/api/ehr/v2/fhir\n    description: CharmHealth FHIR API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHARMHEALTH_TOKEN}}'\n    resources:\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: getcapabilitystatement\n        method: GET\n        description: Get FHIR CapabilityStatement\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: patient-id\n      path: /Patient/{id}\n      operations:\n      - name: readpatient\n        method: GET\n        description: Read Patient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient\n      path: /Patient\n      operations:\n      - name: searchpatient\n        method: GET\n        description: Search Patient\n        inputParameters:\n        - name: identifier\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        - name: birthdate\n          in: query\n          type: string\n        - name: gender\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance\n      path: /AllergyIntolerance\n      operations:\n\
  \      - name: searchallergyintolerance\n        method: GET\n        description: Search AllergyIntolerance\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: clinical-status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /Condition\n      operations:\n      - name: searchcondition\n        method: GET\n        description: Search Condition\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encounter\n      path: /Encounter\n      operations:\n      - name: searchencounter\n        method: GET\n        description:\
  \ Search Encounter\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observation\n      path: /Observation\n      operations:\n      - name: searchobservation\n        method: GET\n        description: Search Observation\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n        - name: code\n          in: query\n          type: string\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medicationrequest\n      path: /MedicationRequest\n      operations:\n      - name: searchmedicationrequest\n\
  \        method: GET\n        description: Search MedicationRequest\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: immunization\n      path: /Immunization\n      operations:\n      - name: searchimmunization\n        method: GET\n        description: Search Immunization\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan\n      path: /CarePlan\n      operations:\n      - name: searchcareplan\n        method: GET\n        description: Search CarePlan\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careteam\n      path: /CareTeam\n      operations:\n      - name: searchcareteam\n        method: GET\n        description: Search CareTeam\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documentreference\n      path: /DocumentReference\n      operations:\n      - name: searchdocumentreference\n        method: GET\n        description: Search DocumentReference\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: practitioner\n\
  \      path: /Practitioner\n      operations:\n      - name: searchpractitioner\n        method: GET\n        description: Search Practitioner\n        inputParameters:\n        - name: identifier\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization\n      path: /Organization\n      operations:\n      - name: searchorganization\n        method: GET\n        description: Search Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appointment\n      path: /Appointment\n      operations:\n      - name: searchappointment\n        method: GET\n        description: Search Appointment\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n     \
  \   - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: charmhealth-rest\n    description: REST adapter for CharmHealth FHIR API.\n    resources:\n    - path: /metadata\n      name: getcapabilitystatement\n      operations:\n      - method: GET\n        name: getcapabilitystatement\n        description: Get FHIR CapabilityStatement\n        call: charmhealth.getcapabilitystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: readpatient\n      operations:\n      - method: GET\n        name: readpatient\n        description: Read Patient\n        call: charmhealth.readpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient\n      name: searchpatient\n      operations:\n      - method:\
  \ GET\n        name: searchpatient\n        description: Search Patient\n        call: charmhealth.searchpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /AllergyIntolerance\n      name: searchallergyintolerance\n      operations:\n      - method: GET\n        name: searchallergyintolerance\n        description: Search AllergyIntolerance\n        call: charmhealth.searchallergyintolerance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Condition\n      name: searchcondition\n      operations:\n      - method: GET\n        name: searchcondition\n        description: Search Condition\n        call: charmhealth.searchcondition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Encounter\n      name: searchencounter\n      operations:\n      - method: GET\n        name: searchencounter\n        description: Search Encounter\n        call: charmhealth.searchencounter\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Observation\n      name: searchobservation\n      operations:\n      - method: GET\n        name: searchobservation\n        description: Search Observation\n        call: charmhealth.searchobservation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MedicationRequest\n      name: searchmedicationrequest\n      operations:\n      - method: GET\n        name: searchmedicationrequest\n        description: Search MedicationRequest\n        call: charmhealth.searchmedicationrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Immunization\n      name: searchimmunization\n      operations:\n      - method: GET\n        name: searchimmunization\n        description: Search Immunization\n        call: charmhealth.searchimmunization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CarePlan\n\
  \      name: searchcareplan\n      operations:\n      - method: GET\n        name: searchcareplan\n        description: Search CarePlan\n        call: charmhealth.searchcareplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CareTeam\n      name: searchcareteam\n      operations:\n      - method: GET\n        name: searchcareteam\n        description: Search CareTeam\n        call: charmhealth.searchcareteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DocumentReference\n      name: searchdocumentreference\n      operations:\n      - method: GET\n        name: searchdocumentreference\n        description: Search DocumentReference\n        call: charmhealth.searchdocumentreference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Practitioner\n      name: searchpractitioner\n      operations:\n      - method: GET\n        name: searchpractitioner\n        description:\
  \ Search Practitioner\n        call: charmhealth.searchpractitioner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Organization\n      name: searchorganization\n      operations:\n      - method: GET\n        name: searchorganization\n        description: Search Organization\n        call: charmhealth.searchorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Appointment\n      name: searchappointment\n      operations:\n      - method: GET\n        name: searchappointment\n        description: Search Appointment\n        call: charmhealth.searchappointment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: charmhealth-mcp\n    transport: http\n    description: MCP adapter for CharmHealth FHIR API for AI agent use.\n    tools:\n    - name: getcapabilitystatement\n      description: Get FHIR CapabilityStatement\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.getcapabilitystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readpatient\n      description: Read Patient\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.readpatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpatient\n      description: Search Patient\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchpatient\n      with:\n        identifier: tools.identifier\n        name: tools.name\n        birthdate: tools.birthdate\n        gender: tools.gender\n      inputParameters:\n      - name: identifier\n        type: string\n        description: identifier\n      - name: name\n        type: string\n        description: name\n      - name: birthdate\n        type: string\n\
  \        description: birthdate\n      - name: gender\n        type: string\n        description: gender\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchallergyintolerance\n      description: Search AllergyIntolerance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchallergyintolerance\n      with:\n        patient: tools.patient\n        clinical-status: tools.clinical-status\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: clinical-status\n        type: string\n        description: clinical-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcondition\n      description: Search Condition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchcondition\n      with:\n        patient: tools.patient\n    \
  \    category: tools.category\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: category\n        type: string\n        description: category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchencounter\n      description: Search Encounter\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchencounter\n      with:\n        patient: tools.patient\n        date: tools.date\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: date\n        type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchobservation\n      description: Search Observation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchobservation\n      with:\n\
  \        patient: tools.patient\n        category: tools.category\n        code: tools.code\n        date: tools.date\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: category\n        type: string\n        description: category\n      - name: code\n        type: string\n        description: code\n      - name: date\n        type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmedicationrequest\n      description: Search MedicationRequest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchmedicationrequest\n      with:\n        patient: tools.patient\n        status: tools.status\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: searchimmunization\n      description: Search Immunization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchimmunization\n      with:\n        patient: tools.patient\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcareplan\n      description: Search CarePlan\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchcareplan\n      with:\n        patient: tools.patient\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcareteam\n      description: Search CareTeam\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: charmhealth.searchcareteam\n      with:\n        patient: tools.patient\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchdocumentreference\n      description: Search DocumentReference\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchdocumentreference\n      with:\n        patient: tools.patient\n        type: tools.type\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: type\n        type: string\n        description: type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpractitioner\n      description: Search Practitioner\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchpractitioner\n\
  \      with:\n        identifier: tools.identifier\n        name: tools.name\n      inputParameters:\n      - name: identifier\n        type: string\n        description: identifier\n      - name: name\n        type: string\n        description: name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchorganization\n      description: Search Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchappointment\n      description: Search Appointment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charmhealth.searchappointment\n      with:\n        patient: tools.patient\n        date: tools.date\n      inputParameters:\n      - name: patient\n        type: string\n        description: patient\n      - name: date\n        type:\
  \ string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHARMHEALTH_TOKEN: CHARMHEALTH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/charmhealth/refs/heads/main/capabilities/charmhealth-capability.yaml
tags:
- Charmhealth
- API
tools:
- description: Get FHIR CapabilityStatement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilitystatement
- description: Read Patient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readpatient
- description: Search Patient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpatient
- description: Search AllergyIntolerance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchallergyintolerance
- description: Search Condition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcondition
- description: Search Encounter
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchencounter
- description: Search Observation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchobservation
- description: Search MedicationRequest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmedicationrequest
- description: Search Immunization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchimmunization
- description: Search CarePlan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcareplan
- description: Search CareTeam
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcareteam
- description: Search DocumentReference
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdocumentreference
- description: Search Practitioner
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpractitioner
- description: Search Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchorganization
- description: Search Appointment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchappointment
---
