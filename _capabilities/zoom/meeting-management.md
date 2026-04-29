---
categories: []
consumed_apis:
- zoom-meeting
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
- video conferencing
- chat
- meeting lifecycle management.
- get recordings for a meeting.
- get past meeting details
- communications
- list participants of a live or past meeting.
- delete recordings for a meeting.
- list registrants
- update a meeting.
- delete a meeting permanently.
- list participants
- list all meetings for a user.
- delete a meeting.
- videos
- meetings
- list all polls for a meeting.
- list polls for a meeting.
- retrieve details of a specific meeting.
- meeting registration management.
- update meeting
- add registrant
- list all meetings scheduled for a user.
- individual meeting operations.
- meeting poll management.
- webinars
- list polls
- update livestream
- list registrants for a meeting.
- create poll
- update meeting details.
- create a new meeting for a user.
- get all recordings for a meeting.
- delete meeting
- create a new meeting.
- get details of a past meeting.
- add a registrant to a meeting.
- get meeting details.
- delete recordings
- get recordings
- list meetings
- create meeting
- collaboration
- list all registrants for a meeting.
- update a meeting's live stream configuration.
- delete all recordings for a meeting.
- zoom
- meeting recording management.
- get meeting
- create a poll for a meeting.
slug: meeting-management
source_filename: meeting-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Zoom Meeting Management\"\n  description: \"Unified workflow for managing the complete Zoom meeting lifecycle including scheduling, registrants, polls, participants, recordings, and live streaming. Used by meeting organizers, administrators, and automation tools.\"\n  tags:\n    - Zoom\n    - Meetings\n    - Video Conferencing\n    - Collaboration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZOOM_OAUTH_TOKEN: ZOOM_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: zoom-meeting\n      location: ./shared/zoom-meeting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zoom-meeting-management-api\n      description: \"Unified REST API for Zoom meeting lifecycle management.\"\n      resources:\n        - path: /v1/meetings\n          name: meetings\n          description: \"Meeting lifecycle management.\"\n          operations:\n            - method:\
  \ GET\n              name: list-meetings\n              description: \"List all meetings for a user.\"\n              call: \"zoom-meeting.list-meetings\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-meeting\n              description: \"Create a new meeting.\"\n              call: \"zoom-meeting.create-meeting\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meetings/{meetingId}\n          name: meeting-details\n          description: \"Individual meeting operations.\"\n          operations:\n            - method: GET\n              name: get-meeting\n              description: \"Get meeting details.\"\n              call: \"zoom-meeting.get-meeting\"\n              with:\n       \
  \         meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-meeting\n              description: \"Update a meeting.\"\n              call: \"zoom-meeting.update-meeting\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-meeting\n              description: \"Delete a meeting.\"\n              call: \"zoom-meeting.delete-meeting\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/registrants\n          name: registrants\n          description: \"Meeting registration management.\"\n          operations:\n            - method: GET\n            \
  \  name: list-registrants\n              description: \"List registrants for a meeting.\"\n              call: \"zoom-meeting.list-meeting-registrants\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-registrant\n              description: \"Add a registrant to a meeting.\"\n              call: \"zoom-meeting.add-meeting-registrant\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/polls\n          name: polls\n          description: \"Meeting poll management.\"\n          operations:\n            - method: GET\n              name: list-polls\n              description: \"List polls for a meeting.\"\n              call: \"zoom-meeting.list-meeting-polls\"\n              with:\n\
  \                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-poll\n              description: \"Create a poll for a meeting.\"\n              call: \"zoom-meeting.create-meeting-poll\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recordings\n          name: recordings\n          description: \"Meeting recording management.\"\n          operations:\n            - method: GET\n              name: get-recordings\n              description: \"Get recordings for a meeting.\"\n              call: \"zoom-meeting.get-meeting-recordings\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        \
  \    - method: DELETE\n              name: delete-recordings\n              description: \"Delete recordings for a meeting.\"\n              call: \"zoom-meeting.delete-meeting-recordings\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: zoom-meeting-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Zoom meeting lifecycle management.\"\n      tools:\n        - name: list-meetings\n          description: \"List all meetings scheduled for a user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoom-meeting.list-meetings\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-meeting\n          description: \"Create a new\
  \ meeting for a user.\"\n          hints:\n            readOnly: false\n          call: \"zoom-meeting.create-meeting\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-meeting\n          description: \"Retrieve details of a specific meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.get-meeting\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-meeting\n          description: \"Update meeting details.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zoom-meeting.update-meeting\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-meeting\n      \
  \    description: \"Delete a meeting permanently.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"zoom-meeting.delete-meeting\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-registrants\n          description: \"List all registrants for a meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.list-meeting-registrants\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-registrant\n          description: \"Add a registrant to a meeting.\"\n          hints:\n            readOnly: false\n          call: \"zoom-meeting.add-meeting-registrant\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: list-polls\n          description: \"List all polls for a meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.list-meeting-polls\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-poll\n          description: \"Create a poll for a meeting.\"\n          hints:\n            readOnly: false\n          call: \"zoom-meeting.create-meeting-poll\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-participants\n          description: \"List participants of a live or past meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.list-meeting-participants\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-recordings\n          description: \"Get all recordings for a meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.get-meeting-recordings\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-recordings\n          description: \"Delete all recordings for a meeting.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"zoom-meeting.delete-meeting-recordings\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-livestream\n          description: \"Update a meeting's live stream configuration.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zoom-meeting.update-meeting-livestream\"\
  \n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-past-meeting-details\n          description: \"Get details of a past meeting.\"\n          hints:\n            readOnly: true\n          call: \"zoom-meeting.get-past-meeting-details\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
