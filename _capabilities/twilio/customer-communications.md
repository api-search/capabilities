---
categories: []
consumed_apis: []
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
- notifications
- video
- check a verification code
- send sms
- list voice calls for the account
- authentication
- send a verification code to a user via sms, voice, or email
- sms
- send message
- list sms/mms messages for the account
- start verification
- make and manage voice calls
- list calls
- start a verification
- t1
- fetch details of a specific message
- send an sms or mms message
- email
- make call
- iot
- list messages
- customer engagement
- check verification codes
- twilio
- send and manage sms/mms messages
- verification
- fetch message
- send an sms or mms message to a customer
- make an outbound call
- voice
- check verification
- phone
- initiate an outbound voice call
- verify a code submitted by a user to complete 2fa
- send verification codes
- messaging
- contact center
- communications
slug: customer-communications
source_filename: customer-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twilio Customer Communications\n  description: Unified capability for customer-facing communications combining SMS/MMS messaging, outbound voice calls, and\n    verification workflows. Used by customer engagement teams, marketing platforms, and notification systems to communicate\n    with users across multiple channels.\n  tags:\n  - Twilio\n  - Messaging\n  - Voice\n  - Customer Engagement\n  - Notifications\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n    TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: twilio-messaging\n    baseUri: https://api.twilio.com/2010-04-01\n    description: Twilio Messaging API for SMS and MMS\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: messages\n      path: /Accounts/{AccountSid}/Messages.json\n\
  \      description: Send and retrieve SMS/MMS messages\n      operations:\n      - name: list-messages\n        method: GET\n        description: Retrieve a list of messages\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        - name: To\n          in: query\n          type: string\n          required: false\n          description: Filter by recipient phone number\n        - name: From\n          in: query\n          type: string\n          required: false\n          description: Filter by sender phone number\n        - name: PageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send an SMS or MMS message\n\
  \        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            From: '{{tools.from}}'\n            Body: '{{tools.body}}'\n      - name: fetch-message\n        method: GET\n        description: Retrieve details of a specific message\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        - name: MessageSid\n          in: path\n          type: string\n          required: true\n          description: Message SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: delete-message\n        method: DELETE\n        description: Delete a message record\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        - name: MessageSid\n          in: path\n          type: string\n          required: true\n          description: Message SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twilio-voice\n    baseUri: https://api.twilio.com/2010-04-01\n    description: Twilio Voice API\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: calls\n      path: /Accounts/{AccountSid}/Calls.json\n      description: Initiate and manage voice calls\n      operations:\n      - name: list-calls\n        method: GET\n        description: Retrieve\
  \ a list of calls\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        - name: To\n          in: query\n          type: string\n          required: false\n          description: Filter by destination number\n        - name: From\n          in: query\n          type: string\n          required: false\n          description: Filter by source number\n        - name: Status\n          in: query\n          type: string\n          required: false\n          description: Filter by call status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: make-call\n        method: POST\n        description: Initiate an outbound voice call\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account\
  \ SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            From: '{{tools.from}}'\n            Url: '{{tools.url}}'\n      - name: fetch-call\n        method: GET\n        description: Retrieve details for a specific call\n        inputParameters:\n        - name: AccountSid\n          in: path\n          type: string\n          required: true\n          description: Twilio Account SID\n        - name: CallSid\n          in: path\n          type: string\n          required: true\n          description: Call SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twilio-verify\n    baseUri: https://verify.twilio.com/v2\n    description: Twilio Verify API v2\n    authentication:\n      type: basic\n      username:\
  \ '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: verifications\n      path: /Services/{ServiceSid}/Verifications\n      description: Send verification codes\n      operations:\n      - name: start-verification\n        method: POST\n        description: Start a verification by sending a code\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n          description: Verify Service SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            Channel: '{{tools.channel}}'\n      - name: fetch-verification\n        method: GET\n        description: Fetch a verification status\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n      \
  \    description: Verify Service SID\n        - name: Sid\n          in: path\n          type: string\n          required: true\n          description: Verification SID or phone number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: verification-checks\n      path: /Services/{ServiceSid}/VerificationCheck\n      description: Check verification codes\n      operations:\n      - name: check-verification\n        method: POST\n        description: Check a verification code\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n          description: Verify Service SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            Code: '{{tools.code}}'\n  exposes:\n  -\
  \ type: rest\n    port: 8080\n    namespace: twilio-communications-api\n    description: Unified REST API for Twilio customer communications.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Send and manage SMS/MMS messages\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages\n        call: twilio-messaging.list-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send an SMS or MMS message\n        call: twilio-messaging.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calls\n      name: calls\n      description: Make and manage voice calls\n      operations:\n      - method: GET\n        name: list-calls\n        description: List calls\n        call: twilio-voice.list-calls\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: make-call\n        description: Make an outbound call\n        call: twilio-voice.make-call\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verifications\n      name: verifications\n      description: Send verification codes\n      operations:\n      - method: POST\n        name: start-verification\n        description: Start a verification\n        call: twilio-verify.start-verification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verification-checks\n      name: verification-checks\n      description: Check verification codes\n      operations:\n      - method: POST\n        name: check-verification\n        description: Check a verification code\n        call: twilio-verify.check-verification\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: twilio-communications-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted Twilio customer communications.\n    tools:\n    - name: list-messages\n      description: List SMS/MMS messages for the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twilio-messaging.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms\n      description: Send an SMS or MMS message to a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-messaging.send-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-message\n      description: Fetch details of a specific message\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twilio-messaging.fetch-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-calls\n      description: List voice calls for the account\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: twilio-voice.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-call\n      description: Initiate an outbound voice call\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-voice.make-call\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-verification\n      description: Send a verification code to a user via SMS, voice, or email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-verify.start-verification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-verification\n      description: Verify a code submitted by a user to complete 2FA\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-verify.check-verification\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n"
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
