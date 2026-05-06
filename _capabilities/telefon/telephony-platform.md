---
categories: []
consumed_apis: []
description: Unified capability combining Telefon Voice and SMS APIs for comprehensive programmable communications. Supports voice calls, conferencing, SMS messaging, and recording across 180+ countries. Designed for developers building customer communication, notification, and engagement applications.
layout: capability
name: Telefon Communications Platform
operations:
- description: List voice calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: Initiate an outbound voice call
  method: POST
  name: create-call
  path: /v1/calls
- description: List conferences
  method: GET
  name: list-conferences
  path: /v1/conferences
- description: Create a conference room
  method: POST
  name: create-conference
  path: /v1/conferences
- description: List messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send an SMS or MMS message
  method: POST
  name: send-message
  path: /v1/messages
personas: []
provider_name: Telefon
provider_slug: telefon
search_terms:
- create conference
- list messages
- cpaas
- send an sms or mms message globally
- global coverage
- send an sms or mms message
- number provisioning
- list voice calls with optional status and direction filters
- list voice calls
- create a new conference call room
- voice
- create call
- sms
- initiate an outbound phone call to a number
- send sms
- telephony
- make call
- list sent and received sms and mms messages
- voip
- messaging
- call recording
- conference call management
- initiate an outbound voice call
- send message
- list calls
- voice call management
- list conferences
- sms and mms messaging
- create a conference room
- list active and completed conferences
- communications
slug: telephony-platform
source_filename: telephony-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefon Communications Platform\n  description: Unified capability combining Telefon Voice and SMS APIs for comprehensive programmable communications. Supports\n    voice calls, conferencing, SMS messaging, and recording across 180+ countries. Designed for developers building customer\n    communication, notification, and engagement applications.\n  tags:\n  - Communications\n  - CPaaS\n  - Messaging\n  - SMS\n  - Telephony\n  - Voice\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFON_API_KEY: TELEFON_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: telefon-voice\n    baseUri: https://api.telefon.com/v1/voice\n    description: Telefon Voice API for programmable calling\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFON_API_KEY}}'\n      placement: header\n    resources:\n    - name: calls\n      path: /calls\n      description: Voice call\
  \ management\n      operations:\n      - name: list-calls\n        method: GET\n        description: List calls with optional filtering\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by call status\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: 'Filter: inbound or outbound'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-call\n        method: POST\n        description: Initiate an outbound voice call\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Destination number (E.164)\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Caller ID number\n        - name:\
  \ url\n          in: body\n          type: string\n          required: false\n          description: Call flow webhook URL\n        - name: record\n          in: body\n          type: boolean\n          required: false\n          description: Auto-record the call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conferences\n      path: /conferences\n      description: Conference call management\n      operations:\n      - name: list-conferences\n        method: GET\n        description: List conferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-conference\n        method: POST\n        description: Create a conference room\n        inputParameters:\n        - name: friendly_name\n          in: body\n          type: string\n          required: false\n          description: Conference name\n \
  \       - name: record\n          in: body\n          type: boolean\n          required: false\n          description: Auto-record the conference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telefon-sms\n    baseUri: https://api.telefon.com/v1/sms\n    description: Telefon SMS API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFON_API_KEY}}'\n      placement: header\n    resources:\n    - name: messages\n      path: /messages\n      description: SMS and MMS messaging\n      operations:\n      - name: list-messages\n        method: GET\n        description: List messages\n        inputParameters:\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: inbound or outbound\n        - name: status\n          in: query\n          type: string\n          required: false\n     \
  \     description: Filter by delivery status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send an SMS or MMS message\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Recipient number (E.164)\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Sender number\n        - name: body\n          in: body\n          type: string\n          required: false\n          description: Message text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: telefon-platform-api\n    description: Unified REST API for Telefon communications.\n    resources:\n    - path: /v1/calls\n\
  \      name: calls\n      description: Voice call management\n      operations:\n      - method: GET\n        name: list-calls\n        description: List voice calls\n        call: telefon-voice.list-calls\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-call\n        description: Initiate an outbound voice call\n        call: telefon-voice.create-call\n        with:\n          to: rest.to\n          from: rest.from\n          url: rest.url\n          record: rest.record\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conferences\n      name: conferences\n      description: Conference call management\n      operations:\n      - method: GET\n        name: list-conferences\n        description: List conferences\n        call: telefon-voice.list-conferences\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-conference\n\
  \        description: Create a conference room\n        call: telefon-voice.create-conference\n        with:\n          friendly_name: rest.friendly_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: SMS and MMS messaging\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages\n        call: telefon-sms.list-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send an SMS or MMS message\n        call: telefon-sms.send-message\n        with:\n          to: rest.to\n          from: rest.from\n          body: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: telefon-platform-mcp\n    transport: http\n    description: MCP server for Telefon voice and SMS communications.\n\
  \    tools:\n    - name: list-calls\n      description: List voice calls with optional status and direction filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefon-voice.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-call\n      description: Initiate an outbound phone call to a number\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefon-voice.create-call\n      with:\n        to: tools.to\n        from: tools.from\n        url: tools.url\n        record: tools.record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conferences\n      description: List active and completed conferences\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefon-voice.list-conferences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-conference\n      description:\
  \ Create a new conference call room\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefon-voice.create-conference\n      with:\n        friendly_name: tools.friendly_name\n        record: tools.record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List sent and received SMS and MMS messages\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefon-sms.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms\n      description: Send an SMS or MMS message globally\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefon-sms.send-message\n      with:\n        to: tools.to\n        from: tools.from\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefon/refs/heads/main/capabilities/telephony-platform.yaml
tags:
- Communications
- CPaaS
- Messaging
- SMS
- Telephony
- Voice
tools:
- description: List voice calls with optional status and direction filters
  hints:
    openWorld: false
    readOnly: true
  name: list-calls
- description: Initiate an outbound phone call to a number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: make-call
- description: List active and completed conferences
  hints:
    openWorld: false
    readOnly: true
  name: list-conferences
- description: Create a new conference call room
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
- description: Send an SMS or MMS message globally
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms
---
