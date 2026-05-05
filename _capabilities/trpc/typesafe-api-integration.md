---
categories: []
consumed_apis:
- trpc
description: Workflow capability for integrating with tRPC-based backends. tRPC enables end-to-end typesafe APIs for TypeScript applications using HTTP as the transport. This capability supports calling tRPC query and mutation procedures via the standard HTTP protocol, enabling AI agents and automation workflows to interact with tRPC servers without requiring TypeScript clients.
layout: capability
name: tRPC Typesafe API Integration
operations:
- description: Check tRPC server health
  method: GET
  name: health-check
  path: /v1/health
- description: Invoke a tRPC query procedure
  method: GET
  name: query-procedure
  path: /v1/procedures/{name}
- description: Invoke a tRPC mutation procedure
  method: POST
  name: mutation-procedure
  path: /v1/procedures/{name}
- description: Execute multiple procedures at once
  method: POST
  name: batch-procedures
  path: /v1/batch
personas: []
provider_name: tRPC
provider_slug: trpc
search_terms:
- trpc procedure proxy
- end-to-end type safety
- check trpc server health
- invoke a trpc query procedure by path. queries are read-only and use http get. the procedure name uses dot notation for nested routers (e.g., 'user.getuser', 'post.list').
- api framework
- invoke a trpc mutation procedure
- execute multiple trpc procedures in a single http request. trpc clients use batching automatically via httpbatchlink.
- backend integration
- rpc
- batch procedures
- server health check
- health check
- query procedure
- mutation procedure
- type safety
- check the health of a trpc server
- bff
- execute multiple procedures at once
- typescript
- invoke a trpc mutation procedure by path. mutations cause side effects and use http post. the procedure name uses dot notation (e.g., 'user.createuser', 'post.delete').
- api composition
- invoke a trpc query procedure
- batch multiple trpc procedure calls
- trpc
slug: typesafe-api-integration
source_filename: typesafe-api-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"tRPC Typesafe API Integration\"\n  description: >-\n    Workflow capability for integrating with tRPC-based backends. tRPC enables\n    end-to-end typesafe APIs for TypeScript applications using HTTP as the transport.\n    This capability supports calling tRPC query and mutation procedures via the\n    standard HTTP protocol, enabling AI agents and automation workflows to interact\n    with tRPC servers without requiring TypeScript clients.\n  tags:\n    - tRPC\n    - TypeScript\n    - RPC\n    - Type Safety\n    - Backend Integration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRPC_BEARER_TOKEN: TRPC_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: trpc\n      location: ./shared/trpc-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trpc-integration-api\n      description: \"REST facade for interacting with tRPC backend servers.\"\n  \
  \    resources:\n        - path: /v1/health\n          name: health\n          description: \"Server health check\"\n          operations:\n            - method: GET\n              name: health-check\n              description: \"Check tRPC server health\"\n              call: \"trpc.health-check\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/procedures/{name}\n          name: procedure\n          description: \"tRPC procedure proxy\"\n          operations:\n            - method: GET\n              name: query-procedure\n              description: \"Invoke a tRPC query procedure\"\n              call: \"trpc.query-procedure\"\n              with:\n                procedure: \"rest.name\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: mutation-procedure\n              description:\
  \ \"Invoke a tRPC mutation procedure\"\n              call: \"trpc.mutation-procedure\"\n              with:\n                procedure: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batch\n          name: batch\n          description: \"Batch multiple tRPC procedure calls\"\n          operations:\n            - method: POST\n              name: batch-procedures\n              description: \"Execute multiple procedures at once\"\n              call: \"trpc.batch-procedures\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trpc-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted interaction with tRPC backends.\"\n      tools:\n        - name: query-procedure\n          description: >-\n            Invoke a tRPC query procedure by path. Queries are read-only\n\
  \            and use HTTP GET. The procedure name uses dot notation for\n            nested routers (e.g., 'user.getUser', 'post.list').\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trpc.query-procedure\"\n          with:\n            procedure: \"tools.procedure\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mutation-procedure\n          description: >-\n            Invoke a tRPC mutation procedure by path. Mutations cause side\n            effects and use HTTP POST. The procedure name uses dot notation\n            (e.g., 'user.createUser', 'post.delete').\n          hints:\n            readOnly: false\n          call: \"trpc.mutation-procedure\"\n          with:\n            procedure: \"tools.procedure\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ batch-procedures\n          description: >-\n            Execute multiple tRPC procedures in a single HTTP request.\n            tRPC clients use batching automatically via httpBatchLink.\n          hints:\n            readOnly: false\n          call: \"trpc.batch-procedures\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: health-check\n          description: \"Check the health of a tRPC server\"\n          hints:\n            readOnly: true\n          call: \"trpc.health-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trpc/refs/heads/main/capabilities/typesafe-api-integration.yaml
tags:
- tRPC
- TypeScript
- RPC
- Type Safety
- Backend Integration
tools:
- description: Invoke a tRPC query procedure by path. Queries are read-only and use HTTP GET. The procedure name uses dot notation for nested routers (e.g., 'user.getUser', 'post.list').
  hints:
    openWorld: true
    readOnly: true
  name: query-procedure
- description: Invoke a tRPC mutation procedure by path. Mutations cause side effects and use HTTP POST. The procedure name uses dot notation (e.g., 'user.createUser', 'post.delete').
  hints:
    readOnly: false
  name: mutation-procedure
- description: Execute multiple tRPC procedures in a single HTTP request. tRPC clients use batching automatically via httpBatchLink.
  hints:
    readOnly: false
  name: batch-procedures
- description: Check the health of a tRPC server
  hints:
    readOnly: true
  name: health-check
---
