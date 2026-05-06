---
categories: []
consumed_apis: []
description: Unified care coordination capability combining WellCare FHIR Patient Access and Provider Directory APIs. Enables care managers, app developers, and member-facing apps to access a member's complete health record alongside in-network provider and facility information for coordinated care delivery across Medicaid and Medicare Advantage plans.
layout: capability
name: WellCare Member Care Coordination
operations:
- description: Get member profile by FHIR Patient ID.
  method: GET
  name: get-member
  path: /v1/members/{id}
- description: Get coverage for a member.
  method: GET
  name: get-member-coverage
  path: /v1/members/{id}/coverage
- description: Get EOB claims for a member.
  method: GET
  name: get-member-claims
  path: /v1/members/{id}/claims
- description: Get conditions for a member.
  method: GET
  name: get-member-conditions
  path: /v1/members/{id}/conditions
- description: Get medication requests for a member.
  method: GET
  name: get-member-medications
  path: /v1/members/{id}/medications
- description: Get care encounters for a member.
  method: GET
  name: get-member-encounters
  path: /v1/members/{id}/encounters
- description: Search in-network providers by specialty or name.
  method: GET
  name: search-providers
  path: /v1/providers
- description: Search in-network hospitals and clinics.
  method: GET
  name: search-facilities
  path: /v1/facilities
- description: Find care locations by ZIP code.
  method: GET
  name: search-locations
  path: /v1/locations
- description: Search insurance plans.
  method: GET
  name: search-plans
  path: /v1/plans
personas: []
provider_name: wellcare-health-plans
provider_slug: wellcare-health-plans
search_terms:
- get member medications
- medicare
- member clinical conditions.
- fhir
- get member coverage
- search providers
- find care locations near zip
- get member claims
- member active medications.
- get member encounters
- search insurance plans.
- find network facilities
- get care visit and encounter history for a wellcare member.
- get conditions for a member.
- get historical claims and eob data for a wellcare member. supports up to 5 years of history.
- get wellcare insurance plan details including network and benefit information.
- care delivery locations.
- get member profile
- search locations
- provider directory
- healthcare
- managed care
- get immunization records and history for a wellcare member.
- member demographic and identity.
- find wellcare in-network care delivery locations near a zip code.
- search plans
- in-network facilities.
- get member care encounters
- in-network providers.
- get member profile by fhir patient id.
- get current and historical medication prescriptions for a wellcare member.
- get plan information
- get coverage for a member.
- member care encounters.
- get member immunization history
- get active diagnoses and conditions for a wellcare member.
- search for in-network wellcare providers by name or specialty.
- get member
- search in network providers
- get member active conditions
- insurance plan information.
- get member claims history
- get a wellcare member's demographic profile and contact information.
- get care encounters for a member.
- get medication requests for a member.
- get insurance coverage and enrollment details for a wellcare member.
- search in-network providers by specialty or name.
- search for in-network hospitals, clinics, and healthcare facilities.
- medicaid
- patient access
- member claims history.
- get member conditions
- search facilities
- care coordination
- search in-network hospitals and clinics.
- get eob claims for a member.
- member insurance coverage and enrollment.
- find care locations by zip code.
slug: member-care-coordination
source_filename: member-care-coordination.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WellCare Member Care Coordination\n  description: Unified care coordination capability combining WellCare FHIR Patient Access and Provider Directory APIs. Enables\n    care managers, app developers, and member-facing apps to access a member's complete health record alongside in-network\n    provider and facility information for coordinated care delivery across Medicaid and Medicare Advantage plans.\n  tags:\n  - Healthcare\n  - FHIR\n  - Care Coordination\n  - Patient Access\n  - Provider Directory\n  - Managed Care\n  - Medicaid\n  - Medicare\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WELLCARE_PATIENT_ACCESS_TOKEN: WELLCARE_PATIENT_ACCESS_TOKEN\n    WELLCARE_PROVIDER_DIRECTORY_TOKEN: WELLCARE_PROVIDER_DIRECTORY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wellcare-patient-access\n    baseUri: https://partners.centene.com\n    description: WellCare FHIR R4 Patient Access\
  \ API for member health data.\n    authentication:\n      type: bearer\n      token: '{{WELLCARE_PATIENT_ACCESS_TOKEN}}'\n    resources:\n    - name: patient\n      path: /fhir/r4/Patient\n      description: Patient demographic and identity resources.\n      operations:\n      - name: get-patient\n        method: GET\n        description: Get Patient by FHIR ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: FHIR Patient resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage\n      path: /fhir/r4/Coverage\n      description: Member insurance coverage and enrollment.\n      operations:\n      - name: list-coverage\n        method: GET\n        description: List Coverage for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required:\
  \ true\n          description: FHIR Patient ID.\n        - name: _count\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: explanation-of-benefit\n      path: /fhir/r4/ExplanationOfBenefit\n      description: Claims and EOB data for medical, pharmacy, dental, and vision.\n      operations:\n      - name: list-explanation-of-benefit\n        method: GET\n        description: List Explanation of Benefit claims for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient ID.\n        - name: service-date\n          in: query\n          type: string\n          required: false\n          description: Filter by service date range.\n        - name: type\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter by claim type.\n        - name: _count\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /fhir/r4/Condition\n      description: Member diagnosed conditions.\n      operations:\n      - name: list-conditions\n        method: GET\n        description: List Conditions for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observation\n      path: /fhir/r4/Observation\n      description: Clinical observations and lab results.\n\
  \      operations:\n      - name: list-observations\n        method: GET\n        description: List Observations for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient ID.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Observation category filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medication-request\n      path: /fhir/r4/MedicationRequest\n      description: Prescribed medications and medication orders.\n      operations:\n      - name: list-medication-requests\n        method: GET\n        description: List Medication Requests for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient\
  \ ID.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Medication status filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: immunization\n      path: /fhir/r4/Immunization\n      description: Immunization records and history.\n      operations:\n      - name: list-immunizations\n        method: GET\n        description: List Immunizations for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encounter\n      path: /fhir/r4/Encounter\n      description: Care encounters and visits.\n      operations:\n      - name: list-encounters\n        method: GET\n        description:\
  \ List Encounters for a member.\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          required: true\n          description: FHIR Patient ID.\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Encounter date range filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wellcare-provider-directory\n    baseUri: https://partners.centene.com\n    description: WellCare FHIR R4 Provider Directory API.\n    authentication:\n      type: bearer\n      token: '{{WELLCARE_PROVIDER_DIRECTORY_TOKEN}}'\n    resources:\n    - name: practitioner\n      path: /fhir/r4/Practitioner\n      description: Individual healthcare practitioners.\n      operations:\n      - name: search-practitioners\n        method: GET\n        description: Search practitioners by name, specialty, or\
  \ NPI.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Practitioner name.\n        - name: identifier\n          in: query\n          type: string\n          required: false\n          description: NPI or other identifier.\n        - name: specialty\n          in: query\n          type: string\n          required: false\n          description: Specialty taxonomy code.\n        - name: _count\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-practitioner\n        method: GET\n        description: Get Practitioner by FHIR ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: FHIR Practitioner ID.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization\n      path: /fhir/r4/Organization\n      description: Healthcare organizations and facilities.\n      operations:\n      - name: search-organizations\n        method: GET\n        description: Search organizations by name, type, or NPI.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Organization name.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Organization type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-organization\n        method: GET\n        description: Get Organization by FHIR ID.\n        inputParameters:\n        - name: id\n          in: path\n          type:\
  \ string\n          required: true\n          description: FHIR Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location\n      path: /fhir/r4/Location\n      description: Care delivery locations.\n      operations:\n      - name: search-locations\n        method: GET\n        description: Search locations by ZIP code or proximity.\n        inputParameters:\n        - name: address-postalcode\n          in: query\n          type: string\n          required: false\n          description: ZIP code for location search.\n        - name: near\n          in: query\n          type: string\n          required: false\n          description: Proximity coordinate search.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: practitioner-role\n      path: /fhir/r4/PractitionerRole\n      description: Practitioner\
  \ network roles and affiliations.\n      operations:\n      - name: search-practitioner-roles\n        method: GET\n        description: Search practitioner roles and network affiliations.\n        inputParameters:\n        - name: practitioner\n          in: query\n          type: string\n          required: false\n          description: FHIR Practitioner ID.\n        - name: organization\n          in: query\n          type: string\n          required: false\n          description: FHIR Organization ID.\n        - name: specialty\n          in: query\n          type: string\n          required: false\n          description: Specialty code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insurance-plan\n      path: /fhir/r4/InsurancePlan\n      description: Insurance plan network and benefit details.\n      operations:\n      - name: search-insurance-plans\n        method: GET\n        description:\
  \ Search insurance plans by name or type.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Plan name.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Plan type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wellcare-care-coordination-api\n    description: Unified REST API for WellCare member care coordination.\n    resources:\n    - path: /v1/members/{id}\n      name: member-profile\n      description: Member demographic and identity.\n      operations:\n      - method: GET\n        name: get-member\n        description: Get member profile by FHIR Patient ID.\n        call: wellcare-patient-access.get-patient\n        with:\n          id: rest.id\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/members/{id}/coverage\n      name: member-coverage\n      description: Member insurance coverage and enrollment.\n      operations:\n      - method: GET\n        name: get-member-coverage\n        description: Get coverage for a member.\n        call: wellcare-patient-access.list-coverage\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/claims\n      name: member-claims\n      description: Member claims history.\n      operations:\n      - method: GET\n        name: get-member-claims\n        description: Get EOB claims for a member.\n        call: wellcare-patient-access.list-explanation-of-benefit\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/conditions\n      name: member-conditions\n      description: Member clinical conditions.\n      operations:\n\
  \      - method: GET\n        name: get-member-conditions\n        description: Get conditions for a member.\n        call: wellcare-patient-access.list-conditions\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/medications\n      name: member-medications\n      description: Member active medications.\n      operations:\n      - method: GET\n        name: get-member-medications\n        description: Get medication requests for a member.\n        call: wellcare-patient-access.list-medication-requests\n        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/encounters\n      name: member-encounters\n      description: Member care encounters.\n      operations:\n      - method: GET\n        name: get-member-encounters\n        description: Get care encounters for a member.\n        call: wellcare-patient-access.list-encounters\n\
  \        with:\n          patient: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/providers\n      name: network-providers\n      description: In-network providers.\n      operations:\n      - method: GET\n        name: search-providers\n        description: Search in-network providers by specialty or name.\n        call: wellcare-provider-directory.search-practitioners\n        with:\n          name: rest.name\n          specialty: rest.specialty\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/facilities\n      name: network-facilities\n      description: In-network facilities.\n      operations:\n      - method: GET\n        name: search-facilities\n        description: Search in-network hospitals and clinics.\n        call: wellcare-provider-directory.search-organizations\n        with:\n          name: rest.name\n          type: rest.type\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/locations\n      name: care-locations\n      description: Care delivery locations.\n      operations:\n      - method: GET\n        name: search-locations\n        description: Find care locations by ZIP code.\n        call: wellcare-provider-directory.search-locations\n        with:\n          address-postalcode: rest.postalcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans\n      name: insurance-plans\n      description: Insurance plan information.\n      operations:\n      - method: GET\n        name: search-plans\n        description: Search insurance plans.\n        call: wellcare-provider-directory.search-insurance-plans\n        with:\n          name: rest.name\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wellcare-care-coordination-mcp\n    transport: http\n    description: MCP server for\
  \ AI-assisted WellCare member care coordination.\n    tools:\n    - name: get-member-profile\n      description: Get a WellCare member's demographic profile and contact information.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.get-patient\n      with:\n        id: tools.patient_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-coverage\n      description: Get insurance coverage and enrollment details for a WellCare member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-coverage\n      with:\n        patient: tools.patient_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-claims-history\n      description: Get historical claims and EOB data for a WellCare member. Supports up to 5 years of history.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-explanation-of-benefit\n\
  \      with:\n        patient: tools.patient_id\n        type: tools.claim_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-active-conditions\n      description: Get active diagnoses and conditions for a WellCare member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-conditions\n      with:\n        patient: tools.patient_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-medications\n      description: Get current and historical medication prescriptions for a WellCare member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-medication-requests\n      with:\n        patient: tools.patient_id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-immunization-history\n      description: Get immunization records and history\
  \ for a WellCare member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-immunizations\n      with:\n        patient: tools.patient_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-care-encounters\n      description: Get care visit and encounter history for a WellCare member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wellcare-patient-access.list-encounters\n      with:\n        patient: tools.patient_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-in-network-providers\n      description: Search for in-network WellCare providers by name or specialty.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wellcare-provider-directory.search-practitioners\n      with:\n        name: tools.provider_name\n        specialty: tools.specialty\n        identifier: tools.npi\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: find-network-facilities\n      description: Search for in-network hospitals, clinics, and healthcare facilities.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wellcare-provider-directory.search-organizations\n      with:\n        name: tools.facility_name\n        type: tools.facility_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-care-locations-near-zip\n      description: Find WellCare in-network care delivery locations near a ZIP code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wellcare-provider-directory.search-locations\n      with:\n        address-postalcode: tools.zip_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plan-information\n      description: Get WellCare insurance plan details including network and benefit information.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: wellcare-provider-directory.search-insurance-plans\n      with:\n        name: tools.plan_name\n        type: tools.plan_type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wellcare-health-plans/refs/heads/main/capabilities/member-care-coordination.yaml
tags:
- Healthcare
- FHIR
- Care Coordination
- Patient Access
- Provider Directory
- Managed Care
- Medicaid
- Medicare
tools:
- description: Get a WellCare member's demographic profile and contact information.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-profile
- description: Get insurance coverage and enrollment details for a WellCare member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-coverage
- description: Get historical claims and EOB data for a WellCare member. Supports up to 5 years of history.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-claims-history
- description: Get active diagnoses and conditions for a WellCare member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-active-conditions
- description: Get current and historical medication prescriptions for a WellCare member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-medications
- description: Get immunization records and history for a WellCare member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-immunization-history
- description: Get care visit and encounter history for a WellCare member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-care-encounters
- description: Search for in-network WellCare providers by name or specialty.
  hints:
    openWorld: true
    readOnly: true
  name: search-in-network-providers
- description: Search for in-network hospitals, clinics, and healthcare facilities.
  hints:
    openWorld: true
    readOnly: true
  name: find-network-facilities
- description: Find WellCare in-network care delivery locations near a ZIP code.
  hints:
    openWorld: true
    readOnly: true
  name: find-care-locations-near-zip
- description: Get WellCare insurance plan details including network and benefit information.
  hints:
    openWorld: true
    readOnly: true
  name: get-plan-information
---
