---
api_specs:
- filename: spring-security-oauth2-openapi.yml
  format: yaml
  label: spring-security-oauth2
  slug: spring-security-oauth2
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spring-security/refs/heads/main/openapi/spring-security-oauth2-openapi.yml
categories: []
consumed_apis:
- spring-security-oauth2
description: Workflow capability for Spring Security OAuth2 and OpenID Connect operations. Provides unified identity verification, token management, and access control operations. Used by platform admins, security engineers, and application developers working with Spring Security-backed APIs.
layout: capability
name: Spring Security - Identity and Access Management
operations:
- description: Issue an OAuth2 access token using the specified grant type
  method: POST
  name: issue-access-token
  path: /v1/tokens
- description: Validate an OAuth2 token and retrieve its metadata
  method: POST
  name: validate-token
  path: /v1/tokens/introspect
- description: Revoke an active access or refresh token
  method: POST
  name: revoke-token
  path: /v1/tokens/revoke
- description: Retrieve JWKS for JWT signature verification
  method: GET
  name: get-signing-keys
  path: /v1/jwks
- description: Get OIDC claims for the authenticated user
  method: GET
  name: get-user-identity
  path: /v1/userinfo
- description: Retrieve OpenID Connect provider configuration
  method: GET
  name: get-provider-config
  path: /v1/discovery
personas: []
provider_name: Spring Security
provider_slug: spring-security
search_terms:
- security
- validate an oauth2 access or refresh token and retrieve its claims and status
- openid connect
- revoke token
- get provider config
- jwt
- token revocation
- get signing keys
- issue access token
- authenticated user identity claims
- validate token
- oidc provider configuration discovery
- public signing key set for jwt verification
- revoke an oauth2 token to prevent further use
- retrieve openid connect provider configuration
- issue an oauth2 access token using the specified grant type
- retrieve jwks for jwt signature verification
- get user claims
- oauth2
- revoke an active access or refresh token
- retrieve openid connect identity claims for the currently authenticated user
- retrieve the json web key set for verifying jwt-format tokens
- get oidc claims for the authenticated user
- issue an oauth2 access token using authorization_code, client_credentials, or refresh_token grant
- discover oidc provider
- saml
- authentication
- authorization
- token validation and metadata retrieval
- validate an oauth2 token and retrieve its metadata
- get user identity
- oauth2 access token management
- spring
- spring framework
- retrieve openid connect provider metadata for automated client configuration
- identity
- java
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spring Security - Identity and Access Management\"\n  description: >-\n    Workflow capability for Spring Security OAuth2 and OpenID Connect operations.\n    Provides unified identity verification, token management, and access control\n    operations. Used by platform admins, security engineers, and application\n    developers working with Spring Security-backed APIs.\n  tags:\n    - Authentication\n    - Authorization\n    - Identity\n    - JWT\n    - OAuth2\n    - OpenID Connect\n    - Security\n    - Spring\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPRING_SECURITY_BASE_URL: SPRING_SECURITY_BASE_URL\n      SPRING_SECURITY_CLIENT_ID: SPRING_SECURITY_CLIENT_ID\n      SPRING_SECURITY_CLIENT_SECRET: SPRING_SECURITY_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: spring-security-oauth2\n      location: ./shared/spring-security-oauth2.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: identity-and-access-api\n      description: \"Unified REST API for Spring Security OAuth2 and OIDC operations.\"\n      resources:\n        - path: /v1/tokens\n          name: tokens\n          description: \"OAuth2 access token management\"\n          operations:\n            - method: POST\n              name: issue-access-token\n              description: \"Issue an OAuth2 access token using the specified grant type\"\n              call: \"spring-security-oauth2.issue-token\"\n              with:\n                grant_type: \"rest.grant_type\"\n                code: \"rest.code\"\n                refresh_token: \"rest.refresh_token\"\n                scope: \"rest.scope\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens/introspect\n          name: token-introspection\n          description: \"Token validation and metadata retrieval\"\n          operations:\n\
  \            - method: POST\n              name: validate-token\n              description: \"Validate an OAuth2 token and retrieve its metadata\"\n              call: \"spring-security-oauth2.introspect-token\"\n              with:\n                token: \"rest.token\"\n                token_type_hint: \"rest.token_type_hint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens/revoke\n          name: token-revocation\n          description: \"Token revocation\"\n          operations:\n            - method: POST\n              name: revoke-token\n              description: \"Revoke an active access or refresh token\"\n              call: \"spring-security-oauth2.revoke-token\"\n              with:\n                token: \"rest.token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jwks\n          name: signing-keys\n          description:\
  \ \"Public signing key set for JWT verification\"\n          operations:\n            - method: GET\n              name: get-signing-keys\n              description: \"Retrieve JWKS for JWT signature verification\"\n              call: \"spring-security-oauth2.get-jwks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/userinfo\n          name: user-identity\n          description: \"Authenticated user identity claims\"\n          operations:\n            - method: GET\n              name: get-user-identity\n              description: \"Get OIDC claims for the authenticated user\"\n              call: \"spring-security-oauth2.get-userinfo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/discovery\n          name: provider-discovery\n          description: \"OIDC provider configuration discovery\"\n          operations:\n            - method:\
  \ GET\n              name: get-provider-config\n              description: \"Retrieve OpenID Connect provider configuration\"\n              call: \"spring-security-oauth2.get-oidc-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: identity-and-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted identity and access management with Spring Security.\"\n      tools:\n        - name: issue-access-token\n          description: \"Issue an OAuth2 access token using authorization_code, client_credentials, or refresh_token grant\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spring-security-oauth2.issue-token\"\n          with:\n            grant_type: \"tools.grant_type\"\n            code: \"tools.code\"\n            refresh_token: \"tools.refresh_token\"\n            scope: \"tools.scope\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-token\n          description: \"Validate an OAuth2 access or refresh token and retrieve its claims and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spring-security-oauth2.introspect-token\"\n          with:\n            token: \"tools.token\"\n            token_type_hint: \"tools.token_type_hint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: revoke-token\n          description: \"Revoke an OAuth2 token to prevent further use\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"spring-security-oauth2.revoke-token\"\n          with:\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-signing-keys\n\
  \          description: \"Retrieve the JSON Web Key Set for verifying JWT-format tokens\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-security-oauth2.get-jwks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-claims\n          description: \"Retrieve OpenID Connect identity claims for the currently authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spring-security-oauth2.get-userinfo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-oidc-provider\n          description: \"Retrieve OpenID Connect provider metadata for automated client configuration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-security-oauth2.get-oidc-config\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-security/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Authentication
- Authorization
- Identity
- JWT
- OAuth2
- OpenID Connect
- Security
- Spring
tools:
- description: Issue an OAuth2 access token using authorization_code, client_credentials, or refresh_token grant
  hints:
    destructive: false
    readOnly: false
  name: issue-access-token
- description: Validate an OAuth2 access or refresh token and retrieve its claims and status
  hints:
    openWorld: false
    readOnly: true
  name: validate-token
- description: Revoke an OAuth2 token to prevent further use
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-token
- description: Retrieve the JSON Web Key Set for verifying JWT-format tokens
  hints:
    openWorld: true
    readOnly: true
  name: get-signing-keys
- description: Retrieve OpenID Connect identity claims for the currently authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: get-user-claims
- description: Retrieve OpenID Connect provider metadata for automated client configuration
  hints:
    openWorld: true
    readOnly: true
  name: discover-oidc-provider
---
