---
categories: []
consumed_apis:
- supertokens-cdi
description: Unified authentication workflow combining all SuperTokens Core authentication capabilities. Covers session management, email/password auth, passwordless OTP and magic links, third-party OAuth (Google, GitHub, Apple), email verification, password reset, user metadata, multi-tenancy, user management, and role-based access control.
layout: capability
name: SuperTokens Authentication
operations:
- description: Create a new authentication session
  method: POST
  name: create-session
  path: /v1/sessions
- description: Verify an access token and get session data
  method: GET
  name: get-session
  path: /v1/sessions
- description: Refresh a session using a refresh token
  method: POST
  name: refresh-session
  path: /v1/sessions
- description: Revoke sessions by handle or user ID
  method: DELETE
  name: remove-sessions
  path: /v1/sessions
- description: Create new user with email and password
  method: POST
  name: signup
  path: /v1/auth/signup
- description: Sign in with email and password
  method: POST
  name: signin
  path: /v1/auth/signin
- description: Generate password reset token
  method: POST
  name: create-reset-token
  path: /v1/auth/password/reset
- description: Reset password using token
  method: PUT
  name: reset-password
  path: /v1/auth/password/reset
- description: Create passwordless OTP or magic link
  method: POST
  name: create-code
  path: /v1/auth/passwordless/code
- description: Consume code to authenticate user
  method: POST
  name: consume-code
  path: /v1/auth/passwordless/code
- description: Sign in or up via OAuth provider
  method: POST
  name: thirdparty-signinup
  path: /v1/auth/thirdparty
- description: Generate email verification token
  method: POST
  name: create-verification-token
  path: /v1/auth/email/verify
- description: Verify email with token
  method: PUT
  name: verify-email
  path: /v1/auth/email/verify
- description: Check email verification status
  method: GET
  name: is-email-verified
  path: /v1/auth/email/verify
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Delete a user permanently
  method: DELETE
  name: delete-user
  path: /v1/users
- description: Get user metadata
  method: GET
  name: get-user-metadata
  path: /v1/users/{userId}/metadata
- description: Update user metadata
  method: PUT
  name: update-user-metadata
  path: /v1/users/{userId}/metadata
- description: Get roles assigned to a user
  method: GET
  name: get-user-roles
  path: /v1/users/{userId}/roles
- description: Assign a role to a user
  method: PUT
  name: assign-role
  path: /v1/users/{userId}/roles
- description: Remove a role from a user
  method: DELETE
  name: remove-role
  path: /v1/users/{userId}/roles
- description: List all tenants
  method: GET
  name: list-tenants
  path: /v1/tenants
- description: Create or update a tenant
  method: POST
  name: create-or-update-tenant
  path: /v1/tenants
personas: []
provider_name: SuperTokens
provider_slug: supertokens
search_terms:
- delete a user permanently
- email verification
- list users
- remove a role from a user
- assign a role to a user for rbac
- create or update a tenant
- create passwordless otp or magic link
- assign role
- list all configured tenants in a multi-tenant deployment
- create session
- create email verification token
- update user metadata
- update custom metadata for a user (shallow merge)
- get session
- retrieve custom metadata stored for a user
- create reset token
- session lifecycle management
- list all tenants
- remove role
- create passwordless code
- reset password using token
- multi-tenant configuration
- identity
- password reset flow
- authenticate user by consuming a passwordless otp or magic link
- sign in with email and password
- verify an access token and get session data
- create or configure a tenant in a multi-tenant setup
- permanently delete a user and all their data
- verify and retrieve session data from an access token
- get user roles
- create a new authentication session
- create a new user account with email and password
- user metadata storage
- oauth
- third-party oauth authentication
- generate password reset token
- refresh session
- create code
- signin
- list all users
- authorization
- verify a user's email address using their verification token
- get user metadata
- reset password
- revoke sessions for a user or specific session handles
- consume passwordless code
- create new user with email and password
- assign role to user
- thirdparty signinup
- check email verification status
- create or update tenant
- sign in or create user via oauth provider (google, github, apple, etc.)
- session management
- passwordless
- check whether a user's email has been verified
- supertokens
- user role management
- list tenants
- is email verified
- consume code to authenticate user
- assign a role to a user
- self-hosted
- authentication
- passwordless authentication
- node.js
- create verification token
- list all users with pagination
- open source
- generate a passwordless otp or magic link for sign in
- refresh a session using a refresh token
- authenticate a user with email and password
- get roles assigned to a user
- email/password sign-in
- get all roles assigned to a user
- remove sessions
- signup
- verify email
- delete user
- generate email verification token
- refresh an authentication session using a refresh token
- revoke sessions by handle or user id
- consume code
- multi-tenancy
- create a new authenticated session for a user
- social login
- verify email with token
- generate an email verification token to send to the user
- sign in or up via oauth provider
- user management
- email/password sign-up
slug: authentication
source_filename: authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SuperTokens Authentication\"\n  description: >-\n    Unified authentication workflow combining all SuperTokens Core authentication\n    capabilities. Covers session management, email/password auth, passwordless OTP\n    and magic links, third-party OAuth (Google, GitHub, Apple), email verification,\n    password reset, user metadata, multi-tenancy, user management, and role-based\n    access control.\n  tags:\n    - SuperTokens\n    - Authentication\n    - Session Management\n    - Identity\n    - OAuth\n    - Passwordless\n    - Multi-Tenancy\n    - Open Source\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SUPERTOKENS_CORE_HOST: SUPERTOKENS_CORE_HOST\n      SUPERTOKENS_API_KEY: SUPERTOKENS_API_KEY\n\ncapability:\n  consumes:\n    - import: supertokens-cdi\n      location: ./shared/core-driver-interface.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ supertokens-auth-api\n      description: \"Unified REST API for SuperTokens authentication and identity management.\"\n      resources:\n        - path: /v1/sessions\n          name: sessions\n          description: \"Session lifecycle management\"\n          operations:\n            - method: POST\n              name: create-session\n              description: \"Create a new authentication session\"\n              call: \"supertokens-cdi.create-session\"\n              with:\n                user_id: \"rest.user_id\"\n                jwt_data: \"rest.jwt_data\"\n                db_data: \"rest.db_data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-session\n              description: \"Verify an access token and get session data\"\n              call: \"supertokens-cdi.get-session\"\n              with:\n                accessToken: \"rest.accessToken\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: refresh-session\n              description: \"Refresh a session using a refresh token\"\n              call: \"supertokens-cdi.refresh-session\"\n              with:\n                refresh_token: \"rest.refresh_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-sessions\n              description: \"Revoke sessions by handle or user ID\"\n              call: \"supertokens-cdi.remove-sessions\"\n              with:\n                session_handles: \"rest.session_handles\"\n                user_id: \"rest.user_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/signup\n          name: email-password-signup\n          description: \"Email/password sign-up\"\n          operations:\n\
  \            - method: POST\n              name: signup\n              description: \"Create new user with email and password\"\n              call: \"supertokens-cdi.signup\"\n              with:\n                email: \"rest.email\"\n                password: \"rest.password\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/signin\n          name: email-password-signin\n          description: \"Email/password sign-in\"\n          operations:\n            - method: POST\n              name: signin\n              description: \"Sign in with email and password\"\n              call: \"supertokens-cdi.signin\"\n              with:\n                email: \"rest.email\"\n                password: \"rest.password\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/password/reset\n          name: password-reset\n          description:\
  \ \"Password reset flow\"\n          operations:\n            - method: POST\n              name: create-reset-token\n              description: \"Generate password reset token\"\n              call: \"supertokens-cdi.create-reset-password-token\"\n              with:\n                user_id: \"rest.user_id\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: reset-password\n              description: \"Reset password using token\"\n              call: \"supertokens-cdi.reset-password\"\n              with:\n                token: \"rest.token\"\n                new_password: \"rest.new_password\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/passwordless/code\n          name: passwordless-code\n          description: \"Passwordless authentication\"\n          operations:\n\
  \            - method: POST\n              name: create-code\n              description: \"Create passwordless OTP or magic link\"\n              call: \"supertokens-cdi.create-passwordless-code\"\n              with:\n                email: \"rest.email\"\n                phone_number: \"rest.phone_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: consume-code\n              description: \"Consume code to authenticate user\"\n              call: \"supertokens-cdi.consume-passwordless-code\"\n              with:\n                pre_auth_session_id: \"rest.pre_auth_session_id\"\n                otp_code: \"rest.otp_code\"\n                device_id: \"rest.device_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/thirdparty\n          name: third-party-auth\n          description: \"Third-party OAuth\
  \ authentication\"\n          operations:\n            - method: POST\n              name: thirdparty-signinup\n              description: \"Sign in or up via OAuth provider\"\n              call: \"supertokens-cdi.third-party-signinup\"\n              with:\n                provider_id: \"rest.provider_id\"\n                provider_user_id: \"rest.provider_user_id\"\n                email_object: \"rest.email_object\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/email/verify\n          name: email-verification\n          description: \"Email verification\"\n          operations:\n            - method: POST\n              name: create-verification-token\n              description: \"Generate email verification token\"\n              call: \"supertokens-cdi.create-email-verification-token\"\n              with:\n                user_id: \"rest.user_id\"\n                email: \"rest.email\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: verify-email\n              description: \"Verify email with token\"\n              call: \"supertokens-cdi.verify-email\"\n              with:\n                token: \"rest.token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: is-email-verified\n              description: \"Check email verification status\"\n              call: \"supertokens-cdi.is-email-verified\"\n              with:\n                userId: \"rest.userId\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n         \
  \     description: \"List all users\"\n              call: \"supertokens-cdi.list-users\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user permanently\"\n              call: \"supertokens-cdi.delete-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{userId}/metadata\n          name: user-metadata\n          description: \"User metadata storage\"\n          operations:\n            - method: GET\n              name: get-user-metadata\n              description: \"Get user metadata\"\n              call: \"supertokens-cdi.get-user-metadata\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-user-metadata\n              description: \"Update user metadata\"\n              call: \"supertokens-cdi.update-user-metadata\"\n              with:\n                user_id: \"rest.user_id\"\n                metadata: \"rest.metadata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{userId}/roles\n          name: user-roles\n          description: \"User role management\"\n          operations:\n            - method: GET\n              name: get-user-roles\n              description: \"Get roles assigned to a user\"\n              call: \"supertokens-cdi.get-user-roles\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: assign-role\n\
  \              description: \"Assign a role to a user\"\n              call: \"supertokens-cdi.assign-role-to-user\"\n              with:\n                user_id: \"rest.user_id\"\n                role: \"rest.role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-role\n              description: \"Remove a role from a user\"\n              call: \"supertokens-cdi.remove-user-role\"\n              with:\n                userId: \"rest.userId\"\n                role: \"rest.role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenants\n          name: tenants\n          description: \"Multi-tenant configuration\"\n          operations:\n            - method: GET\n              name: list-tenants\n              description: \"List all tenants\"\n              call: \"supertokens-cdi.list-tenants\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-or-update-tenant\n              description: \"Create or update a tenant\"\n              call: \"supertokens-cdi.create-or-update-tenant\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n                email_password_enabled: \"rest.email_password_enabled\"\n                passwordless_enabled: \"rest.passwordless_enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: supertokens-auth-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SuperTokens authentication management.\"\n      tools:\n        - name: create-session\n          description: \"Create a new authenticated session for a user\"\n          hints:\n            readOnly: false\n            idempotent: false\n         \
  \ call: \"supertokens-cdi.create-session\"\n          with:\n            user_id: \"tools.user_id\"\n            jwt_data: \"tools.jwt_data\"\n            db_data: \"tools.db_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-session\n          description: \"Verify and retrieve session data from an access token\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.get-session\"\n          with:\n            accessToken: \"tools.accessToken\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refresh-session\n          description: \"Refresh an authentication session using a refresh token\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.refresh-session\"\n          with:\n            refresh_token: \"tools.refresh_token\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: remove-sessions\n          description: \"Revoke sessions for a user or specific session handles\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"supertokens-cdi.remove-sessions\"\n          with:\n            session_handles: \"tools.session_handles\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: signup\n          description: \"Create a new user account with email and password\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.signup\"\n          with:\n            email: \"tools.email\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: signin\n          description: \"Authenticate\
  \ a user with email and password\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.signin\"\n          with:\n            email: \"tools.email\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-passwordless-code\n          description: \"Generate a passwordless OTP or magic link for sign in\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.create-passwordless-code\"\n          with:\n            email: \"tools.email\"\n            phone_number: \"tools.phone_number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: consume-passwordless-code\n          description: \"Authenticate user by consuming a passwordless OTP or magic link\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ false\n          call: \"supertokens-cdi.consume-passwordless-code\"\n          with:\n            pre_auth_session_id: \"tools.pre_auth_session_id\"\n            otp_code: \"tools.otp_code\"\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: thirdparty-signinup\n          description: \"Sign in or create user via OAuth provider (Google, GitHub, Apple, etc.)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.third-party-signinup\"\n          with:\n            provider_id: \"tools.provider_id\"\n            provider_user_id: \"tools.provider_user_id\"\n            email_object: \"tools.email_object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-email-verification-token\n          description: \"Generate an email verification token to send to the user\"\n    \
  \      hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.create-email-verification-token\"\n          with:\n            user_id: \"tools.user_id\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-email\n          description: \"Verify a user's email address using their verification token\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"supertokens-cdi.verify-email\"\n          with:\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: is-email-verified\n          description: \"Check whether a user's email has been verified\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.is-email-verified\"\n          with:\n            userId: \"tools.userId\"\
  \n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all users with pagination\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.list-users\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Permanently delete a user and all their data\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"supertokens-cdi.delete-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user-metadata\n          description: \"Retrieve custom metadata stored for a user\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.get-user-metadata\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user-metadata\n          description: \"Update custom metadata for a user (shallow merge)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"supertokens-cdi.update-user-metadata\"\n          with:\n            user_id: \"tools.user_id\"\n            metadata: \"tools.metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: assign-role-to-user\n          description: \"Assign a role to a user for RBAC\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"supertokens-cdi.assign-role-to-user\"\n          with:\n            user_id: \"tools.user_id\"\n            role:\
  \ \"tools.role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user-roles\n          description: \"Get all roles assigned to a user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.get-user-roles\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tenants\n          description: \"List all configured tenants in a multi-tenant deployment\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supertokens-cdi.list-tenants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-or-update-tenant\n          description: \"Create or configure a tenant in a multi-tenant setup\"\n          hints:\n            readOnly: false\n            idempotent: true\n \
  \         call: \"supertokens-cdi.create-or-update-tenant\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n            email_password_enabled: \"tools.email_password_enabled\"\n            passwordless_enabled: \"tools.passwordless_enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/supertokens/refs/heads/main/capabilities/authentication.yaml
tags:
- SuperTokens
- Authentication
- Session Management
- Identity
- OAuth
- Passwordless
- Multi-Tenancy
- Open Source
tools:
- description: Create a new authenticated session for a user
  hints:
    idempotent: false
    readOnly: false
  name: create-session
- description: Verify and retrieve session data from an access token
  hints:
    idempotent: true
    readOnly: true
  name: get-session
- description: Refresh an authentication session using a refresh token
  hints:
    idempotent: false
    readOnly: false
  name: refresh-session
- description: Revoke sessions for a user or specific session handles
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-sessions
- description: Create a new user account with email and password
  hints:
    idempotent: false
    readOnly: false
  name: signup
- description: Authenticate a user with email and password
  hints:
    idempotent: false
    readOnly: false
  name: signin
- description: Generate a passwordless OTP or magic link for sign in
  hints:
    idempotent: false
    readOnly: false
  name: create-passwordless-code
- description: Authenticate user by consuming a passwordless OTP or magic link
  hints:
    idempotent: false
    readOnly: false
  name: consume-passwordless-code
- description: Sign in or create user via OAuth provider (Google, GitHub, Apple, etc.)
  hints:
    idempotent: false
    readOnly: false
  name: thirdparty-signinup
- description: Generate an email verification token to send to the user
  hints:
    idempotent: false
    readOnly: false
  name: create-email-verification-token
- description: Verify a user's email address using their verification token
  hints:
    idempotent: true
    readOnly: false
  name: verify-email
- description: Check whether a user's email has been verified
  hints:
    idempotent: true
    readOnly: true
  name: is-email-verified
- description: List all users with pagination
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Permanently delete a user and all their data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: Retrieve custom metadata stored for a user
  hints:
    idempotent: true
    readOnly: true
  name: get-user-metadata
- description: Update custom metadata for a user (shallow merge)
  hints:
    idempotent: false
    readOnly: false
  name: update-user-metadata
- description: Assign a role to a user for RBAC
  hints:
    idempotent: true
    readOnly: false
  name: assign-role-to-user
- description: Get all roles assigned to a user
  hints:
    idempotent: true
    readOnly: true
  name: get-user-roles
- description: List all configured tenants in a multi-tenant deployment
  hints:
    idempotent: true
    readOnly: true
  name: list-tenants
- description: Create or configure a tenant in a multi-tenant setup
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-tenant
---
