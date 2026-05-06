---
categories:
- monitoring
consumed_apis: []
description: Unified workflow for infrastructure monitoring and alerting combining monitors, metrics, hosts, and dashboards. Used by SREs and DevOps engineers for setting up alerts, querying metrics, tracking host health, and organizing dashboards.
layout: capability
name: Datadog Monitoring And Alerting
operations:
- description: List all monitors
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
- description: List active metrics
  method: GET
  name: listActiveMetrics
  path: /v1/metrics
- description: Query timeseries data
  method: POST
  name: queryMetricsTimeseries
  path: /v1/metrics/query/timeseries
- description: Submit metrics
  method: POST
  name: submitMetrics
  path: /v1/metrics/series
- description: Get hosts coverage
  method: GET
  name: GetCSMHostsAndContainersCoverageAnalysis
  path: /v1/hosts/coverage
- description: Get dashboards in a list
  method: GET
  name: GetDashboardListItems
  path: /v1/dashboard-lists/{dashboard_list_id}/dashboards
personas: []
provider_name: Datadog
provider_slug: datadog
search_terms:
- monitor management
- delete a monitor
- listActiveMetrics
- queryMetricsTimeseries
- get monitor
- unmute a monitor to resume notifications
- validate a monitor configuration
- infrastructure
- GetCSMHostsAndContainersCoverageAnalysis
- analytics
- visualizations
- submitMetrics
- validate monitor
- mute a monitor
- GetDashboardListItems
- get csm hosts and containers coverage
- metrics
- dashboards
- get a monitor by id
- alerting
- list monitors
- monitoring
- delete monitor
- query timeseries data
- mute a monitor to suppress notifications
- datadog
- submit metric data points
- create monitor
- muteMonitor
- submit metrics
- deleteMonitor
- query timeseries metric data
- t1
- query timeseries
- host coverage
- individual monitor operations
- unmute monitor
- query scalar metric data
- createMonitor
- query scalar
- edit an existing monitor
- list active metrics
- getMonitor
- fetch dashboards in a dashboard list
- dashboard list items
- updateMonitor
- update a monitor
- get dashboard list items
- platform
- get hosts coverage
- get dashboards in a list
- create a new monitor
- create a monitor
- mute monitor
- add dashboards to a dashboard list
- add dashboard list items
- update monitor
- get a monitor
- list all monitors
- active metrics
- listMonitors
slug: monitoring-and-alerting
source_filename: monitoring-and-alerting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Datadog Monitoring And Alerting\n  description: Unified workflow for infrastructure monitoring and alerting combining monitors, metrics, hosts, and dashboards.\n    Used by SREs and DevOps engineers for setting up alerts, querying metrics, tracking host health, and organizing dashboards.\n  tags:\n  - Datadog\n  - Monitoring\n  - Alerting\n  - Metrics\n  - Dashboards\n  - Infrastructure\n  personas:\n  - SRE\n  - DevOps Engineer\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATADOG_API_KEY: DATADOG_API_KEY\n    DATADOG_APP_KEY: DATADOG_APP_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: dd-monitors\n    baseUri: https://api.datadoghq.com\n    description: Datadog Monitors API for creating, reading, updating, deleting, muting, unmuting, and validating monitors.\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY:\
  \ '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: monitors\n      path: /api/v1/monitor\n      description: Monitor collection operations.\n      operations:\n      - name: createMonitor\n        method: POST\n        description: Create a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listMonitors\n        method: GET\n        description: List all monitors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor\n      path: /api/v1/monitor/{monitor_id}\n      description: Individual monitor operations.\n      operations:\n      - name: getMonitor\n        method: GET\n        description: Get a monitor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateMonitor\n\
  \        method: PUT\n        description: Edit a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMonitor\n        method: DELETE\n        description: Delete a monitor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-muting\n      path: /api/v1/monitor/{monitor_id}\n      description: Mute and unmute monitor notifications.\n      operations:\n      - name: muteMonitor\n        method: POST\n        path: /api/v1/monitor/{monitor_id}/mute\n        description: Mute a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unmuteMonitor\n        method: POST\n        path: /api/v1/monitor/{monitor_id}/unmute\n     \
  \   description: Unmute a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-validation\n      path: /api/v1/monitor/validate\n      description: Validate monitor configurations before creation.\n      operations:\n      - name: validateMonitor\n        method: POST\n        description: Validate a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-metrics\n    baseUri: https://api.datadoghq.com\n    description: Datadog Metrics API for submitting, querying, and managing metrics and tag configurations.\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: metrics-submit\n\
  \      path: /api/v2/series\n      description: Submit metric data points.\n      operations:\n      - name: submitMetrics\n        method: POST\n        description: Submit metrics.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-query\n      path: /api/v2/query\n      description: Query metric data.\n      operations:\n      - name: queryMetricsTimeseries\n        method: POST\n        path: /api/v2/query/timeseries\n        description: Query timeseries data.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: queryMetricsScalar\n        method: POST\n        path: /api/v2/query/scalar\n        description: Query scalar data.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: metrics-list\n      path: /api/v1/metrics\n      description: List active metrics.\n      operations:\n      - name: listActiveMetrics\n        method: GET\n        description: List active metrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-tags\n      path: /api/v2/metrics/{metric_name}/tags\n      description: Manage metric tag configurations.\n      operations:\n      - name: getMetricTagConfiguration\n        method: GET\n        description: List tags by metric name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createMetricTagConfiguration\n        method: POST\n        description: Create a tag configuration.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateMetricTagConfiguration\n        method: PATCH\n        description: Update a tag configuration.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMetricTagConfiguration\n        method: DELETE\n        description: Delete a tag configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-hosts\n    baseUri: https://api.datadoghq.com\n    description: Datadog Hosts and Containers API for CSM coverage analysis. Sourced from datadog-api-openapi.yml (1 operation\n      for hosts and containers coverage).\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n\
  \    resources:\n    - name: hosts-coverage\n      path: /api/v2/csm/onboarding/coverage_analysis/hosts_and_containers\n      description: Host and container coverage analysis.\n      operations:\n      - name: GetCSMHostsAndContainersCoverageAnalysis\n        method: GET\n        description: Get CSM hosts and containers coverage analysis.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-dashboards\n    baseUri: https://api.datadoghq.com\n    description: Datadog Dashboard List Items API for managing dashboards within dashboard lists. Sourced from datadog-api-openapi.yml\n      (4 operations on dashboard list items).\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: dashboard-list-items\n      path: /api/v2/dashboard/lists/manual/{dashboard_list_id}/dashboards\n\
  \      description: Dashboard list item operations.\n      operations:\n      - name: GetDashboardListItems\n        method: GET\n        description: Fetch the dashboard list's dashboard definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateDashboardListItems\n        method: POST\n        description: Add dashboards to an existing dashboard list.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UpdateDashboardListItems\n        method: PUT\n        description: Update dashboards of an existing dashboard list.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteDashboardListItems\n        method: DELETE\n        description:\
  \ Delete dashboards from an existing dashboard list.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dd-monitoring-alerting-api\n    description: Unified REST API for monitoring and alerting workflows combining monitors, metrics, hosts, and dashboards.\n    resources:\n    - path: /v1/monitors\n      name: monitors\n      description: Monitor management\n      operations:\n      - method: GET\n        name: listMonitors\n        description: List all monitors\n        call: dd-monitors.listMonitors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createMonitor\n        description: Create a monitor\n        call: dd-monitors.createMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}\n\
  \      name: monitor\n      description: Individual monitor operations\n      operations:\n      - method: GET\n        name: getMonitor\n        description: Get a monitor\n        call: dd-monitors.getMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: updateMonitor\n        description: Update a monitor\n        call: dd-monitors.updateMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deleteMonitor\n        description: Delete a monitor\n        call: dd-monitors.deleteMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}/mute\n      name: monitor-mute\n      description: Mute a monitor\n      operations:\n      - method: POST\n        name: muteMonitor\n        description: Mute a monitor\n        call: dd-monitors.muteMonitor\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Active metrics\n      operations:\n      - method: GET\n        name: listActiveMetrics\n        description: List active metrics\n        call: dd-metrics.listActiveMetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/query/timeseries\n      name: metrics-timeseries\n      description: Query timeseries\n      operations:\n      - method: POST\n        name: queryMetricsTimeseries\n        description: Query timeseries data\n        call: dd-metrics.queryMetricsTimeseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/series\n      name: metrics-submit\n      description: Submit metrics\n      operations:\n      - method: POST\n        name: submitMetrics\n        description: Submit metrics\n        call: dd-metrics.submitMetrics\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/hosts/coverage\n      name: hosts-coverage\n      description: Host coverage\n      operations:\n      - method: GET\n        name: GetCSMHostsAndContainersCoverageAnalysis\n        description: Get hosts coverage\n        call: dd-hosts.GetCSMHostsAndContainersCoverageAnalysis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboard-lists/{dashboard_list_id}/dashboards\n      name: dashboard-list-items\n      description: Dashboard list items\n      operations:\n      - method: GET\n        name: GetDashboardListItems\n        description: Get dashboards in a list\n        call: dd-dashboards.GetDashboardListItems\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: dd-monitoring-alerting-mcp\n    transport: http\n    description: MCP server for AI-assisted monitoring and alerting workflows.\n    tools:\n    - name: list-monitors\n      description: List\
  \ all monitors\n      call: dd-monitors.listMonitors\n      hints:\n        readOnly: true\n    - name: get-monitor\n      description: Get a monitor by ID\n      call: dd-monitors.getMonitor\n      hints:\n        readOnly: true\n    - name: create-monitor\n      description: Create a new monitor\n      call: dd-monitors.createMonitor\n    - name: update-monitor\n      description: Edit an existing monitor\n      call: dd-monitors.updateMonitor\n      hints:\n        idempotent: true\n    - name: delete-monitor\n      description: Delete a monitor\n      call: dd-monitors.deleteMonitor\n      hints:\n        destructive: true\n    - name: mute-monitor\n      description: Mute a monitor to suppress notifications\n      call: dd-monitors.muteMonitor\n    - name: unmute-monitor\n      description: Unmute a monitor to resume notifications\n      call: dd-monitors.unmuteMonitor\n    - name: validate-monitor\n      description: Validate a monitor configuration\n      call: dd-monitors.validateMonitor\n\
  \      hints:\n        readOnly: true\n    - name: submit-metrics\n      description: Submit metric data points\n      call: dd-metrics.submitMetrics\n    - name: query-timeseries\n      description: Query timeseries metric data\n      call: dd-metrics.queryMetricsTimeseries\n      hints:\n        readOnly: true\n    - name: query-scalar\n      description: Query scalar metric data\n      call: dd-metrics.queryMetricsScalar\n      hints:\n        readOnly: true\n    - name: list-active-metrics\n      description: List active metrics\n      call: dd-metrics.listActiveMetrics\n      hints:\n        readOnly: true\n    - name: get-hosts-coverage\n      description: Get CSM hosts and containers coverage\n      call: dd-hosts.GetCSMHostsAndContainersCoverageAnalysis\n      hints:\n        readOnly: true\n    - name: get-dashboard-list-items\n      description: Fetch dashboards in a dashboard list\n      call: dd-dashboards.GetDashboardListItems\n      hints:\n        readOnly: true\n    - name:\
  \ add-dashboard-list-items\n      description: Add dashboards to a dashboard list\n      call: dd-dashboards.CreateDashboardListItems\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/datadog/refs/heads/main/capabilities/monitoring-and-alerting.yaml
tags:
- Datadog
- Monitoring
- Alerting
- Metrics
- Dashboards
- Infrastructure
tools:
- description: List all monitors
  hints:
    readOnly: true
  name: list-monitors
- description: Get a monitor by ID
  hints:
    readOnly: true
  name: get-monitor
- description: Create a new monitor
  hints: {}
  name: create-monitor
- description: Edit an existing monitor
  hints:
    idempotent: true
  name: update-monitor
- description: Delete a monitor
  hints:
    destructive: true
  name: delete-monitor
- description: Mute a monitor to suppress notifications
  hints: {}
  name: mute-monitor
- description: Unmute a monitor to resume notifications
  hints: {}
  name: unmute-monitor
- description: Validate a monitor configuration
  hints:
    readOnly: true
  name: validate-monitor
- description: Submit metric data points
  hints: {}
  name: submit-metrics
- description: Query timeseries metric data
  hints:
    readOnly: true
  name: query-timeseries
- description: Query scalar metric data
  hints:
    readOnly: true
  name: query-scalar
- description: List active metrics
  hints:
    readOnly: true
  name: list-active-metrics
- description: Get CSM hosts and containers coverage
  hints:
    readOnly: true
  name: get-hosts-coverage
- description: Fetch dashboards in a dashboard list
  hints:
    readOnly: true
  name: get-dashboard-list-items
- description: Add dashboards to a dashboard list
  hints: {}
  name: add-dashboard-list-items
---
