---
categories:
- identity-access
consumed_apis: []
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
- token revocation.
- authorize device
- get token info
- revoke token
- initiate the device authorization grant flow for input-constrained devices.
- exchange token
- authorize oauth
- platform
- token introspection and validation.
- authentication
- oauth token exchange and creation.
- revoke an oauth access or refresh token.
- initiate the oauth 2.0 authorization code flow with optional pkce support.
- get user info
- oauth 2.0 authorization code flow initiation.
- initiate the device authorization grant flow.
- authenticated user profile information.
- identity
- initiate the oauth 2.0 authorization code flow.
- software development
- tokens
- device authorization grant flow for input-constrained devices.
- exchange an authorization code, device code, or refresh token for an access token.
- get profile information about the currently authenticated user.
- source control
- get information about the current oauth access token including scopes and expiration.
- gitlab
- revoke an existing oauth access or refresh token.
- code
- oauth
- get information about the current access token.
- get profile information about the authenticated user.
slug: authentication-and-identity
source_filename: authentication-and-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitLab Authentication And Identity\n  description: Unified capability for GitLab OAuth 2.0 authentication flows and user identity. Enables developers and platform\n    administrators to manage OAuth application authorization, token lifecycle, and authenticated user profile retrieval.\n  tags:\n  - Gitlab\n  - Authentication\n  - OAuth\n  - Identity\n  - Tokens\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITLAB_OAUTH_TOKEN: GITLAB_OAUTH_TOKEN\n    GITLAB_CLIENT_ID: GITLAB_CLIENT_ID\n    GITLAB_CLIENT_SECRET: GITLAB_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: gitlab-oauth2\n    baseUri: https://gitlab.com\n    description: GitLab OAuth 2.0 API for authorization flows, token management, and user information.\n    authentication:\n      type: bearer\n      token: '{{GITLAB_OAUTH_TOKEN}}'\n    resources:\n    - name: authorization\n      path: /oauth\n      description:\
  \ OAuth 2.0 authorization endpoints for initiating auth flows.\n      operations:\n      - name: authorize-oauth\n        method: GET\n        description: Initiates the OAuth 2.0 authorization code flow. Redirects the user to the GitLab authorization page\n          where they can grant access to the application.\n        path: /authorize\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: The application ID registered in GitLab.\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: The URI to redirect to after authorization.\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: Must be set to code for the authorization code flow.\n        - name: state\n          in: query\n          type: string\n          required: true\n          description: A random,\
  \ unguessable string used to protect against CSRF attacks.\n        - name: scope\n          in: query\n          type: string\n          required: false\n          description: Space-separated list of scopes to request.\n        - name: code_challenge\n          in: query\n          type: string\n          required: false\n          description: A Base64 URL-encoded SHA-256 hash of the code_verifier for PKCE.\n        - name: code_challenge_method\n          in: query\n          type: string\n          required: false\n          description: The method used to generate the code_challenge. Must be S256.\n        - name: root_namespace_id\n          in: query\n          type: integer\n          required: false\n          description: Limits group access token creation to a specific namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: authorize-device\n        method: POST\n        description:\
  \ Initiates the OAuth 2.0 device authorization grant flow for input-constrained devices.\n        path: /authorize_device\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            client_id: '{{tools.client_id}}'\n            scope: '{{tools.scope}}'\n    - name: tokens\n      path: /oauth\n      description: OAuth 2.0 token management endpoints for exchanging, refreshing, and revoking tokens.\n      operations:\n      - name: exchange-token\n        method: POST\n        description: Exchanges an authorization code, device code, or refresh token for an OAuth 2.0 access token.\n        path: /token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            grant_type:\
  \ '{{tools.grant_type}}'\n            client_id: '{{tools.client_id}}'\n            client_secret: '{{tools.client_secret}}'\n            code: '{{tools.code}}'\n            redirect_uri: '{{tools.redirect_uri}}'\n            code_verifier: '{{tools.code_verifier}}'\n            refresh_token: '{{tools.refresh_token}}'\n            device_code: '{{tools.device_code}}'\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n      - name: revoke-token\n        method: POST\n        description: Revokes an existing OAuth access token or refresh token.\n        path: /revoke\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            client_id: '{{tools.client_id}}'\n            client_secret: '{{tools.client_secret}}'\n            token: '{{tools.token}}'\n      - name: get-token-info\n        method:\
  \ GET\n        description: Returns information about the current OAuth access token, including scopes and expiration time.\n        path: /token/info\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-info\n      path: /oauth\n      description: OpenID Connect UserInfo endpoint for retrieving authenticated user profile information.\n      operations:\n      - name: get-user-info\n        method: GET\n        description: Returns profile information about the currently authenticated user based on the OAuth token's scopes.\n        path: /userinfo\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gitlab-auth-api\n    description: Unified REST API for GitLab OAuth 2.0 authentication and identity management.\n\
  \    resources:\n    - path: /v1/authorizations\n      name: authorizations\n      description: OAuth 2.0 authorization code flow initiation.\n      operations:\n      - method: GET\n        name: authorize-oauth\n        description: Initiate the OAuth 2.0 authorization code flow.\n        call: gitlab-oauth2.authorize-oauth\n        with:\n          client_id: rest.client_id\n          redirect_uri: rest.redirect_uri\n          response_type: rest.response_type\n          state: rest.state\n          scope: rest.scope\n          code_challenge: rest.code_challenge\n          code_challenge_method: rest.code_challenge_method\n          root_namespace_id: rest.root_namespace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/device-authorizations\n      name: device-authorizations\n      description: Device authorization grant flow for input-constrained devices.\n      operations:\n      - method: POST\n        name: authorize-device\n       \
  \ description: Initiate the device authorization grant flow.\n        call: gitlab-oauth2.authorize-device\n        with:\n          client_id: rest.client_id\n          scope: rest.scope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: OAuth token exchange and creation.\n      operations:\n      - method: POST\n        name: exchange-token\n        description: Exchange an authorization code, device code, or refresh token for an access token.\n        call: gitlab-oauth2.exchange-token\n        with:\n          grant_type: rest.grant_type\n          client_id: rest.client_id\n          client_secret: rest.client_secret\n          code: rest.code\n          redirect_uri: rest.redirect_uri\n          code_verifier: rest.code_verifier\n          refresh_token: rest.refresh_token\n          device_code: rest.device_code\n          username: rest.username\n          password: rest.password\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/token-revocations\n      name: token-revocations\n      description: Token revocation.\n      operations:\n      - method: POST\n        name: revoke-token\n        description: Revoke an OAuth access or refresh token.\n        call: gitlab-oauth2.revoke-token\n        with:\n          client_id: rest.client_id\n          client_secret: rest.client_secret\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/token-info\n      name: token-info\n      description: Token introspection and validation.\n      operations:\n      - method: GET\n        name: get-token-info\n        description: Get information about the current access token.\n        call: gitlab-oauth2.get-token-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-info\n      name: user-info\n      description: Authenticated user profile information.\n\
  \      operations:\n      - method: GET\n        name: get-user-info\n        description: Get profile information about the authenticated user.\n        call: gitlab-oauth2.get-user-info\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gitlab-auth-mcp\n    transport: http\n    description: MCP server for AI-assisted GitLab OAuth 2.0 authentication and identity management.\n    tools:\n    - name: authorize-oauth\n      description: Initiate the OAuth 2.0 authorization code flow with optional PKCE support.\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: gitlab-oauth2.authorize-oauth\n      with:\n        client_id: tools.client_id\n        redirect_uri: tools.redirect_uri\n        response_type: tools.response_type\n        state: tools.state\n        scope: tools.scope\n        code_challenge: tools.code_challenge\n        code_challenge_method: tools.code_challenge_method\n\
  \        root_namespace_id: tools.root_namespace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize-device\n      description: Initiate the device authorization grant flow for input-constrained devices.\n      hints:\n        readOnly: false\n        openWorld: true\n        idempotent: false\n      call: gitlab-oauth2.authorize-device\n      with:\n        client_id: tools.client_id\n        scope: tools.scope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exchange-token\n      description: Exchange an authorization code, device code, or refresh token for an access token.\n      hints:\n        readOnly: false\n        openWorld: true\n        idempotent: false\n      call: gitlab-oauth2.exchange-token\n      with:\n        grant_type: tools.grant_type\n        client_id: tools.client_id\n        client_secret: tools.client_secret\n        code: tools.code\n        redirect_uri: tools.redirect_uri\n        code_verifier:\
  \ tools.code_verifier\n        refresh_token: tools.refresh_token\n        device_code: tools.device_code\n        username: tools.username\n        password: tools.password\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-token\n      description: Revoke an existing OAuth access or refresh token.\n      hints:\n        readOnly: false\n        destructive: true\n        openWorld: true\n        idempotent: true\n      call: gitlab-oauth2.revoke-token\n      with:\n        client_id: tools.client_id\n        client_secret: tools.client_secret\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-token-info\n      description: Get information about the current OAuth access token including scopes and expiration.\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: gitlab-oauth2.get-token-info\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: get-user-info\n      description: Get profile information about the currently authenticated user.\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: gitlab-oauth2.get-user-info\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
