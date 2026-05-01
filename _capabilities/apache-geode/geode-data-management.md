---
categories: []
consumed_apis:
- geode-rest
description: Unified capability for managing data in Apache Geode in-memory data grid — accessing regions, executing OQL queries, and running server-side functions. Designed for application developers and platform engineers working with high-performance in-memory data.
layout: capability
name: Apache Geode Data Management
operations:
- description: List all Geode regions
  method: GET
  name: list-regions
  path: /v1/regions
- description: Execute an OQL query
  method: GET
  name: execute-query
  path: /v1/queries
- description: List available functions
  method: GET
  name: list-functions
  path: /v1/functions
personas: []
provider_name: Apache Geode
provider_slug: apache-geode
search_terms:
- developers using geode as a fast data store for applications
- apache geode
- in-memory data grid
- execute an oql query
- caching
- list all server-side functions available in the cluster
- distributed systems
- execute an oql query against geode regions
- Application Developer
- list all regions in the apache geode data grid
- list available functions
- data grid
- platform engineering
- list functions
- list geode functions
- oql query execution
- execute query
- get all keys stored in a geode region
- server-side function execution
- Platform Engineer
- region crud operations, oql queries, and function execution
- execute oql query
- list all geode regions
- manage in-memory data with regions, queries, and functions
- get region keys
- engineers managing the geode cluster infrastructure
- apache
- list regions
- geode region management
- open source
- list geode regions
- in-memory
- high-performance in-memory data caching and distribution
- data management
slug: geode-data-management
source_filename: geode-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Geode Data Management\"\n  description: \"Unified capability for managing data in Apache Geode in-memory data grid — accessing regions, executing OQL queries, and running server-side functions. Designed for application developers and platform engineers working with high-performance in-memory data.\"\n  tags:\n    - Apache Geode\n    - In-Memory Data Grid\n    - Caching\n    - Data Management\n    - Platform Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      GEODE_REST_URL: GEODE_REST_URL\ncapability:\n  consumes:\n    - import: geode-rest\n      location: ./shared/geode-rest.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: geode-management-api\n      description: \"Unified REST API for Apache Geode data management.\"\n      resources:\n        - path: /v1/regions\n          name: regions\n          description: Geode region management\n   \
  \       operations:\n            - method: GET\n              name: list-regions\n              description: List all Geode regions\n              call: \"geode-rest.list-regions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: OQL query execution\n          operations:\n            - method: GET\n              name: execute-query\n              description: Execute an OQL query\n              call: \"geode-rest.execute-adhoc-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/functions\n          name: functions\n          description: Server-side function execution\n          operations:\n            - method: GET\n              name: list-functions\n              description: List available functions\n              call: \"geode-rest.list-functions\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: geode-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Geode data management.\"\n      tools:\n        - name: list-geode-regions\n          description: List all regions in the Apache Geode data grid\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"geode-rest.list-regions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-region-keys\n          description: Get all keys stored in a Geode region\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"geode-rest.get-region-keys\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-oql-query\n\
  \          description: Execute an OQL query against Geode regions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"geode-rest.execute-adhoc-query\"\n          with:\n            q: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-geode-functions\n          description: List all server-side functions available in the cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"geode-rest.list-functions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-geode/refs/heads/main/capabilities/geode-data-management.yaml
tags:
- Apache Geode
- In-Memory Data Grid
- Caching
- Data Management
- Platform Engineering
tools:
- description: List all regions in the Apache Geode data grid
  hints:
    openWorld: true
    readOnly: true
  name: list-geode-regions
- description: Get all keys stored in a Geode region
  hints:
    openWorld: true
    readOnly: true
  name: get-region-keys
- description: Execute an OQL query against Geode regions
  hints:
    openWorld: true
    readOnly: true
  name: execute-oql-query
- description: List all server-side functions available in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-geode-functions
---
