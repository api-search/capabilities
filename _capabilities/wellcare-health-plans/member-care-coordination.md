---
categories: []
consumed_apis:
- wellcare-patient-access
- wellcare-provider-directory
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
- get immunization records and history for a wellcare member.
- managed care
- in-network providers.
- in-network facilities.
- get member coverage
- get coverage for a member.
- medicare
- get member profile
- get wellcare insurance plan details including network and benefit information.
- search for in-network wellcare providers by name or specialty.
- get a wellcare member's demographic profile and contact information.
- member insurance coverage and enrollment.
- search providers
- fhir
- healthcare
- get member encounters
- care delivery locations.
- member demographic and identity.
- member care encounters.
- search insurance plans.
- find network facilities
- medicaid
- find care locations by zip code.
- get member conditions
- get active diagnoses and conditions for a wellcare member.
- search for in-network hospitals, clinics, and healthcare facilities.
- insurance plan information.
- get member claims history
- get member care encounters
- get medication requests for a member.
- member active medications.
- get historical claims and eob data for a wellcare member. supports up to 5 years of history.
- get member profile by fhir patient id.
- search in-network hospitals and clinics.
- get member active conditions
- search locations
- search plans
- search facilities
- get member immunization history
- get current and historical medication prescriptions for a wellcare member.
- get care visit and encounter history for a wellcare member.
- search in network providers
- provider directory
- care coordination
- get member claims
- find wellcare in-network care delivery locations near a zip code.
- patient access
- member clinical conditions.
- get conditions for a member.
- member claims history.
- get plan information
- search in-network providers by specialty or name.
- find care locations near zip
- get member
- get insurance coverage and enrollment details for a wellcare member.
- get eob claims for a member.
- get member medications
- get care encounters for a member.
slug: member-care-coordination
source_filename: member-care-coordination.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WellCare Member Care Coordination\"\n  description: >-\n    Unified care coordination capability combining WellCare FHIR Patient Access\n    and Provider Directory APIs. Enables care managers, app developers, and\n    member-facing apps to access a member's complete health record alongside\n    in-network provider and facility information for coordinated care delivery\n    across Medicaid and Medicare Advantage plans.\n  tags:\n    - Healthcare\n    - FHIR\n    - Care Coordination\n    - Patient Access\n    - Provider Directory\n    - Managed Care\n    - Medicaid\n    - Medicare\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WELLCARE_PATIENT_ACCESS_TOKEN: WELLCARE_PATIENT_ACCESS_TOKEN\n      WELLCARE_PROVIDER_DIRECTORY_TOKEN: WELLCARE_PROVIDER_DIRECTORY_TOKEN\n\ncapability:\n  consumes:\n    - import: wellcare-patient-access\n      location: ./shared/fhir-patient-access.yaml\n\
  \    - import: wellcare-provider-directory\n      location: ./shared/fhir-provider-directory.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wellcare-care-coordination-api\n      description: \"Unified REST API for WellCare member care coordination.\"\n      resources:\n        - path: /v1/members/{id}\n          name: member-profile\n          description: \"Member demographic and identity.\"\n          operations:\n            - method: GET\n              name: get-member\n              description: \"Get member profile by FHIR Patient ID.\"\n              call: \"wellcare-patient-access.get-patient\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{id}/coverage\n          name: member-coverage\n          description: \"Member insurance coverage and enrollment.\"\n          operations:\n            - method: GET\n          \
  \    name: get-member-coverage\n              description: \"Get coverage for a member.\"\n              call: \"wellcare-patient-access.list-coverage\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{id}/claims\n          name: member-claims\n          description: \"Member claims history.\"\n          operations:\n            - method: GET\n              name: get-member-claims\n              description: \"Get EOB claims for a member.\"\n              call: \"wellcare-patient-access.list-explanation-of-benefit\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{id}/conditions\n          name: member-conditions\n          description: \"Member clinical conditions.\"\n          operations:\n            - method:\
  \ GET\n              name: get-member-conditions\n              description: \"Get conditions for a member.\"\n              call: \"wellcare-patient-access.list-conditions\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{id}/medications\n          name: member-medications\n          description: \"Member active medications.\"\n          operations:\n            - method: GET\n              name: get-member-medications\n              description: \"Get medication requests for a member.\"\n              call: \"wellcare-patient-access.list-medication-requests\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{id}/encounters\n          name: member-encounters\n          description: \"Member care encounters.\"\
  \n          operations:\n            - method: GET\n              name: get-member-encounters\n              description: \"Get care encounters for a member.\"\n              call: \"wellcare-patient-access.list-encounters\"\n              with:\n                patient: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers\n          name: network-providers\n          description: \"In-network providers.\"\n          operations:\n            - method: GET\n              name: search-providers\n              description: \"Search in-network providers by specialty or name.\"\n              call: \"wellcare-provider-directory.search-practitioners\"\n              with:\n                name: \"rest.name\"\n                specialty: \"rest.specialty\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/facilities\n          name:\
  \ network-facilities\n          description: \"In-network facilities.\"\n          operations:\n            - method: GET\n              name: search-facilities\n              description: \"Search in-network hospitals and clinics.\"\n              call: \"wellcare-provider-directory.search-organizations\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: care-locations\n          description: \"Care delivery locations.\"\n          operations:\n            - method: GET\n              name: search-locations\n              description: \"Find care locations by ZIP code.\"\n              call: \"wellcare-provider-directory.search-locations\"\n              with:\n                address-postalcode: \"rest.postalcode\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n\n        - path: /v1/plans\n          name: insurance-plans\n          description: \"Insurance plan information.\"\n          operations:\n            - method: GET\n              name: search-plans\n              description: \"Search insurance plans.\"\n              call: \"wellcare-provider-directory.search-insurance-plans\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wellcare-care-coordination-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WellCare member care coordination.\"\n      tools:\n        - name: get-member-profile\n          description: \"Get a WellCare member's demographic profile and contact information.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.get-patient\"\
  \n          with:\n            id: \"tools.patient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-coverage\n          description: \"Get insurance coverage and enrollment details for a WellCare member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-coverage\"\n          with:\n            patient: \"tools.patient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-claims-history\n          description: \"Get historical claims and EOB data for a WellCare member. Supports up to 5 years of history.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-explanation-of-benefit\"\n          with:\n            patient: \"tools.patient_id\"\n            type: \"tools.claim_type\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-active-conditions\n          description: \"Get active diagnoses and conditions for a WellCare member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-conditions\"\n          with:\n            patient: \"tools.patient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-medications\n          description: \"Get current and historical medication prescriptions for a WellCare member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-medication-requests\"\n          with:\n            patient: \"tools.patient_id\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-immunization-history\n\
  \          description: \"Get immunization records and history for a WellCare member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-immunizations\"\n          with:\n            patient: \"tools.patient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-care-encounters\n          description: \"Get care visit and encounter history for a WellCare member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wellcare-patient-access.list-encounters\"\n          with:\n            patient: \"tools.patient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-in-network-providers\n          description: \"Search for in-network WellCare providers by name or specialty.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"wellcare-provider-directory.search-practitioners\"\n          with:\n            name: \"tools.provider_name\"\n            specialty: \"tools.specialty\"\n            identifier: \"tools.npi\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-network-facilities\n          description: \"Search for in-network hospitals, clinics, and healthcare facilities.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wellcare-provider-directory.search-organizations\"\n          with:\n            name: \"tools.facility_name\"\n            type: \"tools.facility_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-care-locations-near-zip\n          description: \"Find WellCare in-network care delivery locations near a ZIP code.\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"wellcare-provider-directory.search-locations\"\n          with:\n            address-postalcode: \"tools.zip_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-plan-information\n          description: \"Get WellCare insurance plan details including network and benefit information.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wellcare-provider-directory.search-insurance-plans\"\n          with:\n            name: \"tools.plan_name\"\n            type: \"tools.plan_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
