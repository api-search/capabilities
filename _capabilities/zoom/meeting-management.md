---
categories: []
consumed_apis: []
description: Unified workflow for managing the complete Zoom meeting lifecycle including scheduling, registrants, polls, participants, recordings, and live streaming. Used by meeting organizers, administrators, and automation tools.
layout: capability
name: Zoom Meeting Management
operations:
- description: List all meetings for a user.
  method: GET
  name: list-meetings
  path: /v1/meetings
- description: Create a new meeting.
  method: POST
  name: create-meeting
  path: /v1/meetings
- description: Get meeting details.
  method: GET
  name: get-meeting
  path: /v1/meetings/{meetingId}
- description: Update a meeting.
  method: PATCH
  name: update-meeting
  path: /v1/meetings/{meetingId}
- description: Delete a meeting.
  method: DELETE
  name: delete-meeting
  path: /v1/meetings/{meetingId}
- description: List registrants for a meeting.
  method: GET
  name: list-registrants
  path: /v1/registrants
- description: Add a registrant to a meeting.
  method: POST
  name: add-registrant
  path: /v1/registrants
- description: List polls for a meeting.
  method: GET
  name: list-polls
  path: /v1/polls
- description: Create a poll for a meeting.
  method: POST
  name: create-poll
  path: /v1/polls
- description: Get recordings for a meeting.
  method: GET
  name: get-recordings
  path: /v1/recordings
- description: Delete recordings for a meeting.
  method: DELETE
  name: delete-recordings
  path: /v1/recordings
personas: []
provider_name: Zoom
provider_slug: zoom
search_terms:
- delete a meeting permanently.
- update livestream
- update meeting
- meeting recording management.
- delete all recordings for a meeting.
- get details of a past meeting.
- create meeting
- list registrants
- meeting registration management.
- meetings
- retrieve details of a specific meeting.
- get past meeting details
- delete meeting
- individual meeting operations.
- get recordings for a meeting.
- collaboration
- list meetings
- create a new meeting for a user.
- webinars
- zoom
- list participants of a live or past meeting.
- update a meeting.
- create a new meeting.
- create poll
- list all registrants for a meeting.
- list participants
- delete a meeting.
- list all polls for a meeting.
- get meeting
- chat
- list all meetings scheduled for a user.
- add a registrant to a meeting.
- meeting poll management.
- list registrants for a meeting.
- videos
- delete recordings for a meeting.
- video conferencing
- list polls for a meeting.
- add registrant
- get meeting details.
- delete recordings
- list all meetings for a user.
- get all recordings for a meeting.
- update a meeting's live stream configuration.
- meeting lifecycle management.
- create a poll for a meeting.
- list polls
- update meeting details.
- get recordings
- communications
slug: meeting-management
source_filename: meeting-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zoom Meeting Management\n  description: Unified workflow for managing the complete Zoom meeting lifecycle including scheduling, registrants, polls,\n    participants, recordings, and live streaming. Used by meeting organizers, administrators, and automation tools.\n  tags:\n  - Zoom\n  - Meetings\n  - Video Conferencing\n  - Collaboration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ZOOM_OAUTH_TOKEN: ZOOM_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: zoom-meeting\n    baseUri: https://api.zoom.us/v2\n    description: Zoom Meeting REST API for managing meetings, registrants, polls, participants, live streams, and recordings.\n    authentication:\n      type: bearer\n      token: '{{ZOOM_OAUTH_TOKEN}}'\n    resources:\n    - name: meetings\n      path: /users/{userId}/meetings\n      description: Meeting lifecycle operations for a user.\n      operations:\n      - name:\
  \ list-meetings\n        method: GET\n        description: List all meetings scheduled for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The user ID or email address. Use 'me' for the current user.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: 'Meeting type filter: scheduled, live, upcoming, previous_meetings.'\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        - name: next_page_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-meeting\n        method: POST\n        description: Create\
  \ a new meeting for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The user ID or email address.\n        body:\n          type: json\n          data:\n            topic: '{{tools.topic}}'\n            type: '{{tools.type}}'\n            start_time: '{{tools.start_time}}'\n            duration: '{{tools.duration}}'\n            timezone: '{{tools.timezone}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-details\n      path: /meetings/{meetingId}\n      description: Single meeting operations.\n      operations:\n      - name: get-meeting\n        method: GET\n        description: Retrieve details of a specific meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-meeting\n        method: PATCH\n        description: Update meeting details.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        body:\n          type: json\n          data:\n            topic: '{{tools.topic}}'\n            start_time: '{{tools.start_time}}'\n            duration: '{{tools.duration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-meeting\n        method: DELETE\n        description: Delete a meeting permanently.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-registrants\n      path: /meetings/{meetingId}/registrants\n      description: Manage meeting registrants.\n      operations:\n      - name: list-meeting-registrants\n        method: GET\n        description: List all registrants for a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-meeting-registrant\n        method: POST\n        description: Add a registrant to a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        body:\n          type: json\n          data:\n            email:\
  \ '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-polls\n      path: /meetings/{meetingId}/polls\n      description: Manage meeting polls.\n      operations:\n      - name: list-meeting-polls\n        method: GET\n        description: List all polls for a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-meeting-poll\n        method: POST\n        description: Create a poll for a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n\
  \          description: The meeting ID.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            questions: '{{tools.questions}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-participants\n      path: /meetings/{meetingId}/participants\n      description: Meeting participant operations.\n      operations:\n      - name: list-meeting-participants\n        method: GET\n        description: List participants of a live or past meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-recordings\n      path: /meetings/{meetingId}/recordings\n      description: Meeting recording operations.\n\
  \      operations:\n      - name: get-meeting-recordings\n        method: GET\n        description: Get all recordings for a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-meeting-recordings\n        method: DELETE\n        description: Delete all recordings for a meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-livestream\n      path: /meetings/{meetingId}/livestream\n      description: Live stream operations.\n      operations:\n      - name: update-meeting-livestream\n\
  \        method: PATCH\n        description: Update a meeting's live stream configuration.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting ID.\n        body:\n          type: json\n          data:\n            stream_url: '{{tools.stream_url}}'\n            stream_key: '{{tools.stream_key}}'\n            page_url: '{{tools.page_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: past-meeting\n      path: /past_meetings/{meetingId}\n      description: Past meeting operations.\n      operations:\n      - name: get-past-meeting-details\n        method: GET\n        description: Get details of a past meeting.\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The meeting UUID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zoom-meeting-management-api\n    description: Unified REST API for Zoom meeting lifecycle management.\n    resources:\n    - path: /v1/meetings\n      name: meetings\n      description: Meeting lifecycle management.\n      operations:\n      - method: GET\n        name: list-meetings\n        description: List all meetings for a user.\n        call: zoom-meeting.list-meetings\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-meeting\n        description: Create a new meeting.\n        call: zoom-meeting.create-meeting\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meetings/{meetingId}\n      name: meeting-details\n      description:\
  \ Individual meeting operations.\n      operations:\n      - method: GET\n        name: get-meeting\n        description: Get meeting details.\n        call: zoom-meeting.get-meeting\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-meeting\n        description: Update a meeting.\n        call: zoom-meeting.update-meeting\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-meeting\n        description: Delete a meeting.\n        call: zoom-meeting.delete-meeting\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registrants\n      name: registrants\n      description: Meeting registration management.\n      operations:\n      - method: GET\n        name: list-registrants\n\
  \        description: List registrants for a meeting.\n        call: zoom-meeting.list-meeting-registrants\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-registrant\n        description: Add a registrant to a meeting.\n        call: zoom-meeting.add-meeting-registrant\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/polls\n      name: polls\n      description: Meeting poll management.\n      operations:\n      - method: GET\n        name: list-polls\n        description: List polls for a meeting.\n        call: zoom-meeting.list-meeting-polls\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-poll\n        description: Create a poll for a meeting.\n        call:\
  \ zoom-meeting.create-meeting-poll\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings\n      name: recordings\n      description: Meeting recording management.\n      operations:\n      - method: GET\n        name: get-recordings\n        description: Get recordings for a meeting.\n        call: zoom-meeting.get-meeting-recordings\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-recordings\n        description: Delete recordings for a meeting.\n        call: zoom-meeting.delete-meeting-recordings\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zoom-meeting-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Zoom\
  \ meeting lifecycle management.\n    tools:\n    - name: list-meetings\n      description: List all meetings scheduled for a user.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: zoom-meeting.list-meetings\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-meeting\n      description: Create a new meeting for a user.\n      hints:\n        readOnly: false\n      call: zoom-meeting.create-meeting\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-meeting\n      description: Retrieve details of a specific meeting.\n      hints:\n        readOnly: true\n      call: zoom-meeting.get-meeting\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-meeting\n      description: Update meeting details.\n      hints:\n        readOnly:\
  \ false\n        idempotent: true\n      call: zoom-meeting.update-meeting\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-meeting\n      description: Delete a meeting permanently.\n      hints:\n        destructive: true\n        idempotent: true\n      call: zoom-meeting.delete-meeting\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-registrants\n      description: List all registrants for a meeting.\n      hints:\n        readOnly: true\n      call: zoom-meeting.list-meeting-registrants\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-registrant\n      description: Add a registrant to a meeting.\n      hints:\n        readOnly: false\n      call: zoom-meeting.add-meeting-registrant\n      with:\n        meetingId: tools.meetingId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-polls\n      description: List all polls for a meeting.\n      hints:\n        readOnly: true\n      call: zoom-meeting.list-meeting-polls\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-poll\n      description: Create a poll for a meeting.\n      hints:\n        readOnly: false\n      call: zoom-meeting.create-meeting-poll\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-participants\n      description: List participants of a live or past meeting.\n      hints:\n        readOnly: true\n      call: zoom-meeting.list-meeting-participants\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recordings\n      description: Get all recordings for a meeting.\n\
  \      hints:\n        readOnly: true\n      call: zoom-meeting.get-meeting-recordings\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-recordings\n      description: Delete all recordings for a meeting.\n      hints:\n        destructive: true\n        idempotent: true\n      call: zoom-meeting.delete-meeting-recordings\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-livestream\n      description: Update a meeting's live stream configuration.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: zoom-meeting.update-meeting-livestream\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-past-meeting-details\n      description: Get details of a past meeting.\n      hints:\n        readOnly: true\n      call: zoom-meeting.get-past-meeting-details\n\
  \      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zoom/refs/heads/main/capabilities/meeting-management.yaml
tags:
- Zoom
- Meetings
- Video Conferencing
- Collaboration
tools:
- description: List all meetings scheduled for a user.
  hints:
    openWorld: true
    readOnly: true
  name: list-meetings
- description: Create a new meeting for a user.
  hints:
    readOnly: false
  name: create-meeting
- description: Retrieve details of a specific meeting.
  hints:
    readOnly: true
  name: get-meeting
- description: Update meeting details.
  hints:
    idempotent: true
    readOnly: false
  name: update-meeting
- description: Delete a meeting permanently.
  hints:
    destructive: true
    idempotent: true
  name: delete-meeting
- description: List all registrants for a meeting.
  hints:
    readOnly: true
  name: list-registrants
- description: Add a registrant to a meeting.
  hints:
    readOnly: false
  name: add-registrant
- description: List all polls for a meeting.
  hints:
    readOnly: true
  name: list-polls
- description: Create a poll for a meeting.
  hints:
    readOnly: false
  name: create-poll
- description: List participants of a live or past meeting.
  hints:
    readOnly: true
  name: list-participants
- description: Get all recordings for a meeting.
  hints:
    readOnly: true
  name: get-recordings
- description: Delete all recordings for a meeting.
  hints:
    destructive: true
    idempotent: true
  name: delete-recordings
- description: Update a meeting's live stream configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-livestream
- description: Get details of a past meeting.
  hints:
    readOnly: true
  name: get-past-meeting-details
---
