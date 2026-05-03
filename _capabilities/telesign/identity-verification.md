---
categories: []
consumed_apis:
- telesign-phoneid
- telesign-score
- telesign-verify
- telesign-sms
description: Unified workflow for phone-based identity verification and fraud prevention. Combines PhoneID intelligence, fraud risk scoring, and multi-channel OTP verification to enable secure account creation, login MFA, and transaction authorization. Used by fraud analysts and security engineers.
layout: capability
name: Telesign Identity Verification
operations:
- description: Get carrier, location, and type data for a phone number
  method: POST
  name: lookup-phone-intelligence
  path: /v1/phone-intelligence/{phone_number}
- description: Score a phone number for fraud risk
  method: POST
  name: score-phone-number
  path: /v1/fraud-scores/{phone_number}
- description: Send OTP to initiate a verification flow
  method: POST
  name: create-verification
  path: /v1/verifications
- description: Get verification status
  method: GET
  name: get-verification
  path: /v1/verifications/{reference_id}
- description: Submit OTP code to complete verification
  method: PATCH
  name: complete-verification
  path: /v1/verifications/{reference_id}
- description: Send an SMS message
  method: POST
  name: send-sms
  path: /v1/messages
- description: Get SMS delivery status by reference ID
  method: GET
  name: get-sms-status
  path: /v1/messages/{reference_id}
personas: []
provider_name: Telesign
provider_slug: telesign
search_terms:
- create otp verification processes
- score phone number
- submit otp code to complete verification
- assess fraud risk for a phone number
- score a phone number for fraud risk
- send an sms message
- get sms delivery status by reference id
- check verification status
- send an otp to a phone number to initiate identity verification
- send an sms message for alerts, notifications, or otp delivery
- verification
- complete verification
- complete otp verification
- send otp to initiate a verification flow
- telesign
- track sms delivery status
- look up phone number intelligence for risk assessment
- send sms notifications and alerts
- authentication
- send sms notification
- sms
- check whether a verification otp has been successfully submitted
- submit the otp code entered by the user to complete verification
- mfa
- identity verification
- look up carrier, location, and phone type data for a number
- communications
- score a phone number for fraud risk using telesign intelligence
- phone intelligence
- get carrier, location, and type data for a phone number
- get or update a verification process
- send sms
- get sms delivery status
- create verification
- get verification
- score phone for fraud
- create otp verification
- check the delivery status of a previously sent sms message
- lookup phone intelligence
- get sms status
- fraud prevention
- get verification status
slug: identity-verification
source_filename: identity-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Telesign Identity Verification\n  description: >-\n    Unified workflow for phone-based identity verification and fraud prevention.\n    Combines PhoneID intelligence, fraud risk scoring, and multi-channel OTP\n    verification to enable secure account creation, login MFA, and transaction\n    authorization. Used by fraud analysts and security engineers.\n  tags:\n    - Authentication\n    - Fraud Prevention\n    - Identity Verification\n    - MFA\n    - Phone Intelligence\n    - Telesign\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELESIGN_CUSTOMER_ID: TELESIGN_CUSTOMER_ID\n      TELESIGN_API_KEY: TELESIGN_API_KEY\n\ncapability:\n  consumes:\n    - import: telesign-phoneid\n      location: ./shared/phoneid.yaml\n    - import: telesign-score\n      location: ./shared/score.yaml\n    - import: telesign-verify\n      location: ./shared/verify.yaml\n    - import: telesign-sms\n\
  \      location: ./shared/sms.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: telesign-identity-api\n      description: >-\n        Unified REST API for phone-based identity verification and fraud prevention\n        combining PhoneID intelligence, risk scoring, and multi-channel OTP.\n      resources:\n        - path: /v1/phone-intelligence/{phone_number}\n          name: phone-intelligence\n          description: Look up phone number intelligence for risk assessment\n          operations:\n            - method: POST\n              name: lookup-phone-intelligence\n              description: Get carrier, location, and type data for a phone number\n              call: \"telesign-phoneid.lookup-phone-id\"\n              with:\n                complete_phone_number: \"rest.phone_number\"\n                account_lifecycle_event: \"rest.account_lifecycle_event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n  \
  \      - path: /v1/fraud-scores/{phone_number}\n          name: fraud-scores\n          description: Assess fraud risk for a phone number\n          operations:\n            - method: POST\n              name: score-phone-number\n              description: Score a phone number for fraud risk\n              call: \"telesign-score.score-phone-number\"\n              with:\n                complete_phone_number: \"rest.phone_number\"\n                account_lifecycle_event: \"rest.account_lifecycle_event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/verifications\n          name: verifications\n          description: Create OTP verification processes\n          operations:\n            - method: POST\n              name: create-verification\n              description: Send OTP to initiate a verification flow\n              call: \"telesign-verify.create-verification\"\n              with:\n                phone_number:\
  \ \"rest.phone_number\"\n                channel: \"rest.channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/verifications/{reference_id}\n          name: verification\n          description: Get or update a verification process\n          operations:\n            - method: GET\n              name: get-verification\n              description: Get verification status\n              call: \"telesign-verify.get-verification\"\n              with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: complete-verification\n              description: Submit OTP code to complete verification\n              call: \"telesign-verify.update-verification\"\n              with:\n                reference_id: \"rest.reference_id\"\n                verify_code: \"rest.verify_code\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: messages\n          description: Send SMS notifications and alerts\n          operations:\n            - method: POST\n              name: send-sms\n              description: Send an SMS message\n              call: \"telesign-sms.send-sms\"\n              with:\n                phone_number: \"rest.phone_number\"\n                message: \"rest.message\"\n                message_type: \"rest.message_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{reference_id}\n          name: message-status\n          description: Track SMS delivery status\n          operations:\n            - method: GET\n              name: get-sms-status\n              description: Get SMS delivery status by reference ID\n              call: \"telesign-sms.get-sms-status\"\n   \
  \           with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: telesign-identity-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted phone-based identity verification and fraud\n        prevention workflows.\n      tools:\n        - name: lookup-phone-intelligence\n          description: Look up carrier, location, and phone type data for a number\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"telesign-phoneid.lookup-phone-id\"\n          with:\n            complete_phone_number: \"tools.phone_number\"\n            account_lifecycle_event: \"tools.account_lifecycle_event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: score-phone-for-fraud\n          description:\
  \ Score a phone number for fraud risk using Telesign intelligence\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"telesign-score.score-phone-number\"\n          with:\n            complete_phone_number: \"tools.phone_number\"\n            account_lifecycle_event: \"tools.account_lifecycle_event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-otp-verification\n          description: Send an OTP to a phone number to initiate identity verification\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telesign-verify.create-verification\"\n          with:\n            phone_number: \"tools.phone_number\"\n            channel: \"tools.channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-verification-status\n\
  \          description: Check whether a verification OTP has been successfully submitted\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"telesign-verify.get-verification\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: complete-otp-verification\n          description: Submit the OTP code entered by the user to complete verification\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telesign-verify.update-verification\"\n          with:\n            reference_id: \"tools.reference_id\"\n            verify_code: \"tools.verify_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-sms-notification\n          description: Send an SMS message for alerts,\
  \ notifications, or OTP delivery\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telesign-sms.send-sms\"\n          with:\n            phone_number: \"tools.phone_number\"\n            message: \"tools.message\"\n            message_type: \"tools.message_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sms-delivery-status\n          description: Check the delivery status of a previously sent SMS message\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"telesign-sms.get-sms-status\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telesign/refs/heads/main/capabilities/identity-verification.yaml
tags:
- Authentication
- Fraud Prevention
- Identity Verification
- MFA
- Phone Intelligence
- Telesign
tools:
- description: Look up carrier, location, and phone type data for a number
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookup-phone-intelligence
- description: Score a phone number for fraud risk using Telesign intelligence
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: score-phone-for-fraud
- description: Send an OTP to a phone number to initiate identity verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-otp-verification
- description: Check whether a verification OTP has been successfully submitted
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: check-verification-status
- description: Submit the OTP code entered by the user to complete verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: complete-otp-verification
- description: Send an SMS message for alerts, notifications, or OTP delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms-notification
- description: Check the delivery status of a previously sent SMS message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-sms-delivery-status
---
