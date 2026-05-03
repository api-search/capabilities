---
categories: []
consumed_apis:
- twilio-lookup
- twilio-verify
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
- check verification
- phone
- video
- t1
- security
- verification
- check a verification code submitted by a user to complete identity confirmation
- look up phone number intelligence including validation, carrier, line type, sim swap status, and fraud risk score
- voice
- start verification
- contact center
- look up phone number intelligence for fraud detection
- authentication
- start a verification workflow
- sms
- verify send code
- fetch verification status
- get phone number intelligence including carrier, line type, and fraud risk
- communications
- messaging
- verify a code to confirm user identity
- identity
- check submitted verification codes
- lookup phone number
- fetch the current status of a verification attempt
- send a verification code to a user via sms, voice, whatsapp, or email to confirm their identity
- email
- verify check code
- twilio
- phone verification
- fraud prevention
- send verification codes for identity confirmation
- iot
- two factor authentication
slug: identity-and-fraud-prevention
source_filename: identity-and-fraud-prevention.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Twilio Identity and Fraud Prevention\"\n  description: >-\n    Capability combining Twilio Lookup for phone intelligence and Twilio Verify\n    for identity verification. Used by security engineers, fraud prevention teams,\n    and platform architects to validate users, detect fraud, and enforce\n    multi-factor authentication workflows.\n  tags:\n    - Twilio\n    - Identity\n    - Fraud Prevention\n    - Phone Verification\n    - Security\n    - Two Factor Authentication\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID\n      TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: twilio-lookup\n      location: ./shared/lookup.yaml\n    - import: twilio-verify\n      location: ./shared/verify.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: twilio-identity-api\n      description: \"Unified\
  \ REST API for identity verification and fraud prevention.\"\n      resources:\n        - path: /v1/phone-numbers/{phone_number}\n          name: phone-number-lookup\n          description: \"Look up phone number intelligence for fraud detection\"\n          operations:\n            - method: GET\n              name: lookup-phone-number\n              description: \"Get phone number intelligence including carrier, line type, and fraud risk\"\n              call: \"twilio-lookup.fetch-phone-number\"\n              with:\n                PhoneNumber: \"rest.phone_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/verifications\n          name: verifications\n          description: \"Send verification codes for identity confirmation\"\n          operations:\n            - method: POST\n              name: start-verification\n              description: \"Start a verification workflow\"\n              call: \"\
  twilio-verify.start-verification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/verification-checks\n          name: verification-checks\n          description: \"Check submitted verification codes\"\n          operations:\n            - method: POST\n              name: check-verification\n              description: \"Verify a code to confirm user identity\"\n              call: \"twilio-verify.check-verification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: twilio-identity-mcp\n      transport: http\n      description: \"MCP server for AI-assisted identity verification and fraud prevention.\"\n      tools:\n        - name: lookup-phone-number\n          description: \"Look up phone number intelligence including validation, carrier, line type, SIM swap status, and fraud risk score\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"twilio-lookup.fetch-phone-number\"\n          with:\n            PhoneNumber: \"tools.phone_number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: verify-send-code\n          description: \"Send a verification code to a user via SMS, voice, WhatsApp, or email to confirm their identity\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-verify.start-verification\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: verify-check-code\n          description: \"Check a verification code submitted by a user to complete identity confirmation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twilio-verify.check-verification\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-verification-status\n          description: \"Fetch the current status of a verification attempt\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"twilio-verify.fetch-verification\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
