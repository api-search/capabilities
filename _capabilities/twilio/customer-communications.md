---
categories: []
consumed_apis:
- twilio-messaging
- twilio-voice
- twilio-verify
description: Unified capability for customer-facing communications combining SMS/MMS messaging, outbound voice calls, and verification workflows. Used by customer engagement teams, marketing platforms, and notification systems to communicate with users across multiple channels.
layout: capability
name: Twilio Customer Communications
operations:
- description: List messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send an SMS or MMS message
  method: POST
  name: send-message
  path: /v1/messages
- description: List calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: Make an outbound call
  method: POST
  name: make-call
  path: /v1/calls
- description: Start a verification
  method: POST
  name: start-verification
  path: /v1/verifications
- description: Check a verification code
  method: POST
  name: check-verification
  path: /v1/verification-checks
personas: []
provider_name: Twilio
provider_slug: twilio
search_terms:
- check verification
- fetch details of a specific message
- fetch message
- phone
- video
- t1
- initiate an outbound voice call
- send message
- send a verification code to a user via sms, voice, or email
- make and manage voice calls
- send an sms or mms message to a customer
- verification
- check a verification code
- make an outbound call
- voice
- start verification
- customer engagement
- contact center
- authentication
- sms
- start a verification
- make call
- messaging
- communications
- send verification codes
- list sms/mms messages for the account
- send an sms or mms message
- send sms
- list messages
- check verification codes
- verify a code submitted by a user to complete 2fa
- email
- list voice calls for the account
- send and manage sms/mms messages
- list calls
- twilio
- iot
- notifications
slug: customer-communications
source_filename: customer-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Twilio Customer Communications\"\n  description: >-\n    Unified capability for customer-facing communications combining SMS/MMS messaging,\n    outbound voice calls, and verification workflows. Used by customer engagement teams,\n    marketing platforms, and notification systems to communicate with users across\n    multiple channels.\n  tags:\n    - Twilio\n    - Messaging\n    - Voice\n    - Customer Engagement\n    - Notifications\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n      TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: twilio-messaging\n      location: ./shared/messaging.yaml\n    - import: twilio-voice\n      location: ./shared/voice.yaml\n    - import: twilio-verify\n      location: ./shared/verify.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: twilio-communications-api\n\
  \      description: \"Unified REST API for Twilio customer communications.\"\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: \"Send and manage SMS/MMS messages\"\n          operations:\n            - method: GET\n              name: list-messages\n              description: \"List messages\"\n              call: \"twilio-messaging.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Send an SMS or MMS message\"\n              call: \"twilio-messaging.send-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/calls\n          name: calls\n          description: \"Make and manage voice calls\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List\
  \ calls\"\n              call: \"twilio-voice.list-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: make-call\n              description: \"Make an outbound call\"\n              call: \"twilio-voice.make-call\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/verifications\n          name: verifications\n          description: \"Send verification codes\"\n          operations:\n            - method: POST\n              name: start-verification\n              description: \"Start a verification\"\n              call: \"twilio-verify.start-verification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/verification-checks\n          name: verification-checks\n          description: \"Check verification codes\"\n          operations:\n\
  \            - method: POST\n              name: check-verification\n              description: \"Check a verification code\"\n              call: \"twilio-verify.check-verification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: twilio-communications-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Twilio customer communications.\"\n      tools:\n        - name: list-messages\n          description: \"List SMS/MMS messages for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twilio-messaging.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-sms\n          description: \"Send an SMS or MMS message to a customer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n\
  \          call: \"twilio-messaging.send-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-message\n          description: \"Fetch details of a specific message\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"twilio-messaging.fetch-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-calls\n          description: \"List voice calls for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twilio-voice.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: make-call\n          description: \"Initiate an outbound voice call\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-voice.make-call\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-verification\n          description: \"Send a verification code to a user via SMS, voice, or email\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-verify.start-verification\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-verification\n          description: \"Verify a code submitted by a user to complete 2FA\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-verify.check-verification\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twilio/refs/heads/main/capabilities/customer-communications.yaml
tags:
- Twilio
- Messaging
- Voice
- Customer Engagement
- Notifications
tools:
- description: List SMS/MMS messages for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Send an SMS or MMS message to a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms
- description: Fetch details of a specific message
  hints:
    openWorld: false
    readOnly: true
  name: fetch-message
- description: List voice calls for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-calls
- description: Initiate an outbound voice call
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: make-call
- description: Send a verification code to a user via SMS, voice, or email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-verification
- description: Verify a code submitted by a user to complete 2FA
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: check-verification
---
