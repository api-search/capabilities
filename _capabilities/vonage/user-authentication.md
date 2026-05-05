---
categories: []
consumed_apis:
- vonage-verify
- vonage-numbers
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
- manage virtual phone numbers.
- verify a pin code entered by the user to complete 2fa.
- vonage
- security
- sms
- check verification
- list owned virtual numbers.
- verify a pin submitted by the user.
- manage phone verifications for 2fa.
- send a verification code to a phone number for 2fa.
- video conferencing
- verification
- cancel a pending verification request.
- request verification
- list owned numbers
- list all virtual phone numbers owned by the account.
- telecommunications
- number management
- two-factor authentication
- search for available phone numbers to purchase in a country.
- communication
- search for phone numbers available to purchase.
- search available numbers.
- voice
- search available numbers
- authentication
- check a verification code.
- cancel verification
- send a verification code to a phone number.
- identity
- purchase a virtual phone number for the account.
- messaging
- buy number
slug: user-authentication
source_filename: user-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vonage User Authentication\"\n  description: >-\n    Phone-based authentication workflow combining Vonage Verify API and Numbers API.\n    Enables two-factor authentication, user onboarding verification, and phone number\n    provisioning. Used by identity teams, onboarding flows, and fraud prevention systems.\n  tags:\n    - Authentication\n    - Communication\n    - Identity\n    - Number Management\n    - Security\n    - Two-Factor Authentication\n    - Vonage\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VONAGE_API_KEY: VONAGE_API_KEY\n      VONAGE_API_SECRET: VONAGE_API_SECRET\n\ncapability:\n  consumes:\n    - import: vonage-verify\n      location: ./shared/verify-api.yaml\n    - import: vonage-numbers\n      location: ./shared/numbers-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: vonage-auth-api\n      description: \"Unified REST API\
  \ for Vonage phone authentication and number management.\"\n      resources:\n        - path: /v1/verifications\n          name: verifications\n          description: \"Manage phone verifications for 2FA.\"\n          operations:\n            - method: POST\n              name: request-verification\n              description: \"Send a verification code to a phone number.\"\n              call: \"vonage-verify.request-verification\"\n              with:\n                number: \"rest.number\"\n                brand: \"rest.brand\"\n                code_length: \"rest.code_length\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/verifications/check\n          name: verification-check\n          description: \"Check a verification code.\"\n          operations:\n            - method: POST\n              name: check-verification\n              description: \"Verify a PIN submitted by the user.\"\n              call:\
  \ \"vonage-verify.check-verification\"\n              with:\n                request_id: \"rest.request_id\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/numbers\n          name: numbers\n          description: \"Manage virtual phone numbers.\"\n          operations:\n            - method: GET\n              name: list-owned-numbers\n              description: \"List owned virtual numbers.\"\n              call: \"vonage-numbers.list-owned-numbers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/numbers/available\n          name: available-numbers\n          description: \"Search available numbers.\"\n          operations:\n            - method: GET\n              name: search-available-numbers\n              description: \"Search for phone numbers available to purchase.\"\n              call: \"vonage-numbers.search-available-numbers\"\
  \n              with:\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: vonage-auth-mcp\n      transport: http\n      description: \"MCP server for AI-assisted phone verification and number management.\"\n      tools:\n        - name: request-verification\n          description: \"Send a verification code to a phone number for 2FA.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-verify.request-verification\"\n          with:\n            number: \"tools.number\"\n            brand: \"tools.brand\"\n            code_length: \"tools.code_length\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-verification\n          description: \"Verify a PIN code entered by the user to complete 2FA.\"\n  \
  \        hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-verify.check-verification\"\n          with:\n            request_id: \"tools.request_id\"\n            code: \"tools.code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-verification\n          description: \"Cancel a pending verification request.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vonage-verify.control-verification\"\n          with:\n            request_id: \"tools.request_id\"\n            cmd: \"cancel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-owned-numbers\n          description: \"List all virtual phone numbers owned by the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"vonage-numbers.list-owned-numbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-available-numbers\n          description: \"Search for available phone numbers to purchase in a country.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vonage-numbers.search-available-numbers\"\n          with:\n            country: \"tools.country\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: buy-number\n          description: \"Purchase a virtual phone number for the account.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-numbers.buy-number\"\n          with:\n            country: \"tools.country\"\n            msisdn: \"tools.msisdn\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n"
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
