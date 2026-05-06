---
categories: []
consumed_apis: []
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
- get provider config
- get user claims
- issue an oauth2 access token using authorization_code, client_credentials, or refresh_token grant
- retrieve openid connect provider configuration
- identity
- oauth2
- java
- issue access token
- get signing keys
- security
- oauth2 access token management
- retrieve openid connect identity claims for the currently authenticated user
- get oidc claims for the authenticated user
- saml
- oidc provider configuration discovery
- token validation and metadata retrieval
- validate an oauth2 access or refresh token and retrieve its claims and status
- validate an oauth2 token and retrieve its metadata
- authorization
- retrieve openid connect provider metadata for automated client configuration
- authentication
- retrieve the json web key set for verifying jwt-format tokens
- spring framework
- retrieve jwks for jwt signature verification
- revoke an oauth2 token to prevent further use
- issue an oauth2 access token using the specified grant type
- public signing key set for jwt verification
- authenticated user identity claims
- get user identity
- validate token
- spring
- jwt
- revoke token
- token revocation
- discover oidc provider
- openid connect
- revoke an active access or refresh token
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Security - Identity and Access Management\n  description: Workflow capability for Spring Security OAuth2 and OpenID Connect operations. Provides unified identity verification,\n    token management, and access control operations. Used by platform admins, security engineers, and application developers\n    working with Spring Security-backed APIs.\n  tags:\n  - Authentication\n  - Authorization\n  - Identity\n  - JWT\n  - OAuth2\n  - OpenID Connect\n  - Security\n  - Spring\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_SECURITY_BASE_URL: SPRING_SECURITY_BASE_URL\n    SPRING_SECURITY_CLIENT_ID: SPRING_SECURITY_CLIENT_ID\n    SPRING_SECURITY_CLIENT_SECRET: SPRING_SECURITY_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-security-oauth2\n    baseUri: '{{env.SPRING_SECURITY_BASE_URL}}'\n    description: Spring Security OAuth2 protocol endpoints\n    authentication:\n\
  \      type: basic\n      username: '{{env.SPRING_SECURITY_CLIENT_ID}}'\n      password: '{{env.SPRING_SECURITY_CLIENT_SECRET}}'\n    resources:\n    - name: token\n      path: /oauth2/token\n      description: OAuth2 token issuance endpoint\n      operations:\n      - name: issue-token\n        method: POST\n        description: Issue access tokens for all supported grant types\n        inputParameters:\n        - name: grant_type\n          in: body\n          type: string\n          required: true\n        - name: code\n          in: body\n          type: string\n          required: false\n        - name: refresh_token\n          in: body\n          type: string\n          required: false\n        - name: scope\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: introspect\n      path: /oauth2/introspect\n      description: Token\
  \ introspection endpoint\n      operations:\n      - name: introspect-token\n        method: POST\n        description: Validate a token and return its metadata\n        inputParameters:\n        - name: token\n          in: body\n          type: string\n          required: true\n        - name: token_type_hint\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revoke\n      path: /oauth2/revoke\n      description: Token revocation endpoint\n      operations:\n      - name: revoke-token\n        method: POST\n        description: Revoke an access or refresh token\n        inputParameters:\n        - name: token\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jwks\n    \
  \  path: /oauth2/jwks\n      description: JSON Web Key Set endpoint\n      operations:\n      - name: get-jwks\n        method: GET\n        description: Retrieve public keys for JWT verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: userinfo\n      path: /userinfo\n      description: OpenID Connect UserInfo endpoint\n      operations:\n      - name: get-userinfo\n        method: GET\n        description: Get claims about the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discovery\n      path: /.well-known/openid-configuration\n      description: OpenID Connect discovery endpoint\n      operations:\n      - name: get-oidc-config\n        method: GET\n        description: Get OpenID Connect provider configuration\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: identity-and-access-api\n    description: Unified REST API for Spring Security OAuth2 and OIDC operations.\n    resources:\n    - path: /v1/tokens\n      name: tokens\n      description: OAuth2 access token management\n      operations:\n      - method: POST\n        name: issue-access-token\n        description: Issue an OAuth2 access token using the specified grant type\n        call: spring-security-oauth2.issue-token\n        with:\n          grant_type: rest.grant_type\n          code: rest.code\n          refresh_token: rest.refresh_token\n          scope: rest.scope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens/introspect\n      name: token-introspection\n      description: Token validation and metadata retrieval\n      operations:\n      - method: POST\n        name: validate-token\n        description:\
  \ Validate an OAuth2 token and retrieve its metadata\n        call: spring-security-oauth2.introspect-token\n        with:\n          token: rest.token\n          token_type_hint: rest.token_type_hint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens/revoke\n      name: token-revocation\n      description: Token revocation\n      operations:\n      - method: POST\n        name: revoke-token\n        description: Revoke an active access or refresh token\n        call: spring-security-oauth2.revoke-token\n        with:\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jwks\n      name: signing-keys\n      description: Public signing key set for JWT verification\n      operations:\n      - method: GET\n        name: get-signing-keys\n        description: Retrieve JWKS for JWT signature verification\n        call: spring-security-oauth2.get-jwks\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/userinfo\n      name: user-identity\n      description: Authenticated user identity claims\n      operations:\n      - method: GET\n        name: get-user-identity\n        description: Get OIDC claims for the authenticated user\n        call: spring-security-oauth2.get-userinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/discovery\n      name: provider-discovery\n      description: OIDC provider configuration discovery\n      operations:\n      - method: GET\n        name: get-provider-config\n        description: Retrieve OpenID Connect provider configuration\n        call: spring-security-oauth2.get-oidc-config\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: identity-and-access-mcp\n    transport: http\n    description: MCP server for AI-assisted identity and access management with Spring Security.\n \
  \   tools:\n    - name: issue-access-token\n      description: Issue an OAuth2 access token using authorization_code, client_credentials, or refresh_token grant\n      hints:\n        readOnly: false\n        destructive: false\n      call: spring-security-oauth2.issue-token\n      with:\n        grant_type: tools.grant_type\n        code: tools.code\n        refresh_token: tools.refresh_token\n        scope: tools.scope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-token\n      description: Validate an OAuth2 access or refresh token and retrieve its claims and status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-security-oauth2.introspect-token\n      with:\n        token: tools.token\n        token_type_hint: tools.token_type_hint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-token\n      description: Revoke an OAuth2 token to prevent further use\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: spring-security-oauth2.revoke-token\n      with:\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-signing-keys\n      description: Retrieve the JSON Web Key Set for verifying JWT-format tokens\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-security-oauth2.get-jwks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-claims\n      description: Retrieve OpenID Connect identity claims for the currently authenticated user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-security-oauth2.get-userinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-oidc-provider\n      description: Retrieve OpenID Connect provider metadata for automated client configuration\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: spring-security-oauth2.get-oidc-config\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
