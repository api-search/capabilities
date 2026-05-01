---
api_specs:
- filename: gitlab-oauth2-openapi.yml
  format: yaml
  label: gitlab-oauth2
  slug: gitlab-oauth2
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/gitlab/refs/heads/main/openapi/gitlab-oauth2-openapi.yml
categories:
- identity-access
consumed_apis:
- gitlab-oauth2
description: Unified capability for GitLab OAuth 2.0 authentication flows and user identity. Enables developers and platform administrators to manage OAuth application authorization, token lifecycle, and authenticated user profile retrieval.
layout: capability
name: GitLab Authentication And Identity
operations:
- description: Initiate the OAuth 2.0 authorization code flow.
  method: GET
  name: authorize-oauth
  path: /v1/authorizations
- description: Initiate the device authorization grant flow.
  method: POST
  name: authorize-device
  path: /v1/device-authorizations
- description: Exchange an authorization code, device code, or refresh token for an access token.
  method: POST
  name: exchange-token
  path: /v1/tokens
- description: Revoke an OAuth access or refresh token.
  method: POST
  name: revoke-token
  path: /v1/token-revocations
- description: Get information about the current access token.
  method: GET
  name: get-token-info
  path: /v1/token-info
- description: Get profile information about the authenticated user.
  method: GET
  name: get-user-info
  path: /v1/user-info
personas: []
provider_name: GitLab
provider_slug: gitlab
search_terms:
- get information about the current oauth access token including scopes and expiration.
- authenticated user profile information.
- source control
- exchange an authorization code, device code, or refresh token for an access token.
- authorize oauth
- initiate the device authorization grant flow for input-constrained devices.
- get token info
- oauth token exchange and creation.
- platform
- revoke an oauth access or refresh token.
- token introspection and validation.
- identity
- get profile information about the authenticated user.
- authorize device
- software development
- initiate the device authorization grant flow.
- device authorization grant flow for input-constrained devices.
- initiate the oauth 2.0 authorization code flow with optional pkce support.
- get user info
- code
- exchange token
- gitlab
- revoke token
- get profile information about the currently authenticated user.
- oauth
- get information about the current access token.
- tokens
- initiate the oauth 2.0 authorization code flow.
- revoke an existing oauth access or refresh token.
- oauth 2.0 authorization code flow initiation.
- authentication
- token revocation.
slug: authentication-and-identity
source_filename: authentication-and-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitLab Authentication And Identity\"\n  description: \"Unified capability for GitLab OAuth 2.0 authentication flows and user identity. Enables developers and platform administrators to manage OAuth application authorization, token lifecycle, and authenticated user profile retrieval.\"\n  tags:\n    - Gitlab\n    - Authentication\n    - OAuth\n    - Identity\n    - Tokens\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITLAB_OAUTH_TOKEN: GITLAB_OAUTH_TOKEN\n      GITLAB_CLIENT_ID: GITLAB_CLIENT_ID\n      GITLAB_CLIENT_SECRET: GITLAB_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: gitlab-oauth2\n      location: ./shared/gitlab-oauth2.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gitlab-auth-api\n      description: \"Unified REST API for GitLab OAuth 2.0 authentication and identity management.\"\n      resources:\n        - path: /v1/authorizations\n\
  \          name: authorizations\n          description: \"OAuth 2.0 authorization code flow initiation.\"\n          operations:\n            - method: GET\n              name: authorize-oauth\n              description: \"Initiate the OAuth 2.0 authorization code flow.\"\n              call: \"gitlab-oauth2.authorize-oauth\"\n              with:\n                client_id: \"rest.client_id\"\n                redirect_uri: \"rest.redirect_uri\"\n                response_type: \"rest.response_type\"\n                state: \"rest.state\"\n                scope: \"rest.scope\"\n                code_challenge: \"rest.code_challenge\"\n                code_challenge_method: \"rest.code_challenge_method\"\n                root_namespace_id: \"rest.root_namespace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/device-authorizations\n          name: device-authorizations\n          description: \"Device authorization\
  \ grant flow for input-constrained devices.\"\n          operations:\n            - method: POST\n              name: authorize-device\n              description: \"Initiate the device authorization grant flow.\"\n              call: \"gitlab-oauth2.authorize-device\"\n              with:\n                client_id: \"rest.client_id\"\n                scope: \"rest.scope\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens\n          name: tokens\n          description: \"OAuth token exchange and creation.\"\n          operations:\n            - method: POST\n              name: exchange-token\n              description: \"Exchange an authorization code, device code, or refresh token for an access token.\"\n              call: \"gitlab-oauth2.exchange-token\"\n              with:\n                grant_type: \"rest.grant_type\"\n                client_id: \"rest.client_id\"\n                client_secret: \"\
  rest.client_secret\"\n                code: \"rest.code\"\n                redirect_uri: \"rest.redirect_uri\"\n                code_verifier: \"rest.code_verifier\"\n                refresh_token: \"rest.refresh_token\"\n                device_code: \"rest.device_code\"\n                username: \"rest.username\"\n                password: \"rest.password\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/token-revocations\n          name: token-revocations\n          description: \"Token revocation.\"\n          operations:\n            - method: POST\n              name: revoke-token\n              description: \"Revoke an OAuth access or refresh token.\"\n              call: \"gitlab-oauth2.revoke-token\"\n              with:\n                client_id: \"rest.client_id\"\n                client_secret: \"rest.client_secret\"\n                token: \"rest.token\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/token-info\n          name: token-info\n          description: \"Token introspection and validation.\"\n          operations:\n            - method: GET\n              name: get-token-info\n              description: \"Get information about the current access token.\"\n              call: \"gitlab-oauth2.get-token-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user-info\n          name: user-info\n          description: \"Authenticated user profile information.\"\n          operations:\n            - method: GET\n              name: get-user-info\n              description: \"Get profile information about the authenticated user.\"\n              call: \"gitlab-oauth2.get-user-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n     \
  \ namespace: gitlab-auth-mcp\n      transport: http\n      description: \"MCP server for AI-assisted GitLab OAuth 2.0 authentication and identity management.\"\n      tools:\n        - name: authorize-oauth\n          description: \"Initiate the OAuth 2.0 authorization code flow with optional PKCE support.\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-oauth2.authorize-oauth\"\n          with:\n            client_id: \"tools.client_id\"\n            redirect_uri: \"tools.redirect_uri\"\n            response_type: \"tools.response_type\"\n            state: \"tools.state\"\n            scope: \"tools.scope\"\n            code_challenge: \"tools.code_challenge\"\n            code_challenge_method: \"tools.code_challenge_method\"\n            root_namespace_id: \"tools.root_namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: authorize-device\n\
  \          description: \"Initiate the device authorization grant flow for input-constrained devices.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: false\n          call: \"gitlab-oauth2.authorize-device\"\n          with:\n            client_id: \"tools.client_id\"\n            scope: \"tools.scope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: exchange-token\n          description: \"Exchange an authorization code, device code, or refresh token for an access token.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: false\n          call: \"gitlab-oauth2.exchange-token\"\n          with:\n            grant_type: \"tools.grant_type\"\n            client_id: \"tools.client_id\"\n            client_secret: \"tools.client_secret\"\n            code: \"tools.code\"\n            redirect_uri: \"tools.redirect_uri\"\n     \
  \       code_verifier: \"tools.code_verifier\"\n            refresh_token: \"tools.refresh_token\"\n            device_code: \"tools.device_code\"\n            username: \"tools.username\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: revoke-token\n          description: \"Revoke an existing OAuth access or refresh token.\"\n          hints:\n            readOnly: false\n            destructive: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-oauth2.revoke-token\"\n          with:\n            client_id: \"tools.client_id\"\n            client_secret: \"tools.client_secret\"\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-token-info\n          description: \"Get information about the current OAuth access token including scopes and expiration.\"\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-oauth2.get-token-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-info\n          description: \"Get profile information about the currently authenticated user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-oauth2.get-user-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gitlab/refs/heads/main/capabilities/authentication-and-identity.yaml
tags:
- Gitlab
- Authentication
- OAuth
- Identity
- Tokens
tools:
- description: Initiate the OAuth 2.0 authorization code flow with optional PKCE support.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: authorize-oauth
- description: Initiate the device authorization grant flow for input-constrained devices.
  hints:
    idempotent: false
    openWorld: true
    readOnly: false
  name: authorize-device
- description: Exchange an authorization code, device code, or refresh token for an access token.
  hints:
    idempotent: false
    openWorld: true
    readOnly: false
  name: exchange-token
- description: Revoke an existing OAuth access or refresh token.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: revoke-token
- description: Get information about the current OAuth access token including scopes and expiration.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-token-info
- description: Get profile information about the currently authenticated user.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-user-info
---
