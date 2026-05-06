---
categories: []
consumed_apis: []
description: RapiDoc is a fast, embeddable web component that renders OpenAPI (Swagger) 2.0/3.x specifications as interactive API documentation. This OpenAPI specification represents the conceptual API surface of the RapiDoc web component, including its configuration attributes, methods, events, and slots. RapiDoc is a client-side web component and does not expose a traditional REST API. It is configured via HTML attributes and JavaScript methods on the <rapi-doc> custom element.
layout: capability
name: RapiDoc API
operations:
- description: Get RapiDoc API Reference
  method: GET
  name: getapireference
  path: /api.html
- description: Get RapiDoc Examples and Demos
  method: GET
  name: getexamples
  path: /examples.html
- description: Get RapiDoc Quick Start Guide
  method: GET
  name: getquickstart
  path: /quickstart.html
personas: []
provider_name: RapiDoc
provider_slug: rapidoc
search_terms:
- rapidoc
- getquickstart
- platform
- web components
- get rapidoc quick start guide
- api
- getexamples
- getapireference
- documentation
- get rapidoc api reference
- openapi
- get rapidoc examples and demos
slug: rapidoc-capability
source_filename: rapidoc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RapiDoc API\n  description: RapiDoc is a fast, embeddable web component that renders OpenAPI (Swagger) 2.0/3.x specifications as interactive\n    API documentation. This OpenAPI specification represents the conceptual API surface of the RapiDoc web component, including\n    its configuration attributes, methods, events, and slots. RapiDoc is a client-side web component and does not expose a\n    traditional REST API. It is configured via HTML attributes and JavaScript methods on the <rapi-doc> custom element.\n  tags:\n  - Rapidoc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: rapidoc\n    baseUri: https://rapidocweb.com\n    description: RapiDoc API HTTP API.\n    resources:\n    - name: api-html\n      path: /api.html\n      operations:\n      - name: getapireference\n        method: GET\n        description: Get RapiDoc API Reference\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: examples-html\n      path: /examples.html\n      operations:\n      - name: getexamples\n        method: GET\n        description: Get RapiDoc Examples and Demos\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quickstart-html\n      path: /quickstart.html\n      operations:\n      - name: getquickstart\n        method: GET\n        description: Get RapiDoc Quick Start Guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rapidoc-rest\n    description: REST adapter for RapiDoc API.\n    resources:\n    - path: /api.html\n      name: getapireference\n      operations:\n      - method: GET\n        name: getapireference\n        description: Get RapiDoc API\
  \ Reference\n        call: rapidoc.getapireference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /examples.html\n      name: getexamples\n      operations:\n      - method: GET\n        name: getexamples\n        description: Get RapiDoc Examples and Demos\n        call: rapidoc.getexamples\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quickstart.html\n      name: getquickstart\n      operations:\n      - method: GET\n        name: getquickstart\n        description: Get RapiDoc Quick Start Guide\n        call: rapidoc.getquickstart\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rapidoc-mcp\n    transport: http\n    description: MCP adapter for RapiDoc API for AI agent use.\n    tools:\n    - name: getapireference\n      description: Get RapiDoc API Reference\n      hints:\n        readOnly: true\n        destructive: false\n     \
  \   idempotent: true\n      call: rapidoc.getapireference\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexamples\n      description: Get RapiDoc Examples and Demos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rapidoc.getexamples\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getquickstart\n      description: Get RapiDoc Quick Start Guide\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rapidoc.getquickstart\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rapidoc/refs/heads/main/capabilities/rapidoc-capability.yaml
tags:
- Rapidoc
- API
tools:
- description: Get RapiDoc API Reference
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapireference
- description: Get RapiDoc Examples and Demos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexamples
- description: Get RapiDoc Quick Start Guide
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquickstart
---
