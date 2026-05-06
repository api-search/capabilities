---
categories: []
consumed_apis: []
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
- search and find walgreens pharmacy locations
- list store numbers
- attach patient to appointment
- get available vaccine appointment timeslots near a location
- immunizations
- get details for a specific pharmacy location
- check vaccine eligibility
- confirm a vaccine appointment
- store locator
- walgreens
- determine which vaccines a patient is eligible for
- healthcare
- retail
- get complete list of all walgreens store numbers
- find nearby walgreens pharmacy locations by address or coordinates
- confirm vaccine appointment
- get detailed hours and services for a specific walgreens
- find available vaccine appointment times at walgreens locations near a specified zip code. returns locations with available dates and time slots.
- finalize a vaccine appointment booking
- finalize a held vaccine appointment to complete the booking
- pharmacy
- hold a vaccine appointment timeslot
- get detailed hours, services, and contact information for a specific walgreens pharmacy
- get vaccine timeslots
- create and manage vaccine appointments
- get pharmacy details
- search stores
- prescriptions
- reserve a specific vaccine appointment slot at a walgreens location
- list all walgreens store numbers
- vaccines
- check which vaccines a patient is eligible for based on their state and date of birth. returns eligible and ineligible vaccine lists with details.
- check patient vaccine eligibility
- find available vaccine appointment times
- register patient for vaccine appointment
- register patient information for a held appointment
- hold vaccine appointment
- find walgreens pharmacy locations near an address, zip code, or coordinates. supports filtering by services like 24-hour pharmacy, drive-thru, or flu shots.
- get store details
- search walgreens pharmacies
- find vaccine appointments
slug: pharmacy-and-healthcare
source_filename: pharmacy-and-healthcare.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Walgreens Pharmacy and Healthcare\n  description: 'Workflow capability combining Walgreens Store Locator and Vaccine Scheduling APIs for pharmacy and healthcare\n    applications. Enables end-to-end patient workflows: finding nearby Walgreens pharmacies, checking vaccine eligibility,\n    discovering available appointment slots, and booking immunization appointments. Designed for healthcare applications,\n    patient portals, and wellness platforms.'\n  tags:\n  - Walgreens\n  - Pharmacy\n  - Healthcare\n  - Vaccines\n  - Immunizations\n  - Store Locator\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WALGREENS_API_KEY: WALGREENS_API_KEY\n    WALGREENS_AFFILIATE_ID: WALGREENS_AFFILIATE_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: walgreens-store-locator\n    baseUri: https://services.walgreens.com\n    description: Walgreens store location search and details API\n    authentication:\n\
  \      type: apikey\n      key: apiKey\n      value: '{{WALGREENS_API_KEY}}'\n      placement: body\n    resources:\n    - name: store-search\n      path: /api/stores/search/v2\n      description: Search Walgreens stores by location\n      operations:\n      - name: search-stores\n        method: POST\n        description: Search for Walgreens stores by geolocation, address, or zip code\n        inputParameters:\n        - name: lat\n          in: body\n          type: number\n          required: false\n          description: Latitude coordinate for search\n        - name: lng\n          in: body\n          type: number\n          required: false\n          description: Longitude coordinate for search\n        - name: address\n          in: body\n          type: string\n          required: false\n          description: Street address for search\n        - name: zip\n          in: body\n          type: string\n          required: false\n          description: Zip code for search\n     \
  \   - name: r\n          in: body\n          type: integer\n          required: true\n          description: Search radius in miles\n        - name: s\n          in: body\n          type: integer\n          required: true\n          description: Items per page\n        - name: p\n          in: body\n          type: integer\n          required: true\n          description: Page number\n        - name: filterOptions\n          in: body\n          type: array\n          required: false\n          description: Service filter options\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: array\n          value: $.results\n    - name: store-details\n      path: /api/stores/details/v1\n      description: Get detailed information for a specific store\n      operations:\n      - name: get-store-details\n        method: POST\n        description: Retrieve comprehensive details for a specific Walgreens store\n        inputParameters:\n        - name: storeNo\n\
  \          in: body\n          type: string\n          required: true\n          description: Store number to query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: store-numbers\n      path: /api/util/storenumber/v1\n      description: Get all store numbers\n      operations:\n      - name: list-store-numbers\n        method: POST\n        description: Retrieve complete list of all Walgreens store numbers\n        inputParameters:\n        - name: act\n          in: body\n          type: string\n          required: true\n          description: Always set to storenumber\n        outputRawFormat: json\n        outputParameters:\n        - name: store\n          type: array\n          value: $.store\n  - type: http\n    namespace: walgreens-vaccine-scheduling\n    baseUri: https://services.walgreens.com\n    description: Walgreens vaccine and immunization appointment scheduling API\n    authentication:\n\
  \      type: apikey\n      key: apiKey\n      value: '{{WALGREENS_API_KEY}}'\n      placement: body\n    resources:\n    - name: eligibility\n      path: /api/vaccine/scheduling/eligibility/v1\n      description: Check vaccine eligibility by state and date of birth\n      operations:\n      - name: check-vaccine-eligibility\n        method: POST\n        description: Determine vaccine eligibility for a patient by state and DOB\n        inputParameters:\n        - name: state\n          in: body\n          type: string\n          required: true\n          description: Two-character US state code\n        - name: dob\n          in: body\n          type: string\n          required: true\n          description: Patient date of birth in YYYY-MM-DD format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeslots\n      path: /api/vaccine/scheduling/timeslots/v1\n      description: Get available vaccine\
  \ appointment timeslots\n      operations:\n      - name: get-vaccine-timeslots\n        method: POST\n        description: Retrieve available appointment timeslots for vaccines near a location\n        inputParameters:\n        - name: state\n          in: body\n          type: string\n          required: true\n          description: Two-character US state code\n        - name: zipCode\n          in: body\n          type: string\n          required: true\n          description: Location zip code\n        - name: dob\n          in: body\n          type: string\n          required: true\n          description: Patient date of birth\n        - name: vaccine\n          in: body\n          type: array\n          required: true\n          description: Array of vaccine codes to search\n        - name: appointmentAvailability\n          in: body\n          type: object\n          required: true\n          description: Date range for appointment search\n        - name: position\n          in:\
  \ body\n          type: object\n          required: true\n          description: Geographic coordinates for distance sorting\n        outputRawFormat: json\n        outputParameters:\n        - name: locations\n          type: array\n          value: $.locations\n    - name: hold\n      path: /api/vaccine/scheduling/hold/v1\n      description: Hold a vaccine appointment timeslot\n      operations:\n      - name: hold-vaccine-appointment\n        method: POST\n        description: Reserve a specific vaccine appointment timeslot\n        inputParameters:\n        - name: locationId\n          in: body\n          type: string\n          required: true\n          description: Store location identifier\n        - name: appointmentDate\n          in: body\n          type: string\n          required: true\n          description: ISO format appointment date/time\n        - name: slot\n          in: body\n          type: string\n          required: true\n          description: Time slot to hold\n\
  \        - name: channel\n          in: body\n          type: string\n          required: true\n          description: Web or Mobile\n        - name: vaccines\n          in: body\n          type: array\n          required: true\n          description: Vaccine selection objects\n        outputRawFormat: json\n        outputParameters:\n        - name: engagementId\n          type: string\n          value: $.engagementId\n    - name: patient\n      path: /api/vaccine/scheduling/patient/v1\n      description: Attach patient information to an appointment\n      operations:\n      - name: attach-patient-to-appointment\n        method: POST\n        description: Register patient PII for a held vaccine appointment\n        inputParameters:\n        - name: engagementId\n          in: body\n          type: string\n          required: true\n          description: Engagement ID from hold response\n        - name: partnerId\n          in: body\n          type: string\n          required: true\n \
  \         description: Client application name\n        - name: firstName\n          in: body\n          type: string\n          required: true\n          description: Patient first name\n        - name: lastName\n          in: body\n          type: string\n          required: true\n          description: Patient last name\n        - name: dob\n          in: body\n          type: string\n          required: true\n          description: Patient date of birth\n        - name: gender\n          in: body\n          type: string\n          required: true\n          description: Patient gender\n        - name: contact\n          in: body\n          type: object\n          required: true\n          description: Patient contact information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: confirm\n      path: /api/vaccine/scheduling/confirm/v1\n      description: Confirm a vaccine appointment\n      operations:\n\
  \      - name: confirm-vaccine-appointment\n        method: PATCH\n        description: Finalize a held vaccine appointment reservation\n        inputParameters:\n        - name: engagementId\n          in: body\n          type: string\n          required: true\n          description: Engagement ID from hold response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: walgreens-pharmacy-healthcare-api\n    description: Unified REST API for Walgreens pharmacy and healthcare workflows.\n    resources:\n    - path: /v1/stores\n      name: stores\n      description: Search and find Walgreens pharmacy locations\n      operations:\n      - method: POST\n        name: search-stores\n        description: Find nearby Walgreens pharmacy locations by address or coordinates\n        call: walgreens-store-locator.search-stores\n        outputParameters:\n        - type:\
  \ array\n          mapping: $.results\n    - path: /v1/stores/{storeNo}\n      name: store-detail\n      description: Get details for a specific pharmacy location\n      operations:\n      - method: GET\n        name: get-store-details\n        description: Get detailed hours and services for a specific Walgreens\n        call: walgreens-store-locator.get-store-details\n        with:\n          storeNo: rest.storeNo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/store-numbers\n      name: store-numbers\n      description: List all Walgreens store numbers\n      operations:\n      - method: GET\n        name: list-store-numbers\n        description: Get complete list of all Walgreens store numbers\n        call: walgreens-store-locator.list-store-numbers\n        outputParameters:\n        - type: array\n          mapping: $.store\n    - path: /v1/vaccine-eligibility\n      name: vaccine-eligibility\n      description: Check patient vaccine eligibility\n\
  \      operations:\n      - method: POST\n        name: check-vaccine-eligibility\n        description: Determine which vaccines a patient is eligible for\n        call: walgreens-vaccine-scheduling.check-vaccine-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vaccine-timeslots\n      name: vaccine-timeslots\n      description: Find available vaccine appointment times\n      operations:\n      - method: POST\n        name: get-vaccine-timeslots\n        description: Get available vaccine appointment timeslots near a location\n        call: walgreens-vaccine-scheduling.get-vaccine-timeslots\n        outputParameters:\n        - type: array\n          mapping: $.locations\n    - path: /v1/vaccine-appointments\n      name: vaccine-appointments\n      description: Create and manage vaccine appointments\n      operations:\n      - method: POST\n        name: hold-vaccine-appointment\n        description: Hold a vaccine appointment timeslot\n\
  \        call: walgreens-vaccine-scheduling.hold-vaccine-appointment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vaccine-appointments/{engagementId}/patient\n      name: vaccine-appointment-patient\n      description: Register patient for vaccine appointment\n      operations:\n      - method: POST\n        name: attach-patient-to-appointment\n        description: Register patient information for a held appointment\n        call: walgreens-vaccine-scheduling.attach-patient-to-appointment\n        with:\n          engagementId: rest.engagementId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vaccine-appointments/{engagementId}/confirm\n      name: vaccine-appointment-confirm\n      description: Confirm a vaccine appointment\n      operations:\n      - method: PATCH\n        name: confirm-vaccine-appointment\n        description: Finalize a vaccine appointment booking\n        call: walgreens-vaccine-scheduling.confirm-vaccine-appointment\n\
  \        with:\n          engagementId: rest.engagementId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: walgreens-pharmacy-healthcare-mcp\n    transport: http\n    description: MCP server for AI-assisted Walgreens pharmacy and healthcare workflows.\n    tools:\n    - name: search-walgreens-pharmacies\n      description: Find Walgreens pharmacy locations near an address, zip code, or coordinates. Supports filtering by services\n        like 24-hour pharmacy, drive-thru, or flu shots.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walgreens-store-locator.search-stores\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        address: tools.address\n        zip: tools.zip\n        r: tools.radius\n        s: tools.pageSize\n        p: tools.page\n        filterOptions: tools.filterOptions\n      outputParameters:\n      - type: array\n        mapping: $.results\n    - name:\
  \ get-pharmacy-details\n      description: Get detailed hours, services, and contact information for a specific Walgreens pharmacy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walgreens-store-locator.get-store-details\n      with:\n        storeNo: tools.storeNo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-vaccine-eligibility\n      description: Check which vaccines a patient is eligible for based on their state and date of birth. Returns eligible\n        and ineligible vaccine lists with details.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walgreens-vaccine-scheduling.check-vaccine-eligibility\n      with:\n        state: tools.state\n        dob: tools.dob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-vaccine-appointments\n      description: Find available vaccine appointment times at Walgreens locations near a specified zip code. Returns\
  \ locations\n        with available dates and time slots.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walgreens-vaccine-scheduling.get-vaccine-timeslots\n      with:\n        state: tools.state\n        zipCode: tools.zipCode\n        dob: tools.dob\n        vaccine: tools.vaccine\n        appointmentAvailability: tools.appointmentAvailability\n        position: tools.position\n      outputParameters:\n      - type: array\n        mapping: $.locations\n    - name: hold-vaccine-appointment\n      description: Reserve a specific vaccine appointment slot at a Walgreens location\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: walgreens-vaccine-scheduling.hold-vaccine-appointment\n      with:\n        locationId: tools.locationId\n        appointmentDate: tools.appointmentDate\n        slot: tools.slot\n        channel: tools.channel\n        vaccines: tools.vaccines\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: confirm-vaccine-appointment\n      description: Finalize a held vaccine appointment to complete the booking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: walgreens-vaccine-scheduling.confirm-vaccine-appointment\n      with:\n        engagementId: tools.engagementId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
