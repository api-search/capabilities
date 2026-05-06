---
categories: []
consumed_apis: []
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
- delete room
- register a webhook to receive webex event notifications
- meetings
- list messages in a room
- calling
- list scheduled webex meetings
- list available webex meeting recordings
- list messages
- webex
- manage webex collaboration rooms
- schedule a new webex video meeting
- get meeting details
- get the list of participants who joined a webex meeting
- schedule a new webex video meeting with participants
- get room
- delete a webex room
- manage webex event webhooks
- list upcoming webex meetings
- access webex meeting recordings
- list people
- create room
- list messages in a webex room
- create webhook
- list registered webhooks
- communication
- enterprise
- list meetings
- post a message to a webex room
- single meeting operations
- search for webex users by email or display name
- get meeting
- messaging
- create a new webex event webhook
- look up webex users
- list webex collaboration rooms available to the user
- send message
- create a new webex collaboration room
- list rooms
- single room operations
- video conferencing
- cancel a scheduled meeting
- list available webex recordings
- schedule meeting
- search people
- get details of a specific room
- list recordings
- delete meeting
- schedule and manage webex meetings
- search webex users by email or name
- list all webex rooms available to the authenticated user
- post and retrieve messages in webex rooms
- team productivity
- create a new webex collaboration room for team communication
- get meeting participants
- list registered webex event webhooks
- list webhooks
- send a message to a webex room
- collaboration
slug: team-collaboration
source_filename: team-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Webex Team Collaboration\n  description: Unified capability for team collaboration workflows combining Webex Messaging and Webex Meetings APIs. Enables\n    teams to communicate via rooms and messages, schedule and manage video meetings, and automate collaboration workflows.\n    Used by development teams, remote workers, and enterprise communication administrators.\n  tags:\n  - Webex\n  - Collaboration\n  - Communication\n  - Meetings\n  - Messaging\n  - Team Productivity\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBEX_ACCESS_TOKEN: WEBEX_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: webex-messaging\n    baseUri: https://webexapis.com/v1\n    description: Webex Messaging REST API for rooms, messages, teams, and memberships.\n    authentication:\n      type: bearer\n      token: '{{WEBEX_ACCESS_TOKEN}}'\n    resources:\n    - name: rooms\n      path: /rooms\n  \
  \    description: Cisco Webex rooms (formerly known as spaces) are virtual meeting places where people post messages and\n        collaborate.\n      operations:\n      - name: list-rooms\n        method: GET\n        description: List Rooms\n        inputParameters:\n        - name: teamId\n          in: query\n          type: string\n          required: false\n          description: List rooms associated with a team.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: direct or group. Group rooms are conversations between two or more people.\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the maximum number of rooms in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-room\n        method: POST\n        description: Create a Room\n \
  \       inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            teamId: '{{tools.teamId}}'\n      - name: get-room\n        method: GET\n        description: Get Room Details\n        inputParameters:\n        - name: roomId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the room.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-room\n        method: PUT\n        description: Update a Room\n        inputParameters:\n        - name: roomId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the room.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: delete-room\n        method: DELETE\n        description: Delete a Room\n        inputParameters:\n        - name: roomId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the room.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /messages\n      description: Messages are how you communicate in a room. In Webex, each message is displayed on its own line along with\n        a timestamp and sender information.\n      operations:\n      - name: list-messages\n        method: GET\n        description: List Messages\n        inputParameters:\n        - name: roomId\n          in: query\n          type: string\n          required: true\n\
  \          description: List messages in a room, by ID.\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the maximum number of messages in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-message\n        method: POST\n        description: Create a Message\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            roomId: '{{tools.roomId}}'\n            text: '{{tools.text}}'\n            markdown: '{{tools.markdown}}'\n      - name: get-message\n        method: GET\n        description: Get Message Details\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n         \
  \ description: The unique identifier for the message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message\n        method: DELETE\n        description: Delete a Message\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Teams are groups of people with a set of rooms that are visible to all members.\n      operations:\n      - name: list-teams\n        method: GET\n        description: List Teams\n        inputParameters:\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the maximum number of teams\
  \ in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n        description: Create a Team\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-team\n        method: GET\n        description: Get Team Details\n        inputParameters:\n        - name: teamId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people\n      description: People are registered users of Webex. Searching and viewing People requires\
  \ an auth token.\n      operations:\n      - name: list-people\n        method: GET\n        description: List People\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: List people with this email address.\n        - name: displayName\n          in: query\n          type: string\n          required: false\n          description: List people whose name starts with the provided string.\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the number of people in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-person\n        method: GET\n        description: Get Person Details\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description:\
  \ A unique identifier for the person.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Webhooks allow your app to be notified via HTTP when a specific event occurs in Webex.\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List Webhooks\n        inputParameters:\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the number of webhooks in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a Webhook\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            name: '{{tools.name}}'\n            targetUrl: '{{tools.targetUrl}}'\n            resource: '{{tools.resource}}'\n            event: '{{tools.event}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Delete a Webhook\n        inputParameters:\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: webex-meetings\n    baseUri: https://webexapis.com/v1\n    description: Webex Meetings REST API for scheduling, managing, and reporting on meetings.\n    authentication:\n      type: bearer\n      token: '{{WEBEX_ACCESS_TOKEN}}'\n    resources:\n    - name: meetings\n      path: /meetings\n      description: Webex meetings for scheduling and managing video\
  \ conferences.\n      operations:\n      - name: list-meetings\n        method: GET\n        description: List Meetings\n        inputParameters:\n        - name: meetingType\n          in: query\n          type: string\n          required: false\n          description: Scheduled meeting, personal room meeting, or webinar.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Active, scheduled, ready, lobby, in-progress, ended, missed, or expired.\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the number of meetings in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-meeting\n        method: POST\n        description: Create a Meeting\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            start: '{{tools.start}}'\n            end: '{{tools.end}}'\n            invitees: '{{tools.invitees}}'\n      - name: get-meeting\n        method: GET\n        description: Get Meeting Details\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the meeting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-meeting\n        method: PUT\n        description: Update a Meeting\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the meeting.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            start: '{{tools.start}}'\n            end: '{{tools.end}}'\n      - name: delete-meeting\n        method: DELETE\n        description: Delete a Meeting\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the meeting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-participants\n      path: /meetingParticipants\n      description: Participants who joined Webex meetings.\n      operations:\n      - name: list-participants\n        method: GET\n        description: List Meeting Participants\n        inputParameters:\n        - name: meetingId\n          in: query\n          type: string\n          required:\
  \ true\n          description: The unique identifier for the meeting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meeting-invitees\n      path: /meetingInvitees\n      description: People invited to Webex meetings.\n      operations:\n      - name: list-invitees\n        method: GET\n        description: List Meeting Invitees\n        inputParameters:\n        - name: meetingId\n          in: query\n          type: string\n          required: true\n          description: The unique identifier for the meeting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invitee\n        method: POST\n        description: Invite Someone to a Meeting\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \      body:\n          type: json\n          data:\n            meetingId: '{{tools.meetingId}}'\n            email: '{{tools.email}}'\n    - name: meeting-recordings\n      path: /recordings\n      description: Webex meeting recordings.\n      operations:\n      - name: list-recordings\n        method: GET\n        description: List Recordings\n        inputParameters:\n        - name: meetingId\n          in: query\n          type: string\n          required: false\n          description: The unique identifier for the meeting.\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Limit the number of recordings in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-recording\n        method: GET\n        description: Get Recording Details\n        inputParameters:\n        - name: recordingId\n          in: path\n\
  \          type: string\n          required: true\n          description: The unique identifier for the recording.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: webex-collaboration-api\n    description: Unified REST API for Webex team collaboration workflows.\n    resources:\n    - path: /v1/rooms\n      name: rooms\n      description: Manage Webex collaboration rooms\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List all Webex rooms available to the authenticated user\n        call: webex-messaging.list-rooms\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-room\n        description: Create a new Webex collaboration room\n        call: webex-messaging.create-room\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/rooms/{roomId}\n      name: room\n      description: Single room operations\n      operations:\n      - method: GET\n        name: get-room\n        description: Get details of a specific room\n        call: webex-messaging.get-room\n        with:\n          roomId: rest.roomId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-room\n        description: Delete a Webex room\n        call: webex-messaging.delete-room\n        with:\n          roomId: rest.roomId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Post and retrieve messages in Webex rooms\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages in a room\n        call: webex-messaging.list-messages\n        with:\n          roomId: rest.roomId\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n      - method: POST\n        name: send-message\n        description: Post a message to a Webex room\n        call: webex-messaging.create-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meetings\n      name: meetings\n      description: Schedule and manage Webex meetings\n      operations:\n      - method: GET\n        name: list-meetings\n        description: List scheduled Webex meetings\n        call: webex-meetings.list-meetings\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: schedule-meeting\n        description: Schedule a new Webex video meeting\n        call: webex-meetings.create-meeting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meetings/{meetingId}\n      name: meeting\n      description: Single meeting operations\n      operations:\n      - method: GET\n        name: get-meeting\n        description:\
  \ Get meeting details\n        call: webex-meetings.get-meeting\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-meeting\n        description: Cancel a scheduled meeting\n        call: webex-meetings.delete-meeting\n        with:\n          meetingId: rest.meetingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: Look up Webex users\n      operations:\n      - method: GET\n        name: list-people\n        description: Search Webex users by email or name\n        call: webex-messaging.list-people\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings\n      name: recordings\n      description: Access Webex meeting recordings\n      operations:\n      - method: GET\n        name: list-recordings\n        description: List available\
  \ Webex recordings\n        call: webex-meetings.list-recordings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Manage Webex event webhooks\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List registered webhooks\n        call: webex-messaging.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a new Webex event webhook\n        call: webex-messaging.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: webex-collaboration-mcp\n    transport: http\n    description: MCP server for AI-assisted Webex team collaboration workflows.\n    tools:\n    - name: list-rooms\n      description: List Webex collaboration rooms available to the user\n      hints:\n     \
  \   readOnly: true\n        openWorld: true\n      call: webex-messaging.list-rooms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-room\n      description: Create a new Webex collaboration room for team communication\n      hints:\n        readOnly: false\n        destructive: false\n      call: webex-messaging.create-room\n      with:\n        title: tools.title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List messages in a Webex room\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webex-messaging.list-messages\n      with:\n        roomId: tools.roomId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-message\n      description: Send a message to a Webex room\n      hints:\n        readOnly: false\n        destructive: false\n      call: webex-messaging.create-message\n      with:\n        roomId: tools.roomId\n\
  \        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-people\n      description: Search for Webex users by email or display name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webex-messaging.list-people\n      with:\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-meetings\n      description: List upcoming Webex meetings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webex-meetings.list-meetings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-meeting\n      description: Schedule a new Webex video meeting with participants\n      hints:\n        readOnly: false\n        destructive: false\n      call: webex-meetings.create-meeting\n      with:\n        title: tools.title\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-meeting-participants\n      description: Get the list of participants who joined a Webex meeting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webex-meetings.list-participants\n      with:\n        meetingId: tools.meetingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recordings\n      description: List available Webex meeting recordings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webex-meetings.list-recordings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List registered Webex event webhooks\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webex-messaging.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Register a webhook to receive Webex event notifications\n      hints:\n\
  \        readOnly: false\n        destructive: false\n      call: webex-messaging.create-webhook\n      with:\n        name: tools.name\n        targetUrl: tools.targetUrl\n        resource: tools.resource\n        event: tools.event\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
