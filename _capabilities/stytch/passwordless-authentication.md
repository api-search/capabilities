---
categories: []
consumed_apis:
- stytch-consumer
description: Unified capability for passwordless authentication workflows using Stytch's Consumer API. Combines magic links, OTP, and session management to deliver secure login flows without passwords. Used by consumer app developers building user authentication.
layout: capability
name: Stytch Passwordless Authentication
operations:
- description: Send a magic link for authentication
  method: POST
  name: send-magic-link
  path: /v1/magic-links/send
- description: Authenticate with a magic link token
  method: POST
  name: authenticate-magic-link
  path: /v1/magic-links/authenticate
- description: Send a one-time passcode via SMS
  method: POST
  name: send-otp-sms
  path: /v1/otps/sms/send
- description: Authenticate with a one-time passcode
  method: POST
  name: authenticate-otp
  path: /v1/otps/authenticate
- description: Validate a session token
  method: POST
  name: authenticate-session
  path: /v1/sessions/authenticate
- description: Revoke a session
  method: POST
  name: revoke-session
  path: /v1/sessions/revoke
- description: Get a user
  method: GET
  name: get-user
  path: /v1/users/{user_id}
personas: []
provider_name: Stytch
provider_slug: stytch
search_terms:
- send magic link
- authenticate with a one-time passcode
- passwordless
- security
- send a stytch magic link to a user's email for passwordless login
- authenticate session
- revoke a session
- validate a stytch consumer session token or jwt
- send sms otp
- magic links
- get user
- session revocation
- authentication
- send a one-time passcode via sms
- send a stytch sms one-time passcode to a phone number
- search users
- complete stytch magic link authentication using the token from the email
- retrieve a stytch user record by id
- get a user
- session validation
- otp
- authenticate magic link
- authenticate otp codes
- stytch
- search stytch users
- authenticate with a magic link token
- identity
- send otp sms
- developer tools
- revoke an active stytch consumer session (logout)
- revoke session
- authenticate magic link tokens
- send a magic link for authentication
- consumer
- authenticate a user with a stytch one-time passcode
- validate a session token
- authenticate otp
- user records
- send email magic links
slug: passwordless-authentication
source_filename: passwordless-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stytch Passwordless Authentication\"\n  description: >-\n    Unified capability for passwordless authentication workflows using Stytch's Consumer API.\n    Combines magic links, OTP, and session management to deliver secure login flows without passwords.\n    Used by consumer app developers building user authentication.\n  tags:\n    - Stytch\n    - Authentication\n    - Passwordless\n    - Magic Links\n    - OTP\n    - Consumer\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STYTCH_PROJECT_ID: STYTCH_PROJECT_ID\n      STYTCH_SECRET: STYTCH_SECRET\n\ncapability:\n  consumes:\n    - import: stytch-consumer\n      location: ./shared/consumer-auth.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: stytch-passwordless-api\n      description: \"Unified REST API for Stytch passwordless authentication workflows.\"\n      resources:\n        - path: /v1/magic-links/send\n\
  \          name: magic-link-send\n          description: \"Send email magic links\"\n          operations:\n            - method: POST\n              name: send-magic-link\n              description: \"Send a magic link for authentication\"\n              call: \"stytch-consumer.send-magic-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/magic-links/authenticate\n          name: magic-link-authenticate\n          description: \"Authenticate magic link tokens\"\n          operations:\n            - method: POST\n              name: authenticate-magic-link\n              description: \"Authenticate with a magic link token\"\n              call: \"stytch-consumer.authenticate-magic-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/otps/sms/send\n          name: otp-sms-send\n          description: \"Send SMS OTP\"\n          operations:\n\
  \            - method: POST\n              name: send-otp-sms\n              description: \"Send a one-time passcode via SMS\"\n              call: \"stytch-consumer.send-otp-sms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/otps/authenticate\n          name: otp-authenticate\n          description: \"Authenticate OTP codes\"\n          operations:\n            - method: POST\n              name: authenticate-otp\n              description: \"Authenticate with a one-time passcode\"\n              call: \"stytch-consumer.authenticate-otp\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sessions/authenticate\n          name: session-authenticate\n          description: \"Session validation\"\n          operations:\n            - method: POST\n              name: authenticate-session\n              description: \"Validate a session token\"\n\
  \              call: \"stytch-consumer.authenticate-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sessions/revoke\n          name: session-revoke\n          description: \"Session revocation\"\n          operations:\n            - method: POST\n              name: revoke-session\n              description: \"Revoke a session\"\n              call: \"stytch-consumer.revoke-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{user_id}\n          name: user\n          description: \"User records\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get a user\"\n              call: \"stytch-consumer.get-user\"\n              with:\n                user_id: \"rest.user_id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: stytch-passwordless-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Stytch passwordless authentication.\"\n      tools:\n        - name: send-magic-link\n          description: \"Send a Stytch magic link to a user's email for passwordless login\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-consumer.send-magic-link\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authenticate-magic-link\n          description: \"Complete Stytch magic link authentication using the token from the email\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-consumer.authenticate-magic-link\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-otp-sms\n          description: \"Send a Stytch SMS\
  \ one-time passcode to a phone number\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-consumer.send-otp-sms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authenticate-otp\n          description: \"Authenticate a user with a Stytch one-time passcode\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-consumer.authenticate-otp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authenticate-session\n          description: \"Validate a Stytch consumer session token or JWT\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stytch-consumer.authenticate-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: revoke-session\n          description: \"Revoke an active\
  \ Stytch consumer session (logout)\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"stytch-consumer.revoke-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Retrieve a Stytch user record by ID\"\n          hints:\n            readOnly: true\n          call: \"stytch-consumer.get-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-users\n          description: \"Search Stytch users\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stytch-consumer.search-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stytch/refs/heads/main/capabilities/passwordless-authentication.yaml
tags:
- Stytch
- Authentication
- Passwordless
- Magic Links
- OTP
- Consumer
tools:
- description: Send a Stytch magic link to a user's email for passwordless login
  hints:
    destructive: false
    readOnly: false
  name: send-magic-link
- description: Complete Stytch magic link authentication using the token from the email
  hints:
    destructive: false
    readOnly: false
  name: authenticate-magic-link
- description: Send a Stytch SMS one-time passcode to a phone number
  hints:
    destructive: false
    readOnly: false
  name: send-otp-sms
- description: Authenticate a user with a Stytch one-time passcode
  hints:
    destructive: false
    readOnly: false
  name: authenticate-otp
- description: Validate a Stytch consumer session token or JWT
  hints:
    idempotent: true
    readOnly: true
  name: authenticate-session
- description: Revoke an active Stytch consumer session (logout)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-session
- description: Retrieve a Stytch user record by ID
  hints:
    readOnly: true
  name: get-user
- description: Search Stytch users
  hints:
    openWorld: true
    readOnly: true
  name: search-users
---
