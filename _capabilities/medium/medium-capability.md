---
categories: []
consumed_apis: []
description: The Medium OAuth2 API enables third-party applications to authenticate and authorize users to act on their behalf on the Medium platform. Applications redirect users to Medium's authorization endpoint to obtain an authorization code, which is then exchanged for an access token and refresh token. The OAuth2 flow supports scoped permissions including basicProfile, publishPost, listPublications, and uploadImage, allowing developers to request only the level of access their application requires. Access tokens are valid for 60 days and can be refreshed using refresh tokens.
layout: capability
name: Medium OAuth2 API
operations:
- description: Authorize a user via OAuth2
  method: GET
  name: authorizeuser
  path: /authorize
- description: Exchange authorization code for tokens
  method: POST
  name: exchangeauthorizationcode
  path: /tokens
- description: Refresh an access token
  method: POST
  name: refreshaccesstoken
  path: /tokens/refresh
personas: []
provider_name: medium
provider_slug: medium
search_terms:
- authorize a user via oauth2
- refresh an access token
- exchange authorization code for tokens
- api
- authorizeuser
- exchangeauthorizationcode
- refreshaccesstoken
- medium
slug: medium-capability
source_filename: medium-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Medium OAuth2 API\n  description: The Medium OAuth2 API enables third-party applications to authenticate and authorize users to act on their\n    behalf on the Medium platform. Applications redirect users to Medium's authorization endpoint to obtain an authorization\n    code, which is then exchanged for an access token and refresh token. The OAuth2 flow supports scoped permissions including\n    basicProfile, publishPost, listPublications, and uploadImage, allowing developers to request only the level of access\n    their application requires. Access tokens are valid for 60 days and can be refreshed using refresh tokens.\n  tags:\n  - Medium\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: medium\n    baseUri: https://medium.com/m/oauth\n    description: Medium OAuth2 API HTTP API.\n    resources:\n    - name: authorize\n      path: /authorize\n      operations:\n  \
  \    - name: authorizeuser\n        method: GET\n        description: Authorize a user via OAuth2\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: The client ID of the application as registered with Medium.\n        - name: scope\n          in: query\n          type: string\n          required: true\n          description: 'A comma-separated list of requested permissions. Available scopes are basicProfile, listPublications,\n            publishPost, and uploadImage. The uploadImage scope is an '\n        - name: state\n          in: query\n          type: string\n          required: true\n          description: An arbitrary string used to prevent cross-site request forgery attacks. This value is returned unchanged\n            in the callback.\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: Must be set to \"code\"\
  \ to indicate the authorization code grant flow.\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: The URL where Medium will redirect the user after authorization. Must match one of the redirect URIs\n            registered for the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      operations:\n      - name: exchangeauthorizationcode\n        method: POST\n        description: Exchange authorization code for tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-refresh\n      path: /tokens/refresh\n      operations:\n      - name: refreshaccesstoken\n        method: POST\n        description: Refresh an access token\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: medium-rest\n    description: REST adapter for Medium OAuth2 API.\n    resources:\n    - path: /authorize\n      name: authorizeuser\n      operations:\n      - method: GET\n        name: authorizeuser\n        description: Authorize a user via OAuth2\n        call: medium.authorizeuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens\n      name: exchangeauthorizationcode\n      operations:\n      - method: POST\n        name: exchangeauthorizationcode\n        description: Exchange authorization code for tokens\n        call: medium.exchangeauthorizationcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens/refresh\n      name: refreshaccesstoken\n      operations:\n      - method: POST\n        name: refreshaccesstoken\n        description: Refresh an access token\n    \
  \    call: medium.refreshaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: medium-mcp\n    transport: http\n    description: MCP adapter for Medium OAuth2 API for AI agent use.\n    tools:\n    - name: authorizeuser\n      description: Authorize a user via OAuth2\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medium.authorizeuser\n      with:\n        client_id: tools.client_id\n        scope: tools.scope\n        state: tools.state\n        response_type: tools.response_type\n        redirect_uri: tools.redirect_uri\n      inputParameters:\n      - name: client_id\n        type: string\n        description: The client ID of the application as registered with Medium.\n        required: true\n      - name: scope\n        type: string\n        description: 'A comma-separated list of requested permissions. Available scopes are basicProfile, listPublications,\n\
  \          publishPost, and uploadImage. The uploadImage scope is an '\n        required: true\n      - name: state\n        type: string\n        description: An arbitrary string used to prevent cross-site request forgery attacks. This value is returned unchanged\n          in the callback.\n        required: true\n      - name: response_type\n        type: string\n        description: Must be set to \"code\" to indicate the authorization code grant flow.\n        required: true\n      - name: redirect_uri\n        type: string\n        description: The URL where Medium will redirect the user after authorization. Must match one of the redirect URIs\n          registered for the application.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exchangeauthorizationcode\n      description: Exchange authorization code for tokens\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: medium.exchangeauthorizationcode\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refreshaccesstoken\n      description: Refresh an access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: medium.refreshaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/medium/refs/heads/main/capabilities/medium-capability.yaml
tags:
- Medium
- API
tools:
- description: Authorize a user via OAuth2
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: authorizeuser
- description: Exchange authorization code for tokens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exchangeauthorizationcode
- description: Refresh an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refreshaccesstoken
---
