---
categories: []
consumed_apis: []
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
- get details of a specific call.
- mute an active call.
- hangup call
- play text-to-speech audio in a call.
- list voice calls with optional status filter.
- create an outbound voice call to a phone number.
- stop text-to-speech in a call.
- list and create voice calls.
- voice
- communication
- create call
- manage a specific call.
- vonage
- mute call
- sms
- ivr
- voip
- messaging
- telecommunications
- create an outbound voice call.
- stop tts
- modify an in-progress call.
- video conferencing
- list calls
- play tts
- update call
- get status and details of a specific call by uuid.
- get call
- hang up an active voice call.
- text-to-speech in active calls.
- play a text-to-speech message into an active call.
- list voice calls, optionally filtered by status.
- verification
slug: voice-communications
source_filename: voice-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vonage Voice Communications\n  description: Voice call workflow for Vonage Voice API. Enables programmatic creation, monitoring, and control of outbound\n    and inbound voice calls. Used by developers building IVR systems, call center solutions, voice notifications, and automated\n    telephony applications.\n  tags:\n  - Communication\n  - Telecommunications\n  - Voice\n  - VoIP\n  - IVR\n  - Vonage\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VONAGE_JWT_TOKEN: VONAGE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vonage-voice\n    baseUri: https://api.nexmo.com\n    description: Vonage Voice API for creating and controlling calls.\n    authentication:\n      type: bearer\n      token: '{{VONAGE_JWT_TOKEN}}'\n    resources:\n    - name: calls\n      path: /v1/calls\n      description: Manage voice calls.\n      operations:\n      - name: list-calls\n        method: GET\n\
  \        description: List all calls for your Vonage account.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by call status.\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-call\n        method: POST\n        description: Create an outbound voice call.\n        inputParameters:\n        - name: to\n          in: body\n          type: array\n          required: true\n          description: Array of call endpoints to call.\n        - name: from\n          in: body\n          type: object\n          required: true\n          description: Caller endpoint.\n        - name: ncco\n          in: body\n          type: array\n          required:\
  \ false\n          description: NCCO call control object.\n        - name: answer_url\n          in: body\n          type: array\n          required: false\n          description: Answer webhook URL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: call\n      path: /v1/calls/{uuid}\n      description: Manage a specific call.\n      operations:\n      - name: get-call\n        method: GET\n        description: Get details of a specific call.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The call UUID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-call\n        method: PUT\n        description: Modify an in-progress call (hangup, mute, transfer).\n        inputParameters:\n        - name: uuid\n      \
  \    in: path\n          type: string\n          required: true\n          description: The call UUID.\n        - name: action\n          in: body\n          type: string\n          required: true\n          description: 'Action to take: hangup, mute, unmute, transfer.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: call-stream\n      path: /v1/calls/{uuid}/stream\n      description: Stream audio into a call.\n      operations:\n      - name: play-audio\n        method: PUT\n        description: Play an audio file into a call.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The call UUID.\n        - name: stream_url\n          in: body\n          type: array\n          required: true\n          description: URLs to stream audio from.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: stop-audio\n        method: DELETE\n        description: Stop playing audio in a call.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The call UUID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: call-talk\n      path: /v1/calls/{uuid}/talk\n      description: Text-to-speech in a call.\n      operations:\n      - name: play-tts\n        method: PUT\n        description: Play text-to-speech in a call.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The call UUID.\n        - name: text\n          in: body\n          type: string\n          required: true\n          description: Text to be read to the callee.\n        - name: voice_name\n\
  \          in: body\n          type: string\n          required: false\n          description: The voice name for TTS.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-tts\n        method: DELETE\n        description: Stop text-to-speech in a call.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The call UUID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: vonage-voice-api\n    description: Unified REST API for Vonage voice call management.\n    resources:\n    - path: /v1/calls\n      name: calls\n      description: List and create voice calls.\n      operations:\n      - method: GET\n        name: list-calls\n        description: List voice calls with optional\
  \ status filter.\n        call: vonage-voice.list-calls\n        with:\n          status: rest.status\n          page_size: rest.page_size\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-call\n        description: Create an outbound voice call.\n        call: vonage-voice.create-call\n        with:\n          to: rest.to\n          from: rest.from\n          ncco: rest.ncco\n          answer_url: rest.answer_url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calls/{uuid}\n      name: call\n      description: Manage a specific call.\n      operations:\n      - method: GET\n        name: get-call\n        description: Get details of a specific call.\n        call: vonage-voice.get-call\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-call\n        description: Modify\
  \ an in-progress call.\n        call: vonage-voice.update-call\n        with:\n          uuid: rest.uuid\n          action: rest.action\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calls/{uuid}/talk\n      name: call-tts\n      description: Text-to-speech in active calls.\n      operations:\n      - method: PUT\n        name: play-tts\n        description: Play text-to-speech audio in a call.\n        call: vonage-voice.play-tts\n        with:\n          uuid: rest.uuid\n          text: rest.text\n          voice_name: rest.voice_name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: stop-tts\n        description: Stop text-to-speech in a call.\n        call: vonage-voice.stop-tts\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: vonage-voice-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted voice call management with Vonage.\n    tools:\n    - name: list-calls\n      description: List voice calls, optionally filtered by status.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vonage-voice.list-calls\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-call\n      description: Create an outbound voice call to a phone number.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-voice.create-call\n      with:\n        to: tools.to\n        from: tools.from\n        ncco: tools.ncco\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-call\n      description: Get status and details of a specific call by UUID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vonage-voice.get-call\n      with:\n        uuid: tools.uuid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hangup-call\n      description: Hang up an active voice call.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vonage-voice.update-call\n      with:\n        uuid: tools.uuid\n        action: hangup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: play-tts\n      description: Play a text-to-speech message into an active call.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-voice.play-tts\n      with:\n        uuid: tools.uuid\n        text: tools.text\n        voice_name: tools.voice_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mute-call\n      description: Mute an active call.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vonage-voice.update-call\n      with:\n\
  \        uuid: tools.uuid\n        action: mute\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
