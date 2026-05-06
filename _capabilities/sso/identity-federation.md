---
categories: []
consumed_apis: []
description: Workflow capability for Single Sign-On identity federation using OpenID Connect (OIDC). Enables applications to integrate SSO authentication flows including authorization code exchange, user profile retrieval, provider discovery, and JWKS key management. Designed for developers and platform engineers implementing federated identity across enterprise applications.
layout: capability
name: SSO Identity Federation
operations:
- description: Exchange an authorization code or refresh token for access and ID tokens
  method: POST
  name: exchange-token
  path: /v1/token
- description: Get the authenticated user's identity claims from the UserInfo endpoint
  method: GET
  name: get-user-info
  path: /v1/userinfo
- description: Get public keys for verifying ID token signatures
  method: GET
  name: get-jwks
  path: /v1/jwks
- description: Get OpenID Provider configuration metadata
  method: GET
  name: get-discovery
  path: /v1/discovery
personas: []
provider_name: SSO
provider_slug: sso
search_terms:
- get public keys for verifying id token signatures
- identity
- get jwks
- openid provider configuration discovery
- get openid provider configuration metadata
- exchange an oidc/oauth 2.0 authorization code for access token, id token, and refresh token
- authenticated user profile claims
- exchange token
- exchange an authorization code or refresh token for access and id tokens
- oauth
- security
- get authenticated user profile
- retrieve the authenticated user's identity claims (name, email, sub, etc.) from the oidc userinfo endpoint
- get user info
- retrieve openid provider configuration metadata including endpoints, supported features, and algorithms
- saml
- sso
- get the authenticated user's identity claims from the userinfo endpoint
- token exchange and refresh
- exchange authorization code
- json web key set for signature verification
- single sign-on
- authorization
- identity federation
- retrieve the openid provider's json web key set (jwks) for verifying id token signatures
- authentication
- discover oidc provider configuration
- get discovery
- get provider signing keys
- oidc
slug: identity-federation
source_filename: identity-federation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SSO Identity Federation\n  description: Workflow capability for Single Sign-On identity federation using OpenID Connect (OIDC). Enables applications\n    to integrate SSO authentication flows including authorization code exchange, user profile retrieval, provider discovery,\n    and JWKS key management. Designed for developers and platform engineers implementing federated identity across enterprise\n    applications.\n  tags:\n  - SSO\n  - Identity Federation\n  - OIDC\n  - Authentication\n  - OAuth\n  - Security\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OIDC_CLIENT_ID: OIDC_CLIENT_ID\n    OIDC_CLIENT_SECRET: OIDC_CLIENT_SECRET\n    OIDC_ACCESS_TOKEN: OIDC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: oidc-authentication\n    baseUri: https://your-idp.example.com\n    description: OpenID Connect authentication and token endpoints\n    resources:\n    - name: token\n\
  \      path: /token\n      description: Token endpoint for code exchange and refresh\n      operations:\n      - name: exchange-token\n        method: POST\n        description: Exchange authorization code for access token, ID token, and refresh token\n        body:\n          type: form\n          data:\n            grant_type: '{{tools.grant_type}}'\n            code: '{{tools.code}}'\n            redirect_uri: '{{tools.redirect_uri}}'\n            client_id: '{{OIDC_CLIENT_ID}}'\n            client_secret: '{{OIDC_CLIENT_SECRET}}'\n            code_verifier: '{{tools.code_verifier}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: userinfo\n      path: /userinfo\n      description: UserInfo endpoint for retrieving authenticated user claims\n      operations:\n      - name: get-user-info\n        method: GET\n        description: Get the authenticated user's profile claims\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jwks\n      path: /jwks\n      description: JWKS endpoint for public key retrieval\n      operations:\n      - name: get-jwks\n        method: GET\n        description: Get JSON Web Key Set for ID token signature verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discovery\n      path: /.well-known/openid-configuration\n      description: OpenID Provider discovery metadata\n      operations:\n      - name: get-oidc-discovery\n        method: GET\n        description: Get OpenID Provider configuration metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: identity-federation-api\n    description: Unified REST API for SSO identity federation\
  \ workflows.\n    resources:\n    - path: /v1/token\n      name: token\n      description: Token exchange and refresh\n      operations:\n      - method: POST\n        name: exchange-token\n        description: Exchange an authorization code or refresh token for access and ID tokens\n        call: oidc-authentication.exchange-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/userinfo\n      name: userinfo\n      description: Authenticated user profile claims\n      operations:\n      - method: GET\n        name: get-user-info\n        description: Get the authenticated user's identity claims from the UserInfo endpoint\n        call: oidc-authentication.get-user-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jwks\n      name: jwks\n      description: JSON Web Key Set for signature verification\n      operations:\n      - method: GET\n        name: get-jwks\n        description: Get public keys\
  \ for verifying ID token signatures\n        call: oidc-authentication.get-jwks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/discovery\n      name: discovery\n      description: OpenID Provider configuration discovery\n      operations:\n      - method: GET\n        name: get-discovery\n        description: Get OpenID Provider configuration metadata\n        call: oidc-authentication.get-oidc-discovery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: identity-federation-mcp\n    transport: http\n    description: MCP server for AI-assisted SSO identity federation and token management.\n    tools:\n    - name: exchange-authorization-code\n      description: Exchange an OIDC/OAuth 2.0 authorization code for access token, ID token, and refresh token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oidc-authentication.exchange-token\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-authenticated-user-profile\n      description: Retrieve the authenticated user's identity claims (name, email, sub, etc.) from the OIDC UserInfo endpoint\n      hints:\n        readOnly: true\n        idempotent: true\n      call: oidc-authentication.get-user-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-provider-signing-keys\n      description: Retrieve the OpenID Provider's JSON Web Key Set (JWKS) for verifying ID token signatures\n      hints:\n        readOnly: true\n        idempotent: true\n      call: oidc-authentication.get-jwks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-oidc-provider-configuration\n      description: Retrieve OpenID Provider configuration metadata including endpoints, supported features, and algorithms\n      hints:\n        readOnly: true\n        idempotent: true\n      call: oidc-authentication.get-oidc-discovery\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sso/refs/heads/main/capabilities/identity-federation.yaml
tags:
- SSO
- Identity Federation
- OIDC
- Authentication
- OAuth
- Security
tools:
- description: Exchange an OIDC/OAuth 2.0 authorization code for access token, ID token, and refresh token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exchange-authorization-code
- description: Retrieve the authenticated user's identity claims (name, email, sub, etc.) from the OIDC UserInfo endpoint
  hints:
    idempotent: true
    readOnly: true
  name: get-authenticated-user-profile
- description: Retrieve the OpenID Provider's JSON Web Key Set (JWKS) for verifying ID token signatures
  hints:
    idempotent: true
    readOnly: true
  name: get-provider-signing-keys
- description: Retrieve OpenID Provider configuration metadata including endpoints, supported features, and algorithms
  hints:
    idempotent: true
    readOnly: true
  name: discover-oidc-provider-configuration
---
