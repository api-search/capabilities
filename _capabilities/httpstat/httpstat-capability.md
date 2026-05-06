---
categories: []
consumed_apis: []
description: A simple service for generating various HTTP status codes. Use this API to test how your scripts handle different HTTP responses.
layout: capability
name: httpstat
operations:
- description: Generate a specific HTTP status code
  method: GET
  name: get-statuscode
  path: /{statusCode}
- description: Generate a random HTTP status code
  method: GET
  name: get-random-range
  path: /random/{range}
personas: []
provider_name: Httpstat.us
provider_slug: httpstat
search_terms:
- http
- status codes
- testing
- generate a random http status code
- utilities
- api
- get statuscode
- httpstat
- get random range
- generate a specific http status code
slug: httpstat-capability
source_filename: httpstat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: httpstat\n  description: A simple service for generating various HTTP status codes. Use this API to test how your scripts handle different\n    HTTP responses.\n  tags:\n  - Httpstat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: httpstat\n    baseUri: https://httpstat.us\n    description: httpstat HTTP API.\n    resources:\n    - name: statuscode\n      path: /{statusCode}\n      operations:\n      - name: get-statuscode\n        method: GET\n        description: Generate a specific HTTP status code\n        inputParameters:\n        - name: statusCode\n          in: path\n          type: string\n          required: true\n          description: The HTTP status code to generate.\n        - name: sleep\n          in: query\n          type: integer\n          description: Delay the response by the specified duration in milliseconds (max 230 seconds for hosted instance).\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: random-range\n      path: /random/{range}\n      operations:\n      - name: get-random-range\n        method: GET\n        description: Generate a random HTTP status code\n        inputParameters:\n        - name: range\n          in: path\n          type: string\n          required: true\n          description: The range of HTTP status codes to randomize (e.g., `200,201,500-504`).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: httpstat-rest\n    description: REST adapter for httpstat.\n    resources:\n    - path: /{statusCode}\n      name: get-statuscode\n      operations:\n      - method: GET\n        name: get-statuscode\n        description: Generate a specific HTTP status code\n        call: httpstat.get-statuscode\n\
  \        with:\n          statusCode: rest.statusCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /random/{range}\n      name: get-random-range\n      operations:\n      - method: GET\n        name: get-random-range\n        description: Generate a random HTTP status code\n        call: httpstat.get-random-range\n        with:\n          range: rest.range\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: httpstat-mcp\n    transport: http\n    description: MCP adapter for httpstat for AI agent use.\n    tools:\n    - name: get-statuscode\n      description: Generate a specific HTTP status code\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: httpstat.get-statuscode\n      with:\n        statusCode: tools.statusCode\n        sleep: tools.sleep\n      inputParameters:\n      - name: statusCode\n        type: string\n    \
  \    description: The HTTP status code to generate.\n        required: true\n      - name: sleep\n        type: integer\n        description: Delay the response by the specified duration in milliseconds (max 230 seconds for hosted instance).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-random-range\n      description: Generate a random HTTP status code\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: httpstat.get-random-range\n      with:\n        range: tools.range\n      inputParameters:\n      - name: range\n        type: string\n        description: The range of HTTP status codes to randomize (e.g., `200,201,500-504`).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/httpstat/refs/heads/main/capabilities/httpstat-capability.yaml
tags:
- Httpstat
- API
tools:
- description: Generate a specific HTTP status code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-statuscode
- description: Generate a random HTTP status code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-random-range
---
