---
categories: []
consumed_apis:
- webex-messaging
- webex-meetings
description: Unified capability for team collaboration workflows combining Webex Messaging and Webex Meetings APIs. Enables teams to communicate via rooms and messages, schedule and manage video meetings, and automate collaboration workflows. Used by development teams, remote workers, and enterprise communication administrators.
layout: capability
name: Webex Team Collaboration
operations:
- description: List all Webex rooms available to the authenticated user
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Create a new Webex collaboration room
  method: POST
  name: create-room
  path: /v1/rooms
- description: Get details of a specific room
  method: GET
  name: get-room
  path: /v1/rooms/{roomId}
- description: Delete a Webex room
  method: DELETE
  name: delete-room
  path: /v1/rooms/{roomId}
- description: List messages in a room
  method: GET
  name: list-messages
  path: /v1/messages
- description: Post a message to a Webex room
  method: POST
  name: send-message
  path: /v1/messages
- description: List scheduled Webex meetings
  method: GET
  name: list-meetings
  path: /v1/meetings
- description: Schedule a new Webex video meeting
  method: POST
  name: schedule-meeting
  path: /v1/meetings
- description: Get meeting details
  method: GET
  name: get-meeting
  path: /v1/meetings/{meetingId}
- description: Cancel a scheduled meeting
  method: DELETE
  name: delete-meeting
  path: /v1/meetings/{meetingId}
- description: Search Webex users by email or name
  method: GET
  name: list-people
  path: /v1/people
- description: List available Webex recordings
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: List registered webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a new Webex event webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Webex
provider_slug: webex
search_terms:
- get meeting details
- schedule and manage webex meetings
- list meetings
- send message
- delete meeting
- post and retrieve messages in webex rooms
- schedule a new webex video meeting with participants
- manage webex collaboration rooms
- list scheduled webex meetings
- list all webex rooms available to the authenticated user
- get meeting
- create webhook
- search for webex users by email or display name
- get the list of participants who joined a webex meeting
- list registered webex event webhooks
- schedule meeting
- look up webex users
- list available webex meeting recordings
- delete a webex room
- create a new webex event webhook
- communication
- register a webhook to receive webex event notifications
- create room
- search webex users by email or name
- get details of a specific room
- video conferencing
- cancel a scheduled meeting
- single meeting operations
- messaging
- collaboration
- list upcoming webex meetings
- get meeting participants
- list recordings
- calling
- list messages in a webex room
- access webex meeting recordings
- enterprise
- list messages
- schedule a new webex video meeting
- list webhooks
- manage webex event webhooks
- team productivity
- single room operations
- list messages in a room
- webex
- meetings
- create a new webex collaboration room
- list registered webhooks
- delete room
- list webex collaboration rooms available to the user
- send a message to a webex room
- get room
- list available webex recordings
- search people
- post a message to a webex room
- list people
- list rooms
- create a new webex collaboration room for team communication
slug: team-collaboration
source_filename: team-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Webex Team Collaboration\"\n  description: >-\n    Unified capability for team collaboration workflows combining Webex Messaging\n    and Webex Meetings APIs. Enables teams to communicate via rooms and messages,\n    schedule and manage video meetings, and automate collaboration workflows. Used\n    by development teams, remote workers, and enterprise communication administrators.\n  tags:\n    - Webex\n    - Collaboration\n    - Communication\n    - Meetings\n    - Messaging\n    - Team Productivity\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBEX_ACCESS_TOKEN: WEBEX_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: webex-messaging\n      location: ./shared/messaging.yaml\n    - import: webex-meetings\n      location: ./shared/meetings.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: webex-collaboration-api\n      description: \"Unified REST\
  \ API for Webex team collaboration workflows.\"\n      resources:\n        - path: /v1/rooms\n          name: rooms\n          description: \"Manage Webex collaboration rooms\"\n          operations:\n            - method: GET\n              name: list-rooms\n              description: \"List all Webex rooms available to the authenticated user\"\n              call: \"webex-messaging.list-rooms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-room\n              description: \"Create a new Webex collaboration room\"\n              call: \"webex-messaging.create-room\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rooms/{roomId}\n          name: room\n          description: \"Single room operations\"\n          operations:\n            - method: GET\n              name: get-room\n              description:\
  \ \"Get details of a specific room\"\n              call: \"webex-messaging.get-room\"\n              with:\n                roomId: \"rest.roomId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-room\n              description: \"Delete a Webex room\"\n              call: \"webex-messaging.delete-room\"\n              with:\n                roomId: \"rest.roomId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: messages\n          description: \"Post and retrieve messages in Webex rooms\"\n          operations:\n            - method: GET\n              name: list-messages\n              description: \"List messages in a room\"\n              call: \"webex-messaging.list-messages\"\n              with:\n                roomId: \"rest.roomId\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Post a message to a Webex room\"\n              call: \"webex-messaging.create-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meetings\n          name: meetings\n          description: \"Schedule and manage Webex meetings\"\n          operations:\n            - method: GET\n              name: list-meetings\n              description: \"List scheduled Webex meetings\"\n              call: \"webex-meetings.list-meetings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: schedule-meeting\n              description: \"Schedule a new Webex video meeting\"\n              call: \"webex-meetings.create-meeting\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n        - path: /v1/meetings/{meetingId}\n          name: meeting\n          description: \"Single meeting operations\"\n          operations:\n            - method: GET\n              name: get-meeting\n              description: \"Get meeting details\"\n              call: \"webex-meetings.get-meeting\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-meeting\n              description: \"Cancel a scheduled meeting\"\n              call: \"webex-meetings.delete-meeting\"\n              with:\n                meetingId: \"rest.meetingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people\n          name: people\n          description: \"Look up Webex users\"\n          operations:\n\
  \            - method: GET\n              name: list-people\n              description: \"Search Webex users by email or name\"\n              call: \"webex-messaging.list-people\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recordings\n          name: recordings\n          description: \"Access Webex meeting recordings\"\n          operations:\n            - method: GET\n              name: list-recordings\n              description: \"List available Webex recordings\"\n              call: \"webex-meetings.list-recordings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Manage Webex event webhooks\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List registered webhooks\"\n              call: \"webex-messaging.list-webhooks\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a new Webex event webhook\"\n              call: \"webex-messaging.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: webex-collaboration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Webex team collaboration workflows.\"\n      tools:\n        - name: list-rooms\n          description: \"List Webex collaboration rooms available to the user\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webex-messaging.list-rooms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-room\n          description: \"Create a new Webex collaboration room\
  \ for team communication\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webex-messaging.create-room\"\n          with:\n            title: \"tools.title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messages\n          description: \"List messages in a Webex room\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webex-messaging.list-messages\"\n          with:\n            roomId: \"tools.roomId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-message\n          description: \"Send a message to a Webex room\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webex-messaging.create-message\"\n          with:\n            roomId: \"tools.roomId\"\n            text: \"tools.text\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: search-people\n          description: \"Search for Webex users by email or display name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webex-messaging.list-people\"\n          with:\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-meetings\n          description: \"List upcoming Webex meetings\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webex-meetings.list-meetings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-meeting\n          description: \"Schedule a new Webex video meeting with participants\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webex-meetings.create-meeting\"\n          with:\n          \
  \  title: \"tools.title\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-meeting-participants\n          description: \"Get the list of participants who joined a Webex meeting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webex-meetings.list-participants\"\n          with:\n            meetingId: \"tools.meetingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-recordings\n          description: \"List available Webex meeting recordings\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webex-meetings.list-recordings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List registered Webex event webhooks\"\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webex-messaging.list-webhooks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Register a webhook to receive Webex event notifications\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webex-messaging.create-webhook\"\n          with:\n            name: \"tools.name\"\n            targetUrl: \"tools.targetUrl\"\n            resource: \"tools.resource\"\n            event: \"tools.event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/webex/refs/heads/main/capabilities/team-collaboration.yaml
tags:
- Webex
- Collaboration
- Communication
- Meetings
- Messaging
- Team Productivity
tools:
- description: List Webex collaboration rooms available to the user
  hints:
    openWorld: true
    readOnly: true
  name: list-rooms
- description: Create a new Webex collaboration room for team communication
  hints:
    destructive: false
    readOnly: false
  name: create-room
- description: List messages in a Webex room
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Send a message to a Webex room
  hints:
    destructive: false
    readOnly: false
  name: send-message
- description: Search for Webex users by email or display name
  hints:
    openWorld: true
    readOnly: true
  name: search-people
- description: List upcoming Webex meetings
  hints:
    openWorld: true
    readOnly: true
  name: list-meetings
- description: Schedule a new Webex video meeting with participants
  hints:
    destructive: false
    readOnly: false
  name: schedule-meeting
- description: Get the list of participants who joined a Webex meeting
  hints:
    openWorld: false
    readOnly: true
  name: get-meeting-participants
- description: List available Webex meeting recordings
  hints:
    openWorld: true
    readOnly: true
  name: list-recordings
- description: List registered Webex event webhooks
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: Register a webhook to receive Webex event notifications
  hints:
    destructive: false
    readOnly: false
  name: create-webhook
---
