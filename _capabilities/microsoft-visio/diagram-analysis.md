---
categories: []
consumed_apis:
- visio-graph
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
- list shapes
- list all pages in a visio diagram.
- it architects analyzing network and system diagrams.
- business process
- microsoft 365
- microsoft visio
- visualization
- flowcharts
- diagram analysis
- list shapes on a page.
- get shape
- list all pages.
- diagram page operations.
- list pages
- list data items attached to a shape.
- diagramming
- shape data operations.
- Business Analyst
- list data items for a shape.
- business analysts reviewing process flow diagrams.
- list shape data items
- analyze visio diagrams programmatically.
- IT Architect
- list all shapes on a diagram page.
- get details of a specific shape.
- shape operations.
slug: diagram-analysis
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Visio Diagram Analysis\"\n  description: \"Workflow capability for analyzing Visio diagrams including reading pages, shapes, data items, comments, and hyperlinks. Used by business analysts and IT architects to programmatically inspect diagram content.\"\n  tags:\n    - Microsoft Visio\n    - Diagram Analysis\n    - Visualization\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n\ncapability:\n  consumes:\n    - import: visio-graph\n      location: ./shared/visio-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: diagram-analysis-api\n      description: \"Unified REST API for Visio diagram analysis.\"\n      resources:\n        - path: /v1/pages\n          name: pages\n          description: \"Diagram page operations.\"\n          operations:\n            - method: GET\n              name:\
  \ list-pages\n              description: \"List all pages.\"\n              call: \"visio-graph.list-pages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shapes\n          name: shapes\n          description: \"Shape operations.\"\n          operations:\n            - method: GET\n              name: list-shapes\n              description: \"List shapes on a page.\"\n              call: \"visio-graph.list-shapes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shape-data\n          name: shape-data\n          description: \"Shape data operations.\"\n          operations:\n            - method: GET\n              name: list-shape-data-items\n              description: \"List data items for a shape.\"\n              call: \"visio-graph.list-shape-data-items\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: diagram-analysis-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Visio diagram analysis.\"\n      tools:\n        - name: list-pages\n          description: \"List all pages in a Visio diagram.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"visio-graph.list-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shapes\n          description: \"List all shapes on a diagram page.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"visio-graph.list-shapes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-shape\n          description: \"Get details of a specific shape.\"\n          hints:\n            readOnly: true\n          call: \"visio-graph.get-shape\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-shape-data-items\n          description: \"List data items attached to a shape.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"visio-graph.list-shape-data-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
