---
api_specs:
- filename: telefon-voice-openapi.yml
  format: yaml
  label: telefon-voice
  slug: telefon-voice
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefon/refs/heads/main/openapi/telefon-voice-openapi.yml
- filename: telefon-sms-openapi.yml
  format: yaml
  label: telefon-sms
  slug: telefon-sms
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefon/refs/heads/main/openapi/telefon-sms-openapi.yml
categories: []
consumed_apis:
- telefon-voice
- telefon-sms
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
- list conferences
- communications
- number provisioning
- sms
- send an sms or mms message globally
- initiate an outbound phone call to a number
- send message
- sms and mms messaging
- list sent and received sms and mms messages
- telephony
- create call
- list calls
- list voice calls with optional status and direction filters
- conference call management
- create a conference room
- call recording
- create conference
- voip
- global coverage
- list active and completed conferences
- send an sms or mms message
- voice
- make call
- create a new conference call room
- initiate an outbound voice call
- list voice calls
- cpaas
- voice call management
- send sms
- list messages
- messaging
slug: telephony-platform
source_filename: telephony-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Telefon Communications Platform\"\n  description: >-\n    Unified capability combining Telefon Voice and SMS APIs for comprehensive\n    programmable communications. Supports voice calls, conferencing, SMS messaging,\n    and recording across 180+ countries. Designed for developers building customer\n    communication, notification, and engagement applications.\n  tags:\n    - Communications\n    - CPaaS\n    - Messaging\n    - SMS\n    - Telephony\n    - Voice\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELEFON_API_KEY: TELEFON_API_KEY\n\ncapability:\n  consumes:\n    - import: telefon-voice\n      location: ./shared/telefon-voice.yaml\n    - import: telefon-sms\n      location: ./shared/telefon-sms.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: telefon-platform-api\n      description: \"Unified REST API for Telefon communications.\"\n      resources:\n\
  \        - path: /v1/calls\n          name: calls\n          description: \"Voice call management\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List voice calls\"\n              call: \"telefon-voice.list-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-call\n              description: \"Initiate an outbound voice call\"\n              call: \"telefon-voice.create-call\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                url: \"rest.url\"\n                record: \"rest.record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/conferences\n          name: conferences\n          description: \"Conference call management\"\n          operations:\n            - method: GET\n     \
  \         name: list-conferences\n              description: \"List conferences\"\n              call: \"telefon-voice.list-conferences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-conference\n              description: \"Create a conference room\"\n              call: \"telefon-voice.create-conference\"\n              with:\n                friendly_name: \"rest.friendly_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages\n          name: messages\n          description: \"SMS and MMS messaging\"\n          operations:\n            - method: GET\n              name: list-messages\n              description: \"List messages\"\n              call: \"telefon-sms.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            -\
  \ method: POST\n              name: send-message\n              description: \"Send an SMS or MMS message\"\n              call: \"telefon-sms.send-message\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: telefon-platform-mcp\n      transport: http\n      description: \"MCP server for Telefon voice and SMS communications.\"\n      tools:\n        - name: list-calls\n          description: \"List voice calls with optional status and direction filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefon-voice.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: make-call\n          description: \"Initiate an outbound phone call to a number\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefon-voice.create-call\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            url: \"tools.url\"\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-conferences\n          description: \"List active and completed conferences\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefon-voice.list-conferences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-conference\n          description: \"Create a new conference call room\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefon-voice.create-conference\"\n          with:\n        \
  \    friendly_name: \"tools.friendly_name\"\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messages\n          description: \"List sent and received SMS and MMS messages\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefon-sms.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-sms\n          description: \"Send an SMS or MMS message globally\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefon-sms.send-message\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
