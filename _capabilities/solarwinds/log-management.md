---
categories: []
consumed_apis: []
description: Workflow for centralized log management combining Loggly cloud log aggregation with Papertrail log search and system management for DevOps and operations teams.
layout: capability
name: SolarWinds Log Management
operations:
- description: Search Loggly log events
  method: GET
  name: loggly-search-events
  path: /v1/loggly-search
- description: Search Papertrail log events
  method: GET
  name: papertrail-search-events
  path: /v1/papertrail-search
- description: List log-sending systems
  method: GET
  name: list-systems
  path: /v1/systems
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- list papertrail log-sending systems
- papertrail list saved searches
- papertrail list systems
- loggly search
- log management
- list log-sending systems
- get loggly account information
- it management
- papertrail list groups
- ip address management
- application monitoring
- loggly get account info
- papertrail system management
- infrastructure
- papertrail search
- papertrail
- observability
- papertrail log search
- list papertrail saved searches
- search loggly log events
- solarwinds
- loggly get events
- loggly log search
- loggly search events
- database monitoring
- list papertrail system groups
- search papertrail log events
- list systems
- network monitoring
- papertrail search events
- itsm
- loggly
- retrieve loggly search results by rsid
slug: log-management
source_filename: log-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SolarWinds Log Management\n  description: Workflow for centralized log management combining Loggly cloud log aggregation with Papertrail log search and\n    system management for DevOps and operations teams.\n  tags:\n  - SolarWinds\n  - Log Management\n  - Loggly\n  - Papertrail\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LOGGLY_API_TOKEN: LOGGLY_API_TOKEN\n    PAPERTRAIL_API_TOKEN: PAPERTRAIL_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: loggly\n    baseUri: https://logs-01.loggly.com/apiv2\n    description: Loggly API for log search and retrieval\n    authentication:\n      type: bearer\n      token: '{{LOGGLY_API_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      description: Log search\n      operations:\n      - name: search-events\n        method: GET\n        description: Initiate a log search query\n        inputParameters:\n        - name:\
  \ q\n          in: query\n          type: string\n          required: true\n          description: Search query string\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start time\n        - name: until\n          in: query\n          type: string\n          required: false\n          description: End time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-events\n        method: GET\n        description: Retrieve search results\n        inputParameters:\n        - name: rsid\n          in: path\n          type: string\n          required: true\n          description: Search result set ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account\n      path: /customer\n      description: Account management\n      operations:\n      - name:\
  \ get-account-info\n        method: GET\n        description: Get account information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: papertrail\n    baseUri: https://papertrailapp.com/api/v1\n    description: Papertrail HTTP API for log management\n    authentication:\n      type: apikey\n      key: X-Papertrail-Token\n      value: '{{PAPERTRAIL_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: events\n      path: /events/search.json\n      description: Log event search\n      operations:\n      - name: search-events\n        method: GET\n        description: Search log events\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: system_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by\
  \ system\n        - name: group_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems\n      path: /systems.json\n      description: System management\n      operations:\n      - name: list-systems\n        method: GET\n        description: List log-sending systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-system\n        method: POST\n        description: Register a new system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            system:\n              name: '{{tools.name}}'\n    - name: groups\n      path: /groups.json\n      description:\
  \ Group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List system groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saved-searches\n      path: /searches.json\n      description: Saved search management\n      operations:\n      - name: list-saved-searches\n        method: GET\n        description: List saved searches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: log-management-api\n    description: Unified REST API for SolarWinds log management.\n    resources:\n    - path: /v1/loggly-search\n      name: loggly-search\n      description: Loggly log search\n      operations:\n      - method: GET\n        name: loggly-search-events\n        description: Search Loggly log events\n        call: loggly.search-events\n\
  \        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/papertrail-search\n      name: papertrail-search\n      description: Papertrail log search\n      operations:\n      - method: GET\n        name: papertrail-search-events\n        description: Search Papertrail log events\n        call: papertrail.search-events\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/systems\n      name: systems\n      description: Papertrail system management\n      operations:\n      - method: GET\n        name: list-systems\n        description: List log-sending systems\n        call: papertrail.list-systems\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: log-management-mcp\n    transport: http\n    description: MCP server for AI-assisted log management.\n    tools:\n    - name: loggly-search\n\
  \      description: Search Loggly log events\n      hints:\n        readOnly: true\n      call: loggly.search-events\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loggly-get-events\n      description: Retrieve Loggly search results by RSID\n      hints:\n        readOnly: true\n      call: loggly.get-events\n      with:\n        rsid: tools.rsid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loggly-get-account-info\n      description: Get Loggly account information\n      hints:\n        readOnly: true\n      call: loggly.get-account-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: papertrail-search\n      description: Search Papertrail log events\n      hints:\n        readOnly: true\n      call: papertrail.search-events\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: papertrail-list-systems\n\
  \      description: List Papertrail log-sending systems\n      hints:\n        readOnly: true\n      call: papertrail.list-systems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: papertrail-list-groups\n      description: List Papertrail system groups\n      hints:\n        readOnly: true\n      call: papertrail.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: papertrail-list-saved-searches\n      description: List Papertrail saved searches\n      hints:\n        readOnly: true\n      call: papertrail.list-saved-searches\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solarwinds/refs/heads/main/capabilities/log-management.yaml
tags:
- SolarWinds
- Log Management
- Loggly
- Papertrail
tools:
- description: Search Loggly log events
  hints:
    readOnly: true
  name: loggly-search
- description: Retrieve Loggly search results by RSID
  hints:
    readOnly: true
  name: loggly-get-events
- description: Get Loggly account information
  hints:
    readOnly: true
  name: loggly-get-account-info
- description: Search Papertrail log events
  hints:
    readOnly: true
  name: papertrail-search
- description: List Papertrail log-sending systems
  hints:
    readOnly: true
  name: papertrail-list-systems
- description: List Papertrail system groups
  hints:
    readOnly: true
  name: papertrail-list-groups
- description: List Papertrail saved searches
  hints:
    readOnly: true
  name: papertrail-list-saved-searches
---
