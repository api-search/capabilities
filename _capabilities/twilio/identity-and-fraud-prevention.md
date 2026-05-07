---
categories: []
consumed_apis: []
description: Capability combining Twilio Lookup for phone intelligence and Twilio Verify for identity verification. Used by security engineers, fraud prevention teams, and platform architects to validate users, detect fraud, and enforce multi-factor authentication workflows.
layout: capability
name: Twilio Identity and Fraud Prevention
operations:
- description: Get phone number intelligence including carrier, line type, and fraud risk
  method: GET
  name: lookup-phone-number
  path: /v1/phone-numbers/{phone_number}
- description: Start a verification workflow
  method: POST
  name: start-verification
  path: /v1/verifications
- description: Verify a code to confirm user identity
  method: POST
  name: check-verification
  path: /v1/verification-checks
personas: []
provider_name: Twilio
provider_slug: twilio
search_terms:
- video
- fetch verification status
- send a verification code to a user via sms, voice, whatsapp, or email to confirm their identity
- verify send code
- authentication
- look up phone number intelligence for fraud detection
- sms
- check a verification code submitted by a user to complete identity confirmation
- get phone number intelligence including carrier, line type, and fraud risk
- identity
- start verification
- send verification codes for identity confirmation
- verify a code to confirm user identity
- t1
- email
- fraud prevention
- iot
- check submitted verification codes
- twilio
- verification
- two factor authentication
- verify check code
- start a verification workflow
- look up phone number intelligence including validation, carrier, line type, sim swap status, and fraud risk score
- check verification
- voice
- phone
- lookup phone number
- messaging
- phone verification
- security
- contact center
- fetch the current status of a verification attempt
- communications
slug: identity-and-fraud-prevention
source_filename: identity-and-fraud-prevention.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twilio Identity and Fraud Prevention\n  description: Capability combining Twilio Lookup for phone intelligence and Twilio Verify for identity verification. Used\n    by security engineers, fraud prevention teams, and platform architects to validate users, detect fraud, and enforce multi-factor\n    authentication workflows.\n  tags:\n  - Twilio\n  - Identity\n  - Fraud Prevention\n  - Phone Verification\n  - Security\n  - Two Factor Authentication\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n    TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: twilio-lookup\n    baseUri: https://lookups.twilio.com/v2\n    description: Twilio Lookup API v2\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: phone-numbers\n  \
  \    path: /PhoneNumbers/{PhoneNumber}\n      description: Query phone number intelligence\n      operations:\n      - name: fetch-phone-number\n        method: GET\n        description: Look up phone number intelligence data\n        inputParameters:\n        - name: PhoneNumber\n          in: path\n          type: string\n          required: true\n          description: Phone number in E.164 format\n        - name: Fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated data packages (validation, line_type_intelligence, caller_name, sim_swap, identity_match,\n            sms_pumping_risk)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twilio-verify\n    baseUri: https://verify.twilio.com/v2\n    description: Twilio Verify API v2\n    authentication:\n      type: basic\n      username: '{{TWILIO_ACCOUNT_SID}}'\n\
  \      password: '{{TWILIO_AUTH_TOKEN}}'\n    resources:\n    - name: verifications\n      path: /Services/{ServiceSid}/Verifications\n      description: Send verification codes\n      operations:\n      - name: start-verification\n        method: POST\n        description: Start a verification by sending a code\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n          description: Verify Service SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            Channel: '{{tools.channel}}'\n      - name: fetch-verification\n        method: GET\n        description: Fetch a verification status\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n          description: Verify Service\
  \ SID\n        - name: Sid\n          in: path\n          type: string\n          required: true\n          description: Verification SID or phone number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: verification-checks\n      path: /Services/{ServiceSid}/VerificationCheck\n      description: Check verification codes\n      operations:\n      - name: check-verification\n        method: POST\n        description: Check a verification code\n        inputParameters:\n        - name: ServiceSid\n          in: path\n          type: string\n          required: true\n          description: Verify Service SID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            To: '{{tools.to}}'\n            Code: '{{tools.code}}'\n  exposes:\n  - type: rest\n    port: 8081\n  \
  \  namespace: twilio-identity-api\n    description: Unified REST API for identity verification and fraud prevention.\n    resources:\n    - path: /v1/phone-numbers/{phone_number}\n      name: phone-number-lookup\n      description: Look up phone number intelligence for fraud detection\n      operations:\n      - method: GET\n        name: lookup-phone-number\n        description: Get phone number intelligence including carrier, line type, and fraud risk\n        call: twilio-lookup.fetch-phone-number\n        with:\n          PhoneNumber: rest.phone_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verifications\n      name: verifications\n      description: Send verification codes for identity confirmation\n      operations:\n      - method: POST\n        name: start-verification\n        description: Start a verification workflow\n        call: twilio-verify.start-verification\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/verification-checks\n      name: verification-checks\n      description: Check submitted verification codes\n      operations:\n      - method: POST\n        name: check-verification\n        description: Verify a code to confirm user identity\n        call: twilio-verify.check-verification\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: twilio-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted identity verification and fraud prevention.\n    tools:\n    - name: lookup-phone-number\n      description: Look up phone number intelligence including validation, carrier, line type, SIM swap status, and fraud\n        risk score\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twilio-lookup.fetch-phone-number\n      with:\n        PhoneNumber: tools.phone_number\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: verify-send-code\n      description: Send a verification code to a user via SMS, voice, WhatsApp, or email to confirm their identity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-verify.start-verification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-check-code\n      description: Check a verification code submitted by a user to complete identity confirmation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twilio-verify.check-verification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-verification-status\n      description: Fetch the current status of a verification attempt\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twilio-verify.fetch-verification\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twilio/refs/heads/main/capabilities/identity-and-fraud-prevention.yaml
tags:
- Twilio
- Identity
- Fraud Prevention
- Phone Verification
- Security
- Two Factor Authentication
tools:
- description: Look up phone number intelligence including validation, carrier, line type, SIM swap status, and fraud risk score
  hints:
    openWorld: true
    readOnly: true
  name: lookup-phone-number
- description: Send a verification code to a user via SMS, voice, WhatsApp, or email to confirm their identity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verify-send-code
- description: Check a verification code submitted by a user to complete identity confirmation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verify-check-code
- description: Fetch the current status of a verification attempt
  hints:
    openWorld: false
    readOnly: true
  name: fetch-verification-status
---
