---
categories: []
consumed_apis: []
description: Unified capability combining Telefonie Voice and SMS APIs for comprehensive communications workflows. Enables voice calling, SMS messaging, conferencing, and call recording from a single interface. Designed for developers building customer communication, notification, and engagement platforms.
layout: capability
name: Telefonie Communications
operations:
- description: List voice calls with filtering options
  method: GET
  name: list-calls
  path: /v1/calls
- description: Initiate an outbound voice call
  method: POST
  name: initiate-call
  path: /v1/calls
- description: List all conferences
  method: GET
  name: list-conferences
  path: /v1/conferences
- description: Create a new conference room
  method: POST
  name: create-conference
  path: /v1/conferences
- description: List SMS and MMS messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send an SMS or MMS message
  method: POST
  name: send-message
  path: /v1/messages
personas: []
provider_name: Telefonie
provider_slug: telefonie
search_terms:
- create conference
- list messages
- cpaas
- send an sms or mms message to a phone number
- send an sms or mms message
- number provisioning
- list voice calls with filtering options
- create a new multi-party conference call room
- voice
- list all conferences
- sms
- send sms
- initiate call
- telephony
- make call
- list sent and received sms and mms messages
- voip
- messaging
- multi-party conference management
- call recording
- telecommunications
- initiate an outbound voice call
- list sms and mms messages
- send message
- create a new conference room
- list calls
- voice call management
- list conferences
- initiate an outbound phone call to a specified number
- list voice calls with optional status and direction filtering
- list all active and completed conference calls
- sms and mms messaging
- communications
slug: telephony-communications
source_filename: telephony-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefonie Communications\n  description: Unified capability combining Telefonie Voice and SMS APIs for comprehensive communications workflows. Enables\n    voice calling, SMS messaging, conferencing, and call recording from a single interface. Designed for developers building\n    customer communication, notification, and engagement platforms.\n  tags:\n  - Call Recording\n  - Communications\n  - CPaaS\n  - Messaging\n  - SMS\n  - Telephony\n  - Voice\n  - VoIP\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFONIE_API_KEY: TELEFONIE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: telefonie-voice\n    baseUri: https://api.telefonie.com/v1/voice\n    description: Telefonie Voice API for call management and conferencing\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFONIE_API_KEY}}'\n      placement: header\n    resources:\n    - name: calls\n\
  \      path: /calls\n      description: Voice call management\n      operations:\n      - name: list-calls\n        method: GET\n        description: List calls with optional status and direction filters\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by call status\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: inbound or outbound\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: initiate-call\n        method: POST\n        description: Initiate an outbound phone call\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Destination phone number in E.164 format\n        - name: from\n          in: body\n          type: string\n    \
  \      required: true\n          description: Caller ID phone number\n        - name: url\n          in: body\n          type: string\n          required: false\n          description: Webhook URL for call flow control\n        - name: record\n          in: body\n          type: boolean\n          required: false\n          description: Whether to record the call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conferences\n      path: /conferences\n      description: Multi-party conference management\n      operations:\n      - name: list-conferences\n        method: GET\n        description: List all conference calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-conference\n        method: POST\n        description: Create a new conference room\n        inputParameters:\n        - name: friendly_name\n\
  \          in: body\n          type: string\n          required: false\n          description: Human-readable name for the conference\n        - name: record\n          in: body\n          type: boolean\n          required: false\n          description: Auto-record the conference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telefonie-sms\n    baseUri: https://api.telefonie.com/v1/sms\n    description: Telefonie SMS API for sending and receiving text messages\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFONIE_API_KEY}}'\n      placement: header\n    resources:\n    - name: messages\n      path: /messages\n      description: SMS and MMS message management\n      operations:\n      - name: list-messages\n        method: GET\n        description: List sent and received messages\n        inputParameters:\n        - name: direction\n       \
  \   in: query\n          type: string\n          required: false\n          description: inbound or outbound\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by delivery status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send an SMS or MMS message\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Recipient phone number in E.164 format\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Sender phone number\n        - name: body\n          in: body\n          type: string\n          required: false\n          description: Text content of the message\n        - name: media_url\n          in: body\n          type:\
  \ array\n          required: false\n          description: URLs of media for MMS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: telefonie-communications-api\n    description: Unified REST API for Telefonie voice and SMS communications.\n    resources:\n    - path: /v1/calls\n      name: calls\n      description: Voice call management\n      operations:\n      - method: GET\n        name: list-calls\n        description: List voice calls with filtering options\n        call: telefonie-voice.list-calls\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: initiate-call\n        description: Initiate an outbound voice call\n        call: telefonie-voice.initiate-call\n        with:\n          to: rest.to\n          from: rest.from\n          url: rest.url\n          record: rest.record\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conferences\n      name: conferences\n      description: Multi-party conference management\n      operations:\n      - method: GET\n        name: list-conferences\n        description: List all conferences\n        call: telefonie-voice.list-conferences\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-conference\n        description: Create a new conference room\n        call: telefonie-voice.create-conference\n        with:\n          friendly_name: rest.friendly_name\n          record: rest.record\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: SMS and MMS messaging\n      operations:\n      - method: GET\n        name: list-messages\n        description: List SMS and MMS messages\n        call: telefonie-sms.list-messages\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send an SMS or MMS message\n        call: telefonie-sms.send-message\n        with:\n          to: rest.to\n          from: rest.from\n          body: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: telefonie-communications-mcp\n    transport: http\n    description: MCP server for AI-assisted communications using Telefonie voice and SMS APIs.\n    tools:\n    - name: list-calls\n      description: List voice calls with optional status and direction filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefonie-voice.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-call\n      description: Initiate an outbound phone call to a specified number\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: telefonie-voice.initiate-call\n      with:\n        to: tools.to\n        from: tools.from\n        url: tools.url\n        record: tools.record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conferences\n      description: List all active and completed conference calls\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefonie-voice.list-conferences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-conference\n      description: Create a new multi-party conference call room\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefonie-voice.create-conference\n      with:\n        friendly_name: tools.friendly_name\n        record: tools.record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List sent and received SMS and MMS\
  \ messages\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefonie-sms.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms\n      description: Send an SMS or MMS message to a phone number\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefonie-sms.send-message\n      with:\n        to: tools.to\n        from: tools.from\n        body: tools.body\n        media_url: tools.media_url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefonie/refs/heads/main/capabilities/telephony-communications.yaml
tags:
- Call Recording
- Communications
- CPaaS
- Messaging
- SMS
- Telephony
- Voice
- VoIP
tools:
- description: List voice calls with optional status and direction filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-calls
- description: Initiate an outbound phone call to a specified number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: make-call
- description: List all active and completed conference calls
  hints:
    openWorld: false
    readOnly: true
  name: list-conferences
- description: Create a new multi-party conference call room
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-conference
- description: List sent and received SMS and MMS messages
  hints:
    openWorld: false
    readOnly: true
  name: list-messages
- description: Send an SMS or MMS message to a phone number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms
---
