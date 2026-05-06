---
categories: []
consumed_apis: []
description: Workflow capability for defense logistics intelligence using the RTX EAGLE platform. Combines data source management, analytics job monitoring, and report generation for logistics support analysis (LSA) workflows. Serves logistics engineers, program managers, and defense operations teams managing the lifecycle of complex defense systems.
layout: capability
name: RTX Logistics Intelligence
operations:
- description: List all configured intelligence data sources
  method: GET
  name: list-data-sources
  path: /v1/data-sources
- description: List analytics jobs and statuses
  method: GET
  name: list-analytics
  path: /v1/analytics
- description: List generated intelligence reports
  method: GET
  name: list-reports
  path: /v1/reports
personas: []
provider_name: RTX
provider_slug: rtx
search_terms:
- intelligence
- logistics
- intelligence and logistics reports
- list analytics
- defense
- analytics jobs for logistics data
- list analytics jobs
- analytics
- list analytics jobs and statuses
- list data sources
- government
- list all intelligence and logistics data sources configured in the rtx eagle platform
- list generated intelligence reports
- list reports
- aerospace
- rtx
- intelligence and logistics data sources
- list all analytics jobs and their current status in rtx eagle
- raytheon
- military
- list all configured intelligence data sources
- list generated intelligence and logistics reports available for review
slug: logistics-intelligence
source_filename: logistics-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RTX Logistics Intelligence\n  description: Workflow capability for defense logistics intelligence using the RTX EAGLE platform. Combines data source management,\n    analytics job monitoring, and report generation for logistics support analysis (LSA) workflows. Serves logistics engineers,\n    program managers, and defense operations teams managing the lifecycle of complex defense systems.\n  tags:\n  - Defense\n  - Logistics\n  - Intelligence\n  - Analytics\n  - RTX\n  - Raytheon\n  - Government\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RTX_EAGLE_API_TOKEN: RTX_EAGLE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: eagle-api\n    baseUri: https://api.rtx.com/eagle\n    description: RTX EAGLE logistics support analysis API\n    authentication:\n      type: bearer\n      token: '{{RTX_EAGLE_API_TOKEN}}'\n    resources:\n    - name: data-sources\n      path: /data-sources\n\
  \      description: Manage and query intelligence data sources\n      operations:\n      - name: list-data-sources\n        method: GET\n        description: List configured data sources available for intelligence analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /analytics\n      description: Run analytics jobs and retrieve analysis results\n      operations:\n      - name: list-analytics-jobs\n        method: GET\n        description: List analytics jobs and their statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Generate and retrieve intelligence reports\n      operations:\n      - name: list-reports\n        method: GET\n        description: List generated intelligence reports\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: logistics-intelligence-api\n    description: Unified REST API for RTX EAGLE logistics intelligence workflows.\n    resources:\n    - path: /v1/data-sources\n      name: data-sources\n      description: Intelligence and logistics data sources\n      operations:\n      - method: GET\n        name: list-data-sources\n        description: List all configured intelligence data sources\n        call: eagle-api.list-data-sources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics\n      name: analytics\n      description: Analytics jobs for logistics data\n      operations:\n      - method: GET\n        name: list-analytics\n        description: List analytics jobs and statuses\n        call: eagle-api.list-analytics-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/reports\n      name: reports\n      description: Intelligence and logistics reports\n      operations:\n      - method: GET\n        name: list-reports\n        description: List generated intelligence reports\n        call: eagle-api.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: logistics-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted RTX EAGLE logistics intelligence workflows.\n    tools:\n    - name: list-data-sources\n      description: List all intelligence and logistics data sources configured in the RTX EAGLE platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eagle-api.list-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analytics-jobs\n      description: List all analytics jobs and their current status in RTX EAGLE\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: eagle-api.list-analytics-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List generated intelligence and logistics reports available for review\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eagle-api.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rtx/refs/heads/main/capabilities/logistics-intelligence.yaml
tags:
- Defense
- Logistics
- Intelligence
- Analytics
- RTX
- Raytheon
- Government
tools:
- description: List all intelligence and logistics data sources configured in the RTX EAGLE platform
  hints:
    openWorld: false
    readOnly: true
  name: list-data-sources
- description: List all analytics jobs and their current status in RTX EAGLE
  hints:
    openWorld: false
    readOnly: true
  name: list-analytics-jobs
- description: List generated intelligence and logistics reports available for review
  hints:
    openWorld: false
    readOnly: true
  name: list-reports
---
