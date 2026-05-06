---
categories: []
consumed_apis: []
description: OpenAPI specification for OAuth 2.0 authorization server endpoints as defined in RFC 6749 (The OAuth 2.0 Authorization Framework) and RFC 6750 (Bearer Token Usage). Covers the token endpoint, authorization endpoint, and token revocation endpoint (RFC 7009).
layout: capability
name: OAuth 2.0 Authorization Server
operations:
- description: Authorization Endpoint
  method: GET
  name: authorize
  path: /authorize
- description: Token Endpoint
  method: POST
  name: requesttoken
  path: /token
- description: Token Revocation Endpoint
  method: POST
  name: revoketoken
  path: /revoke
personas: []
provider_name: OAuth
provider_slug: oauth
search_terms:
- token revocation endpoint
- authorization endpoint
- api
- oauth
- revoketoken
- authorization
- security
- token endpoint
- tokens
- requesttoken
- authorize
- access control
slug: oauth-capability
source_filename: oauth-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OAuth 2.0 Authorization Server\n  description: OpenAPI specification for OAuth 2.0 authorization server endpoints as defined in RFC 6749 (The OAuth 2.0 Authorization\n    Framework) and RFC 6750 (Bearer Token Usage). Covers the token endpoint, authorization endpoint, and token revocation\n    endpoint (RFC 7009).\n  tags:\n  - Oauth\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oauth\n    baseUri: https://authorization-server.example.com\n    description: OAuth 2.0 Authorization Server HTTP API.\n    authentication:\n      type: basic\n      username: '{{OAUTH_USERNAME}}'\n      password: '{{OAUTH_PASSWORD}}'\n    resources:\n    - name: authorize\n      path: /authorize\n      operations:\n      - name: authorize\n        method: GET\n        description: Authorization Endpoint\n        inputParameters:\n        - name: response_type\n          in: query\n       \
  \   type: string\n          required: true\n          description: The value MUST be \"code\" for requesting an authorization code or \"token\" for requesting an access token\n            (implicit grant).\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: The client identifier issued to the client during registration.\n        - name: redirect_uri\n          in: query\n          type: string\n          description: The URI to which the authorization server will redirect the user-agent after authorization is granted\n            or denied.\n        - name: scope\n          in: query\n          type: string\n          description: The scope of the access request as a space-delimited list of values.\n        - name: state\n          in: query\n          type: string\n          description: An opaque value used by the client to maintain state between the request and callback. Used to prevent\n            cross-site request\
  \ forgery.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token\n      path: /token\n      operations:\n      - name: requesttoken\n        method: POST\n        description: Token Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revoke\n      path: /revoke\n      operations:\n      - name: revoketoken\n        method: POST\n        description: Token Revocation Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oauth-rest\n    description: REST adapter for OAuth 2.0 Authorization Server.\n    resources:\n    - path: /authorize\n      name: authorize\n      operations:\n      - method: GET\n        name: authorize\n        description: Authorization Endpoint\n\
  \        call: oauth.authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /token\n      name: requesttoken\n      operations:\n      - method: POST\n        name: requesttoken\n        description: Token Endpoint\n        call: oauth.requesttoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /revoke\n      name: revoketoken\n      operations:\n      - method: POST\n        name: revoketoken\n        description: Token Revocation Endpoint\n        call: oauth.revoketoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oauth-mcp\n    transport: http\n    description: MCP adapter for OAuth 2.0 Authorization Server for AI agent use.\n    tools:\n    - name: authorize\n      description: Authorization Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oauth.authorize\n    \
  \  with:\n        response_type: tools.response_type\n        client_id: tools.client_id\n        redirect_uri: tools.redirect_uri\n        scope: tools.scope\n        state: tools.state\n      inputParameters:\n      - name: response_type\n        type: string\n        description: The value MUST be \"code\" for requesting an authorization code or \"token\" for requesting an access token\n          (implicit grant).\n        required: true\n      - name: client_id\n        type: string\n        description: The client identifier issued to the client during registration.\n        required: true\n      - name: redirect_uri\n        type: string\n        description: The URI to which the authorization server will redirect the user-agent after authorization is granted\n          or denied.\n      - name: scope\n        type: string\n        description: The scope of the access request as a space-delimited list of values.\n      - name: state\n        type: string\n        description: An\
  \ opaque value used by the client to maintain state between the request and callback. Used to prevent\n          cross-site request forgery.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requesttoken\n      description: Token Endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oauth.requesttoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoketoken\n      description: Token Revocation Endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oauth.revoketoken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OAUTH_USERNAME: OAUTH_USERNAME\n    OAUTH_PASSWORD: OAUTH_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oauth/refs/heads/main/capabilities/oauth-capability.yaml
tags:
- Oauth
- API
tools:
- description: Authorization Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: authorize
- description: Token Endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requesttoken
- description: Token Revocation Endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revoketoken
---
