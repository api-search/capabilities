---
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
- it architects analyzing network and system diagrams.
- diagramming
- flowcharts
- analyze visio diagrams programmatically.
- list data items attached to a shape.
- diagram analysis
- microsoft 365
- get shape
- list all pages in a visio diagram.
- business analysts reviewing process flow diagrams.
- IT Architect
- visualization
- Business Analyst
- list all pages.
- diagram page operations.
- list data items for a shape.
- get details of a specific shape.
- business process
- list shape data items
- list shapes
- list shapes on a page.
- shape operations.
- list pages
- shape data operations.
- list all shapes on a diagram page.
- microsoft visio
slug: diagram-analysis
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
