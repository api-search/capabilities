---
categories: []
consumed_apis: []
description: Stoplight Elements is an open-source API documentation component library that renders OpenAPI 2.0, 3.0, and 3.1 specifications as beautiful, interactive developer documentation. This OpenAPI specification represents the conceptual API surface of the Stoplight Elements component library, including its React component props, Web Component attributes, configuration options, and supported layouts. Elements is a client-side component library and does not expose a traditional REST API. It is configured via React props on the API React component or HTML attributes on the elements-api custom element.
layout: capability
name: Stoplight Elements API
operations:
- description: Get Stoplight Elements Overview
  method: GET
  name: getelementsoverview
  path: /open-source/elements
- description: Stoplight Elements Get Elements Documentation
  method: GET
  name: getelementsdocumentation
  path: /docs/elements
- description: Stoplight Elements Get React Integration Guide
  method: GET
  name: getreactgettingstarted
  path: /docs/elements/b074dc07b3bae-getting-started-with-elements-in-react
- description: Stoplight Elements Get Web Component Integration Guide
  method: GET
  name: getwebcomponentgettingstarted
  path: /docs/elements/19a7f9f0cbf23-getting-started-with-web-component
- description: Stoplight Elements Get Angular Integration Guide
  method: GET
  name: getangulargettingstarted
  path: /docs/elements/507fb7fab9b7d-getting-started-with-elements-in-angular
- description: Stoplight Elements Get Configuration Options Reference
  method: GET
  name: getconfigurationoptions
  path: /docs/elements/ZG9jOjMyNjU5MTM-elements-configuration-options
personas: []
provider_name: Stoplight Elements
provider_slug: elements
search_terms:
- getwebcomponentgettingstarted
- web components
- get stoplight elements overview
- api
- getelementsoverview
- openapi
- stoplight elements get web component integration guide
- documentation
- stoplight elements get configuration options reference
- getconfigurationoptions
- developer tools
- getangulargettingstarted
- stoplight elements get elements documentation
- getelementsdocumentation
- elements
- react
- interactive docs
- stoplight elements get react integration guide
- stoplight elements get angular integration guide
- api documentation
- getreactgettingstarted
slug: elements-capability
source_filename: elements-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stoplight Elements API\n  description: Stoplight Elements is an open-source API documentation component library that renders OpenAPI 2.0, 3.0, and\n    3.1 specifications as beautiful, interactive developer documentation. This OpenAPI specification represents the conceptual\n    API surface of the Stoplight Elements component library, including its React component props, Web Component attributes,\n    configuration options, and supported layouts. Elements is a client-side component library and does not expose a traditional\n    REST API. It is configured via React props on the API React component or HTML attributes on the elements-api custom element.\n  tags:\n  - Elements\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: elements\n    baseUri: https://stoplight.io\n    description: Stoplight Elements API HTTP API.\n    resources:\n    - name: open-source-elements\n  \
  \    path: /open-source/elements\n      operations:\n      - name: getelementsoverview\n        method: GET\n        description: Get Stoplight Elements Overview\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docs-elements\n      path: /docs/elements\n      operations:\n      - name: getelementsdocumentation\n        method: GET\n        description: Stoplight Elements Get Elements Documentation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docs-elements-b074dc07b3bae-getting-started-with\n      path: /docs/elements/b074dc07b3bae-getting-started-with-elements-in-react\n      operations:\n      - name: getreactgettingstarted\n        method: GET\n        description: Stoplight Elements Get React Integration Guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: docs-elements-19a7f9f0cbf23-getting-started-with\n      path: /docs/elements/19a7f9f0cbf23-getting-started-with-web-component\n      operations:\n      - name: getwebcomponentgettingstarted\n        method: GET\n        description: Stoplight Elements Get Web Component Integration Guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docs-elements-507fb7fab9b7d-getting-started-with\n      path: /docs/elements/507fb7fab9b7d-getting-started-with-elements-in-angular\n      operations:\n      - name: getangulargettingstarted\n        method: GET\n        description: Stoplight Elements Get Angular Integration Guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docs-elements-zg9jojmynju5mtm-elements-configura\n      path: /docs/elements/ZG9jOjMyNjU5MTM-elements-configuration-options\n\
  \      operations:\n      - name: getconfigurationoptions\n        method: GET\n        description: Stoplight Elements Get Configuration Options Reference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: elements-rest\n    description: REST adapter for Stoplight Elements API.\n    resources:\n    - path: /open-source/elements\n      name: getelementsoverview\n      operations:\n      - method: GET\n        name: getelementsoverview\n        description: Get Stoplight Elements Overview\n        call: elements.getelementsoverview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docs/elements\n      name: getelementsdocumentation\n      operations:\n      - method: GET\n        name: getelementsdocumentation\n        description: Stoplight Elements Get Elements Documentation\n        call: elements.getelementsdocumentation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docs/elements/b074dc07b3bae-getting-started-with-elements-in-react\n      name: getreactgettingstarted\n      operations:\n      - method: GET\n        name: getreactgettingstarted\n        description: Stoplight Elements Get React Integration Guide\n        call: elements.getreactgettingstarted\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docs/elements/19a7f9f0cbf23-getting-started-with-web-component\n      name: getwebcomponentgettingstarted\n      operations:\n      - method: GET\n        name: getwebcomponentgettingstarted\n        description: Stoplight Elements Get Web Component Integration Guide\n        call: elements.getwebcomponentgettingstarted\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docs/elements/507fb7fab9b7d-getting-started-with-elements-in-angular\n      name: getangulargettingstarted\n      operations:\n\
  \      - method: GET\n        name: getangulargettingstarted\n        description: Stoplight Elements Get Angular Integration Guide\n        call: elements.getangulargettingstarted\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docs/elements/ZG9jOjMyNjU5MTM-elements-configuration-options\n      name: getconfigurationoptions\n      operations:\n      - method: GET\n        name: getconfigurationoptions\n        description: Stoplight Elements Get Configuration Options Reference\n        call: elements.getconfigurationoptions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: elements-mcp\n    transport: http\n    description: MCP adapter for Stoplight Elements API for AI agent use.\n    tools:\n    - name: getelementsoverview\n      description: Get Stoplight Elements Overview\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ elements.getelementsoverview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelementsdocumentation\n      description: Stoplight Elements Get Elements Documentation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elements.getelementsdocumentation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreactgettingstarted\n      description: Stoplight Elements Get React Integration Guide\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elements.getreactgettingstarted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwebcomponentgettingstarted\n      description: Stoplight Elements Get Web Component Integration Guide\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elements.getwebcomponentgettingstarted\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getangulargettingstarted\n      description: Stoplight Elements Get Angular Integration Guide\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elements.getangulargettingstarted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfigurationoptions\n      description: Stoplight Elements Get Configuration Options Reference\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elements.getconfigurationoptions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/elements/refs/heads/main/capabilities/elements-capability.yaml
tags:
- Elements
- API
tools:
- description: Get Stoplight Elements Overview
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelementsoverview
- description: Stoplight Elements Get Elements Documentation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelementsdocumentation
- description: Stoplight Elements Get React Integration Guide
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreactgettingstarted
- description: Stoplight Elements Get Web Component Integration Guide
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebcomponentgettingstarted
- description: Stoplight Elements Get Angular Integration Guide
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getangulargettingstarted
- description: Stoplight Elements Get Configuration Options Reference
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfigurationoptions
---
