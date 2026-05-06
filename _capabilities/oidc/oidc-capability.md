---
categories: []
consumed_apis: []
description: OpenID Connect (OIDC) is an identity layer built on top of the OAuth 2.0 protocol. It allows clients to verify the identity of end-users based on the authentication performed by an authorization server, and to obtain basic profile information about the end-user in an interoperable and REST-like manner. This specification covers the core OIDC endpoints including discovery, token, userinfo, and JWKS.
layout: capability
name: OpenID Connect API
operations:
- description: OpenID Connect Discovery
  method: GET
  name: getdiscovery
  path: /.well-known/openid-configuration
- description: Authorization Endpoint
  method: GET
  name: authorize
  path: /authorize
- description: Token Endpoint
  method: POST
  name: gettoken
  path: /token
- description: UserInfo Endpoint
  method: GET
  name: getuserinfo
  path: /userinfo
- description: UserInfo Endpoint (POST)
  method: POST
  name: postuserinfo
  path: /userinfo
- description: JSON Web Key Set Endpoint
  method: GET
  name: getjwks
  path: /.well-known/jwks.json
- description: End Session Endpoint
  method: GET
  name: endsession
  path: /end-session
personas: []
provider_name: OIDC
provider_slug: oidc
search_terms:
- identity
- getuserinfo
- token endpoint
- authorize
- postuserinfo
- oauth
- getdiscovery
- api
- authorization endpoint
- endsession
- openid connect discovery
- authentication
- end session endpoint
- userinfo endpoint (post)
- oidc
- jwt
- openid connect
- json web key set endpoint
- userinfo endpoint
- getjwks
- gettoken
slug: oidc-capability
source_filename: oidc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenID Connect API\n  description: OpenID Connect (OIDC) is an identity layer built on top of the OAuth 2.0 protocol. It allows clients to verify\n    the identity of end-users based on the authentication performed by an authorization server, and to obtain basic profile\n    information about the end-user in an interoperable and REST-like manner. This specification covers the core OIDC endpoints\n    including discovery, token, userinfo, and JWKS.\n  tags:\n  - Oidc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oidc\n    baseUri: https://example.com\n    description: OpenID Connect API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OIDC_TOKEN}}'\n    resources:\n    - name: well-known-openid-configuration\n      path: /.well-known/openid-configuration\n      operations:\n      - name: getdiscovery\n        method: GET\n        description: OpenID\
  \ Connect Discovery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorize\n      path: /authorize\n      operations:\n      - name: authorize\n        method: GET\n        description: Authorization Endpoint\n        inputParameters:\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: The value must include 'code' for the Authorization Code Flow, 'id_token' for the Implicit Flow, or\n            'code id_token' for the Hybrid Flow.\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: The client identifier issued during registration.\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: The redirection URI to which the response will be sent. Must exactly match one of the redirection\
  \ URIs\n            registered for the client.\n        - name: scope\n          in: query\n          type: string\n          required: true\n          description: Space-delimited list of scopes. Must include 'openid' to indicate an OIDC request. May also include\n            'profile', 'email', 'address', and 'phone'.\n        - name: state\n          in: query\n          type: string\n          description: An opaque value used by the client to maintain state between the request and callback. Recommended\n            for CSRF protection.\n        - name: nonce\n          in: query\n          type: string\n          description: A string value used to associate a client session with an ID Token and to mitigate replay attacks.\n            Required for implicit flow.\n        - name: prompt\n          in: query\n          type: string\n          description: Space-delimited list of values that specifies whether the authorization server prompts the end-user\n            for reauthentication\
  \ and consent.\n        - name: login_hint\n          in: query\n          type: string\n          description: A hint to the authorization server about the login identifier the end-user might use.\n        - name: acr_values\n          in: query\n          type: string\n          description: Requested Authentication Context Class Reference values.\n        - name: code_challenge\n          in: query\n          type: string\n          description: PKCE code challenge derived from the code verifier.\n        - name: code_challenge_method\n          in: query\n          type: string\n          description: Code challenge method used to derive the code challenge.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token\n      path: /token\n      operations:\n      - name: gettoken\n        method: POST\n        description: Token Endpoint\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: userinfo\n      path: /userinfo\n      operations:\n      - name: getuserinfo\n        method: GET\n        description: UserInfo Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postuserinfo\n        method: POST\n        description: UserInfo Endpoint (POST)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: well-known-jwks-json\n      path: /.well-known/jwks.json\n      operations:\n      - name: getjwks\n        method: GET\n        description: JSON Web Key Set Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: end-session\n      path: /end-session\n      operations:\n      - name: endsession\n        method: GET\n   \
  \     description: End Session Endpoint\n        inputParameters:\n        - name: id_token_hint\n          in: query\n          type: string\n          description: The ID token previously issued to the client.\n        - name: post_logout_redirect_uri\n          in: query\n          type: string\n          description: The URI to redirect to after logout.\n        - name: state\n          in: query\n          type: string\n          description: Opaque value for maintaining state between request and callback.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oidc-rest\n    description: REST adapter for OpenID Connect API.\n    resources:\n    - path: /.well-known/openid-configuration\n      name: getdiscovery\n      operations:\n      - method: GET\n        name: getdiscovery\n        description: OpenID Connect Discovery\n        call: oidc.getdiscovery\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authorize\n      name: authorize\n      operations:\n      - method: GET\n        name: authorize\n        description: Authorization Endpoint\n        call: oidc.authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /token\n      name: gettoken\n      operations:\n      - method: POST\n        name: gettoken\n        description: Token Endpoint\n        call: oidc.gettoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /userinfo\n      name: getuserinfo\n      operations:\n      - method: GET\n        name: getuserinfo\n        description: UserInfo Endpoint\n        call: oidc.getuserinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /userinfo\n      name: postuserinfo\n      operations:\n      - method: POST\n        name: postuserinfo\n        description: UserInfo Endpoint\
  \ (POST)\n        call: oidc.postuserinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /.well-known/jwks.json\n      name: getjwks\n      operations:\n      - method: GET\n        name: getjwks\n        description: JSON Web Key Set Endpoint\n        call: oidc.getjwks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /end-session\n      name: endsession\n      operations:\n      - method: GET\n        name: endsession\n        description: End Session Endpoint\n        call: oidc.endsession\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oidc-mcp\n    transport: http\n    description: MCP adapter for OpenID Connect API for AI agent use.\n    tools:\n    - name: getdiscovery\n      description: OpenID Connect Discovery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oidc.getdiscovery\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize\n      description: Authorization Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oidc.authorize\n      with:\n        response_type: tools.response_type\n        client_id: tools.client_id\n        redirect_uri: tools.redirect_uri\n        scope: tools.scope\n        state: tools.state\n        nonce: tools.nonce\n        prompt: tools.prompt\n        login_hint: tools.login_hint\n        acr_values: tools.acr_values\n        code_challenge: tools.code_challenge\n        code_challenge_method: tools.code_challenge_method\n      inputParameters:\n      - name: response_type\n        type: string\n        description: The value must include 'code' for the Authorization Code Flow, 'id_token' for the Implicit Flow, or 'code\n          id_token' for the Hybrid Flow.\n        required: true\n      - name: client_id\n        type: string\n\
  \        description: The client identifier issued during registration.\n        required: true\n      - name: redirect_uri\n        type: string\n        description: The redirection URI to which the response will be sent. Must exactly match one of the redirection URIs\n          registered for the client.\n        required: true\n      - name: scope\n        type: string\n        description: Space-delimited list of scopes. Must include 'openid' to indicate an OIDC request. May also include 'profile',\n          'email', 'address', and 'phone'.\n        required: true\n      - name: state\n        type: string\n        description: An opaque value used by the client to maintain state between the request and callback. Recommended for\n          CSRF protection.\n      - name: nonce\n        type: string\n        description: A string value used to associate a client session with an ID Token and to mitigate replay attacks. Required\n          for implicit flow.\n      - name: prompt\n\
  \        type: string\n        description: Space-delimited list of values that specifies whether the authorization server prompts the end-user for\n          reauthentication and consent.\n      - name: login_hint\n        type: string\n        description: A hint to the authorization server about the login identifier the end-user might use.\n      - name: acr_values\n        type: string\n        description: Requested Authentication Context Class Reference values.\n      - name: code_challenge\n        type: string\n        description: PKCE code challenge derived from the code verifier.\n      - name: code_challenge_method\n        type: string\n        description: Code challenge method used to derive the code challenge.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettoken\n      description: Token Endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oidc.gettoken\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getuserinfo\n      description: UserInfo Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oidc.getuserinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postuserinfo\n      description: UserInfo Endpoint (POST)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oidc.postuserinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjwks\n      description: JSON Web Key Set Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oidc.getjwks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: endsession\n      description: End Session Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oidc.endsession\n\
  \      with:\n        id_token_hint: tools.id_token_hint\n        post_logout_redirect_uri: tools.post_logout_redirect_uri\n        state: tools.state\n      inputParameters:\n      - name: id_token_hint\n        type: string\n        description: The ID token previously issued to the client.\n      - name: post_logout_redirect_uri\n        type: string\n        description: The URI to redirect to after logout.\n      - name: state\n        type: string\n        description: Opaque value for maintaining state between request and callback.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OIDC_TOKEN: OIDC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oidc/refs/heads/main/capabilities/oidc-capability.yaml
tags:
- Oidc
- API
tools:
- description: OpenID Connect Discovery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiscovery
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
  name: gettoken
- description: UserInfo Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserinfo
- description: UserInfo Endpoint (POST)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postuserinfo
- description: JSON Web Key Set Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjwks
- description: End Session Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endsession
---
