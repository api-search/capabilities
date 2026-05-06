---
categories: []
consumed_apis: []
description: The Orion Health FHIR API provides standards-based access to healthcare data using the HL7 FHIR (Fast Healthcare Interoperability Resources) specification. It enables healthcare organizations to read, search, create, and update clinical resources including patients, encounters, observations, conditions, medications, allergies, procedures, diagnostic reports, and care plans. The API conforms to FHIR R4 (v4.0.1) and supports both JSON and XML representations.
layout: capability
name: Orion Health FHIR API
operations:
- description: Orion Health Get server capability statement
  method: GET
  name: getcapabilitystatement
  path: /metadata
- description: Orion Health Search for patients
  method: GET
  name: searchpatients
  path: /Patient
- description: Orion Health Create a new patient
  method: POST
  name: createpatient
  path: /Patient
- description: Orion Health Read a patient by ID
  method: GET
  name: getpatient
  path: /Patient/{id}
- description: Orion Health Update a patient
  method: PUT
  name: updatepatient
  path: /Patient/{id}
- description: Orion Health Get patient version history
  method: GET
  name: getpatienthistory
  path: /Patient/{id}/_history
- description: Orion Health Search for encounters
  method: GET
  name: searchencounters
  path: /Encounter
- description: Orion Health Read an encounter by ID
  method: GET
  name: getencounter
  path: /Encounter/{id}
- description: Orion Health Search for observations
  method: GET
  name: searchobservations
  path: /Observation
- description: Orion Health Create a new observation
  method: POST
  name: createobservation
  path: /Observation
- description: Orion Health Read an observation by ID
  method: GET
  name: getobservation
  path: /Observation/{id}
- description: Orion Health Search for conditions
  method: GET
  name: searchconditions
  path: /Condition
- description: Orion Health Read a condition by ID
  method: GET
  name: getcondition
  path: /Condition/{id}
- description: Orion Health Search for medication requests
  method: GET
  name: searchmedicationrequests
  path: /MedicationRequest
- description: Orion Health Read a medication request by ID
  method: GET
  name: getmedicationrequest
  path: /MedicationRequest/{id}
- description: Orion Health Search for allergy intolerances
  method: GET
  name: searchallergyintolerances
  path: /AllergyIntolerance
- description: Orion Health Read an allergy intolerance by ID
  method: GET
  name: getallergyintolerance
  path: /AllergyIntolerance/{id}
- description: Orion Health Search for procedures
  method: GET
  name: searchprocedures
  path: /Procedure
- description: Orion Health Read a procedure by ID
  method: GET
  name: getprocedure
  path: /Procedure/{id}
- description: Orion Health Search for diagnostic reports
  method: GET
  name: searchdiagnosticreports
  path: /DiagnosticReport
- description: Orion Health Read a diagnostic report by ID
  method: GET
  name: getdiagnosticreport
  path: /DiagnosticReport/{id}
- description: Orion Health Search for care plans
  method: GET
  name: searchcareplans
  path: /CarePlan
- description: Orion Health Read a care plan by ID
  method: GET
  name: getcareplan
  path: /CarePlan/{id}
- description: Orion Health Search for immunizations
  method: GET
  name: searchimmunizations
  path: /Immunization
- description: Orion Health Read an immunization by ID
  method: GET
  name: getimmunization
  path: /Immunization/{id}
- description: Orion Health Search for document references
  method: GET
  name: searchdocumentreferences
  path: /DocumentReference
- description: Orion Health Read a document reference by ID
  method: GET
  name: getdocumentreference
  path: /DocumentReference/{id}
personas: []
provider_name: Orion Health
provider_slug: orion
search_terms:
- orion health get server capability statement
- orion health read an allergy intolerance by id
- getdocumentreference
- orion health read an observation by id
- fhir
- integration
- createobservation
- population health
- getencounter
- orion health read an encounter by id
- orion health search for document references
- getmedicationrequest
- getprocedure
- health it
- hl7
- orion health create a new patient
- orion health read a condition by id
- orion health get patient version history
- searchimmunizations
- updatepatient
- orion health create a new observation
- orion health search for immunizations
- orion health search for procedures
- orion health read a procedure by id
- healthcare
- searchmedicationrequests
- searchcareplans
- getcareplan
- orion health read a document reference by id
- searchpatients
- orion health read a diagnostic report by id
- hie
- orion health search for medication requests
- getcapabilitystatement
- orion health search for allergy intolerances
- orion health search for patients
- searchallergyintolerances
- searchdocumentreferences
- orion health read a care plan by id
- getobservation
- getdiagnosticreport
- orion health read an immunization by id
- orion health search for care plans
- getpatienthistory
- orion
- searchconditions
- orion health search for diagnostic reports
- api
- orion health search for conditions
- interoperability
- searchprocedures
- getpatient
- createpatient
- orion health update a patient
- ehr
- getcondition
- orion health read a medication request by id
- orion health search for observations
- getimmunization
- orion health search for encounters
- getallergyintolerance
- orion health read a patient by id
- searchdiagnosticreports
- searchobservations
- searchencounters
slug: orion-capability
source_filename: orion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Orion Health FHIR API\n  description: The Orion Health FHIR API provides standards-based access to healthcare data using the HL7 FHIR (Fast Healthcare\n    Interoperability Resources) specification. It enables healthcare organizations to read, search, create, and update clinical\n    resources including patients, encounters, observations, conditions, medications, allergies, procedures, diagnostic reports,\n    and care plans. The API conforms to FHIR R4 (v4.0.1) and supports both JSON and XML representations.\n  tags:\n  - Orion\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: orion\n    baseUri: https://api.orionhealth.com/fhir\n    description: Orion Health FHIR API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORION_TOKEN}}'\n    resources:\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: getcapabilitystatement\n\
  \        method: GET\n        description: Orion Health Get server capability statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient\n      path: /Patient\n      operations:\n      - name: searchpatients\n        method: GET\n        description: Orion Health Search for patients\n        inputParameters:\n        - name: _id\n          in: query\n          type: string\n          description: Logical ID of the patient resource\n        - name: identifier\n          in: query\n          type: string\n          description: Patient identifier (e.g., MRN, SSN) in format system|value\n        - name: family\n          in: query\n          type: string\n          description: Family (last) name of the patient\n        - name: given\n          in: query\n          type: string\n          description: Given (first) name of the patient\n        - name: name\n          in: query\n          type:\
  \ string\n          description: Any part of the patient name\n        - name: birthdate\n          in: query\n          type: string\n          description: Patient date of birth (YYYY-MM-DD)\n        - name: gender\n          in: query\n          type: string\n          description: Patient gender\n        - name: address\n          in: query\n          type: string\n          description: Any part of the patient address\n        - name: telecom\n          in: query\n          type: string\n          description: Patient phone number or email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpatient\n        method: POST\n        description: Orion Health Create a new patient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id\n      path: /Patient/{id}\n      operations:\n      - name: getpatient\n\
  \        method: GET\n        description: Orion Health Read a patient by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepatient\n        method: PUT\n        description: Orion Health Update a patient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patient-id-history\n      path: /Patient/{id}/_history\n      operations:\n      - name: getpatienthistory\n        method: GET\n        description: Orion Health Get patient version history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encounter\n      path: /Encounter\n      operations:\n      - name: searchencounters\n        method: GET\n        description: Orion Health Search for encounters\n        inputParameters:\n        - name: patient\n       \
  \   in: query\n          type: string\n          description: Reference to the patient\n        - name: date\n          in: query\n          type: string\n          description: Encounter date or date range\n        - name: status\n          in: query\n          type: string\n          description: Encounter status\n        - name: class\n          in: query\n          type: string\n          description: Classification of the encounter (e.g., ambulatory, inpatient)\n        - name: type\n          in: query\n          type: string\n          description: Specific type of encounter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encounter-id\n      path: /Encounter/{id}\n      operations:\n      - name: getencounter\n        method: GET\n        description: Orion Health Read an encounter by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: observation\n      path: /Observation\n      operations:\n      - name: searchobservations\n        method: GET\n        description: Orion Health Search for observations\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: category\n          in: query\n          type: string\n          description: Observation category (e.g., vital-signs, laboratory)\n        - name: code\n          in: query\n          type: string\n          description: LOINC or SNOMED code for the observation\n        - name: date\n          in: query\n          type: string\n          description: Observation date or date range\n        - name: status\n          in: query\n          type: string\n          description: Observation status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: createobservation\n        method: POST\n        description: Orion Health Create a new observation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observation-id\n      path: /Observation/{id}\n      operations:\n      - name: getobservation\n        method: GET\n        description: Orion Health Read an observation by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /Condition\n      operations:\n      - name: searchconditions\n        method: GET\n        description: Orion Health Search for conditions\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: code\n          in: query\n          type: string\n          description: ICD-10 or SNOMED code for the condition\n\
  \        - name: clinical-status\n          in: query\n          type: string\n          description: Clinical status of the condition\n        - name: category\n          in: query\n          type: string\n          description: Condition category\n        - name: onset-date\n          in: query\n          type: string\n          description: Date of onset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition-id\n      path: /Condition/{id}\n      operations:\n      - name: getcondition\n        method: GET\n        description: Orion Health Read a condition by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medicationrequest\n      path: /MedicationRequest\n      operations:\n      - name: searchmedicationrequests\n        method: GET\n        description: Orion Health Search for medication requests\n\
  \        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: status\n          in: query\n          type: string\n          description: Prescription status\n        - name: intent\n          in: query\n          type: string\n          description: Kind of medication request\n        - name: authoredon\n          in: query\n          type: string\n          description: Date the prescription was written\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medicationrequest-id\n      path: /MedicationRequest/{id}\n      operations:\n      - name: getmedicationrequest\n        method: GET\n        description: Orion Health Read a medication request by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance\n\
  \      path: /AllergyIntolerance\n      operations:\n      - name: searchallergyintolerances\n        method: GET\n        description: Orion Health Search for allergy intolerances\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: clinical-status\n          in: query\n          type: string\n          description: Clinical status of the allergy\n        - name: type\n          in: query\n          type: string\n          description: allergy or intolerance\n        - name: criticality\n          in: query\n          type: string\n          description: Criticality level\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance-id\n      path: /AllergyIntolerance/{id}\n      operations:\n      - name: getallergyintolerance\n        method: GET\n        description: Orion Health\
  \ Read an allergy intolerance by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: procedure\n      path: /Procedure\n      operations:\n      - name: searchprocedures\n        method: GET\n        description: Orion Health Search for procedures\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: code\n          in: query\n          type: string\n          description: CPT or SNOMED code for the procedure\n        - name: date\n          in: query\n          type: string\n          description: Procedure date or date range\n        - name: status\n          in: query\n          type: string\n          description: Procedure status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: procedure-id\n   \
  \   path: /Procedure/{id}\n      operations:\n      - name: getprocedure\n        method: GET\n        description: Orion Health Read a procedure by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnosticreport\n      path: /DiagnosticReport\n      operations:\n      - name: searchdiagnosticreports\n        method: GET\n        description: Orion Health Search for diagnostic reports\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: category\n          in: query\n          type: string\n          description: Report category (e.g., LAB, RAD)\n        - name: code\n          in: query\n          type: string\n          description: LOINC code for the report\n        - name: date\n          in: query\n          type: string\n          description: Report date or date range\n       \
  \ - name: status\n          in: query\n          type: string\n          description: Report status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnosticreport-id\n      path: /DiagnosticReport/{id}\n      operations:\n      - name: getdiagnosticreport\n        method: GET\n        description: Orion Health Read a diagnostic report by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan\n      path: /CarePlan\n      operations:\n      - name: searchcareplans\n        method: GET\n        description: Orion Health Search for care plans\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: status\n          in: query\n          type: string\n          description: Care plan status\n      \
  \  - name: category\n          in: query\n          type: string\n          description: Type of care plan\n        - name: date\n          in: query\n          type: string\n          description: Care plan period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan-id\n      path: /CarePlan/{id}\n      operations:\n      - name: getcareplan\n        method: GET\n        description: Orion Health Read a care plan by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: immunization\n      path: /Immunization\n      operations:\n      - name: searchimmunizations\n        method: GET\n        description: Orion Health Search for immunizations\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: date\n\
  \          in: query\n          type: string\n          description: Vaccination date or date range\n        - name: vaccine-code\n          in: query\n          type: string\n          description: CVX code for the vaccine\n        - name: status\n          in: query\n          type: string\n          description: Immunization status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: immunization-id\n      path: /Immunization/{id}\n      operations:\n      - name: getimmunization\n        method: GET\n        description: Orion Health Read an immunization by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documentreference\n      path: /DocumentReference\n      operations:\n      - name: searchdocumentreferences\n        method: GET\n        description: Orion Health Search for document references\n    \
  \    inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: Reference to the patient\n        - name: type\n          in: query\n          type: string\n          description: Document type code\n        - name: category\n          in: query\n          type: string\n          description: Document category\n        - name: date\n          in: query\n          type: string\n          description: Document date or date range\n        - name: status\n          in: query\n          type: string\n          description: Document status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documentreference-id\n      path: /DocumentReference/{id}\n      operations:\n      - name: getdocumentreference\n        method: GET\n        description: Orion Health Read a document reference by ID\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: orion-rest\n    description: REST adapter for Orion Health FHIR API.\n    resources:\n    - path: /metadata\n      name: getcapabilitystatement\n      operations:\n      - method: GET\n        name: getcapabilitystatement\n        description: Orion Health Get server capability statement\n        call: orion.getcapabilitystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient\n      name: searchpatients\n      operations:\n      - method: GET\n        name: searchpatients\n        description: Orion Health Search for patients\n        call: orion.searchpatients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient\n      name: createpatient\n      operations:\n      - method: POST\n        name: createpatient\n        description: Orion Health Create a new patient\n        call:\
  \ orion.createpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: getpatient\n      operations:\n      - method: GET\n        name: getpatient\n        description: Orion Health Read a patient by ID\n        call: orion.getpatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}\n      name: updatepatient\n      operations:\n      - method: PUT\n        name: updatepatient\n        description: Orion Health Update a patient\n        call: orion.updatepatient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Patient/{id}/_history\n      name: getpatienthistory\n      operations:\n      - method: GET\n        name: getpatienthistory\n        description: Orion Health Get patient version history\n        call: orion.getpatienthistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Encounter\n\
  \      name: searchencounters\n      operations:\n      - method: GET\n        name: searchencounters\n        description: Orion Health Search for encounters\n        call: orion.searchencounters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Encounter/{id}\n      name: getencounter\n      operations:\n      - method: GET\n        name: getencounter\n        description: Orion Health Read an encounter by ID\n        call: orion.getencounter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Observation\n      name: searchobservations\n      operations:\n      - method: GET\n        name: searchobservations\n        description: Orion Health Search for observations\n        call: orion.searchobservations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Observation\n      name: createobservation\n      operations:\n      - method: POST\n        name: createobservation\n \
  \       description: Orion Health Create a new observation\n        call: orion.createobservation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Observation/{id}\n      name: getobservation\n      operations:\n      - method: GET\n        name: getobservation\n        description: Orion Health Read an observation by ID\n        call: orion.getobservation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Condition\n      name: searchconditions\n      operations:\n      - method: GET\n        name: searchconditions\n        description: Orion Health Search for conditions\n        call: orion.searchconditions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Condition/{id}\n      name: getcondition\n      operations:\n      - method: GET\n        name: getcondition\n        description: Orion Health Read a condition by ID\n        call: orion.getcondition\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /MedicationRequest\n      name: searchmedicationrequests\n      operations:\n      - method: GET\n        name: searchmedicationrequests\n        description: Orion Health Search for medication requests\n        call: orion.searchmedicationrequests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MedicationRequest/{id}\n      name: getmedicationrequest\n      operations:\n      - method: GET\n        name: getmedicationrequest\n        description: Orion Health Read a medication request by ID\n        call: orion.getmedicationrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /AllergyIntolerance\n      name: searchallergyintolerances\n      operations:\n      - method: GET\n        name: searchallergyintolerances\n        description: Orion Health Search for allergy intolerances\n        call: orion.searchallergyintolerances\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /AllergyIntolerance/{id}\n      name: getallergyintolerance\n      operations:\n      - method: GET\n        name: getallergyintolerance\n        description: Orion Health Read an allergy intolerance by ID\n        call: orion.getallergyintolerance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Procedure\n      name: searchprocedures\n      operations:\n      - method: GET\n        name: searchprocedures\n        description: Orion Health Search for procedures\n        call: orion.searchprocedures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Procedure/{id}\n      name: getprocedure\n      operations:\n      - method: GET\n        name: getprocedure\n        description: Orion Health Read a procedure by ID\n        call: orion.getprocedure\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DiagnosticReport\n\
  \      name: searchdiagnosticreports\n      operations:\n      - method: GET\n        name: searchdiagnosticreports\n        description: Orion Health Search for diagnostic reports\n        call: orion.searchdiagnosticreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DiagnosticReport/{id}\n      name: getdiagnosticreport\n      operations:\n      - method: GET\n        name: getdiagnosticreport\n        description: Orion Health Read a diagnostic report by ID\n        call: orion.getdiagnosticreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CarePlan\n      name: searchcareplans\n      operations:\n      - method: GET\n        name: searchcareplans\n        description: Orion Health Search for care plans\n        call: orion.searchcareplans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CarePlan/{id}\n      name: getcareplan\n      operations:\n      - method:\
  \ GET\n        name: getcareplan\n        description: Orion Health Read a care plan by ID\n        call: orion.getcareplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Immunization\n      name: searchimmunizations\n      operations:\n      - method: GET\n        name: searchimmunizations\n        description: Orion Health Search for immunizations\n        call: orion.searchimmunizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Immunization/{id}\n      name: getimmunization\n      operations:\n      - method: GET\n        name: getimmunization\n        description: Orion Health Read an immunization by ID\n        call: orion.getimmunization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DocumentReference\n      name: searchdocumentreferences\n      operations:\n      - method: GET\n        name: searchdocumentreferences\n        description: Orion Health Search\
  \ for document references\n        call: orion.searchdocumentreferences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DocumentReference/{id}\n      name: getdocumentreference\n      operations:\n      - method: GET\n        name: getdocumentreference\n        description: Orion Health Read a document reference by ID\n        call: orion.getdocumentreference\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: orion-mcp\n    transport: http\n    description: MCP adapter for Orion Health FHIR API for AI agent use.\n    tools:\n    - name: getcapabilitystatement\n      description: Orion Health Get server capability statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getcapabilitystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpatients\n      description: Orion Health\
  \ Search for patients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchpatients\n      with:\n        _id: tools._id\n        identifier: tools.identifier\n        family: tools.family\n        given: tools.given\n        name: tools.name\n        birthdate: tools.birthdate\n        gender: tools.gender\n        address: tools.address\n        telecom: tools.telecom\n      inputParameters:\n      - name: _id\n        type: string\n        description: Logical ID of the patient resource\n      - name: identifier\n        type: string\n        description: Patient identifier (e.g., MRN, SSN) in format system|value\n      - name: family\n        type: string\n        description: Family (last) name of the patient\n      - name: given\n        type: string\n        description: Given (first) name of the patient\n      - name: name\n        type: string\n        description: Any part of the patient name\n      - name: birthdate\n\
  \        type: string\n        description: Patient date of birth (YYYY-MM-DD)\n      - name: gender\n        type: string\n        description: Patient gender\n      - name: address\n        type: string\n        description: Any part of the patient address\n      - name: telecom\n        type: string\n        description: Patient phone number or email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpatient\n      description: Orion Health Create a new patient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orion.createpatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatient\n      description: Orion Health Read a patient by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getpatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepatient\n   \
  \   description: Orion Health Update a patient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orion.updatepatient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatienthistory\n      description: Orion Health Get patient version history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getpatienthistory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchencounters\n      description: Orion Health Search for encounters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchencounters\n      with:\n        patient: tools.patient\n        date: tools.date\n        status: tools.status\n        class: tools.class\n        type: tools.type\n      inputParameters:\n      - name: patient\n        type: string\n        description: Reference to\
  \ the patient\n      - name: date\n        type: string\n        description: Encounter date or date range\n      - name: status\n        type: string\n        description: Encounter status\n      - name: class\n        type: string\n        description: Classification of the encounter (e.g., ambulatory, inpatient)\n      - name: type\n        type: string\n        description: Specific type of encounter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getencounter\n      description: Orion Health Read an encounter by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getencounter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchobservations\n      description: Orion Health Search for observations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchobservations\n      with:\n        patient:\
  \ tools.patient\n        category: tools.category\n        code: tools.code\n        date: tools.date\n        status: tools.status\n      inputParameters:\n      - name: patient\n        type: string\n        description: Reference to the patient\n      - name: category\n        type: string\n        description: Observation category (e.g., vital-signs, laboratory)\n      - name: code\n        type: string\n        description: LOINC or SNOMED code for the observation\n      - name: date\n        type: string\n        description: Observation date or date range\n      - name: status\n        type: string\n        description: Observation status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createobservation\n      description: Orion Health Create a new observation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orion.createobservation\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getobservation\n      description: Orion Health Read an observation by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getobservation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchconditions\n      description: Orion Health Search for conditions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchconditions\n      with:\n        patient: tools.patient\n        code: tools.code\n        clinical-status: tools.clinical-status\n        category: tools.category\n        onset-date: tools.onset-date\n      inputParameters:\n      - name: patient\n        type: string\n        description: Reference to the patient\n      - name: code\n        type: string\n        description: ICD-10 or SNOMED code for the condition\n      - name: clinical-status\n        type: string\n        description: Clinical status\
  \ of the condition\n      - name: category\n        type: string\n        description: Condition category\n      - name: onset-date\n        type: string\n        description: Date of onset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcondition\n      description: Orion Health Read a condition by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getcondition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmedicationrequests\n      description: Orion Health Search for medication requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchmedicationrequests\n      with:\n        patient: tools.patient\n        status: tools.status\n        intent: tools.intent\n        authoredon: tools.authoredon\n      inputParameters:\n      - name: patient\n        type: string\n        description:\
  \ Reference to the patient\n      - name: status\n        type: string\n        description: Prescription status\n      - name: intent\n        type: string\n        description: Kind of medication request\n      - name: authoredon\n        type: string\n        description: Date the prescription was written\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmedicationrequest\n      description: Orion Health Read a medication request by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getmedicationrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchallergyintolerances\n      description: Orion Health Search for allergy intolerances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.searchallergyintolerances\n      with:\n        patient: tools.patient\n        clinical-status: tools.clinical-status\n\
  \        type: tools.type\n        criticality: tools.criticality\n      inputParameters:\n      - name: patient\n        type: string\n        description: Reference to the patient\n      - name: clinical-status\n        type: string\n        description: Clinical status of the allergy\n      - name: type\n        type: string\n        description: allergy or intolerance\n      - name: criticality\n        type: string\n        description: Criticality level\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getallergyintolerance\n      description: Orion Health Read an allergy intolerance by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orion.getallergyintolerance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n\n# --- truncated at 32 KB (37 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/orion/refs/heads/main/capabilities/orion-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/orion/refs/heads/main/capabilities/orion-capability.yaml
tags:
- Orion
- API
tools:
- description: Orion Health Get server capability statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilitystatement
- description: Orion Health Search for patients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpatients
- description: Orion Health Create a new patient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpatient
- description: Orion Health Read a patient by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatient
- description: Orion Health Update a patient
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepatient
- description: Orion Health Get patient version history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatienthistory
- description: Orion Health Search for encounters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchencounters
- description: Orion Health Read an encounter by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getencounter
- description: Orion Health Search for observations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchobservations
- description: Orion Health Create a new observation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createobservation
- description: Orion Health Read an observation by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getobservation
- description: Orion Health Search for conditions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchconditions
- description: Orion Health Read a condition by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcondition
- description: Orion Health Search for medication requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmedicationrequests
- description: Orion Health Read a medication request by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmedicationrequest
- description: Orion Health Search for allergy intolerances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchallergyintolerances
- description: Orion Health Read an allergy intolerance by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallergyintolerance
- description: Orion Health Search for procedures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchprocedures
- description: Orion Health Read a procedure by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprocedure
- description: Orion Health Search for diagnostic reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdiagnosticreports
- description: Orion Health Read a diagnostic report by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiagnosticreport
- description: Orion Health Search for care plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcareplans
- description: Orion Health Read a care plan by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcareplan
- description: Orion Health Search for immunizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchimmunizations
- description: Orion Health Read an immunization by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimmunization
- description: Orion Health Search for document references
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdocumentreferences
- description: Orion Health Read a document reference by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentreference
---
