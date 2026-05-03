---
api_specs:
- filename: telefonie-voice-openapi.yml
  format: yaml
  label: telefonie-voice
  slug: telefonie-voice
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefonie/refs/heads/main/openapi/telefonie-voice-openapi.yml
- filename: telefonie-sms-openapi.yml
  format: yaml
  label: telefonie-sms
  slug: telefonie-sms
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefonie/refs/heads/main/openapi/telefonie-sms-openapi.yml
categories: []
consumed_apis:
- telefonie-voice
- telefonie-sms
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
- voice call management
- create a new multi-party conference call room
- create conference
- initiate an outbound voice call
- list sent and received sms and mms messages
- multi-party conference management
- send message
- sms and mms messaging
- create a new conference room
- voice
- list conferences
- list sms and mms messages
- sms
- list voice calls with optional status and direction filtering
- telephony
- make call
- messaging
- communications
- send an sms or mms message to a phone number
- call recording
- send an sms or mms message
- number provisioning
- send sms
- list messages
- list all conferences
- voip
- list all active and completed conference calls
- cpaas
- list calls
- telecommunications
- initiate an outbound phone call to a specified number
- initiate call
- list voice calls with filtering options
slug: telephony-communications
source_filename: telephony-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Telefonie Communications\"\n  description: >-\n    Unified capability combining Telefonie Voice and SMS APIs for comprehensive\n    communications workflows. Enables voice calling, SMS messaging, conferencing,\n    and call recording from a single interface. Designed for developers building\n    customer communication, notification, and engagement platforms.\n  tags:\n    - Call Recording\n    - Communications\n    - CPaaS\n    - Messaging\n    - SMS\n    - Telephony\n    - Voice\n    - VoIP\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELEFONIE_API_KEY: TELEFONIE_API_KEY\n\ncapability:\n  consumes:\n    - import: telefonie-voice\n      location: ./shared/telefonie-voice.yaml\n    - import: telefonie-sms\n      location: ./shared/telefonie-sms.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: telefonie-communications-api\n      description: \"Unified\
  \ REST API for Telefonie voice and SMS communications.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: \"Voice call management\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List voice calls with filtering options\"\n              call: \"telefonie-voice.list-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: initiate-call\n              description: \"Initiate an outbound voice call\"\n              call: \"telefonie-voice.initiate-call\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                url: \"rest.url\"\n                record: \"rest.record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/conferences\n          name: conferences\n    \
  \      description: \"Multi-party conference management\"\n          operations:\n            - method: GET\n              name: list-conferences\n              description: \"List all conferences\"\n              call: \"telefonie-voice.list-conferences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-conference\n              description: \"Create a new conference room\"\n              call: \"telefonie-voice.create-conference\"\n              with:\n                friendly_name: \"rest.friendly_name\"\n                record: \"rest.record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages\n          name: messages\n          description: \"SMS and MMS messaging\"\n          operations:\n            - method: GET\n              name: list-messages\n              description: \"List SMS and MMS\
  \ messages\"\n              call: \"telefonie-sms.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Send an SMS or MMS message\"\n              call: \"telefonie-sms.send-message\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: telefonie-communications-mcp\n      transport: http\n      description: \"MCP server for AI-assisted communications using Telefonie voice and SMS APIs.\"\n      tools:\n        - name: list-calls\n          description: \"List voice calls with optional status and direction filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"telefonie-voice.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: make-call\n          description: \"Initiate an outbound phone call to a specified number\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefonie-voice.initiate-call\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            url: \"tools.url\"\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-conferences\n          description: \"List all active and completed conference calls\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefonie-voice.list-conferences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-conference\n\
  \          description: \"Create a new multi-party conference call room\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefonie-voice.create-conference\"\n          with:\n            friendly_name: \"tools.friendly_name\"\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-messages\n          description: \"List sent and received SMS and MMS messages\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefonie-sms.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-sms\n          description: \"Send an SMS or MMS message to a phone number\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefonie-sms.send-message\"\
  \n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            body: \"tools.body\"\n            media_url: \"tools.media_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
