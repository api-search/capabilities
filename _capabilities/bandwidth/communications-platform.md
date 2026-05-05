---
categories:
- messaging
consumed_apis:
- bandwidth-voice
- bandwidth-messaging
- bandwidth-mfa
- bandwidth-phone-numbers
- bandwidth-emergency
- bandwidth-toll-free
description: Unified communications platform workflow covering voice calls, messaging (SMS/MMS), multi-factor authentication, phone number management, emergency calling (E911), and toll-free verification. Serves developers building communication-enabled applications.
layout: capability
name: Bandwidth Communications Platform
operations:
- description: Initiate an outbound voice call
  method: POST
  name: create-call
  path: /v1/calls
- description: Send an SMS or MMS message
  method: POST
  name: send-message
  path: /v1/messages
- description: Verify an MFA code
  method: POST
  name: verify-mfa
  path: /v1/mfa/verify
personas: []
provider_name: Bandwidth
provider_slug: bandwidth
search_terms:
- order phone numbers
- administrator managing bandwidth account, numbers, and compliance
- communications
- send an mfa verification code via sms
- sms
- send an sms or mms message via bandwidth messaging
- list emergency calling (e911) endpoints for the account
- list toll free verifications
- send message
- send sms message
- Platform Administrator
- create e911 endpoint
- sms and mms message delivery and media management
- e911 endpoint registration and management
- list e911 endpoints
- bandwidth
- telephony
- get call status
- initiate an outbound voice call through bandwidth
- developer building communication-enabled web or mobile applications
- register an endpoint for e911 emergency calling
- verify mfa
- multi-factor authentication via voice or sms
- create call
- verify an mfa code
- search available phone numbers
- verify mfa code
- sms/mms messaging
- search for available phone numbers to order
- list messages sent or received on the account
- multi-factor authentication
- unified voice, messaging, mfa, phone numbers, e911, and toll-free management
- place an order for phone numbers
- Communications Engineer
- outbound and inbound voice call management and recording
- submit toll free verification
- engineer designing and operating telephony and messaging infrastructure
- send an sms or mms message
- create voice call
- voice
- Application Developer
- initiate an outbound voice call
- submit a toll-free number for verification
- mfa
- verify a multi-factor authentication code
- list toll-free number verification requests
- voice call management
- send mfa code sms
- search, order, and manage telephone numbers
- retrieve the status and details of a voice call
- cpaas
- list messages
- messaging
slug: communications-platform
source_filename: communications-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bandwidth Communications Platform\"\n  description: >-\n    Unified communications platform workflow covering voice calls, messaging (SMS/MMS),\n    multi-factor authentication, phone number management, emergency calling (E911),\n    and toll-free verification. Serves developers building communication-enabled applications.\n  tags:\n    - Bandwidth\n    - Voice\n    - Messaging\n    - Communications\n    - Telephony\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BANDWIDTH_ACCOUNT_ID: BANDWIDTH_ACCOUNT_ID\n      BANDWIDTH_API_TOKEN: BANDWIDTH_API_TOKEN\n      BANDWIDTH_API_SECRET: BANDWIDTH_API_SECRET\n\ncapability:\n  consumes:\n    - import: bandwidth-voice\n      location: ./shared/voice-api.yaml\n    - import: bandwidth-messaging\n      location: ./shared/messaging-api.yaml\n    - import: bandwidth-mfa\n      location: ./shared/mfa-api.yaml\n    - import: bandwidth-phone-numbers\n\
  \      location: ./shared/phone-numbers-api.yaml\n    - import: bandwidth-emergency\n      location: ./shared/emergency-api.yaml\n    - import: bandwidth-toll-free\n      location: ./shared/toll-free-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bandwidth-platform-api\n      description: \"Unified REST API for Bandwidth communications platform.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: Voice call management\n          operations:\n            - method: POST\n              name: create-call\n              description: Initiate an outbound voice call\n              call: \"bandwidth-voice.createCall\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: messages\n          description: SMS/MMS messaging\n          operations:\n            - method:\
  \ POST\n              name: send-message\n              description: Send an SMS or MMS message\n              call: \"bandwidth-messaging.createMessage\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mfa/verify\n          name: mfa-verify\n          description: Multi-factor authentication\n          operations:\n            - method: POST\n              name: verify-mfa\n              description: Verify an MFA code\n              call: \"bandwidth-mfa.verifyMfaCode\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: bandwidth-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bandwidth communications management.\"\n      tools:\n        -\
  \ name: create-voice-call\n          description: Initiate an outbound voice call through Bandwidth\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-voice.createCall\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-call-status\n          description: Retrieve the status and details of a voice call\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bandwidth-voice.getCall\"\n          with:\n            accountId: \"tools.accountId\"\n            callId: \"tools.callId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-sms-message\n          description: Send an SMS or MMS message via Bandwidth messaging\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-messaging.createMessage\"\
  \n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messages\n          description: List messages sent or received on the account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bandwidth-messaging.listMessages\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-mfa-code-sms\n          description: Send an MFA verification code via SMS\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-mfa.createMessagingMfa\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-mfa-code\n          description: Verify a multi-factor authentication\
  \ code\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-mfa.verifyMfaCode\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-available-phone-numbers\n          description: Search for available phone numbers to order\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bandwidth-phone-numbers.searchAvailableNumbers\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: order-phone-numbers\n          description: Place an order for phone numbers\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-phone-numbers.createOrder\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-e911-endpoints\n          description: List emergency calling (E911) endpoints for the account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bandwidth-emergency.listEndpoints\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-e911-endpoint\n          description: Register an endpoint for E911 emergency calling\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-emergency.createEndpoint\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-toll-free-verifications\n          description: List toll-free number verification requests\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"bandwidth-toll-free.listTollFreeVerifications\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-toll-free-verification\n          description: Submit a toll-free number for verification\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bandwidth-toll-free.createTollFreeVerification\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bandwidth/refs/heads/main/capabilities/communications-platform.yaml
tags:
- Bandwidth
- Voice
- Messaging
- Communications
- Telephony
tools:
- description: Initiate an outbound voice call through Bandwidth
  hints:
    openWorld: false
    readOnly: false
  name: create-voice-call
- description: Retrieve the status and details of a voice call
  hints:
    openWorld: false
    readOnly: true
  name: get-call-status
- description: Send an SMS or MMS message via Bandwidth messaging
  hints:
    openWorld: false
    readOnly: false
  name: send-sms-message
- description: List messages sent or received on the account
  hints:
    openWorld: false
    readOnly: true
  name: list-messages
- description: Send an MFA verification code via SMS
  hints:
    openWorld: false
    readOnly: false
  name: send-mfa-code-sms
- description: Verify a multi-factor authentication code
  hints:
    openWorld: false
    readOnly: false
  name: verify-mfa-code
- description: Search for available phone numbers to order
  hints:
    openWorld: true
    readOnly: true
  name: search-available-phone-numbers
- description: Place an order for phone numbers
  hints:
    openWorld: false
    readOnly: false
  name: order-phone-numbers
- description: List emergency calling (E911) endpoints for the account
  hints:
    openWorld: false
    readOnly: true
  name: list-e911-endpoints
- description: Register an endpoint for E911 emergency calling
  hints:
    openWorld: false
    readOnly: false
  name: create-e911-endpoint
- description: List toll-free number verification requests
  hints:
    openWorld: false
    readOnly: true
  name: list-toll-free-verifications
- description: Submit a toll-free number for verification
  hints:
    openWorld: false
    readOnly: false
  name: submit-toll-free-verification
---
