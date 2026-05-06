---
categories: []
consumed_apis: []
description: Unified workflow for synthetic testing combining synthetics concurrency management and monitors. Used by QA engineers and SREs for managing synthetic test execution capacity and monitoring test results.
layout: capability
name: Datadog Synthetic Testing
operations:
- description: Get the on-demand concurrency cap
  method: GET
  name: GetOnDemandConcurrencyCap
  path: /v1/synthetics/concurrency-cap
- description: Set the on-demand concurrency cap
  method: POST
  name: SetOnDemandConcurrencyCap
  path: /v1/synthetics/concurrency-cap
- description: List monitors
  method: GET
  name: listMonitors
  path: /v1/monitors
- description: Create a monitor
  method: POST
  name: createMonitor
  path: /v1/monitors
- description: Get a monitor
  method: GET
  name: getMonitor
  path: /v1/monitors/{monitor_id}
- description: Update a monitor
  method: PUT
  name: updateMonitor
  path: /v1/monitors/{monitor_id}
- description: Delete a monitor
  method: DELETE
  name: deleteMonitor
  path: /v1/monitors/{monitor_id}
- description: Mute a monitor
  method: POST
  name: muteMonitor
  path: /v1/monitors/{monitor_id}/mute
- description: Validate a monitor
  method: POST
  name: validateMonitor
  path: /v1/monitors/validate
personas: []
provider_name: Datadog
provider_slug: datadog
search_terms:
- mute a synthetic test monitor
- synthetics
- delete a monitor
- get the on-demand concurrency cap
- validate a monitor
- visualizations
- analytics
- synthetics concurrency settings
- get concurrency cap
- validate monitor
- SetOnDemandConcurrencyCap
- mute a monitor
- validate synthetic monitor configurations
- unmute a synthetic test monitor
- dashboards
- get a monitor by id
- monitoring
- set a new synthetics on-demand concurrency cap
- delete monitor
- mute synthetic alert monitors
- synthetic testing
- datadog
- monitors
- create monitor
- muteMonitor
- create a synthetics alert monitor
- GetOnDemandConcurrencyCap
- deleteMonitor
- t1
- individual monitor operations
- unmute monitor
- createMonitor
- get the synthetics on-demand concurrency cap
- set concurrency cap
- qa
- validateMonitor
- monitor management for synthetic alerts
- getMonitor
- platform
- updateMonitor
- update a monitor
- validate a synthetic monitor configuration
- mute monitor
- create a monitor
- set the on-demand concurrency cap
- update monitor
- get a monitor
- get monitor
- list monitors
- listMonitors
- list monitors including synthetic alert monitors
- update a synthetics alert monitor
slug: synthetic-testing
source_filename: synthetic-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Datadog Synthetic Testing\n  description: Unified workflow for synthetic testing combining synthetics concurrency management and monitors. Used by QA\n    engineers and SREs for managing synthetic test execution capacity and monitoring test results.\n  tags:\n  - Datadog\n  - Synthetic Testing\n  - Synthetics\n  - Monitors\n  - QA\n  personas:\n  - QA Engineer\n  - SRE\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATADOG_API_KEY: DATADOG_API_KEY\n    DATADOG_APP_KEY: DATADOG_APP_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: dd-synthetics\n    baseUri: https://api.datadoghq.com\n    description: Datadog Synthetics API for managing on-demand concurrency cap settings. Sourced from datadog-api-openapi.yml\n      (2 operations on synthetics settings).\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n\
  \    resources:\n    - name: synthetics-settings\n      path: /api/v2/synthetics/settings/on_demand_concurrency_cap\n      description: Synthetics on-demand concurrency cap operations.\n      operations:\n      - name: GetOnDemandConcurrencyCap\n        method: GET\n        description: Get the on-demand concurrency cap.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: SetOnDemandConcurrencyCap\n        method: POST\n        description: Save new value for on-demand concurrency cap.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-monitors\n    baseUri: https://api.datadoghq.com\n    description: Datadog Monitors API for creating, reading, updating, deleting, muting, unmuting, and validating monitors.\n    authentication:\n      type: apikey\n   \
  \   headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: monitors\n      path: /api/v1/monitor\n      description: Monitor collection operations.\n      operations:\n      - name: createMonitor\n        method: POST\n        description: Create a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listMonitors\n        method: GET\n        description: List all monitors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor\n      path: /api/v1/monitor/{monitor_id}\n      description: Individual monitor operations.\n      operations:\n      - name: getMonitor\n        method: GET\n        description: Get a monitor.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: updateMonitor\n        method: PUT\n        description: Edit a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMonitor\n        method: DELETE\n        description: Delete a monitor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-muting\n      path: /api/v1/monitor/{monitor_id}\n      description: Mute and unmute monitor notifications.\n      operations:\n      - name: muteMonitor\n        method: POST\n        path: /api/v1/monitor/{monitor_id}/mute\n        description: Mute a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unmuteMonitor\n\
  \        method: POST\n        path: /api/v1/monitor/{monitor_id}/unmute\n        description: Unmute a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-validation\n      path: /api/v1/monitor/validate\n      description: Validate monitor configurations before creation.\n      operations:\n      - name: validateMonitor\n        method: POST\n        description: Validate a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: dd-synthetic-testing-api\n    description: Unified REST API for synthetic testing workflows combining synthetics and monitors.\n    resources:\n    - path: /v1/synthetics/concurrency-cap\n      name: synthetics-concurrency-cap\n      description:\
  \ Synthetics concurrency settings\n      operations:\n      - method: GET\n        name: GetOnDemandConcurrencyCap\n        description: Get the on-demand concurrency cap\n        call: dd-synthetics.GetOnDemandConcurrencyCap\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: SetOnDemandConcurrencyCap\n        description: Set the on-demand concurrency cap\n        call: dd-synthetics.SetOnDemandConcurrencyCap\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors\n      name: monitors\n      description: Monitor management for synthetic alerts\n      operations:\n      - method: GET\n        name: listMonitors\n        description: List monitors\n        call: dd-monitors.listMonitors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createMonitor\n        description: Create a monitor\n        call: dd-monitors.createMonitor\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}\n      name: monitor\n      description: Individual monitor operations\n      operations:\n      - method: GET\n        name: getMonitor\n        description: Get a monitor\n        call: dd-monitors.getMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: updateMonitor\n        description: Update a monitor\n        call: dd-monitors.updateMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deleteMonitor\n        description: Delete a monitor\n        call: dd-monitors.deleteMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}/mute\n      name: monitor-mute\n      description: Mute synthetic alert monitors\n      operations:\n      - method: POST\n        name: muteMonitor\n \
  \       description: Mute a monitor\n        call: dd-monitors.muteMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/validate\n      name: monitor-validate\n      description: Validate synthetic monitor configurations\n      operations:\n      - method: POST\n        name: validateMonitor\n        description: Validate a monitor\n        call: dd-monitors.validateMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: dd-synthetic-testing-mcp\n    transport: http\n    description: MCP server for AI-assisted synthetic testing workflows.\n    tools:\n    - name: get-concurrency-cap\n      description: Get the synthetics on-demand concurrency cap\n      call: dd-synthetics.GetOnDemandConcurrencyCap\n      hints:\n        readOnly: true\n    - name: set-concurrency-cap\n      description: Set a new synthetics on-demand concurrency cap\n      call: dd-synthetics.SetOnDemandConcurrencyCap\n\
  \    - name: list-monitors\n      description: List monitors including synthetic alert monitors\n      call: dd-monitors.listMonitors\n      hints:\n        readOnly: true\n    - name: get-monitor\n      description: Get a monitor by ID\n      call: dd-monitors.getMonitor\n      hints:\n        readOnly: true\n    - name: create-monitor\n      description: Create a synthetics alert monitor\n      call: dd-monitors.createMonitor\n    - name: update-monitor\n      description: Update a synthetics alert monitor\n      call: dd-monitors.updateMonitor\n      hints:\n        idempotent: true\n    - name: delete-monitor\n      description: Delete a monitor\n      call: dd-monitors.deleteMonitor\n      hints:\n        destructive: true\n    - name: mute-monitor\n      description: Mute a synthetic test monitor\n      call: dd-monitors.muteMonitor\n    - name: unmute-monitor\n      description: Unmute a synthetic test monitor\n      call: dd-monitors.unmuteMonitor\n    - name: validate-monitor\n\
  \      description: Validate a synthetic monitor configuration\n      call: dd-monitors.validateMonitor\n      hints:\n        readOnly: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/datadog/refs/heads/main/capabilities/synthetic-testing.yaml
tags:
- Datadog
- Synthetic Testing
- Synthetics
- Monitors
- QA
tools:
- description: Get the synthetics on-demand concurrency cap
  hints:
    readOnly: true
  name: get-concurrency-cap
- description: Set a new synthetics on-demand concurrency cap
  hints: {}
  name: set-concurrency-cap
- description: List monitors including synthetic alert monitors
  hints:
    readOnly: true
  name: list-monitors
- description: Get a monitor by ID
  hints:
    readOnly: true
  name: get-monitor
- description: Create a synthetics alert monitor
  hints: {}
  name: create-monitor
- description: Update a synthetics alert monitor
  hints:
    idempotent: true
  name: update-monitor
- description: Delete a monitor
  hints:
    destructive: true
  name: delete-monitor
- description: Mute a synthetic test monitor
  hints: {}
  name: mute-monitor
- description: Unmute a synthetic test monitor
  hints: {}
  name: unmute-monitor
- description: Validate a synthetic monitor configuration
  hints:
    readOnly: true
  name: validate-monitor
---
