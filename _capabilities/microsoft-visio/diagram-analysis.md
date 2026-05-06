---
categories: []
consumed_apis: []
description: Workflow capability for analyzing Visio diagrams including reading pages, shapes, data items, comments, and hyperlinks. Used by business analysts and IT architects to programmatically inspect diagram content.
layout: capability
name: Microsoft Visio Diagram Analysis
operations:
- description: List all pages.
  method: GET
  name: list-pages
  path: /v1/pages
- description: List shapes on a page.
  method: GET
  name: list-shapes
  path: /v1/shapes
- description: List data items for a shape.
  method: GET
  name: list-shape-data-items
  path: /v1/shape-data
personas: []
provider_name: Microsoft Visio
provider_slug: microsoft-visio
search_terms:
- microsoft 365
- list data items for a shape.
- list shapes
- visualization
- list pages
- list all pages.
- business analysts reviewing process flow diagrams.
- IT Architect
- list shapes on a page.
- diagram page operations.
- microsoft visio
- list all pages in a visio diagram.
- it architects analyzing network and system diagrams.
- business process
- analyze visio diagrams programmatically.
- diagramming
- list shape data items
- shape data operations.
- flowcharts
- shape operations.
- get shape
- diagram analysis
- Business Analyst
- get details of a specific shape.
- list all shapes on a diagram page.
- list data items attached to a shape.
slug: diagram-analysis
source_filename: diagram-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Visio Diagram Analysis\n  description: Workflow capability for analyzing Visio diagrams including reading pages, shapes, data items, comments, and\n    hyperlinks. Used by business analysts and IT architects to programmatically inspect diagram content.\n  tags:\n  - Microsoft Visio\n  - Diagram Analysis\n  - Visualization\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: visio-graph\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Visio API for diagram operations.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_GRAPH_TOKEN}}'\n    resources:\n    - name: pages\n      path: /me/drive/items/{item-id}/workbook/pages\n      description: Visio page operations.\n      operations:\n      - name: list-pages\n        method: GET\n        description:\
  \ List pages in a Visio document.\n        inputParameters:\n        - name: item-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Visio file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shapes\n      path: /me/drive/items/{item-id}/workbook/pages/{page-id}/shapes\n      description: Shape operations.\n      operations:\n      - name: list-shapes\n        method: GET\n        description: List shapes on a page.\n        inputParameters:\n        - name: item-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Visio file.\n        - name: page-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: get-shape\n        method: GET\n        description: Get a specific shape.\n        inputParameters:\n        - name: item-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Visio file.\n        - name: page-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shape-data\n      path: /me/drive/items/{item-id}/workbook/pages/{page-id}/shapes/{shape-id}/shapeDataItems\n      description: Shape data item operations.\n      operations:\n      - name: list-shape-data-items\n        method: GET\n        description: List data items for a shape.\n        inputParameters:\n        - name: item-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Visio\
  \ file.\n        - name: page-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the page.\n        - name: shape-id\n          in: path\n          type: string\n          required: true\n          description: The ID of the shape.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: diagram-analysis-api\n    description: Unified REST API for Visio diagram analysis.\n    resources:\n    - path: /v1/pages\n      name: pages\n      description: Diagram page operations.\n      operations:\n      - method: GET\n        name: list-pages\n        description: List all pages.\n        call: visio-graph.list-pages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shapes\n      name: shapes\n      description: Shape operations.\n      operations:\n      - method: GET\n\
  \        name: list-shapes\n        description: List shapes on a page.\n        call: visio-graph.list-shapes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shape-data\n      name: shape-data\n      description: Shape data operations.\n      operations:\n      - method: GET\n        name: list-shape-data-items\n        description: List data items for a shape.\n        call: visio-graph.list-shape-data-items\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: diagram-analysis-mcp\n    transport: http\n    description: MCP server for AI-assisted Visio diagram analysis.\n    tools:\n    - name: list-pages\n      description: List all pages in a Visio diagram.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: visio-graph.list-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shapes\n      description: List all\
  \ shapes on a diagram page.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: visio-graph.list-shapes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shape\n      description: Get details of a specific shape.\n      hints:\n        readOnly: true\n      call: visio-graph.get-shape\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shape-data-items\n      description: List data items attached to a shape.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: visio-graph.list-shape-data-items\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-visio/refs/heads/main/capabilities/diagram-analysis.yaml
tags:
- Microsoft Visio
- Diagram Analysis
- Visualization
tools:
- description: List all pages in a Visio diagram.
  hints:
    openWorld: true
    readOnly: true
  name: list-pages
- description: List all shapes on a diagram page.
  hints:
    openWorld: true
    readOnly: true
  name: list-shapes
- description: Get details of a specific shape.
  hints:
    readOnly: true
  name: get-shape
- description: List data items attached to a shape.
  hints:
    openWorld: true
    readOnly: true
  name: list-shape-data-items
---
