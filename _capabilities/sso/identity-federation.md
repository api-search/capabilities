---
categories: []
consumed_apis:
- oidc-authentication
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
- single sign-on
- openid provider configuration discovery
- saml
- security
- exchange token
- get provider signing keys
- json web key set for signature verification
- get openid provider configuration metadata
- get authenticated user profile
- get user info
- authentication
- exchange an oidc/oauth 2.0 authorization code for access token, id token, and refresh token
- get discovery
- exchange an authorization code or refresh token for access and id tokens
- identity federation
- discover oidc provider configuration
- oauth
- get the authenticated user's identity claims from the userinfo endpoint
- exchange authorization code
- retrieve openid provider configuration metadata including endpoints, supported features, and algorithms
- identity
- sso
- authorization
- get public keys for verifying id token signatures
- retrieve the openid provider's json web key set (jwks) for verifying id token signatures
- token exchange and refresh
- oidc
- authenticated user profile claims
- retrieve the authenticated user's identity claims (name, email, sub, etc.) from the oidc userinfo endpoint
- get jwks
slug: identity-federation
source_filename: identity-federation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SSO Identity Federation\"\n  description: >-\n    Workflow capability for Single Sign-On identity federation using OpenID\n    Connect (OIDC). Enables applications to integrate SSO authentication flows\n    including authorization code exchange, user profile retrieval, provider\n    discovery, and JWKS key management. Designed for developers and platform\n    engineers implementing federated identity across enterprise applications.\n  tags:\n    - SSO\n    - Identity Federation\n    - OIDC\n    - Authentication\n    - OAuth\n    - Security\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      OIDC_CLIENT_ID: OIDC_CLIENT_ID\n      OIDC_CLIENT_SECRET: OIDC_CLIENT_SECRET\n      OIDC_ACCESS_TOKEN: OIDC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: oidc-authentication\n      location: ./shared/oidc-authentication.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n     \
  \ namespace: identity-federation-api\n      description: \"Unified REST API for SSO identity federation workflows.\"\n      resources:\n        - path: /v1/token\n          name: token\n          description: \"Token exchange and refresh\"\n          operations:\n            - method: POST\n              name: exchange-token\n              description: \"Exchange an authorization code or refresh token for access and ID tokens\"\n              call: \"oidc-authentication.exchange-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/userinfo\n          name: userinfo\n          description: \"Authenticated user profile claims\"\n          operations:\n            - method: GET\n              name: get-user-info\n              description: \"Get the authenticated user's identity claims from the UserInfo endpoint\"\n              call: \"oidc-authentication.get-user-info\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jwks\n          name: jwks\n          description: \"JSON Web Key Set for signature verification\"\n          operations:\n            - method: GET\n              name: get-jwks\n              description: \"Get public keys for verifying ID token signatures\"\n              call: \"oidc-authentication.get-jwks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/discovery\n          name: discovery\n          description: \"OpenID Provider configuration discovery\"\n          operations:\n            - method: GET\n              name: get-discovery\n              description: \"Get OpenID Provider configuration metadata\"\n              call: \"oidc-authentication.get-oidc-discovery\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ identity-federation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SSO identity federation and token management.\"\n      tools:\n        - name: exchange-authorization-code\n          description: \"Exchange an OIDC/OAuth 2.0 authorization code for access token, ID token, and refresh token\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"oidc-authentication.exchange-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-authenticated-user-profile\n          description: \"Retrieve the authenticated user's identity claims (name, email, sub, etc.) from the OIDC UserInfo endpoint\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"oidc-authentication.get-user-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ get-provider-signing-keys\n          description: \"Retrieve the OpenID Provider's JSON Web Key Set (JWKS) for verifying ID token signatures\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"oidc-authentication.get-jwks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-oidc-provider-configuration\n          description: \"Retrieve OpenID Provider configuration metadata including endpoints, supported features, and algorithms\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"oidc-authentication.get-oidc-discovery\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
