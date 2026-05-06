---
categories: []
consumed_apis: []
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
- send an sms message for alerts, notifications, or otp delivery
- score phone number
- create verification
- send otp to initiate a verification flow
- track sms delivery status
- check whether a verification otp has been successfully submitted
- send an otp to a phone number to initiate identity verification
- fraud prevention
- create otp verification
- get sms delivery status
- send an sms message
- mfa
- check verification status
- submit the otp code entered by the user to complete verification
- look up phone number intelligence for risk assessment
- send sms notifications and alerts
- send sms notification
- get or update a verification process
- sms
- send sms
- complete otp verification
- look up carrier, location, and phone type data for a number
- telesign
- score a phone number for fraud risk using telesign intelligence
- get sms delivery status by reference id
- authentication
- identity verification
- phone intelligence
- lookup phone intelligence
- submit otp code to complete verification
- create otp verification processes
- assess fraud risk for a phone number
- get verification
- get verification status
- check the delivery status of a previously sent sms message
- get sms status
- complete verification
- verification
- score a phone number for fraud risk
- score phone for fraud
- get carrier, location, and type data for a phone number
- communications
slug: identity-verification
source_filename: identity-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telesign Identity Verification\n  description: Unified workflow for phone-based identity verification and fraud prevention. Combines PhoneID intelligence,\n    fraud risk scoring, and multi-channel OTP verification to enable secure account creation, login MFA, and transaction authorization.\n    Used by fraud analysts and security engineers.\n  tags:\n  - Authentication\n  - Fraud Prevention\n  - Identity Verification\n  - MFA\n  - Phone Intelligence\n  - Telesign\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELESIGN_CUSTOMER_ID: TELESIGN_CUSTOMER_ID\n    TELESIGN_API_KEY: TELESIGN_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: telesign-phoneid\n    baseUri: https://rest-ww.telesign.com/v1\n    description: Telesign phone number intelligence and lookup service.\n    authentication:\n      type: basic\n      username: '{{TELESIGN_CUSTOMER_ID}}'\n      password: '{{TELESIGN_API_KEY}}'\n\
  \    resources:\n    - name: phoneid\n      path: /phoneid\n      description: Phone number intelligence lookup\n      operations:\n      - name: lookup-phone-id\n        method: POST\n        description: Look up carrier, location, and type information for a phone number\n        inputParameters:\n        - name: complete_phone_number\n          in: path\n          type: string\n          required: true\n          description: Complete phone number including country code\n        - name: account_lifecycle_event\n          in: body\n          type: string\n          required: false\n          description: Account lifecycle stage (create, sign-in, transact, update, delete)\n        - name: originating_ip\n          in: body\n          type: string\n          required: false\n          description: End user's IP address for additional fraud signals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: telesign-score\n    baseUri: https://rest-ww.telesign.com/v1\n    description: Telesign phone number reputation and fraud risk scoring service.\n    authentication:\n      type: basic\n      username: '{{TELESIGN_CUSTOMER_ID}}'\n      password: '{{TELESIGN_API_KEY}}'\n    resources:\n    - name: score\n      path: /score\n      description: Phone number fraud risk scoring\n      operations:\n      - name: score-phone-number\n        method: POST\n        description: Score a phone number for fraud risk using multi-dimensional intelligence\n        inputParameters:\n        - name: complete_phone_number\n          in: path\n          type: string\n          required: true\n          description: Complete phone number including country code\n        - name: account_lifecycle_event\n          in: body\n          type: string\n          required: true\n          description: Account lifecycle stage (create, sign-in, transact, update, delete)\n        - name: originating_ip\n\
  \          in: body\n          type: string\n          required: false\n          description: End user's IP address\n        - name: device_id\n          in: body\n          type: string\n          required: false\n          description: End user's device ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telesign-verify\n    baseUri: https://rest-ww.telesign.com/v1\n    description: Telesign multi-channel verification and MFA service.\n    authentication:\n      type: basic\n      username: '{{TELESIGN_CUSTOMER_ID}}'\n      password: '{{TELESIGN_API_KEY}}'\n    resources:\n    - name: verify\n      path: /verify\n      description: Create, retrieve, and update verification processes\n      operations:\n      - name: create-verification\n        method: POST\n        description: Send an OTP to a phone number to initiate verification\n        inputParameters:\n        - name:\
  \ phone_number\n          in: body\n          type: string\n          required: true\n          description: End user's phone number including country code\n        - name: channel\n          in: body\n          type: string\n          required: false\n          description: Delivery channel (sms, voice, whatsapp, viber, rcs, email)\n        - name: code_length\n          in: body\n          type: integer\n          required: false\n          description: OTP code length (4-10 digits)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-verification\n        method: GET\n        description: Check the status of an existing verification process\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Reference ID from the create verification response\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-verification\n        method: PATCH\n        description: Submit the OTP code entered by the end user to complete verification\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Reference ID of the verification to update\n        - name: verify_code\n          in: body\n          type: string\n          required: true\n          description: OTP code entered by the end user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telesign-sms\n    baseUri: https://rest-ww.telesign.com/v1\n    description: Telesign SMS messaging service for global SMS delivery.\n    authentication:\n      type: basic\n      username: '{{TELESIGN_CUSTOMER_ID}}'\n      password: '{{TELESIGN_API_KEY}}'\n    resources:\n\
  \    - name: messaging\n      path: /messaging\n      description: Send and retrieve SMS messages\n      operations:\n      - name: send-sms\n        method: POST\n        description: Send an SMS message to a specified phone number\n        inputParameters:\n        - name: phone_number\n          in: body\n          type: string\n          required: true\n          description: Recipient phone number including country code\n        - name: message\n          in: body\n          type: string\n          required: true\n          description: Text content of the message\n        - name: message_type\n          in: body\n          type: string\n          required: true\n          description: Message type - OTP, ARN, or MKT\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sms-status\n        method: GET\n        description: Retrieve the delivery status of an SMS transaction\n        inputParameters:\n\
  \        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Transaction reference ID returned when message was sent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: telesign-identity-api\n    description: Unified REST API for phone-based identity verification and fraud prevention combining PhoneID intelligence,\n      risk scoring, and multi-channel OTP.\n    resources:\n    - path: /v1/phone-intelligence/{phone_number}\n      name: phone-intelligence\n      description: Look up phone number intelligence for risk assessment\n      operations:\n      - method: POST\n        name: lookup-phone-intelligence\n        description: Get carrier, location, and type data for a phone number\n        call: telesign-phoneid.lookup-phone-id\n        with:\n          complete_phone_number: rest.phone_number\n\
  \          account_lifecycle_event: rest.account_lifecycle_event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fraud-scores/{phone_number}\n      name: fraud-scores\n      description: Assess fraud risk for a phone number\n      operations:\n      - method: POST\n        name: score-phone-number\n        description: Score a phone number for fraud risk\n        call: telesign-score.score-phone-number\n        with:\n          complete_phone_number: rest.phone_number\n          account_lifecycle_event: rest.account_lifecycle_event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verifications\n      name: verifications\n      description: Create OTP verification processes\n      operations:\n      - method: POST\n        name: create-verification\n        description: Send OTP to initiate a verification flow\n        call: telesign-verify.create-verification\n        with:\n          phone_number: rest.phone_number\n\
  \          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verifications/{reference_id}\n      name: verification\n      description: Get or update a verification process\n      operations:\n      - method: GET\n        name: get-verification\n        description: Get verification status\n        call: telesign-verify.get-verification\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: complete-verification\n        description: Submit OTP code to complete verification\n        call: telesign-verify.update-verification\n        with:\n          reference_id: rest.reference_id\n          verify_code: rest.verify_code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Send SMS notifications and alerts\n      operations:\n\
  \      - method: POST\n        name: send-sms\n        description: Send an SMS message\n        call: telesign-sms.send-sms\n        with:\n          phone_number: rest.phone_number\n          message: rest.message\n          message_type: rest.message_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages/{reference_id}\n      name: message-status\n      description: Track SMS delivery status\n      operations:\n      - method: GET\n        name: get-sms-status\n        description: Get SMS delivery status by reference ID\n        call: telesign-sms.get-sms-status\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: telesign-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted phone-based identity verification and fraud prevention workflows.\n    tools:\n    - name: lookup-phone-intelligence\n\
  \      description: Look up carrier, location, and phone type data for a number\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: telesign-phoneid.lookup-phone-id\n      with:\n        complete_phone_number: tools.phone_number\n        account_lifecycle_event: tools.account_lifecycle_event\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: score-phone-for-fraud\n      description: Score a phone number for fraud risk using Telesign intelligence\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: telesign-score.score-phone-number\n      with:\n        complete_phone_number: tools.phone_number\n        account_lifecycle_event: tools.account_lifecycle_event\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-otp-verification\n      description: Send an OTP to a phone number to initiate identity verification\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telesign-verify.create-verification\n      with:\n        phone_number: tools.phone_number\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-verification-status\n      description: Check whether a verification OTP has been successfully submitted\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: telesign-verify.get-verification\n      with:\n        reference_id: tools.reference_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: complete-otp-verification\n      description: Submit the OTP code entered by the user to complete verification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telesign-verify.update-verification\n      with:\n        reference_id: tools.reference_id\n       \
  \ verify_code: tools.verify_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms-notification\n      description: Send an SMS message for alerts, notifications, or OTP delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telesign-sms.send-sms\n      with:\n        phone_number: tools.phone_number\n        message: tools.message\n        message_type: tools.message_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sms-delivery-status\n      description: Check the delivery status of a previously sent SMS message\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: telesign-sms.get-sms-status\n      with:\n        reference_id: tools.reference_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
