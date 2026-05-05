---
categories: []
consumed_apis:
- twilio-video
- twilio-accounts
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
- create room
- create subaccount
- communications
- manage accounts for credential administration
- real time
- sms
- list accounts
- create a new video room for real-time communication
- twilio
- manage video rooms
- create a new subaccount to isolate resources for a video application
- email
- verification
- t1
- list video rooms
- conferencing
- list active and completed video rooms
- contact center
- video
- list twilio subaccounts for credential management
- authentication
- voice
- list rooms
- iot
- phone
- create a video room
- collaboration
- messaging
slug: video-conferencing
source_filename: video-conferencing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Twilio Video Conferencing\"\n  description: >-\n    Real-time video communication capability combining Twilio Video for room management\n    and Twilio Accounts for credential management. Used by developers building\n    telehealth, remote collaboration, education, and live event platforms that require\n    video calls, recordings, and multi-participant conferencing.\n  tags:\n    - Twilio\n    - Video\n    - Conferencing\n    - Real Time\n    - Collaboration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n      TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: twilio-video\n      location: ./shared/video.yaml\n    - import: twilio-accounts\n      location: ./shared/accounts.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: twilio-video-conference-api\n      description: \"Unified REST\
  \ API for Twilio video conferencing.\"\n      resources:\n        - path: /v1/rooms\n          name: rooms\n          description: \"Manage video rooms\"\n          operations:\n            - method: GET\n              name: list-rooms\n              description: \"List video rooms\"\n              call: \"twilio-video.list-rooms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-room\n              description: \"Create a video room\"\n              call: \"twilio-video.create-room\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts\n          name: accounts\n          description: \"Manage accounts for credential administration\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List accounts\"\n              call: \"twilio-accounts.list-accounts\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: twilio-video-conference-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Twilio video conferencing.\"\n      tools:\n        - name: list-rooms\n          description: \"List active and completed video rooms\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twilio-video.list-rooms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-room\n          description: \"Create a new video room for real-time communication\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-video.create-room\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accounts\n         \
  \ description: \"List Twilio subaccounts for credential management\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"twilio-accounts.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-subaccount\n          description: \"Create a new subaccount to isolate resources for a video application\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-accounts.create-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
