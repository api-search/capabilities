---
categories: []
consumed_apis: []
description: Phone-based authentication workflow combining Vonage Verify API and Numbers API. Enables two-factor authentication, user onboarding verification, and phone number provisioning. Used by identity teams, onboarding flows, and fraud prevention systems.
layout: capability
name: Vonage User Authentication
operations:
- description: Send a verification code to a phone number.
  method: POST
  name: request-verification
  path: /v1/verifications
- description: Verify a PIN submitted by the user.
  method: POST
  name: check-verification
  path: /v1/verifications/check
- description: List owned virtual numbers.
  method: GET
  name: list-owned-numbers
  path: /v1/numbers
- description: Search for phone numbers available to purchase.
  method: GET
  name: search-available-numbers
  path: /v1/numbers/available
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- buy number
- identity
- list owned numbers
- list owned virtual numbers.
- voice
- search for phone numbers available to purchase.
- communication
- security
- manage virtual phone numbers.
- send a verification code to a phone number.
- vonage
- purchase a virtual phone number for the account.
- cancel verification
- sms
- messaging
- request verification
- check verification
- cancel a pending verification request.
- list all virtual phone numbers owned by the account.
- telecommunications
- verify a pin submitted by the user.
- authentication
- video conferencing
- number management
- search available numbers
- send a verification code to a phone number for 2fa.
- check a verification code.
- two-factor authentication
- verify a pin code entered by the user to complete 2fa.
- verification
- search for available phone numbers to purchase in a country.
- manage phone verifications for 2fa.
- search available numbers.
slug: user-authentication
source_filename: user-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vonage User Authentication\n  description: Phone-based authentication workflow combining Vonage Verify API and Numbers API. Enables two-factor authentication,\n    user onboarding verification, and phone number provisioning. Used by identity teams, onboarding flows, and fraud prevention\n    systems.\n  tags:\n  - Authentication\n  - Communication\n  - Identity\n  - Number Management\n  - Security\n  - Two-Factor Authentication\n  - Vonage\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VONAGE_API_KEY: VONAGE_API_KEY\n    VONAGE_API_SECRET: VONAGE_API_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: vonage-verify\n    baseUri: https://api.nexmo.com\n    description: Vonage Verify API for phone verification and 2FA.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{VONAGE_API_KEY}}'\n      placement: body\n    resources:\n    - name: verify\n      path:\
  \ /verify/json\n      description: Request phone number verification.\n      operations:\n      - name: request-verification\n        method: POST\n        description: Start a phone verification workflow.\n        inputParameters:\n        - name: number\n          in: body\n          type: string\n          required: true\n          description: Phone number to verify (E.164 format).\n        - name: brand\n          in: body\n          type: string\n          required: true\n          description: Brand name shown in the verification message.\n        - name: code_length\n          in: body\n          type: integer\n          required: false\n          description: Length of verification code (4 or 6).\n        - name: workflow_id\n          in: body\n          type: integer\n          required: false\n          description: Workflow ID selecting SMS/TTS sequence.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: verify-check\n      path: /verify/check/json\n      description: Check a verification code.\n      operations:\n      - name: check-verification\n        method: POST\n        description: Confirm whether the user's PIN matches the sent code.\n        inputParameters:\n        - name: request_id\n          in: body\n          type: string\n          required: true\n          description: Verification request ID.\n        - name: code\n          in: body\n          type: string\n          required: true\n          description: PIN entered by the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: verify-control\n      path: /verify/control/json\n      description: Cancel or trigger next verification event.\n      operations:\n      - name: control-verification\n        method: POST\n        description: Cancel a verification request or trigger next workflow.\n        inputParameters:\n\
  \        - name: request_id\n          in: body\n          type: string\n          required: true\n          description: Verification request ID.\n        - name: cmd\n          in: body\n          type: string\n          required: true\n          description: 'Command: cancel or trigger_next_event.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: vonage-numbers\n    baseUri: https://rest.nexmo.com\n    description: Vonage Numbers API for virtual number management.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{VONAGE_API_KEY}}'\n      placement: query\n    resources:\n    - name: account-numbers\n      path: /account/numbers\n      description: List owned phone numbers.\n      operations:\n      - name: list-owned-numbers\n        method: GET\n        description: Retrieve all inbound numbers associated with your Vonage account.\n        inputParameters:\n\
  \        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by two-character country code.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        - name: index\n          in: query\n          type: integer\n          required: false\n          description: Page index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: number-search\n      path: /number/search\n      description: Search available numbers.\n      operations:\n      - name: search-available-numbers\n        method: GET\n        description: Find inbound numbers available for purchase.\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: true\n          description: Two-character country code.\n        - name:\
  \ type\n          in: query\n          type: string\n          required: false\n          description: 'Number type: landline, mobile-lvn, landline-toll-free.'\n        - name: features\n          in: query\n          type: string\n          required: false\n          description: 'Required features: SMS, VOICE, MMS.'\n        - name: pattern\n          in: query\n          type: string\n          required: false\n          description: Pattern to filter numbers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: number-buy\n      path: /number/buy\n      description: Purchase a phone number.\n      operations:\n      - name: buy-number\n        method: POST\n        description: Purchase a specific inbound number.\n        inputParameters:\n        - name: country\n          in: body\n          type: string\n          required: true\n          description: Two-character country code.\n        - name:\
  \ msisdn\n          in: body\n          type: string\n          required: true\n          description: Phone number to purchase (E.164).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: number-cancel\n      path: /number/cancel\n      description: Cancel a phone number.\n      operations:\n      - name: cancel-number\n        method: POST\n        description: Cancel subscription for a virtual number.\n        inputParameters:\n        - name: country\n          in: body\n          type: string\n          required: true\n          description: Two-character country code.\n        - name: msisdn\n          in: body\n          type: string\n          required: true\n          description: Phone number to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: number-update\n      path: /number/update\n     \
  \ description: Update number configuration.\n      operations:\n      - name: update-number\n        method: POST\n        description: Change the behavior of a number you own.\n        inputParameters:\n        - name: country\n          in: body\n          type: string\n          required: true\n          description: Two-character country code.\n        - name: msisdn\n          in: body\n          type: string\n          required: true\n          description: Phone number to update.\n        - name: mo_http_url\n          in: body\n          type: string\n          required: false\n          description: Inbound SMS webhook URL.\n        - name: voice_callback_type\n          in: body\n          type: string\n          required: false\n          description: 'Voice routing type: sip, tel, app.'\n        - name: voice_callback_value\n          in: body\n          type: string\n          required: false\n          description: Voice routing destination.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: vonage-auth-api\n    description: Unified REST API for Vonage phone authentication and number management.\n    resources:\n    - path: /v1/verifications\n      name: verifications\n      description: Manage phone verifications for 2FA.\n      operations:\n      - method: POST\n        name: request-verification\n        description: Send a verification code to a phone number.\n        call: vonage-verify.request-verification\n        with:\n          number: rest.number\n          brand: rest.brand\n          code_length: rest.code_length\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verifications/check\n      name: verification-check\n      description: Check a verification code.\n      operations:\n      - method: POST\n        name: check-verification\n        description: Verify a PIN\
  \ submitted by the user.\n        call: vonage-verify.check-verification\n        with:\n          request_id: rest.request_id\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/numbers\n      name: numbers\n      description: Manage virtual phone numbers.\n      operations:\n      - method: GET\n        name: list-owned-numbers\n        description: List owned virtual numbers.\n        call: vonage-numbers.list-owned-numbers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/numbers/available\n      name: available-numbers\n      description: Search available numbers.\n      operations:\n      - method: GET\n        name: search-available-numbers\n        description: Search for phone numbers available to purchase.\n        call: vonage-numbers.search-available-numbers\n        with:\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9092\n    namespace: vonage-auth-mcp\n    transport: http\n    description: MCP server for AI-assisted phone verification and number management.\n    tools:\n    - name: request-verification\n      description: Send a verification code to a phone number for 2FA.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-verify.request-verification\n      with:\n        number: tools.number\n        brand: tools.brand\n        code_length: tools.code_length\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-verification\n      description: Verify a PIN code entered by the user to complete 2FA.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-verify.check-verification\n      with:\n        request_id: tools.request_id\n        code: tools.code\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: cancel-verification\n      description: Cancel a pending verification request.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vonage-verify.control-verification\n      with:\n        request_id: tools.request_id\n        cmd: cancel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-owned-numbers\n      description: List all virtual phone numbers owned by the account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vonage-numbers.list-owned-numbers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-available-numbers\n      description: Search for available phone numbers to purchase in a country.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vonage-numbers.search-available-numbers\n      with:\n        country: tools.country\n        type: tools.type\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: buy-number\n      description: Purchase a virtual phone number for the account.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-numbers.buy-number\n      with:\n        country: tools.country\n        msisdn: tools.msisdn\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vonage/refs/heads/main/capabilities/user-authentication.yaml
tags:
- Authentication
- Communication
- Identity
- Number Management
- Security
- Two-Factor Authentication
- Vonage
tools:
- description: Send a verification code to a phone number for 2FA.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: request-verification
- description: Verify a PIN code entered by the user to complete 2FA.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: check-verification
- description: Cancel a pending verification request.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-verification
- description: List all virtual phone numbers owned by the account.
  hints:
    idempotent: true
    readOnly: true
  name: list-owned-numbers
- description: Search for available phone numbers to purchase in a country.
  hints:
    idempotent: true
    readOnly: true
  name: search-available-numbers
- description: Purchase a virtual phone number for the account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: buy-number
---
