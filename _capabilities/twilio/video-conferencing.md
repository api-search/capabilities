---
categories: []
consumed_apis: []
description: Real-time video communication capability combining Twilio Video for room management and Twilio Accounts for credential management. Used by developers building telehealth, remote collaboration, education, and live event platforms that require video calls, recordings, and multi-participant conferencing.
layout: capability
name: Twilio Video Conferencing
operations:
- description: List video rooms
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Create a video room
  method: POST
  name: create-room
  path: /v1/rooms
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
personas: []
provider_name: Twilio
provider_slug: twilio
search_terms:
- video
- list video rooms
- create a new subaccount to isolate resources for a video application
- conferencing
- manage video rooms
- list accounts
- list twilio subaccounts for credential management
- authentication
- sms
- collaboration
- create a video room
- create subaccount
- t1
- email
- create room
- iot
- real time
- twilio
- verification
- create a new video room for real-time communication
- list rooms
- manage accounts for credential administration
- voice
- phone
- list active and completed video rooms
- messaging
- contact center
- communications
slug: video-conferencing
source_filename: video-conferencing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twilio Video Conferencing\n  description: Real-time video communication capability combining Twilio Video for room management and Twilio Accounts for\n    credential management. Used by developers building telehealth, remote collaboration, education, and live event platforms\n    that require video calls, recordings, and multi-participant conferencing.\n  tags:\n  - Twilio\n  - Video\n  - Conferencing\n  - Real Time\n  - Collaboration\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n    TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: twilio-video\n    baseUri: https://video.twilio.com/v1\n    description: Twilio Video API v1\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: rooms\n      path: /Rooms\n      description:\
  \ Create and manage video rooms\n      operations:\n      - name: list-rooms\n        method: GET\n        description: Retrieve a list of video rooms\n        inputParameters:\n        - name: Status\n          in: query\n          type: string\n          required: false\n          description: Filter by room status (in-progress, completed)\n        - name: UniqueName\n          in: query\n          type: string\n          required: false\n          description: Filter by unique room name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-room\n        method: POST\n        description: Create a new video room\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            UniqueName: '{{tools.unique_name}}'\n            Type: '{{tools.type}}'\n\
  \            MaxParticipants: '{{tools.max_participants}}'\n  - type: http\n    namespace: twilio-accounts\n    baseUri: https://accounts.twilio.com/v1\n    description: Twilio Accounts API\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /Accounts.json\n      description: Manage Twilio accounts and subaccounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: Retrieve list of subaccounts\n        inputParameters:\n        - name: FriendlyName\n          in: query\n          type: string\n          required: false\n          description: Filter by friendly name\n        - name: Status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: create-account\n        method: POST\n        description: Create a new subaccount\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            FriendlyName: '{{tools.friendly_name}}'\n    - name: keys\n      path: /Accounts/{AccountSid}/Keys.json\n      description: Manage API keys\n      operations:\n      - name: list-keys\n        method: GET\n        description: List API keys for an account\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-key\n        method: POST\n        description: Create a new API key\n        inputParameters:\n        - name:\
  \ AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            FriendlyName: '{{tools.friendly_name}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: twilio-video-conference-api\n    description: Unified REST API for Twilio video conferencing.\n    resources:\n    - path: /v1/rooms\n      name: rooms\n      description: Manage video rooms\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List video rooms\n        call: twilio-video.list-rooms\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-room\n        description: Create a video room\n        call: twilio-video.create-room\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Manage accounts for credential administration\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List accounts\n        call: twilio-accounts.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: twilio-video-conference-mcp\n    transport: http\n    description: MCP server for AI-assisted Twilio video conferencing.\n    tools:\n    - name: list-rooms\n      description: List active and completed video rooms\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twilio-video.list-rooms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-room\n      description: Create a new video room for real-time communication\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ twilio-video.create-room\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List Twilio subaccounts for credential management\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twilio-accounts.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subaccount\n      description: Create a new subaccount to isolate resources for a video application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-accounts.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twilio/refs/heads/main/capabilities/video-conferencing.yaml
tags:
- Twilio
- Video
- Conferencing
- Real Time
- Collaboration
tools:
- description: List active and completed video rooms
  hints:
    openWorld: true
    readOnly: true
  name: list-rooms
- description: Create a new video room for real-time communication
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-room
- description: List Twilio subaccounts for credential management
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Create a new subaccount to isolate resources for a video application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-subaccount
---
