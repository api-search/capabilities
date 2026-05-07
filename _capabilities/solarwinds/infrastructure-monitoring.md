---
categories: []
consumed_apis: []
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
- create a new pingdom monitoring check
- list pingdom checks
- check results
- list pingdom uptime monitoring checks
- get summary average
- infrastructure monitoring
- log management
- it management
- get results
- ip address management
- application monitoring
- get check results
- get pingdom check results
- infrastructure
- observability
- get pingdom performance summary
- uptime monitoring
- list checks
- solarwinds
- create a monitored entity in orion
- create orion entity
- query orion
- create check
- database monitoring
- uptime monitoring checks
- execute a swql query
- network monitoring
- get pingdom check details
- swql query execution
- get check details
- query swis
- get check
- itsm
- execute a swql query against orion platform
slug: infrastructure-monitoring
source_filename: infrastructure-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SolarWinds Infrastructure Monitoring\n  description: Workflow for monitoring network infrastructure and website uptime combining Orion Platform SWQL queries with\n    Pingdom synthetic monitoring for network and IT operations teams.\n  tags:\n  - SolarWinds\n  - Infrastructure Monitoring\n  - Network Monitoring\n  - Uptime Monitoring\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORION_USERNAME: ORION_USERNAME\n    ORION_PASSWORD: ORION_PASSWORD\n    PINGDOM_API_TOKEN: PINGDOM_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: orion\n    baseUri: https://localhost:17774/SolarWinds/InformationService/v3/Json\n    description: SolarWinds Orion Platform SWIS REST API\n    authentication:\n      type: basic\n      username: '{{ORION_USERNAME}}'\n      password: '{{ORION_PASSWORD}}'\n    resources:\n    - name: query\n      path: /Query\n      description: SWQL query execution\n \
  \     operations:\n      - name: query-swis\n        method: GET\n        description: Execute a SWQL query\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: SWQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crud\n      path: /\n      description: CRUD operations on SWIS entities\n      operations:\n      - name: create-entity\n        method: POST\n        description: Create a SWIS entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-entity\n        method: GET\n        description: Read a SWIS entity\n        inputParameters:\n        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-entity\n        method: POST\n        description: Update a SWIS entity\n        inputParameters:\n        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-entity\n        method: DELETE\n        description: Delete a SWIS entity\n        inputParameters:\n        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoke-verb\n        method: POST\n        description: Invoke a verb on a SWIS entity\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: bulk\n      path: /BulkDelete\n      description: Bulk operations\n      operations:\n      - name: bulk-delete\n        method: POST\n        description: Delete multiple SWIS entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pingdom\n    baseUri: https://api.pingdom.com/api/3.1\n    description: Pingdom API for uptime and performance monitoring\n    authentication:\n      type: bearer\n      token: '{{PINGDOM_API_TOKEN}}'\n    resources:\n    - name: checks\n      path: /checks\n      description: Uptime and transaction checks\n      operations:\n      - name: list-checks\n        method: GET\n        description: List all checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-check\n      \
  \  method: GET\n        description: Get check details\n        inputParameters:\n        - name: checkId\n          in: path\n          type: integer\n          required: true\n          description: Check ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-check\n        method: POST\n        description: Create a new check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            host: '{{tools.host}}'\n            type: '{{tools.type}}'\n      - name: delete-check\n        method: DELETE\n        description: Delete a check\n        inputParameters:\n        - name: checkId\n          in: path\n          type: integer\n          required: true\n          description: Check ID\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /results\n      description: Check results and performance data\n      operations:\n      - name: get-results\n        method: GET\n        description: Get check results\n        inputParameters:\n        - name: checkId\n          in: path\n          type: integer\n          required: true\n          description: Check ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: summary\n      path: /summary.average\n      description: Performance summaries\n      operations:\n      - name: get-summary-average\n        method: GET\n        description: Get average performance summary\n        inputParameters:\n        - name: checkId\n          in: path\n          type: integer\n          required: true\n          description: Check ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infra-monitoring-api\n    description: Unified REST API for SolarWinds infrastructure monitoring.\n    resources:\n    - path: /v1/query\n      name: query\n      description: SWQL query execution\n      operations:\n      - method: GET\n        name: query-swis\n        description: Execute a SWQL query\n        call: orion.query-swis\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checks\n      name: checks\n      description: Uptime monitoring checks\n      operations:\n      - method: GET\n        name: list-checks\n        description: List Pingdom checks\n        call: pingdom.list-checks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-check\n        description: Get check details\n        call: pingdom.get-check\n\
  \        with:\n          checkId: rest.checkId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/results\n      name: results\n      description: Check results\n      operations:\n      - method: GET\n        name: get-results\n        description: Get check results\n        call: pingdom.get-results\n        with:\n          checkId: rest.checkId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: infra-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted infrastructure monitoring.\n    tools:\n    - name: query-orion\n      description: Execute a SWQL query against Orion Platform\n      hints:\n        readOnly: true\n      call: orion.query-swis\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-orion-entity\n      description: Create a monitored entity in Orion\n     \
  \ hints:\n        readOnly: false\n      call: orion.create-entity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-checks\n      description: List Pingdom uptime monitoring checks\n      hints:\n        readOnly: true\n      call: pingdom.list-checks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-check\n      description: Get Pingdom check details\n      hints:\n        readOnly: true\n      call: pingdom.get-check\n      with:\n        checkId: tools.checkId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-check\n      description: Create a new Pingdom monitoring check\n      hints:\n        readOnly: false\n      call: pingdom.create-check\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-check-results\n      description: Get Pingdom check results\n      hints:\n        readOnly: true\n      call: pingdom.get-results\n      with:\n    \
  \    checkId: tools.checkId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-summary-average\n      description: Get Pingdom performance summary\n      hints:\n        readOnly: true\n      call: pingdom.get-summary-average\n      with:\n        checkId: tools.checkId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
