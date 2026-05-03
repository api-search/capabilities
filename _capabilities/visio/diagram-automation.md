---
api_specs:
- filename: visio-javascript-openapi.yml
  format: yaml
  label: visio-javascript
  slug: visio-javascript
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/visio/refs/heads/main/openapi/visio-javascript-openapi.yml
categories: []
consumed_apis:
- visio-javascript
description: Workflow capability for automating Visio diagram inspection, data extraction, and visual presentation via the Visio JavaScript API embedded in SharePoint Online. Used by developers and business analysts to programmatically read diagram content, extract business data from shapes, navigate pages, and update visual highlighting for interactive dashboard experiences.
layout: capability
name: Visio Diagram Automation
operations:
- description: Get the active Visio document and its settings
  method: GET
  name: get-document
  path: /v1/document
- description: List all pages in the Visio diagram
  method: GET
  name: list-pages
  path: /v1/pages
- description: Get the currently active Visio page
  method: GET
  name: get-active-page
  path: /v1/pages/active
- description: Get a specific Visio page by name
  method: GET
  name: get-page
  path: /v1/pages/{pageName}
- description: List all shapes on the specified page
  method: GET
  name: list-shapes
  path: /v1/pages/{pageName}/shapes
- description: Get a specific shape by ID
  method: GET
  name: get-shape
  path: /v1/pages/{pageName}/shapes/{shapeId}
- description: Extract all structured data items from a shape
  method: GET
  name: list-shape-data-items
  path: /v1/pages/{pageName}/shapes/{shapeId}/data
- description: List all hyperlinks on a shape
  method: GET
  name: list-shape-hyperlinks
  path: /v1/pages/{pageName}/shapes/{shapeId}/hyperlinks
- description: List all comments on a shape
  method: GET
  name: list-shape-comments
  path: /v1/pages/{pageName}/shapes/{shapeId}/comments
personas: []
provider_name: Microsoft Visio API
provider_slug: visio
search_terms:
- list all pages in the embedded visio diagram
- structured business data embedded in a shape
- individual shape on a visio page
- sharepoint
- get the currently active visio page
- get the active visio document properties and settings
- list shapes
- list shape hyperlinks
- extract all structured data items from a shape
- hyperlinks attached to a shape
- get the active visio document and its settings
- get details of a specific shape including text and bounding box
- microsoft 365
- list shape comments
- shapes on a visio page
- diagrams
- extract business data items stored in a shape
- flowcharts
- visualization
- get active page
- list all pages in the visio diagram
- office add-ins
- get page
- read comments attached to a visio shape
- list pages
- get a specific shape by id
- collaboration
- get document
- list all shapes on the specified page
- enterprise
- list all shapes on a named visio page
- get the currently active page in the visio diagram
- visio diagram pages
- get shape
- list shape data items
- list all hyperlinks on a shape
- list all comments on a shape
- current visio document
- comments on a shape
- currently active visio page
- list hyperlinks embedded in a visio shape
- individual visio page
- get a specific visio page by name
- business process
slug: diagram-automation
source_filename: diagram-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Visio Diagram Automation\"\n  description: >-\n    Workflow capability for automating Visio diagram inspection, data extraction,\n    and visual presentation via the Visio JavaScript API embedded in SharePoint Online.\n    Used by developers and business analysts to programmatically read diagram content,\n    extract business data from shapes, navigate pages, and update visual highlighting\n    for interactive dashboard experiences.\n  tags:\n    - Business Process\n    - Collaboration\n    - Diagrams\n    - Microsoft 365\n    - Office Add-Ins\n    - SharePoint\n    - Visualization\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VISIO_EMBEDDED_SESSION: VISIO_EMBEDDED_SESSION\n\ncapability:\n  consumes:\n    - import: visio-javascript\n      location: ./shared/visio-javascript.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: visio-automation-api\n   \
  \   description: \"Unified REST API for Visio diagram automation and data extraction.\"\n      resources:\n        - path: /v1/document\n          name: document\n          description: \"Current Visio document\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Get the active Visio document and its settings\"\n              call: \"visio-javascript.get-document\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages\n          name: pages\n          description: \"Visio diagram pages\"\n          operations:\n            - method: GET\n              name: list-pages\n              description: \"List all pages in the Visio diagram\"\n              call: \"visio-javascript.list-pages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/active\n          name: active-page\n   \
  \       description: \"Currently active Visio page\"\n          operations:\n            - method: GET\n              name: get-active-page\n              description: \"Get the currently active Visio page\"\n              call: \"visio-javascript.get-active-page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}\n          name: page\n          description: \"Individual Visio page\"\n          operations:\n            - method: GET\n              name: get-page\n              description: \"Get a specific Visio page by name\"\n              call: \"visio-javascript.get-page\"\n              with:\n                pageName: \"rest.pageName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}/shapes\n          name: shapes\n          description: \"Shapes on a Visio page\"\n          operations:\n            - method:\
  \ GET\n              name: list-shapes\n              description: \"List all shapes on the specified page\"\n              call: \"visio-javascript.list-shapes\"\n              with:\n                pageName: \"rest.pageName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}/shapes/{shapeId}\n          name: shape\n          description: \"Individual shape on a Visio page\"\n          operations:\n            - method: GET\n              name: get-shape\n              description: \"Get a specific shape by ID\"\n              call: \"visio-javascript.get-shape\"\n              with:\n                pageName: \"rest.pageName\"\n                shapeId: \"rest.shapeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}/shapes/{shapeId}/data\n          name: shape-data\n          description: \"Structured business\
  \ data embedded in a shape\"\n          operations:\n            - method: GET\n              name: list-shape-data-items\n              description: \"Extract all structured data items from a shape\"\n              call: \"visio-javascript.list-shape-data-items\"\n              with:\n                pageName: \"rest.pageName\"\n                shapeId: \"rest.shapeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}/shapes/{shapeId}/hyperlinks\n          name: shape-hyperlinks\n          description: \"Hyperlinks attached to a shape\"\n          operations:\n            - method: GET\n              name: list-shape-hyperlinks\n              description: \"List all hyperlinks on a shape\"\n              call: \"visio-javascript.list-shape-hyperlinks\"\n              with:\n                pageName: \"rest.pageName\"\n                shapeId: \"rest.shapeId\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{pageName}/shapes/{shapeId}/comments\n          name: shape-comments\n          description: \"Comments on a shape\"\n          operations:\n            - method: GET\n              name: list-shape-comments\n              description: \"List all comments on a shape\"\n              call: \"visio-javascript.list-shape-comments\"\n              with:\n                pageName: \"rest.pageName\"\n                shapeId: \"rest.shapeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: visio-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Visio diagram analysis and automation.\"\n      tools:\n        - name: get-document\n          description: \"Get the active Visio document properties and settings\"\n          hints:\n            readOnly: true\n      \
  \      idempotent: true\n          call: \"visio-javascript.get-document\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pages\n          description: \"List all pages in the embedded Visio diagram\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.list-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-active-page\n          description: \"Get the currently active page in the Visio diagram\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.get-active-page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-page\n          description: \"Get a specific Visio page by name\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.get-page\"\
  \n          with:\n            pageName: \"tools.pageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shapes\n          description: \"List all shapes on a named Visio page\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.list-shapes\"\n          with:\n            pageName: \"tools.pageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-shape\n          description: \"Get details of a specific shape including text and bounding box\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.get-shape\"\n          with:\n            pageName: \"tools.pageName\"\n            shapeId: \"tools.shapeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shape-data-items\n          description:\
  \ \"Extract business data items stored in a shape\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.list-shape-data-items\"\n          with:\n            pageName: \"tools.pageName\"\n            shapeId: \"tools.shapeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shape-hyperlinks\n          description: \"List hyperlinks embedded in a Visio shape\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"visio-javascript.list-shape-hyperlinks\"\n          with:\n            pageName: \"tools.pageName\"\n            shapeId: \"tools.shapeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shape-comments\n          description: \"Read comments attached to a Visio shape\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"visio-javascript.list-shape-comments\"\n          with:\n            pageName: \"tools.pageName\"\n            shapeId: \"tools.shapeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/visio/refs/heads/main/capabilities/diagram-automation.yaml
tags:
- Business Process
- Collaboration
- Diagrams
- Microsoft 365
- Office Add-Ins
- SharePoint
- Visualization
tools:
- description: Get the active Visio document properties and settings
  hints:
    idempotent: true
    readOnly: true
  name: get-document
- description: List all pages in the embedded Visio diagram
  hints:
    idempotent: true
    readOnly: true
  name: list-pages
- description: Get the currently active page in the Visio diagram
  hints:
    idempotent: true
    readOnly: true
  name: get-active-page
- description: Get a specific Visio page by name
  hints:
    idempotent: true
    readOnly: true
  name: get-page
- description: List all shapes on a named Visio page
  hints:
    idempotent: true
    readOnly: true
  name: list-shapes
- description: Get details of a specific shape including text and bounding box
  hints:
    idempotent: true
    readOnly: true
  name: get-shape
- description: Extract business data items stored in a shape
  hints:
    idempotent: true
    readOnly: true
  name: list-shape-data-items
- description: List hyperlinks embedded in a Visio shape
  hints:
    idempotent: true
    readOnly: true
  name: list-shape-hyperlinks
- description: Read comments attached to a Visio shape
  hints:
    idempotent: true
    readOnly: true
  name: list-shape-comments
---
