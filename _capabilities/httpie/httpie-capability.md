---
categories: []
consumed_apis: []
description: The HTTPie API provides endpoints for the HTTPie web application, including a simple hello endpoint for connectivity testing and access to the HTTPie web-based API client interface. HTTPie is a user-friendly command-line and web-based HTTP client that makes interacting with APIs and web services intuitive and productive.
layout: capability
name: HTTPie API
operations:
- description: HTTPie Hello endpoint
  method: GET
  name: gethello
  path: /hello
- description: HTTPie web application
  method: GET
  name: getapp
  path: /app
personas: []
provider_name: HTTPie
provider_slug: httpie
search_terms:
- sessions
- open source
- gethello
- command line
- cli
- httpie web application
- client
- api client
- api
- http
- getapp
- httpie hello endpoint
- httpie
- developer tools
- api testing
slug: httpie-capability
source_filename: httpie-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HTTPie API\n  description: The HTTPie API provides endpoints for the HTTPie web application, including a simple hello endpoint for connectivity\n    testing and access to the HTTPie web-based API client interface. HTTPie is a user-friendly command-line and web-based\n    HTTP client that makes interacting with APIs and web services intuitive and productive.\n  tags:\n  - Httpie\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: httpie\n    baseUri: https://httpie.io\n    description: HTTPie API HTTP API.\n    resources:\n    - name: hello\n      path: /hello\n      operations:\n      - name: gethello\n        method: GET\n        description: HTTPie Hello endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app\n      path: /app\n      operations:\n      - name: getapp\n    \
  \    method: GET\n        description: HTTPie web application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: httpie-rest\n    description: REST adapter for HTTPie API.\n    resources:\n    - path: /hello\n      name: gethello\n      operations:\n      - method: GET\n        name: gethello\n        description: HTTPie Hello endpoint\n        call: httpie.gethello\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /app\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: HTTPie web application\n        call: httpie.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: httpie-mcp\n    transport: http\n    description: MCP adapter for HTTPie API for AI agent use.\n    tools:\n    - name: gethello\n\
  \      description: HTTPie Hello endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: httpie.gethello\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: HTTPie web application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: httpie.getapp\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/httpie/refs/heads/main/capabilities/httpie-capability.yaml
tags:
- Httpie
- API
tools:
- description: HTTPie Hello endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethello
- description: HTTPie web application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
---
