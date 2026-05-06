---
categories: []
consumed_apis: []
description: Unified GDPR-compliant communications capability for European markets. Combines Telefoon Voice and SMS APIs for Dutch, Belgian, German, and EU-wide communications. Supports branded sender IDs, multi-language TTS, GDPR consent tracking, and EU data residency. Designed for developers building compliant European customer communication workflows.
layout: capability
name: Telefoon EU Communications
operations:
- description: List voice calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: Initiate an outbound EU call with multi-language TTS support
  method: POST
  name: initiate-call
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
- description: Send an SMS with optional branded sender ID and GDPR consent reference
  method: POST
  name: send-message
  path: /v1/messages
personas: []
provider_name: Telefoon
provider_slug: telefoon
search_terms:
- gdpr-compliant sms messaging
- create conference
- list messages
- cpaas
- europe
- send an sms in european markets with branded sender id and gdpr consent reference for compliance
- number provisioning
- send an sms with optional branded sender id and gdpr consent reference
- eu voice call management
- list voice calls
- list eu sms messages sent or received
- voice
- initiate an outbound eu call with multi-language tts support
- make eu call
- eu conference calls
- sms
- initiate call
- telephony
- messaging
- eu data residency
- send message
- gdpr compliant
- netherlands
- list calls
- create a new eu conference call room
- send eu sms
- belgium
- initiate an outbound call via eu networks with multi-language tts (nl-nl, fr-be, de-de, en-gb)
- list conferences
- create a conference room
- list eu voice calls with optional status and direction filters
- list eu conference calls
slug: eu-communications
source_filename: eu-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefoon EU Communications\n  description: Unified GDPR-compliant communications capability for European markets. Combines Telefoon Voice and SMS APIs\n    for Dutch, Belgian, German, and EU-wide communications. Supports branded sender IDs, multi-language TTS, GDPR consent\n    tracking, and EU data residency. Designed for developers building compliant European customer communication workflows.\n  tags:\n  - Belgium\n  - CPaaS\n  - EU Data Residency\n  - Europe\n  - GDPR Compliant\n  - Messaging\n  - Netherlands\n  - SMS\n  - Telephony\n  - Voice\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFOON_API_KEY: TELEFOON_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: telefoon-voice\n    baseUri: https://api.telefoon.com/v1/voice\n    description: Telefoon Voice API — EU telephony platform\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFOON_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: calls\n      path: /calls\n      description: Voice call management\n      operations:\n      - name: list-calls\n        method: GET\n        description: List voice calls\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by call status\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: inbound or outbound\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: initiate-call\n        method: POST\n        description: Initiate an outbound voice call\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Destination number (E.164)\n        - name: from\n          in: body\n          type: string\n\
  \          required: true\n          description: Caller ID\n        - name: tts_language\n          in: body\n          type: string\n          required: false\n          description: TTS language (nl-NL, fr-BE, de-DE, en-GB)\n        - name: record\n          in: body\n          type: boolean\n          required: false\n          description: Record call (requires GDPR consent)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conferences\n      path: /conferences\n      description: Conference management\n      operations:\n      - name: list-conferences\n        method: GET\n        description: List conferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-conference\n        method: POST\n        description: Create a conference room\n        inputParameters:\n        - name: friendly_name\n\
  \          in: body\n          type: string\n          required: false\n          description: Conference name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telefoon-sms\n    baseUri: https://api.telefoon.com/v1/sms\n    description: Telefoon SMS API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFOON_API_KEY}}'\n      placement: header\n    resources:\n    - name: messages\n      path: /messages\n      description: SMS messaging\n      operations:\n      - name: list-messages\n        method: GET\n        description: List messages\n        inputParameters:\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: inbound or outbound\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ send-message\n        method: POST\n        description: Send an SMS with optional GDPR consent reference\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Recipient (E.164)\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Sender number or alphanumeric ID\n        - name: body\n          in: body\n          type: string\n          required: false\n          description: Message text\n        - name: gdpr_consent_ref\n          in: body\n          type: string\n          required: false\n          description: GDPR consent reference for audit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eu-communications-api\n    description: Unified GDPR-compliant EU communications REST API.\n    resources:\n\
  \    - path: /v1/calls\n      name: calls\n      description: EU voice call management\n      operations:\n      - method: GET\n        name: list-calls\n        description: List voice calls\n        call: telefoon-voice.list-calls\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: initiate-call\n        description: Initiate an outbound EU call with multi-language TTS support\n        call: telefoon-voice.initiate-call\n        with:\n          to: rest.to\n          from: rest.from\n          tts_language: rest.tts_language\n          record: rest.record\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conferences\n      name: conferences\n      description: EU conference calls\n      operations:\n      - method: GET\n        name: list-conferences\n        description: List conferences\n        call: telefoon-voice.list-conferences\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: create-conference\n        description: Create a conference room\n        call: telefoon-voice.create-conference\n        with:\n          friendly_name: rest.friendly_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: GDPR-compliant SMS messaging\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages\n        call: telefoon-sms.list-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send an SMS with optional branded sender ID and GDPR consent reference\n        call: telefoon-sms.send-message\n        with:\n          to: rest.to\n          from: rest.from\n          body: rest.body\n          gdpr_consent_ref: rest.gdpr_consent_ref\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eu-communications-mcp\n    transport: http\n    description: MCP server for AI-assisted GDPR-compliant European communications.\n    tools:\n    - name: list-calls\n      description: List EU voice calls with optional status and direction filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefoon-voice.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-eu-call\n      description: Initiate an outbound call via EU networks with multi-language TTS (nl-NL, fr-BE, de-DE, en-GB)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefoon-voice.initiate-call\n      with:\n        to: tools.to\n        from: tools.from\n        tts_language: tools.tts_language\n        record: tools.record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conferences\n  \
  \    description: List EU conference calls\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefoon-voice.list-conferences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-conference\n      description: Create a new EU conference call room\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telefoon-voice.create-conference\n      with:\n        friendly_name: tools.friendly_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List EU SMS messages sent or received\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telefoon-sms.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-eu-sms\n      description: Send an SMS in European markets with branded sender ID and GDPR consent reference for compliance\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: telefoon-sms.send-message\n      with:\n        to: tools.to\n        from: tools.from\n        body: tools.body\n        gdpr_consent_ref: tools.gdpr_consent_ref\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefoon/refs/heads/main/capabilities/eu-communications.yaml
tags:
- Belgium
- CPaaS
- EU Data Residency
- Europe
- GDPR Compliant
- Messaging
- Netherlands
- SMS
- Telephony
- Voice
tools:
- description: List EU voice calls with optional status and direction filters
  hints:
    openWorld: false
    readOnly: true
  name: list-calls
- description: Initiate an outbound call via EU networks with multi-language TTS (nl-NL, fr-BE, de-DE, en-GB)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: make-eu-call
- description: List EU conference calls
  hints:
    openWorld: false
    readOnly: true
  name: list-conferences
- description: Create a new EU conference call room
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-conference
- description: List EU SMS messages sent or received
  hints:
    openWorld: false
    readOnly: true
  name: list-messages
- description: Send an SMS in European markets with branded sender ID and GDPR consent reference for compliance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-eu-sms
---
