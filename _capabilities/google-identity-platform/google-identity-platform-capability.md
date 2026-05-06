---
categories: []
consumed_apis: []
description: The Identity Toolkit API provides REST endpoints for user authentication and management in Google Identity Platform. It supports email/password, phone, and federated sign-in, token management, multi-factor authentication, and user account operations.
layout: capability
name: Google Identity Platform Google Identity Toolkit API
operations:
- description: Google Identity Platform Sign up with email/password
  method: POST
  name: signup
  path: /accounts:signUp
- description: Google Identity Platform Sign in with email/password
  method: POST
  name: signinwithpassword
  path: /accounts:signInWithPassword
- description: Google Identity Platform Sign in with identity provider
  method: POST
  name: signinwithidp
  path: /accounts:signInWithIdp
- description: Google Identity Platform Get user account info
  method: POST
  name: lookupaccount
  path: /accounts:lookup
- description: Google Identity Platform Send out-of-band code
  method: POST
  name: sendoobcode
  path: /accounts:sendOobCode
- description: Google Identity Platform Delete account
  method: POST
  name: deleteaccount
  path: /accounts:delete
personas: []
provider_name: Google Identity Platform
provider_slug: google-identity-platform
search_terms:
- google identity platform sign in with identity provider
- identity
- signinwithidp
- signup
- signinwithpassword
- deleteaccount
- google
- oauth
- google identity platform send out-of-band code
- sendoobcode
- saml
- api
- google identity platform sign up with email/password
- google identity platform get user account info
- authentication
- lookupaccount
- google identity platform delete account
- platform
- openid connect
- google cloud
- google identity platform sign in with email/password
- multi-tenancy
slug: google-identity-platform-capability
source_filename: google-identity-platform-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Identity Platform Google Identity Toolkit API\n  description: The Identity Toolkit API provides REST endpoints for user authentication and management in Google Identity\n    Platform. It supports email/password, phone, and federated sign-in, token management, multi-factor authentication, and\n    user account operations.\n  tags:\n  - Google\n  - Identity\n  - Platform\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-identity-platform\n    baseUri: https://identitytoolkit.googleapis.com/v1\n    description: Google Identity Platform Google Identity Toolkit API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_IDENTITY_PLATFORM_TOKEN}}'\n    resources:\n    - name: accounts-signup\n      path: /accounts:signUp\n      operations:\n      - name: signup\n        method: POST\n        description: Google\
  \ Identity Platform Sign up with email/password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-signinwithpassword\n      path: /accounts:signInWithPassword\n      operations:\n      - name: signinwithpassword\n        method: POST\n        description: Google Identity Platform Sign in with email/password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-signinwithidp\n      path: /accounts:signInWithIdp\n      operations:\n      - name: signinwithidp\n        method: POST\n        description: Google Identity Platform Sign in with identity provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-lookup\n      path: /accounts:lookup\n      operations:\n      - name: lookupaccount\n        method:\
  \ POST\n        description: Google Identity Platform Get user account info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-sendoobcode\n      path: /accounts:sendOobCode\n      operations:\n      - name: sendoobcode\n        method: POST\n        description: Google Identity Platform Send out-of-band code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-delete\n      path: /accounts:delete\n      operations:\n      - name: deleteaccount\n        method: POST\n        description: Google Identity Platform Delete account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-identity-platform-rest\n    description: REST adapter for Google Identity Platform\
  \ Google Identity Toolkit API.\n    resources:\n    - path: /accounts:signUp\n      name: signup\n      operations:\n      - method: POST\n        name: signup\n        description: Google Identity Platform Sign up with email/password\n        call: google-identity-platform.signup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts:signInWithPassword\n      name: signinwithpassword\n      operations:\n      - method: POST\n        name: signinwithpassword\n        description: Google Identity Platform Sign in with email/password\n        call: google-identity-platform.signinwithpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts:signInWithIdp\n      name: signinwithidp\n      operations:\n      - method: POST\n        name: signinwithidp\n        description: Google Identity Platform Sign in with identity provider\n        call: google-identity-platform.signinwithidp\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts:lookup\n      name: lookupaccount\n      operations:\n      - method: POST\n        name: lookupaccount\n        description: Google Identity Platform Get user account info\n        call: google-identity-platform.lookupaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts:sendOobCode\n      name: sendoobcode\n      operations:\n      - method: POST\n        name: sendoobcode\n        description: Google Identity Platform Send out-of-band code\n        call: google-identity-platform.sendoobcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts:delete\n      name: deleteaccount\n      operations:\n      - method: POST\n        name: deleteaccount\n        description: Google Identity Platform Delete account\n        call: google-identity-platform.deleteaccount\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: google-identity-platform-mcp\n    transport: http\n    description: MCP adapter for Google Identity Platform Google Identity Toolkit API for AI agent use.\n    tools:\n    - name: signup\n      description: Google Identity Platform Sign up with email/password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-identity-platform.signup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: signinwithpassword\n      description: Google Identity Platform Sign in with email/password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-identity-platform.signinwithpassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: signinwithidp\n      description: Google Identity Platform Sign in with identity provider\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: google-identity-platform.signinwithidp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookupaccount\n      description: Google Identity Platform Get user account info\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-identity-platform.lookupaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendoobcode\n      description: Google Identity Platform Send out-of-band code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-identity-platform.sendoobcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaccount\n      description: Google Identity Platform Delete account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-identity-platform.deleteaccount\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_IDENTITY_PLATFORM_TOKEN: GOOGLE_IDENTITY_PLATFORM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-identity-platform/refs/heads/main/capabilities/google-identity-platform-capability.yaml
tags:
- Google
- Identity
- Platform
- API
tools:
- description: Google Identity Platform Sign up with email/password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: signup
- description: Google Identity Platform Sign in with email/password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: signinwithpassword
- description: Google Identity Platform Sign in with identity provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: signinwithidp
- description: Google Identity Platform Get user account info
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lookupaccount
- description: Google Identity Platform Send out-of-band code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendoobcode
- description: Google Identity Platform Delete account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteaccount
---
