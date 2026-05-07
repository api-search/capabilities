---
categories: []
consumed_apis: []
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
- authenticate magic link tokens
- authenticate with a one-time passcode
- authenticate session
- revoke session
- authenticate a user with a stytch one-time passcode
- revoke an active stytch consumer session (logout)
- session revocation
- user records
- send magic link
- send email magic links
- validate a stytch consumer session token or jwt
- authentication
- authenticate otp codes
- passwordless
- validate a session token
- get a user
- send a stytch sms one-time passcode to a phone number
- identity
- search users
- send a stytch magic link to a user's email for passwordless login
- complete stytch magic link authentication using the token from the email
- send a magic link for authentication
- stytch
- revoke a session
- developer tools
- authenticate with a magic link token
- session validation
- magic links
- send otp sms
- retrieve a stytch user record by id
- search stytch users
- authenticate otp
- send a one-time passcode via sms
- otp
- get user
- consumer
- send sms otp
- authenticate magic link
- security
slug: passwordless-authentication
source_filename: passwordless-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stytch Passwordless Authentication\n  description: Unified capability for passwordless authentication workflows using Stytch's Consumer API. Combines magic links,\n    OTP, and session management to deliver secure login flows without passwords. Used by consumer app developers building\n    user authentication.\n  tags:\n  - Stytch\n  - Authentication\n  - Passwordless\n  - Magic Links\n  - OTP\n  - Consumer\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STYTCH_PROJECT_ID: STYTCH_PROJECT_ID\n    STYTCH_SECRET: STYTCH_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: stytch-consumer\n    baseUri: https://api.stytch.com/v1\n    description: Stytch Consumer Authentication API.\n    authentication:\n      type: basic\n      username: '{{STYTCH_PROJECT_ID}}'\n      password: '{{STYTCH_SECRET}}'\n    resources:\n    - name: magic-link-send\n      path: /magic_links/email/send\n      description:\
  \ Send authentication magic links\n      operations:\n      - name: send-magic-link\n        method: POST\n        description: Send a magic link email to authenticate a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n    - name: magic-link-authenticate\n      path: /magic_links/authenticate\n      description: Authenticate magic link tokens\n      operations:\n      - name: authenticate-magic-link\n        method: POST\n        description: Authenticate a user with a magic link token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            token: '{{tools.token}}'\n            session_duration_minutes: '{{tools.session_duration_minutes}}'\n    - name: otp-sms-send\n      path:\
  \ /otps/sms/send\n      description: Send SMS OTP\n      operations:\n      - name: send-otp-sms\n        method: POST\n        description: Send a one-time passcode via SMS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phone_number: '{{tools.phone_number}}'\n    - name: otp-authenticate\n      path: /otps/authenticate\n      description: Authenticate OTP codes\n      operations:\n      - name: authenticate-otp\n        method: POST\n        description: Authenticate a user with an OTP code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            method_id: '{{tools.method_id}}'\n            code: '{{tools.code}}'\n            session_duration_minutes: '{{tools.session_duration_minutes}}'\n    - name: sessions\n\
  \      path: /sessions\n      description: Session listing\n      operations:\n      - name: get-sessions\n        method: GET\n        description: Get all sessions for a user\n        inputParameters:\n        - name: user_id\n          in: query\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: session-authenticate\n      path: /sessions/authenticate\n      description: Session authentication\n      operations:\n      - name: authenticate-session\n        method: POST\n        description: Validate and authenticate a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            session_token: '{{tools.session_token}}'\n            session_jwt: '{{tools.session_jwt}}'\n    - name:\
  \ session-revoke\n      path: /sessions/revoke\n      description: Session revocation\n      operations:\n      - name: revoke-session\n        method: POST\n        description: Revoke an active session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: search-users\n        method: GET\n        description: Search user records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /users/{user_id}\n      description: Individual user operations\n      operations:\n      - name: get-user\n        method: GET\n        description: Get a user by ID\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stytch-passwordless-api\n    description: Unified REST API for Stytch passwordless authentication workflows.\n    resources:\n    - path: /v1/magic-links/send\n      name: magic-link-send\n      description: Send email magic links\n      operations:\n      - method: POST\n        name: send-magic-link\n        description: Send a magic link for authentication\n        call: stytch-consumer.send-magic-link\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/magic-links/authenticate\n      name: magic-link-authenticate\n      description: Authenticate magic link tokens\n      operations:\n      - method: POST\n        name: authenticate-magic-link\n        description: Authenticate with a magic link token\n        call: stytch-consumer.authenticate-magic-link\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/otps/sms/send\n      name: otp-sms-send\n      description: Send SMS OTP\n      operations:\n      - method: POST\n        name: send-otp-sms\n        description: Send a one-time passcode via SMS\n        call: stytch-consumer.send-otp-sms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/otps/authenticate\n      name: otp-authenticate\n      description: Authenticate OTP codes\n      operations:\n      - method: POST\n        name: authenticate-otp\n        description: Authenticate with a one-time passcode\n\
  \        call: stytch-consumer.authenticate-otp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sessions/authenticate\n      name: session-authenticate\n      description: Session validation\n      operations:\n      - method: POST\n        name: authenticate-session\n        description: Validate a session token\n        call: stytch-consumer.authenticate-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sessions/revoke\n      name: session-revoke\n      description: Session revocation\n      operations:\n      - method: POST\n        name: revoke-session\n        description: Revoke a session\n        call: stytch-consumer.revoke-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}\n      name: user\n      description: User records\n      operations:\n      - method: GET\n        name: get-user\n        description: Get a user\n   \
  \     call: stytch-consumer.get-user\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: stytch-passwordless-mcp\n    transport: http\n    description: MCP server for AI-assisted Stytch passwordless authentication.\n    tools:\n    - name: send-magic-link\n      description: Send a Stytch magic link to a user's email for passwordless login\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-consumer.send-magic-link\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenticate-magic-link\n      description: Complete Stytch magic link authentication using the token from the email\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-consumer.authenticate-magic-link\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-otp-sms\n      description:\
  \ Send a Stytch SMS one-time passcode to a phone number\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-consumer.send-otp-sms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenticate-otp\n      description: Authenticate a user with a Stytch one-time passcode\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-consumer.authenticate-otp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenticate-session\n      description: Validate a Stytch consumer session token or JWT\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stytch-consumer.authenticate-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-session\n      description: Revoke an active Stytch consumer session (logout)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call:\
  \ stytch-consumer.revoke-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Retrieve a Stytch user record by ID\n      hints:\n        readOnly: true\n      call: stytch-consumer.get-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-users\n      description: Search Stytch users\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stytch-consumer.search-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
