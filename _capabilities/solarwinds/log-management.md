---
categories: []
consumed_apis:
- loggly
- papertrail
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
- loggly search
- ip address management
- application monitoring
- list papertrail log-sending systems
- papertrail list systems
- list papertrail system groups
- loggly get account info
- get loggly account information
- infrastructure
- it management
- loggly get events
- papertrail log search
- search papertrail log events
- loggly search events
- log management
- solarwinds
- papertrail system management
- loggly log search
- papertrail list saved searches
- papertrail search events
- list papertrail saved searches
- observability
- list log-sending systems
- network monitoring
- papertrail
- papertrail search
- retrieve loggly search results by rsid
- loggly
- search loggly log events
- list systems
- papertrail list groups
- itsm
- database monitoring
slug: log-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SolarWinds Log Management\"\n  description: \"Workflow for centralized log management combining Loggly cloud log aggregation with Papertrail log search and system management for DevOps and operations teams.\"\n  tags:\n    - SolarWinds\n    - Log Management\n    - Loggly\n    - Papertrail\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LOGGLY_API_TOKEN: LOGGLY_API_TOKEN\n      PAPERTRAIL_API_TOKEN: PAPERTRAIL_API_TOKEN\n\ncapability:\n  consumes:\n    - import: loggly\n      location: ./shared/loggly.yaml\n    - import: papertrail\n      location: ./shared/papertrail.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: log-management-api\n      description: \"Unified REST API for SolarWinds log management.\"\n      resources:\n        - path: /v1/loggly-search\n          name: loggly-search\n          description: \"Loggly log search\"\n          operations:\n\
  \            - method: GET\n              name: loggly-search-events\n              description: \"Search Loggly log events\"\n              call: \"loggly.search-events\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/papertrail-search\n          name: papertrail-search\n          description: \"Papertrail log search\"\n          operations:\n            - method: GET\n              name: papertrail-search-events\n              description: \"Search Papertrail log events\"\n              call: \"papertrail.search-events\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems\n          name: systems\n          description: \"Papertrail system management\"\n          operations:\n            - method: GET\n              name: list-systems\n\
  \              description: \"List log-sending systems\"\n              call: \"papertrail.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: log-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted log management.\"\n      tools:\n        - name: loggly-search\n          description: \"Search Loggly log events\"\n          hints:\n            readOnly: true\n          call: \"loggly.search-events\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: loggly-get-events\n          description: \"Retrieve Loggly search results by RSID\"\n          hints:\n            readOnly: true\n          call: \"loggly.get-events\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: loggly-get-account-info\n          description: \"Get Loggly account information\"\n          hints:\n            readOnly: true\n          call: \"loggly.get-account-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: papertrail-search\n          description: \"Search Papertrail log events\"\n          hints:\n            readOnly: true\n          call: \"papertrail.search-events\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: papertrail-list-systems\n          description: \"List Papertrail log-sending systems\"\n          hints:\n            readOnly: true\n          call: \"papertrail.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: papertrail-list-groups\n          description: \"List Papertrail system groups\"\n          hints:\n\
  \            readOnly: true\n          call: \"papertrail.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: papertrail-list-saved-searches\n          description: \"List Papertrail saved searches\"\n          hints:\n            readOnly: true\n          call: \"papertrail.list-saved-searches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
