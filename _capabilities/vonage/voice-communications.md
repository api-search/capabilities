---
categories: []
consumed_apis:
- vonage-voice
description: Voice call workflow for Vonage Voice API. Enables programmatic creation, monitoring, and control of outbound and inbound voice calls. Used by developers building IVR systems, call center solutions, voice notifications, and automated telephony applications.
layout: capability
name: Vonage Voice Communications
operations:
- description: List voice calls with optional status filter.
  method: GET
  name: list-calls
  path: /v1/calls
- description: Create an outbound voice call.
  method: POST
  name: create-call
  path: /v1/calls
- description: Get details of a specific call.
  method: GET
  name: get-call
  path: /v1/calls/{uuid}
- description: Modify an in-progress call.
  method: PUT
  name: update-call
  path: /v1/calls/{uuid}
- description: Play text-to-speech audio in a call.
  method: PUT
  name: play-tts
  path: /v1/calls/{uuid}/talk
- description: Stop text-to-speech in a call.
  method: DELETE
  name: stop-tts
  path: /v1/calls/{uuid}/talk
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- vonage
- update call
- get status and details of a specific call by uuid.
- verification
- play tts
- mute call
- get call
- voice
- create an outbound voice call.
- mute an active call.
- hangup call
- list and create voice calls.
- list voice calls, optionally filtered by status.
- communication
- sms
- play text-to-speech audio in a call.
- text-to-speech in active calls.
- play a text-to-speech message into an active call.
- video conferencing
- messaging
- stop tts
- ivr
- modify an in-progress call.
- manage a specific call.
- voip
- create an outbound voice call to a phone number.
- get details of a specific call.
- stop text-to-speech in a call.
- hang up an active voice call.
- create call
- list calls
- telecommunications
- list voice calls with optional status filter.
slug: voice-communications
source_filename: voice-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vonage Voice Communications\"\n  description: >-\n    Voice call workflow for Vonage Voice API. Enables programmatic creation,\n    monitoring, and control of outbound and inbound voice calls. Used by\n    developers building IVR systems, call center solutions, voice notifications,\n    and automated telephony applications.\n  tags:\n    - Communication\n    - Telecommunications\n    - Voice\n    - VoIP\n    - IVR\n    - Vonage\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VONAGE_JWT_TOKEN: VONAGE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: vonage-voice\n      location: ./shared/voice-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: vonage-voice-api\n      description: \"Unified REST API for Vonage voice call management.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: \"List and create voice\
  \ calls.\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List voice calls with optional status filter.\"\n              call: \"vonage-voice.list-calls\"\n              with:\n                status: \"rest.status\"\n                page_size: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-call\n              description: \"Create an outbound voice call.\"\n              call: \"vonage-voice.create-call\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                ncco: \"rest.ncco\"\n                answer_url: \"rest.answer_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calls/{uuid}\n          name: call\n          description: \"Manage a specific call.\"\n          operations:\n\
  \            - method: GET\n              name: get-call\n              description: \"Get details of a specific call.\"\n              call: \"vonage-voice.get-call\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-call\n              description: \"Modify an in-progress call.\"\n              call: \"vonage-voice.update-call\"\n              with:\n                uuid: \"rest.uuid\"\n                action: \"rest.action\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calls/{uuid}/talk\n          name: call-tts\n          description: \"Text-to-speech in active calls.\"\n          operations:\n            - method: PUT\n              name: play-tts\n              description: \"Play text-to-speech audio in a call.\"\n              call: \"vonage-voice.play-tts\"\
  \n              with:\n                uuid: \"rest.uuid\"\n                text: \"rest.text\"\n                voice_name: \"rest.voice_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: stop-tts\n              description: \"Stop text-to-speech in a call.\"\n              call: \"vonage-voice.stop-tts\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: vonage-voice-mcp\n      transport: http\n      description: \"MCP server for AI-assisted voice call management with Vonage.\"\n      tools:\n        - name: list-calls\n          description: \"List voice calls, optionally filtered by status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vonage-voice.list-calls\"\n    \
  \      with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-call\n          description: \"Create an outbound voice call to a phone number.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-voice.create-call\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            ncco: \"tools.ncco\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-call\n          description: \"Get status and details of a specific call by UUID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vonage-voice.get-call\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hangup-call\n  \
  \        description: \"Hang up an active voice call.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vonage-voice.update-call\"\n          with:\n            uuid: \"tools.uuid\"\n            action: \"hangup\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: play-tts\n          description: \"Play a text-to-speech message into an active call.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-voice.play-tts\"\n          with:\n            uuid: \"tools.uuid\"\n            text: \"tools.text\"\n            voice_name: \"tools.voice_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mute-call\n          description: \"Mute an active call.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: true\n          call: \"vonage-voice.update-call\"\n          with:\n            uuid: \"tools.uuid\"\n            action: \"mute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vonage/refs/heads/main/capabilities/voice-communications.yaml
tags:
- Communication
- Telecommunications
- Voice
- VoIP
- IVR
- Vonage
tools:
- description: List voice calls, optionally filtered by status.
  hints:
    idempotent: true
    readOnly: true
  name: list-calls
- description: Create an outbound voice call to a phone number.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-call
- description: Get status and details of a specific call by UUID.
  hints:
    idempotent: true
    readOnly: true
  name: get-call
- description: Hang up an active voice call.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: hangup-call
- description: Play a text-to-speech message into an active call.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: play-tts
- description: Mute an active call.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: mute-call
---
