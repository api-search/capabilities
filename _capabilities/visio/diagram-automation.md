---
categories: []
consumed_apis: []
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
- visualization
- shapes on a visio page
- sharepoint
- get the currently active visio page
- currently active visio page
- list shape data items
- extract all structured data items from a shape
- microsoft 365
- individual visio page
- list shape hyperlinks
- business process
- get the active visio document and its settings
- list all pages in the embedded visio diagram
- individual shape on a visio page
- list all shapes on the specified page
- get document
- list hyperlinks embedded in a visio shape
- hyperlinks attached to a shape
- read comments attached to a visio shape
- collaboration
- list shapes
- get shape
- diagrams
- current visio document
- get active page
- list all comments on a shape
- extract business data items stored in a shape
- get a specific visio page by name
- list shape comments
- enterprise
- list all pages in the visio diagram
- list pages
- office add-ins
- flowcharts
- visio diagram pages
- get page
- comments on a shape
- get a specific shape by id
- get details of a specific shape including text and bounding box
- get the currently active page in the visio diagram
- list all hyperlinks on a shape
- list all shapes on a named visio page
- get the active visio document properties and settings
- structured business data embedded in a shape
slug: diagram-automation
source_filename: diagram-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Visio Diagram Automation\n  description: Workflow capability for automating Visio diagram inspection, data extraction, and visual presentation via the\n    Visio JavaScript API embedded in SharePoint Online. Used by developers and business analysts to programmatically read\n    diagram content, extract business data from shapes, navigate pages, and update visual highlighting for interactive dashboard\n    experiences.\n  tags:\n  - Business Process\n  - Collaboration\n  - Diagrams\n  - Microsoft 365\n  - Office Add-Ins\n  - SharePoint\n  - Visualization\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VISIO_EMBEDDED_SESSION: VISIO_EMBEDDED_SESSION\ncapability:\n  consumes:\n  - type: http\n    namespace: visio-javascript\n    baseUri: https://appsforoffice.microsoft.com/embedded/1.0\n    description: Visio JavaScript API for Office Add-ins embedded in SharePoint Online\n    authentication:\n  \
  \    type: apikey\n      key: X-Embedded-Session\n      value: '{{VISIO_EMBEDDED_SESSION}}'\n      placement: header\n    resources:\n    - name: documents\n      path: /document\n      description: Visio document management operations\n      operations:\n      - name: get-document\n        method: GET\n        description: Get the current Visio document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages\n      path: /document/pages\n      description: Page listing and management operations\n      operations:\n      - name: list-pages\n        method: GET\n        description: List all pages in the Visio document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-active-page\n        method: GET\n        description: Get the currently active page\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: page\n      path: /document/pages/{pageName}\n      description: Individual page operations\n      operations:\n      - name: get-page\n        method: GET\n        description: Get a specific Visio page by name\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-page-view\n        method: PATCH\n        description: Update page view zoom settings\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \    body:\n          type: json\n          data:\n            zoom: '{{tools.zoom}}'\n    - name: shapes\n      path: /document/pages/{pageName}/shapes\n      description: Shape listing operations per page\n      operations:\n      - name: list-shapes\n        method: GET\n        description: List all shapes on a Visio page\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shape\n      path: /document/pages/{pageName}/shapes/{shapeId}\n      description: Individual shape operations\n      operations:\n      - name: get-shape\n        method: GET\n        description: Get a specific shape by ID\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description:\
  \ Name of the Visio page\n        - name: shapeId\n          in: path\n          type: integer\n          required: true\n          description: Numeric ID of the shape\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shape-data-items\n      path: /document/pages/{pageName}/shapes/{shapeId}/shapeDataItems\n      description: Shape structured data operations\n      operations:\n      - name: list-shape-data-items\n        method: GET\n        description: List all data items for a shape\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        - name: shapeId\n          in: path\n          type: integer\n          required: true\n          description: Numeric ID of the shape\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: shape-hyperlinks\n      path: /document/pages/{pageName}/shapes/{shapeId}/hyperlinks\n      description: Shape hyperlink operations\n      operations:\n      - name: list-shape-hyperlinks\n        method: GET\n        description: List all hyperlinks on a shape\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        - name: shapeId\n          in: path\n          type: integer\n          required: true\n          description: Numeric ID of the shape\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shape-comments\n      path: /document/pages/{pageName}/shapes/{shapeId}/comments\n      description: Shape comment operations\n      operations:\n      - name: list-shape-comments\n        method: GET\n        description: List all comments on a shape\n\
  \        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: Name of the Visio page\n        - name: shapeId\n          in: path\n          type: integer\n          required: true\n          description: Numeric ID of the shape\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application\n      path: /document/application\n      description: Application host settings\n      operations:\n      - name: get-application\n        method: GET\n        description: Get Visio application settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-application\n        method: PATCH\n        description: Update Visio application settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n        body:\n          type: json\n          data:\n            showToolbars: '{{tools.showToolbars}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: visio-automation-api\n    description: Unified REST API for Visio diagram automation and data extraction.\n    resources:\n    - path: /v1/document\n      name: document\n      description: Current Visio document\n      operations:\n      - method: GET\n        name: get-document\n        description: Get the active Visio document and its settings\n        call: visio-javascript.get-document\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages\n      name: pages\n      description: Visio diagram pages\n      operations:\n      - method: GET\n        name: list-pages\n        description: List all pages in the Visio diagram\n        call: visio-javascript.list-pages\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/pages/active\n      name: active-page\n      description: Currently active Visio page\n      operations:\n      - method: GET\n        name: get-active-page\n        description: Get the currently active Visio page\n        call: visio-javascript.get-active-page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}\n      name: page\n      description: Individual Visio page\n      operations:\n      - method: GET\n        name: get-page\n        description: Get a specific Visio page by name\n        call: visio-javascript.get-page\n        with:\n          pageName: rest.pageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}/shapes\n      name: shapes\n      description: Shapes on a Visio page\n      operations:\n      - method: GET\n        name: list-shapes\n        description: List all shapes on the specified page\n        call: visio-javascript.list-shapes\n\
  \        with:\n          pageName: rest.pageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}/shapes/{shapeId}\n      name: shape\n      description: Individual shape on a Visio page\n      operations:\n      - method: GET\n        name: get-shape\n        description: Get a specific shape by ID\n        call: visio-javascript.get-shape\n        with:\n          pageName: rest.pageName\n          shapeId: rest.shapeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}/shapes/{shapeId}/data\n      name: shape-data\n      description: Structured business data embedded in a shape\n      operations:\n      - method: GET\n        name: list-shape-data-items\n        description: Extract all structured data items from a shape\n        call: visio-javascript.list-shape-data-items\n        with:\n          pageName: rest.pageName\n          shapeId: rest.shapeId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}/shapes/{shapeId}/hyperlinks\n      name: shape-hyperlinks\n      description: Hyperlinks attached to a shape\n      operations:\n      - method: GET\n        name: list-shape-hyperlinks\n        description: List all hyperlinks on a shape\n        call: visio-javascript.list-shape-hyperlinks\n        with:\n          pageName: rest.pageName\n          shapeId: rest.shapeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{pageName}/shapes/{shapeId}/comments\n      name: shape-comments\n      description: Comments on a shape\n      operations:\n      - method: GET\n        name: list-shape-comments\n        description: List all comments on a shape\n        call: visio-javascript.list-shape-comments\n        with:\n          pageName: rest.pageName\n          shapeId: rest.shapeId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: visio-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Visio diagram analysis and automation.\n    tools:\n    - name: get-document\n      description: Get the active Visio document properties and settings\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.get-document\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pages\n      description: List all pages in the embedded Visio diagram\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.list-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-page\n      description: Get the currently active page in the Visio diagram\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.get-active-page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-page\n      description: Get a specific Visio page by name\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.get-page\n      with:\n        pageName: tools.pageName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shapes\n      description: List all shapes on a named Visio page\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.list-shapes\n      with:\n        pageName: tools.pageName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shape\n      description: Get details of a specific shape including text and bounding box\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.get-shape\n      with:\n        pageName: tools.pageName\n        shapeId: tools.shapeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shape-data-items\n      description:\
  \ Extract business data items stored in a shape\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.list-shape-data-items\n      with:\n        pageName: tools.pageName\n        shapeId: tools.shapeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shape-hyperlinks\n      description: List hyperlinks embedded in a Visio shape\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.list-shape-hyperlinks\n      with:\n        pageName: tools.pageName\n        shapeId: tools.shapeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shape-comments\n      description: Read comments attached to a Visio shape\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visio-javascript.list-shape-comments\n      with:\n        pageName: tools.pageName\n        shapeId: tools.shapeId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
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
