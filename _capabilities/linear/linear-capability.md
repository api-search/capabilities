---
categories: []
consumed_apis: []
description: Linear's public GraphQL API provides full access to create, read, update, and query issues, projects, cycles, roadmaps, and teams. It is the same API Linear uses internally for its own applications, supporting pagination, filtering, attachments, and file uploads.
layout: capability
name: Linear GraphQL API
operations:
- description: Execute a GraphQL query or mutation
  method: POST
  name: executegraphqlquery
  path: /graphql
- description: Upload a file attachment
  method: POST
  name: uploadfile
  path: /graphql/upload
personas: []
provider_name: linear
provider_slug: linear
search_terms:
- upload a file attachment
- uploadfile
- linear
- execute a graphql query or mutation
- api
- executegraphqlquery
slug: linear-capability
source_filename: linear-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Linear GraphQL API\n  description: Linear's public GraphQL API provides full access to create, read, update, and query issues, projects, cycles,\n    roadmaps, and teams. It is the same API Linear uses internally for its own applications, supporting pagination, filtering,\n    attachments, and file uploads.\n  tags:\n  - Linear\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: linear\n    baseUri: https://api.linear.app/graphql\n    description: Linear GraphQL API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LINEAR_TOKEN}}'\n    resources:\n    - name: graphql\n      path: /graphql\n      operations:\n      - name: executegraphqlquery\n        method: POST\n        description: Execute a GraphQL query or mutation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ graphql-upload\n      path: /graphql/upload\n      operations:\n      - name: uploadfile\n        method: POST\n        description: Upload a file attachment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: linear-rest\n    description: REST adapter for Linear GraphQL API.\n    resources:\n    - path: /graphql\n      name: executegraphqlquery\n      operations:\n      - method: POST\n        name: executegraphqlquery\n        description: Execute a GraphQL query or mutation\n        call: linear.executegraphqlquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /graphql/upload\n      name: uploadfile\n      operations:\n      - method: POST\n        name: uploadfile\n        description: Upload a file attachment\n        call: linear.uploadfile\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: linear-mcp\n    transport: http\n    description: MCP adapter for Linear GraphQL API for AI agent use.\n    tools:\n    - name: executegraphqlquery\n      description: Execute a GraphQL query or mutation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: linear.executegraphqlquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadfile\n      description: Upload a file attachment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: linear.uploadfile\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LINEAR_TOKEN: LINEAR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linear/refs/heads/main/capabilities/linear-capability.yaml
tags:
- Linear
- API
tools:
- description: Execute a GraphQL query or mutation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executegraphqlquery
- description: Upload a file attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfile
---
