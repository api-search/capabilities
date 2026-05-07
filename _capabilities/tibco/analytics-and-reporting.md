---
categories: []
consumed_apis: []
description: Workflow capability for data analysts and BI administrators to manage TIBCO Spotfire analytics content, data sources, users, and scheduled reporting. Enables programmatic management of the Spotfire library and automation of analytics workflows.
layout: capability
name: TIBCO Analytics and Reporting
operations:
- description: List Spotfire library items
  method: GET
  name: list-library-items
  path: /v1/library-items
- description: Get Spotfire library item details
  method: GET
  name: get-library-item
  path: /v1/library-items/{itemId}
- description: List Spotfire analyses
  method: GET
  name: list-analyses
  path: /v1/analyses
- description: List Spotfire data sources
  method: GET
  name: list-data-sources
  path: /v1/data-sources
- description: List Spotfire users
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: TIBCO
provider_slug: tibco
search_terms:
- visualization
- analytics
- enterprise software
- get spotfire library item details
- get library item
- spotfire analyses
- list spotfire analyses
- api management
- business intelligence
- integration
- list spotfire library items
- list library items
- spotfire library content
- list spotfire analyses available in the platform
- tibco
- list spotfire data source connections
- individual library item
- list users
- spotfire
- list spotfire data sources
- list spotfire library items by path or search query
- cloud
- real-time data
- list users registered in tibco spotfire
- get details for a specific spotfire library item
- data source connections
- reporting
- list analyses
- list spotfire users
- list data sources
- spotfire users
- messaging
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TIBCO Analytics and Reporting\n  description: Workflow capability for data analysts and BI administrators to manage TIBCO Spotfire analytics content, data\n    sources, users, and scheduled reporting. Enables programmatic management of the Spotfire library and automation of analytics\n    workflows.\n  tags:\n  - TIBCO\n  - Analytics\n  - Business Intelligence\n  - Reporting\n  - Spotfire\n  - Visualization\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIBCO_SPOTFIRE_TOKEN: TIBCO_SPOTFIRE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tibco-spotfire\n    baseUri: https://spotfire.cloud.tibco.com/api/rest/v1\n    description: TIBCO Spotfire Analytics REST API\n    authentication:\n      type: bearer\n      token: '{{TIBCO_SPOTFIRE_TOKEN}}'\n    resources:\n    - name: library\n      path: /library\n      description: Spotfire library management\n      operations:\n      - name:\
  \ list-library-items\n        method: GET\n        description: List Spotfire library items\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: false\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-library-item\n        method: GET\n        description: Get a specific library item\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analyses\n      path: /analyses\n      description: Spotfire analysis management\n      operations:\n      -\
  \ name: list-analyses\n        method: GET\n        description: List Spotfire analyses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-sources\n      path: /datasources\n      description: Data source connections\n      operations:\n      - name: list-data-sources\n        method: GET\n        description: List Spotfire data sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List Spotfire users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: tibco-analytics-api\n    description: Unified REST API for managing TIBCO\
  \ Spotfire analytics content and users.\n    resources:\n    - path: /v1/library-items\n      name: library-items\n      description: Spotfire library content\n      operations:\n      - method: GET\n        name: list-library-items\n        description: List Spotfire library items\n        call: tibco-spotfire.list-library-items\n        with:\n          path: rest.path\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/library-items/{itemId}\n      name: library-item-detail\n      description: Individual library item\n      operations:\n      - method: GET\n        name: get-library-item\n        description: Get Spotfire library item details\n        call: tibco-spotfire.get-library-item\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analyses\n      name: analyses\n      description: Spotfire analyses\n      operations:\n  \
  \    - method: GET\n        name: list-analyses\n        description: List Spotfire analyses\n        call: tibco-spotfire.list-analyses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-sources\n      name: data-sources\n      description: Data source connections\n      operations:\n      - method: GET\n        name: list-data-sources\n        description: List Spotfire data sources\n        call: tibco-spotfire.list-data-sources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Spotfire users\n      operations:\n      - method: GET\n        name: list-users\n        description: List Spotfire users\n        call: tibco-spotfire.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: tibco-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted TIBCO Spotfire\
  \ analytics management and content discovery.\n    tools:\n    - name: list-library-items\n      description: List Spotfire library items by path or search query\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-spotfire.list-library-items\n      with:\n        path: tools.path\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-library-item\n      description: Get details for a specific Spotfire library item\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-spotfire.get-library-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analyses\n      description: List Spotfire analyses available in the platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-spotfire.list-analyses\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-data-sources\n      description: List Spotfire data source connections\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-spotfire.list-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spotfire-users\n      description: List users registered in TIBCO Spotfire\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-spotfire.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tibco/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- TIBCO
- Analytics
- Business Intelligence
- Reporting
- Spotfire
- Visualization
tools:
- description: List Spotfire library items by path or search query
  hints:
    openWorld: false
    readOnly: true
  name: list-library-items
- description: Get details for a specific Spotfire library item
  hints:
    openWorld: false
    readOnly: true
  name: get-library-item
- description: List Spotfire analyses available in the platform
  hints:
    openWorld: false
    readOnly: true
  name: list-analyses
- description: List Spotfire data source connections
  hints:
    openWorld: false
    readOnly: true
  name: list-data-sources
- description: List users registered in TIBCO Spotfire
  hints:
    openWorld: false
    readOnly: true
  name: list-spotfire-users
---
