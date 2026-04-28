---
categories: []
consumed_apis:
- orion
- pingdom
description: Workflow for monitoring network infrastructure and website uptime combining Orion Platform SWQL queries with Pingdom synthetic monitoring for network and IT operations teams.
layout: capability
name: SolarWinds Infrastructure Monitoring
operations:
- description: Execute a SWQL query
  method: GET
  name: query-swis
  path: /v1/query
- description: List Pingdom checks
  method: GET
  name: list-checks
  path: /v1/checks
- description: Get check details
  method: GET
  name: get-check
  path: /v1/checks
- description: Get check results
  method: GET
  name: get-results
  path: /v1/results
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- network monitoring
- get check results
- infrastructure monitoring
- check results
- get pingdom performance summary
- it management
- get pingdom check details
- create a monitored entity in orion
- create a new pingdom monitoring check
- list checks
- observability
- infrastructure
- list pingdom checks
- execute a swql query
- database monitoring
- uptime monitoring checks
- swql query execution
- solarwinds
- create check
- query orion
- query swis
- execute a swql query against orion platform
- application monitoring
- get check details
- get check
- get results
- get pingdom check results
- create orion entity
- list pingdom uptime monitoring checks
- get summary average
- log management
- uptime monitoring
- ip address management
- itsm
slug: infrastructure-monitoring
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SolarWinds Infrastructure Monitoring\"\n  description: \"Workflow for monitoring network infrastructure and website uptime combining Orion Platform SWQL queries with Pingdom synthetic monitoring for network and IT operations teams.\"\n  tags:\n    - SolarWinds\n    - Infrastructure Monitoring\n    - Network Monitoring\n    - Uptime Monitoring\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORION_USERNAME: ORION_USERNAME\n      ORION_PASSWORD: ORION_PASSWORD\n      PINGDOM_API_TOKEN: PINGDOM_API_TOKEN\n\ncapability:\n  consumes:\n    - import: orion\n      location: ./shared/orion.yaml\n    - import: pingdom\n      location: ./shared/pingdom.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: infra-monitoring-api\n      description: \"Unified REST API for SolarWinds infrastructure monitoring.\"\n      resources:\n        - path: /v1/query\n          name:\
  \ query\n          description: \"SWQL query execution\"\n          operations:\n            - method: GET\n              name: query-swis\n              description: \"Execute a SWQL query\"\n              call: \"orion.query-swis\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/checks\n          name: checks\n          description: \"Uptime monitoring checks\"\n          operations:\n            - method: GET\n              name: list-checks\n              description: \"List Pingdom checks\"\n              call: \"pingdom.list-checks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-check\n              description: \"Get check details\"\n              call: \"pingdom.get-check\"\n              with:\n                checkId: \"rest.checkId\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/results\n          name: results\n          description: \"Check results\"\n          operations:\n            - method: GET\n              name: get-results\n              description: \"Get check results\"\n              call: \"pingdom.get-results\"\n              with:\n                checkId: \"rest.checkId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: infra-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted infrastructure monitoring.\"\n      tools:\n        - name: query-orion\n          description: \"Execute a SWQL query against Orion Platform\"\n          hints:\n            readOnly: true\n          call: \"orion.query-swis\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: create-orion-entity\n          description: \"Create a monitored entity in Orion\"\n          hints:\n            readOnly: false\n          call: \"orion.create-entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-checks\n          description: \"List Pingdom uptime monitoring checks\"\n          hints:\n            readOnly: true\n          call: \"pingdom.list-checks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-check\n          description: \"Get Pingdom check details\"\n          hints:\n            readOnly: true\n          call: \"pingdom.get-check\"\n          with:\n            checkId: \"tools.checkId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-check\n          description: \"Create a new Pingdom monitoring check\"\
  \n          hints:\n            readOnly: false\n          call: \"pingdom.create-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-check-results\n          description: \"Get Pingdom check results\"\n          hints:\n            readOnly: true\n          call: \"pingdom.get-results\"\n          with:\n            checkId: \"tools.checkId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-summary-average\n          description: \"Get Pingdom performance summary\"\n          hints:\n            readOnly: true\n          call: \"pingdom.get-summary-average\"\n          with:\n            checkId: \"tools.checkId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solarwinds/refs/heads/main/capabilities/infrastructure-monitoring.yaml
tags:
- SolarWinds
- Infrastructure Monitoring
- Network Monitoring
- Uptime Monitoring
tools:
- description: Execute a SWQL query against Orion Platform
  hints:
    readOnly: true
  name: query-orion
- description: Create a monitored entity in Orion
  hints:
    readOnly: false
  name: create-orion-entity
- description: List Pingdom uptime monitoring checks
  hints:
    readOnly: true
  name: list-checks
- description: Get Pingdom check details
  hints:
    readOnly: true
  name: get-check
- description: Create a new Pingdom monitoring check
  hints:
    readOnly: false
  name: create-check
- description: Get Pingdom check results
  hints:
    readOnly: true
  name: get-check-results
- description: Get Pingdom performance summary
  hints:
    readOnly: true
  name: get-summary-average
---
