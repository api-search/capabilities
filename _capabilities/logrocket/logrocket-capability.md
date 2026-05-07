---
categories: []
consumed_apis: []
description: The LogRocket GraphQL API allows developers to query session replay and analytics data using GraphQL. It provides a flexible query interface for retrieving session information, user activity, error details, and performance metrics. Developers can use this API to build custom dashboards, integrate session data into internal tools, and perform advanced filtering and aggregation of LogRocket monitoring data.
layout: capability
name: LogRocket GraphQL API
operations:
- description: Execute a GraphQL query
  method: POST
  name: executegraphqlquery
  path: /graphql
personas: []
provider_name: LogRocket
provider_slug: logrocket
search_terms:
- analytics
- observability
- execute a graphql query
- session replay
- logrocket
- error monitoring
- frontend monitoring
- api
- executegraphqlquery
slug: logrocket-capability
source_filename: logrocket-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LogRocket GraphQL API\n  description: The LogRocket GraphQL API allows developers to query session replay and analytics data using GraphQL. It provides\n    a flexible query interface for retrieving session information, user activity, error details, and performance metrics.\n    Developers can use this API to build custom dashboards, integrate session data into internal tools, and perform advanced\n    filtering and aggregation of LogRocket monitoring data.\n  tags:\n  - Logrocket\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: logrocket\n    baseUri: https://api.logrocket.com\n    description: LogRocket GraphQL API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{LOGROCKET_TOKEN}}'\n    resources:\n    - name: graphql\n      path: /graphql\n      operations:\n      - name: executegraphqlquery\n        method:\
  \ POST\n        description: Execute a GraphQL query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: logrocket-rest\n    description: REST adapter for LogRocket GraphQL API.\n    resources:\n    - path: /graphql\n      name: executegraphqlquery\n      operations:\n      - method: POST\n        name: executegraphqlquery\n        description: Execute a GraphQL query\n        call: logrocket.executegraphqlquery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: logrocket-mcp\n    transport: http\n    description: MCP adapter for LogRocket GraphQL API for AI agent use.\n    tools:\n    - name: executegraphqlquery\n      description: Execute a GraphQL query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logrocket.executegraphqlquery\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LOGROCKET_TOKEN: LOGROCKET_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/logrocket/refs/heads/main/capabilities/logrocket-capability.yaml
tags:
- Logrocket
- API
tools:
- description: Execute a GraphQL query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executegraphqlquery
---
