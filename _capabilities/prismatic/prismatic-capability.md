---
categories: []
consumed_apis: []
description: Prismatic provides a GraphQL-based API for building, deploying, and supporting integrations programmatically. The API allows you to manage customers, integrations, instances, components, and other resources. GraphQL operations include queries (pulling data) and mutations (creating, modifying, or deleting data). The API endpoint accepts GraphQL queries via HTTP POST requests. Authentication is handled via JWT bearer tokens obtained through the Prismatic web app or CLI tool.
layout: capability
name: Prismatic GraphQL API
operations:
- description: Prismatic Execute GraphQL Query or Mutation
  method: POST
  name: executegraphqlquery
  path: /api
- description: Prismatic Refresh Authentication Token
  method: POST
  name: refreshauthtoken
  path: /auth/refresh
- description: Prismatic Revoke Refresh Token
  method: POST
  name: revokeauthtoken
  path: /auth/revoke
- description: Prismatic Get Short-Lived Auth Token
  method: GET
  name: getauthtoken
  path: /get_auth_token/
personas: []
provider_name: Prismatic
provider_slug: prismatic
search_terms:
- embedded ipaas
- prismatic refresh authentication token
- integrations
- getauthtoken
- prismatic execute graphql query or mutation
- prismatic get short-lived auth token
- workflows
- refreshauthtoken
- prismatic
- api
- executegraphqlquery
- prismatic revoke refresh token
- revokeauthtoken
slug: prismatic-capability
source_filename: prismatic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Prismatic GraphQL API\n  description: Prismatic provides a GraphQL-based API for building, deploying, and supporting integrations programmatically.\n    The API allows you to manage customers, integrations, instances, components, and other resources. GraphQL operations include\n    queries (pulling data) and mutations (creating, modifying, or deleting data). The API endpoint accepts GraphQL queries\n    via HTTP POST requests. Authentication is handled via JWT bearer tokens obtained through the Prismatic web app or CLI\n    tool.\n  tags:\n  - Prismatic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: prismatic\n    baseUri: https://app.prismatic.io\n    description: Prismatic GraphQL API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PRISMATIC_TOKEN}}'\n    resources:\n    - name: api\n      path: /api\n      operations:\n      - name: executegraphqlquery\n\
  \        method: POST\n        description: Prismatic Execute GraphQL Query or Mutation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-refresh\n      path: /auth/refresh\n      operations:\n      - name: refreshauthtoken\n        method: POST\n        description: Prismatic Refresh Authentication Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-revoke\n      path: /auth/revoke\n      operations:\n      - name: revokeauthtoken\n        method: POST\n        description: Prismatic Revoke Refresh Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-auth-token\n      path: /get_auth_token/\n      operations:\n      - name: getauthtoken\n        method: GET\n        description: Prismatic Get Short-Lived\
  \ Auth Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: prismatic-rest\n    description: REST adapter for Prismatic GraphQL API.\n    resources:\n    - path: /api\n      name: executegraphqlquery\n      operations:\n      - method: POST\n        name: executegraphqlquery\n        description: Prismatic Execute GraphQL Query or Mutation\n        call: prismatic.executegraphqlquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/refresh\n      name: refreshauthtoken\n      operations:\n      - method: POST\n        name: refreshauthtoken\n        description: Prismatic Refresh Authentication Token\n        call: prismatic.refreshauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/revoke\n      name: revokeauthtoken\n      operations:\n      - method: POST\n\
  \        name: revokeauthtoken\n        description: Prismatic Revoke Refresh Token\n        call: prismatic.revokeauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_auth_token/\n      name: getauthtoken\n      operations:\n      - method: GET\n        name: getauthtoken\n        description: Prismatic Get Short-Lived Auth Token\n        call: prismatic.getauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prismatic-mcp\n    transport: http\n    description: MCP adapter for Prismatic GraphQL API for AI agent use.\n    tools:\n    - name: executegraphqlquery\n      description: Prismatic Execute GraphQL Query or Mutation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prismatic.executegraphqlquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refreshauthtoken\n    \
  \  description: Prismatic Refresh Authentication Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prismatic.refreshauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeauthtoken\n      description: Prismatic Revoke Refresh Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prismatic.revokeauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getauthtoken\n      description: Prismatic Get Short-Lived Auth Token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prismatic.getauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PRISMATIC_TOKEN: PRISMATIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/prismatic/refs/heads/main/capabilities/prismatic-capability.yaml
tags:
- Prismatic
- API
tools:
- description: Prismatic Execute GraphQL Query or Mutation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executegraphqlquery
- description: Prismatic Refresh Authentication Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refreshauthtoken
- description: Prismatic Revoke Refresh Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeauthtoken
- description: Prismatic Get Short-Lived Auth Token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtoken
---
