---
api_specs:
- filename: telefoon-voice-openapi.yml
  format: yaml
  label: telefoon-voice
  slug: telefoon-voice
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefoon/refs/heads/main/openapi/telefoon-voice-openapi.yml
- filename: telefoon-sms-openapi.yml
  format: yaml
  label: telefoon-sms
  slug: telefoon-sms
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefoon/refs/heads/main/openapi/telefoon-sms-openapi.yml
categories: []
consumed_apis:
- telefoon-voice
- telefoon-sms
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
- eu data residency
- initiate call
- list conferences
- number provisioning
- belgium
- sms
- list eu voice calls with optional status and direction filters
- gdpr compliant
- initiate an outbound eu call with multi-language tts support
- send message
- telephony
- list calls
- make eu call
- send an sms in european markets with branded sender id and gdpr consent reference for compliance
- eu conference calls
- europe
- send eu sms
- create a conference room
- create conference
- list eu sms messages sent or received
- gdpr-compliant sms messaging
- netherlands
- list eu conference calls
- initiate an outbound call via eu networks with multi-language tts (nl-nl, fr-be, de-de, en-gb)
- voice
- eu voice call management
- create a new eu conference call room
- list voice calls
- cpaas
- list messages
- messaging
- send an sms with optional branded sender id and gdpr consent reference
slug: eu-communications
source_filename: eu-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Telefoon EU Communications\"\n  description: >-\n    Unified GDPR-compliant communications capability for European markets.\n    Combines Telefoon Voice and SMS APIs for Dutch, Belgian, German, and EU-wide\n    communications. Supports branded sender IDs, multi-language TTS, GDPR consent\n    tracking, and EU data residency. Designed for developers building compliant\n    European customer communication workflows.\n  tags:\n    - Belgium\n    - CPaaS\n    - EU Data Residency\n    - Europe\n    - GDPR Compliant\n    - Messaging\n    - Netherlands\n    - SMS\n    - Telephony\n    - Voice\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELEFOON_API_KEY: TELEFOON_API_KEY\n\ncapability:\n  consumes:\n    - import: telefoon-voice\n      location: ./shared/telefoon-voice.yaml\n    - import: telefoon-sms\n      location: ./shared/telefoon-sms.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: eu-communications-api\n      description: \"Unified GDPR-compliant EU communications REST API.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: \"EU voice call management\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List voice calls\"\n              call: \"telefoon-voice.list-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: initiate-call\n              description: \"Initiate an outbound EU call with multi-language TTS support\"\n              call: \"telefoon-voice.initiate-call\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                tts_language: \"rest.tts_language\"\n                record: \"rest.record\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n\n        - path: /v1/conferences\n          name: conferences\n          description: \"EU conference calls\"\n          operations:\n            - method: GET\n              name: list-conferences\n              description: \"List conferences\"\n              call: \"telefoon-voice.list-conferences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-conference\n              description: \"Create a conference room\"\n              call: \"telefoon-voice.create-conference\"\n              with:\n                friendly_name: \"rest.friendly_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages\n          name: messages\n          description: \"GDPR-compliant SMS messaging\"\n          operations:\n            - method: GET\n              name: list-messages\n \
  \             description: \"List messages\"\n              call: \"telefoon-sms.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Send an SMS with optional branded sender ID and GDPR consent reference\"\n              call: \"telefoon-sms.send-message\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                body: \"rest.body\"\n                gdpr_consent_ref: \"rest.gdpr_consent_ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: eu-communications-mcp\n      transport: http\n      description: \"MCP server for AI-assisted GDPR-compliant European communications.\"\n      tools:\n        - name: list-calls\n          description: \"List EU voice calls with optional status\
  \ and direction filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefoon-voice.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: make-eu-call\n          description: \"Initiate an outbound call via EU networks with multi-language TTS (nl-NL, fr-BE, de-DE, en-GB)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefoon-voice.initiate-call\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            tts_language: \"tools.tts_language\"\n            record: \"tools.record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-conferences\n          description: \"List EU conference calls\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefoon-voice.list-conferences\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-conference\n          description: \"Create a new EU conference call room\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefoon-voice.create-conference\"\n          with:\n            friendly_name: \"tools.friendly_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-messages\n          description: \"List EU SMS messages sent or received\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telefoon-sms.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-eu-sms\n          description: \"Send an SMS in European markets with branded sender ID and GDPR consent reference for compliance\"\n          hints:\n \
  \           readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telefoon-sms.send-message\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            body: \"tools.body\"\n            gdpr_consent_ref: \"tools.gdpr_consent_ref\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
