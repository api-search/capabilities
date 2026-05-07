---
categories: []
consumed_apis: []
description: The Marriott Developer API provides programmatic access to Marriott International's hotel and property systems. The API enables integration with Marriott's Central Reservation System for property search, availability lookup, and booking management across Marriott's portfolio of hotel brands worldwide.
layout: capability
name: Marriott Developer API
operations:
- description: Search properties
  method: GET
  name: searchproperties
  path: /properties
- description: Get property details
  method: GET
  name: getproperty
  path: /properties/{propertyId}
- description: Check room availability
  method: GET
  name: checkavailability
  path: /availability
- description: Create a reservation
  method: POST
  name: createreservation
  path: /reservations
- description: Get reservation details
  method: GET
  name: getreservation
  path: /reservations/{confirmationNumber}
personas: []
provider_name: Marriott International
provider_slug: marriott-international
search_terms:
- getreservation
- createreservation
- marriott
- checkavailability
- searchproperties
- international
- get property details
- create a reservation
- api
- search properties
- getproperty
- get reservation details
- check room availability
slug: marriott-international-capability
source_filename: marriott-international-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Marriott Developer API\n  description: The Marriott Developer API provides programmatic access to Marriott International's hotel and property systems.\n    The API enables integration with Marriott's Central Reservation System for property search, availability lookup, and booking\n    management across Marriott's portfolio of hotel brands worldwide.\n  tags:\n  - Marriott\n  - International\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marriott-international\n    baseUri: https://devportalprod.marriott.com\n    description: Marriott Developer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MARRIOTT_INTERNATIONAL_TOKEN}}'\n    resources:\n    - name: properties\n      path: /properties\n      operations:\n      - name: searchproperties\n        method: GET\n        description: Search properties\n        inputParameters:\n        - name: location\n\
  \          in: query\n          type: string\n          description: City or geographic location to search.\n        - name: brand\n          in: query\n          type: string\n          description: Filter by Marriott brand code.\n        - name: radius\n          in: query\n          type: number\n          description: Search radius in miles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties-propertyid\n      path: /properties/{propertyId}\n      operations:\n      - name: getproperty\n        method: GET\n        description: Get property details\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: The unique property identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability\n      path:\
  \ /availability\n      operations:\n      - name: checkavailability\n        method: GET\n        description: Check room availability\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: string\n          required: true\n          description: The unique property identifier.\n        - name: checkIn\n          in: query\n          type: string\n          required: true\n          description: Check-in date.\n        - name: checkOut\n          in: query\n          type: string\n          required: true\n          description: Check-out date.\n        - name: guests\n          in: query\n          type: integer\n          description: Number of guests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reservations\n      path: /reservations\n      operations:\n      - name: createreservation\n        method: POST\n        description: Create a reservation\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reservations-confirmationnumber\n      path: /reservations/{confirmationNumber}\n      operations:\n      - name: getreservation\n        method: GET\n        description: Get reservation details\n        inputParameters:\n        - name: confirmationNumber\n          in: path\n          type: string\n          required: true\n          description: The reservation confirmation number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marriott-international-rest\n    description: REST adapter for Marriott Developer API.\n    resources:\n    - path: /properties\n      name: searchproperties\n      operations:\n      - method: GET\n        name: searchproperties\n        description: Search properties\n        call:\
  \ marriott-international.searchproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/{propertyId}\n      name: getproperty\n      operations:\n      - method: GET\n        name: getproperty\n        description: Get property details\n        call: marriott-international.getproperty\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /availability\n      name: checkavailability\n      operations:\n      - method: GET\n        name: checkavailability\n        description: Check room availability\n        call: marriott-international.checkavailability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reservations\n      name: createreservation\n      operations:\n      - method: POST\n        name: createreservation\n        description: Create a reservation\n        call: marriott-international.createreservation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reservations/{confirmationNumber}\n      name: getreservation\n      operations:\n      - method: GET\n        name: getreservation\n        description: Get reservation details\n        call: marriott-international.getreservation\n        with:\n          confirmationNumber: rest.confirmationNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marriott-international-mcp\n    transport: http\n    description: MCP adapter for Marriott Developer API for AI agent use.\n    tools:\n    - name: searchproperties\n      description: Search properties\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marriott-international.searchproperties\n      with:\n        location: tools.location\n        brand: tools.brand\n        radius: tools.radius\n      inputParameters:\n      - name:\
  \ location\n        type: string\n        description: City or geographic location to search.\n      - name: brand\n        type: string\n        description: Filter by Marriott brand code.\n      - name: radius\n        type: number\n        description: Search radius in miles.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproperty\n      description: Get property details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marriott-international.getproperty\n      with:\n        propertyId: tools.propertyId\n      inputParameters:\n      - name: propertyId\n        type: string\n        description: The unique property identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkavailability\n      description: Check room availability\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ marriott-international.checkavailability\n      with:\n        propertyId: tools.propertyId\n        checkIn: tools.checkIn\n        checkOut: tools.checkOut\n        guests: tools.guests\n      inputParameters:\n      - name: propertyId\n        type: string\n        description: The unique property identifier.\n        required: true\n      - name: checkIn\n        type: string\n        description: Check-in date.\n        required: true\n      - name: checkOut\n        type: string\n        description: Check-out date.\n        required: true\n      - name: guests\n        type: integer\n        description: Number of guests.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreservation\n      description: Create a reservation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marriott-international.createreservation\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: getreservation\n      description: Get reservation details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marriott-international.getreservation\n      with:\n        confirmationNumber: tools.confirmationNumber\n      inputParameters:\n      - name: confirmationNumber\n        type: string\n        description: The reservation confirmation number.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MARRIOTT_INTERNATIONAL_TOKEN: MARRIOTT_INTERNATIONAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marriott-international/refs/heads/main/capabilities/marriott-international-capability.yaml
tags:
- Marriott
- International
- API
tools:
- description: Search properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchproperties
- description: Get property details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperty
- description: Check room availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: checkavailability
- description: Create a reservation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreservation
- description: Get reservation details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreservation
---
