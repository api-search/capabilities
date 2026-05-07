---
categories: []
consumed_apis: []
description: Room scheduling workflow capability using the Steelcase RoomWizard API to manage conference room reservations, check availability, and synchronize bookings with enterprise calendaring systems. Enables facilities managers, employees, and workplace automation tools to find available rooms, create bookings, and manage reservations across an organization's conference room inventory.
layout: capability
name: Steelcase Room Scheduling
operations:
- description: List all conference rooms filtered by building, floor, or minimum capacity.
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Get conference room details.
  method: GET
  name: get-room
  path: /v1/rooms/{room_id}
- description: Check room availability for a given time window.
  method: GET
  name: get-availability
  path: /v1/availability
- description: Retrieve bookings for a room or date range.
  method: GET
  name: get-bookings
  path: /v1/bookings
- description: Create a new room booking.
  method: POST
  name: create-booking
  path: /v1/bookings
- description: Cancel an existing booking.
  method: POST
  name: cancel-booking
  path: /v1/bookings/{booking_id}/cancel
- description: Get RoomWizard connector health status.
  method: GET
  name: get-status
  path: /v1/status
personas: []
provider_name: Steelcase
provider_slug: steelcase
search_terms:
- check which conference rooms are available during a specified time window.
- calendaring
- cancel a booking.
- list conference rooms filtered by building, floor, or minimum capacity.
- check room availability for a given time window.
- system status.
- check availability
- office furniture
- room availability across a time window.
- list bookings
- get availability
- cancel an existing booking.
- get system status
- room scheduling
- retrieve bookings for a room or date range.
- create booking
- conference rooms
- conference rooms available for booking.
- list existing bookings for a room or date range.
- get status
- cancel an existing conference room booking.
- workplace
- check the health and connectivity status of the roomwizard system.
- facilities management
- iot
- create a new conference room booking for a meeting.
- get roomwizard connector health status.
- get room details
- create a new room booking.
- get bookings
- cancel booking
- list rooms
- smart office
- list all conference rooms filtered by building, floor, or minimum capacity.
- get conference room details.
- get details about a specific conference room including capacity and equipment.
- individual room details.
- get room
- conference room bookings.
- office 365
slug: room-scheduling
source_filename: room-scheduling.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Steelcase Room Scheduling\n  description: Room scheduling workflow capability using the Steelcase RoomWizard API to manage conference room reservations,\n    check availability, and synchronize bookings with enterprise calendaring systems. Enables facilities managers, employees,\n    and workplace automation tools to find available rooms, create bookings, and manage reservations across an organization's\n    conference room inventory.\n  tags:\n  - Room Scheduling\n  - Conference Rooms\n  - Facilities Management\n  - Workplace\n  - Calendaring\n  - Office 365\n  - Smart Office\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: steelcase-roomwizard\n    baseUri: https://roomwizard.local:443/api\n    description: Steelcase RoomWizard Connector API for room booking management.\n    resources:\n    - name: bookings\n      path: /get_bookings\n \
  \     description: Conference room bookings.\n      operations:\n      - name: get-bookings\n        method: GET\n        description: Returns room bookings optionally filtered by room or date range.\n        inputParameters:\n        - name: room_id\n          in: query\n          type: string\n          required: false\n          description: Filter by room ID.\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD).\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-booking\n        method: POST\n        description: Creates a new conference room booking.\n        body:\n          type: json\n          data:\n            room_id: '{{tools.room_id}}'\n  \
  \          subject: '{{tools.subject}}'\n            organizer: '{{tools.organizer}}'\n            start_time: '{{tools.start_time}}'\n            end_time: '{{tools.end_time}}'\n            attendee_count: '{{tools.attendee_count}}'\n            notes: '{{tools.notes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-booking\n        method: POST\n        description: Cancels an existing room booking.\n        body:\n          type: json\n          data:\n            booking_id: '{{tools.booking_id}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability\n      path: /get_availability\n      description: Room availability.\n      operations:\n      - name: get-room-availability\n        method: GET\n        description: Returns room availability for\
  \ a time range.\n        inputParameters:\n        - name: room_id\n          in: query\n          type: string\n          required: false\n          description: Specific room ID.\n        - name: start_time\n          in: query\n          type: string\n          required: true\n          description: Start of availability window (ISO 8601).\n        - name: end_time\n          in: query\n          type: string\n          required: true\n          description: End of availability window (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rooms\n      path: /get_rooms\n      description: Conference rooms.\n      operations:\n      - name: list-rooms\n        method: GET\n        description: Returns all RoomWizard-managed conference rooms.\n        inputParameters:\n        - name: building\n          in: query\n          type: string\n          required: false\n          description: Filter\
  \ by building.\n        - name: floor\n          in: query\n          type: string\n          required: false\n          description: Filter by floor.\n        - name: min_capacity\n          in: query\n          type: integer\n          required: false\n          description: Minimum room capacity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-room\n        method: GET\n        description: Returns details for a specific room.\n        inputParameters:\n        - name: room_id\n          in: query\n          type: string\n          required: true\n          description: Room identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      description: Connector health status.\n      operations:\n      - name: get-connector-status\n        method: GET\n        description:\
  \ Returns the health and connectivity status of the RoomWizard connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: steelcase-scheduling-api\n    description: Unified REST API for conference room scheduling and management via Steelcase RoomWizard.\n    resources:\n    - path: /v1/rooms\n      name: rooms\n      description: Conference rooms available for booking.\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List all conference rooms filtered by building, floor, or minimum capacity.\n        call: steelcase-roomwizard.list-rooms\n        with:\n          building: rest.building\n          floor: rest.floor\n          min_capacity: rest.min_capacity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms/{room_id}\n      name: room\n      description: Individual\
  \ room details.\n      operations:\n      - method: GET\n        name: get-room\n        description: Get conference room details.\n        call: steelcase-roomwizard.get-room\n        with:\n          room_id: rest.room_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/availability\n      name: availability\n      description: Room availability across a time window.\n      operations:\n      - method: GET\n        name: get-availability\n        description: Check room availability for a given time window.\n        call: steelcase-roomwizard.get-room-availability\n        with:\n          room_id: rest.room_id\n          start_time: rest.start_time\n          end_time: rest.end_time\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings\n      name: bookings\n      description: Conference room bookings.\n      operations:\n      - method: GET\n        name: get-bookings\n        description: Retrieve\
  \ bookings for a room or date range.\n        call: steelcase-roomwizard.get-bookings\n        with:\n          room_id: rest.room_id\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-booking\n        description: Create a new room booking.\n        call: steelcase-roomwizard.create-booking\n        with:\n          room_id: rest.room_id\n          subject: rest.subject\n          organizer: rest.organizer\n          start_time: rest.start_time\n          end_time: rest.end_time\n          attendee_count: rest.attendee_count\n          notes: rest.notes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings/{booking_id}/cancel\n      name: cancel-booking\n      description: Cancel a booking.\n      operations:\n      - method: POST\n        name: cancel-booking\n        description: Cancel an existing\
  \ booking.\n        call: steelcase-roomwizard.cancel-booking\n        with:\n          booking_id: rest.booking_id\n          reason: rest.reason\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/status\n      name: status\n      description: System status.\n      operations:\n      - method: GET\n        name: get-status\n        description: Get RoomWizard connector health status.\n        call: steelcase-roomwizard.get-connector-status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: steelcase-scheduling-mcp\n    transport: http\n    description: MCP server for AI-assisted conference room scheduling using Steelcase RoomWizard.\n    tools:\n    - name: list-rooms\n      description: List conference rooms filtered by building, floor, or minimum capacity.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: steelcase-roomwizard.list-rooms\n      with:\n\
  \        building: tools.building\n        floor: tools.floor\n        min_capacity: tools.min_capacity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-room-details\n      description: Get details about a specific conference room including capacity and equipment.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: steelcase-roomwizard.get-room\n      with:\n        room_id: tools.room_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-availability\n      description: Check which conference rooms are available during a specified time window.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: steelcase-roomwizard.get-room-availability\n      with:\n        room_id: tools.room_id\n        start_time: tools.start_time\n        end_time: tools.end_time\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bookings\n      description:\
  \ List existing bookings for a room or date range.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: steelcase-roomwizard.get-bookings\n      with:\n        room_id: tools.room_id\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-booking\n      description: Create a new conference room booking for a meeting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: steelcase-roomwizard.create-booking\n      with:\n        room_id: tools.room_id\n        subject: tools.subject\n        organizer: tools.organizer\n        start_time: tools.start_time\n        end_time: tools.end_time\n        attendee_count: tools.attendee_count\n        notes: tools.notes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-booking\n      description: Cancel an existing conference room\
  \ booking.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: steelcase-roomwizard.cancel-booking\n      with:\n        booking_id: tools.booking_id\n        reason: tools.reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system-status\n      description: Check the health and connectivity status of the RoomWizard system.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: steelcase-roomwizard.get-connector-status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/steelcase/refs/heads/main/capabilities/room-scheduling.yaml
tags:
- Room Scheduling
- Conference Rooms
- Facilities Management
- Workplace
- Calendaring
- Office 365
- Smart Office
tools:
- description: List conference rooms filtered by building, floor, or minimum capacity.
  hints:
    openWorld: true
    readOnly: true
  name: list-rooms
- description: Get details about a specific conference room including capacity and equipment.
  hints:
    openWorld: false
    readOnly: true
  name: get-room-details
- description: Check which conference rooms are available during a specified time window.
  hints:
    openWorld: false
    readOnly: true
  name: check-availability
- description: List existing bookings for a room or date range.
  hints:
    openWorld: false
    readOnly: true
  name: list-bookings
- description: Create a new conference room booking for a meeting.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-booking
- description: Cancel an existing conference room booking.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cancel-booking
- description: Check the health and connectivity status of the RoomWizard system.
  hints:
    openWorld: false
    readOnly: true
  name: get-system-status
---
