---
categories: []
consumed_apis:
- walgreens-store-locator
- walgreens-vaccine-scheduling
description: 'Workflow capability combining Walgreens Store Locator and Vaccine Scheduling APIs for pharmacy and healthcare applications. Enables end-to-end patient workflows: finding nearby Walgreens pharmacies, checking vaccine eligibility, discovering available appointment slots, and booking immunization appointments. Designed for healthcare applications, patient portals, and wellness platforms.'
layout: capability
name: Walgreens Pharmacy and Healthcare
operations:
- description: Find nearby Walgreens pharmacy locations by address or coordinates
  method: POST
  name: search-stores
  path: /v1/stores
- description: Get detailed hours and services for a specific Walgreens
  method: GET
  name: get-store-details
  path: /v1/stores/{storeNo}
- description: Get complete list of all Walgreens store numbers
  method: GET
  name: list-store-numbers
  path: /v1/store-numbers
- description: Determine which vaccines a patient is eligible for
  method: POST
  name: check-vaccine-eligibility
  path: /v1/vaccine-eligibility
- description: Get available vaccine appointment timeslots near a location
  method: POST
  name: get-vaccine-timeslots
  path: /v1/vaccine-timeslots
- description: Hold a vaccine appointment timeslot
  method: POST
  name: hold-vaccine-appointment
  path: /v1/vaccine-appointments
- description: Register patient information for a held appointment
  method: POST
  name: attach-patient-to-appointment
  path: /v1/vaccine-appointments/{engagementId}/patient
- description: Finalize a vaccine appointment booking
  method: PATCH
  name: confirm-vaccine-appointment
  path: /v1/vaccine-appointments/{engagementId}/confirm
personas: []
provider_name: Walgreens
provider_slug: walgreens
search_terms:
- get details for a specific pharmacy location
- find walgreens pharmacy locations near an address, zip code, or coordinates. supports filtering by services like 24-hour pharmacy, drive-thru, or flu shots.
- finalize a vaccine appointment booking
- find available vaccine appointment times at walgreens locations near a specified zip code. returns locations with available dates and time slots.
- find nearby walgreens pharmacy locations by address or coordinates
- prescriptions
- store locator
- determine which vaccines a patient is eligible for
- search stores
- get vaccine timeslots
- find available vaccine appointment times
- healthcare
- immunizations
- pharmacy
- create and manage vaccine appointments
- confirm a vaccine appointment
- vaccines
- check vaccine eligibility
- reserve a specific vaccine appointment slot at a walgreens location
- search walgreens pharmacies
- confirm vaccine appointment
- get detailed hours, services, and contact information for a specific walgreens pharmacy
- retail
- get pharmacy details
- attach patient to appointment
- register patient information for a held appointment
- list all walgreens store numbers
- hold vaccine appointment
- get available vaccine appointment timeslots near a location
- hold a vaccine appointment timeslot
- register patient for vaccine appointment
- get complete list of all walgreens store numbers
- check which vaccines a patient is eligible for based on their state and date of birth. returns eligible and ineligible vaccine lists with details.
- finalize a held vaccine appointment to complete the booking
- get store details
- walgreens
- search and find walgreens pharmacy locations
- check patient vaccine eligibility
- find vaccine appointments
- list store numbers
- get detailed hours and services for a specific walgreens
slug: pharmacy-and-healthcare
source_filename: pharmacy-and-healthcare.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Walgreens Pharmacy and Healthcare\"\n  description: >-\n    Workflow capability combining Walgreens Store Locator and Vaccine Scheduling APIs\n    for pharmacy and healthcare applications. Enables end-to-end patient workflows:\n    finding nearby Walgreens pharmacies, checking vaccine eligibility, discovering\n    available appointment slots, and booking immunization appointments. Designed\n    for healthcare applications, patient portals, and wellness platforms.\n  tags:\n    - Walgreens\n    - Pharmacy\n    - Healthcare\n    - Vaccines\n    - Immunizations\n    - Store Locator\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WALGREENS_API_KEY: WALGREENS_API_KEY\n      WALGREENS_AFFILIATE_ID: WALGREENS_AFFILIATE_ID\n\ncapability:\n  consumes:\n    - import: walgreens-store-locator\n      location: ./shared/store-locator.yaml\n    - import: walgreens-vaccine-scheduling\n   \
  \   location: ./shared/vaccine-scheduling.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: walgreens-pharmacy-healthcare-api\n      description: \"Unified REST API for Walgreens pharmacy and healthcare workflows.\"\n      resources:\n        - path: /v1/stores\n          name: stores\n          description: \"Search and find Walgreens pharmacy locations\"\n          operations:\n            - method: POST\n              name: search-stores\n              description: \"Find nearby Walgreens pharmacy locations by address or coordinates\"\n              call: \"walgreens-store-locator.search-stores\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.results\"\n        - path: /v1/stores/{storeNo}\n          name: store-detail\n          description: \"Get details for a specific pharmacy location\"\n          operations:\n            - method: GET\n              name: get-store-details\n              description: \"Get\
  \ detailed hours and services for a specific Walgreens\"\n              call: \"walgreens-store-locator.get-store-details\"\n              with:\n                storeNo: \"rest.storeNo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/store-numbers\n          name: store-numbers\n          description: \"List all Walgreens store numbers\"\n          operations:\n            - method: GET\n              name: list-store-numbers\n              description: \"Get complete list of all Walgreens store numbers\"\n              call: \"walgreens-store-locator.list-store-numbers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.store\"\n        - path: /v1/vaccine-eligibility\n          name: vaccine-eligibility\n          description: \"Check patient vaccine eligibility\"\n          operations:\n            - method: POST\n              name: check-vaccine-eligibility\n  \
  \            description: \"Determine which vaccines a patient is eligible for\"\n              call: \"walgreens-vaccine-scheduling.check-vaccine-eligibility\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vaccine-timeslots\n          name: vaccine-timeslots\n          description: \"Find available vaccine appointment times\"\n          operations:\n            - method: POST\n              name: get-vaccine-timeslots\n              description: \"Get available vaccine appointment timeslots near a location\"\n              call: \"walgreens-vaccine-scheduling.get-vaccine-timeslots\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.locations\"\n        - path: /v1/vaccine-appointments\n          name: vaccine-appointments\n          description: \"Create and manage vaccine appointments\"\n          operations:\n            - method: POST\n              name: hold-vaccine-appointment\n\
  \              description: \"Hold a vaccine appointment timeslot\"\n              call: \"walgreens-vaccine-scheduling.hold-vaccine-appointment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vaccine-appointments/{engagementId}/patient\n          name: vaccine-appointment-patient\n          description: \"Register patient for vaccine appointment\"\n          operations:\n            - method: POST\n              name: attach-patient-to-appointment\n              description: \"Register patient information for a held appointment\"\n              call: \"walgreens-vaccine-scheduling.attach-patient-to-appointment\"\n              with:\n                engagementId: \"rest.engagementId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vaccine-appointments/{engagementId}/confirm\n          name: vaccine-appointment-confirm\n          description:\
  \ \"Confirm a vaccine appointment\"\n          operations:\n            - method: PATCH\n              name: confirm-vaccine-appointment\n              description: \"Finalize a vaccine appointment booking\"\n              call: \"walgreens-vaccine-scheduling.confirm-vaccine-appointment\"\n              with:\n                engagementId: \"rest.engagementId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: walgreens-pharmacy-healthcare-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Walgreens pharmacy and healthcare workflows.\"\n      tools:\n        - name: search-walgreens-pharmacies\n          description: >-\n            Find Walgreens pharmacy locations near an address, zip code, or coordinates.\n            Supports filtering by services like 24-hour pharmacy, drive-thru, or flu shots.\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"walgreens-store-locator.search-stores\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            address: \"tools.address\"\n            zip: \"tools.zip\"\n            r: \"tools.radius\"\n            s: \"tools.pageSize\"\n            p: \"tools.page\"\n            filterOptions: \"tools.filterOptions\"\n          outputParameters:\n            - type: array\n              mapping: \"$.results\"\n        - name: get-pharmacy-details\n          description: \"Get detailed hours, services, and contact information for a specific Walgreens pharmacy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"walgreens-store-locator.get-store-details\"\n          with:\n            storeNo: \"tools.storeNo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-vaccine-eligibility\n          description: >-\n            Check\
  \ which vaccines a patient is eligible for based on their state and\n            date of birth. Returns eligible and ineligible vaccine lists with details.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"walgreens-vaccine-scheduling.check-vaccine-eligibility\"\n          with:\n            state: \"tools.state\"\n            dob: \"tools.dob\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-vaccine-appointments\n          description: >-\n            Find available vaccine appointment times at Walgreens locations near a\n            specified zip code. Returns locations with available dates and time slots.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"walgreens-vaccine-scheduling.get-vaccine-timeslots\"\n          with:\n            state: \"tools.state\"\n            zipCode: \"tools.zipCode\"\n            dob: \"tools.dob\"\n    \
  \        vaccine: \"tools.vaccine\"\n            appointmentAvailability: \"tools.appointmentAvailability\"\n            position: \"tools.position\"\n          outputParameters:\n            - type: array\n              mapping: \"$.locations\"\n        - name: hold-vaccine-appointment\n          description: \"Reserve a specific vaccine appointment slot at a Walgreens location\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"walgreens-vaccine-scheduling.hold-vaccine-appointment\"\n          with:\n            locationId: \"tools.locationId\"\n            appointmentDate: \"tools.appointmentDate\"\n            slot: \"tools.slot\"\n            channel: \"tools.channel\"\n            vaccines: \"tools.vaccines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: confirm-vaccine-appointment\n          description: \"Finalize a held vaccine appointment to\
  \ complete the booking\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"walgreens-vaccine-scheduling.confirm-vaccine-appointment\"\n          with:\n            engagementId: \"tools.engagementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/walgreens/refs/heads/main/capabilities/pharmacy-and-healthcare.yaml
tags:
- Walgreens
- Pharmacy
- Healthcare
- Vaccines
- Immunizations
- Store Locator
tools:
- description: Find Walgreens pharmacy locations near an address, zip code, or coordinates. Supports filtering by services like 24-hour pharmacy, drive-thru, or flu shots.
  hints:
    openWorld: true
    readOnly: true
  name: search-walgreens-pharmacies
- description: Get detailed hours, services, and contact information for a specific Walgreens pharmacy
  hints:
    openWorld: false
    readOnly: true
  name: get-pharmacy-details
- description: Check which vaccines a patient is eligible for based on their state and date of birth. Returns eligible and ineligible vaccine lists with details.
  hints:
    openWorld: true
    readOnly: true
  name: check-vaccine-eligibility
- description: Find available vaccine appointment times at Walgreens locations near a specified zip code. Returns locations with available dates and time slots.
  hints:
    openWorld: true
    readOnly: true
  name: find-vaccine-appointments
- description: Reserve a specific vaccine appointment slot at a Walgreens location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: hold-vaccine-appointment
- description: Finalize a held vaccine appointment to complete the booking
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: confirm-vaccine-appointment
---
