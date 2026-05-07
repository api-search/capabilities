---
categories: []
consumed_apis: []
description: Equinix APIs use the OAuth 2.0 for authentication and authorization. Equinix supports the resource owner password and the client credentials flow. To begin, obtain OAuth 2.0 client credentials from the Equinix Developer Console under "My Apps". Then your client application requests an access token from the Equinix API Authorization endpoint, extracts the access_token from the response, and sends the Bearer token to the API that you want to access
layout: capability
name: Equinix API Authentication
operations:
- description: Renew Access Tokens
  method: POST
  name: refreshoauth2accesstoken
  path: /oauth2/v1/refreshaccesstoken
- description: Generate New Access Token
  method: POST
  name: getoauth2accesstoken
  path: /oauth2/v1/token
personas: []
provider_name: Equinix
provider_slug: equinix
search_terms:
- renew access tokens
- refreshoauth2accesstoken
- networking
- colocation
- generate new access token
- bare metal
- getoauth2accesstoken
- equinix
- interconnection
- api
- cloud infrastructure
- data centers
slug: equinix-capability
source_filename: equinix-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Equinix API Authentication\n  description: Equinix APIs use the OAuth 2.0 for authentication and authorization. Equinix supports the resource owner password\n    and the client credentials flow. To begin, obtain OAuth 2.0 client credentials from the Equinix Developer Console under\n    \"My Apps\". Then your client application requests an access token from the Equinix API Authorization endpoint, extracts\n    the access_token from the response, and sends the Bearer token to the API that you want to access\n  tags:\n  - Equinix\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: equinix\n    baseUri: https://api.equinix.com\n    description: Equinix API Authentication HTTP API.\n    resources:\n    - name: oauth2-v1-refreshaccesstoken\n      path: /oauth2/v1/refreshaccesstoken\n      operations:\n      - name: refreshoauth2accesstoken\n        method: POST\n        description:\
  \ Renew Access Tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-v1-token\n      path: /oauth2/v1/token\n      operations:\n      - name: getoauth2accesstoken\n        method: POST\n        description: Generate New Access Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: equinix-rest\n    description: REST adapter for Equinix API Authentication.\n    resources:\n    - path: /oauth2/v1/refreshaccesstoken\n      name: refreshoauth2accesstoken\n      operations:\n      - method: POST\n        name: refreshoauth2accesstoken\n        description: Renew Access Tokens\n        call: equinix.refreshoauth2accesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/v1/token\n      name: getoauth2accesstoken\n\
  \      operations:\n      - method: POST\n        name: getoauth2accesstoken\n        description: Generate New Access Token\n        call: equinix.getoauth2accesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: equinix-mcp\n    transport: http\n    description: MCP adapter for Equinix API Authentication for AI agent use.\n    tools:\n    - name: refreshoauth2accesstoken\n      description: Renew Access Tokens\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: equinix.refreshoauth2accesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoauth2accesstoken\n      description: Generate New Access Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: equinix.getoauth2accesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/equinix/refs/heads/main/capabilities/equinix-capability.yaml
tags:
- Equinix
- API
tools:
- description: Renew Access Tokens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refreshoauth2accesstoken
- description: Generate New Access Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getoauth2accesstoken
---
