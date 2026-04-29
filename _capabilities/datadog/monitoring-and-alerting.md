---
categories:
- monitoring
consumed_apis:
- dd-monitors
- dd-metrics
- dd-hosts
- dd-dashboards
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
- mute monitor
- t1
- get a monitor
- analytics
- query timeseries
- infrastructure
- query timeseries data
- update monitor
- mute a monitor
- get csm hosts and containers coverage
- getMonitor
- unmute monitor
- host coverage
- listActiveMetrics
- get hosts coverage
- list monitors
- create a new monitor
- fetch dashboards in a dashboard list
- query timeseries metric data
- updateMonitor
- submit metrics
- delete monitor
- edit an existing monitor
- muteMonitor
- update a monitor
- GetDashboardListItems
- active metrics
- monitoring
- get dashboards in a list
- create monitor
- platform
- deleteMonitor
- query scalar metric data
- submit metric data points
- get a monitor by id
- create a monitor
- mute a monitor to suppress notifications
- list active metrics
- createMonitor
- query scalar
- monitor management
- validate a monitor configuration
- get monitor
- visualizations
- dashboard list items
- unmute a monitor to resume notifications
- listMonitors
- queryMetricsTimeseries
- add dashboards to a dashboard list
- alerting
- individual monitor operations
- validate monitor
- dashboards
- GetCSMHostsAndContainersCoverageAnalysis
- delete a monitor
- metrics
- submitMetrics
- datadog
- list all monitors
- add dashboard list items
- get dashboard list items
slug: monitoring-and-alerting
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Datadog Monitoring And Alerting\"\n  description: \"Unified workflow for infrastructure monitoring and alerting combining monitors, metrics, hosts, and dashboards. Used by SREs and DevOps engineers for setting up alerts, querying metrics, tracking host health, and organizing dashboards.\"\n  tags:\n    - Datadog\n    - Monitoring\n    - Alerting\n    - Metrics\n    - Dashboards\n    - Infrastructure\n  personas:\n    - SRE\n    - DevOps Engineer\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DATADOG_API_KEY: DATADOG_API_KEY\n      DATADOG_APP_KEY: DATADOG_APP_KEY\n\ncapability:\n  consumes:\n    - import: dd-monitors\n      location: \"./shared/monitors.yaml\"\n    - import: dd-metrics\n      location: \"./shared/metrics.yaml\"\n    - import: dd-hosts\n      location: \"./shared/hosts.yaml\"\n    - import: dd-dashboards\n      location: \"./shared/dashboards.yaml\"\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: dd-monitoring-alerting-api\n      description: \"Unified REST API for monitoring and alerting workflows combining monitors, metrics, hosts, and dashboards.\"\n      resources:\n        - path: /v1/monitors\n          name: monitors\n          description: \"Monitor management\"\n          operations:\n            - method: GET\n              name: listMonitors\n              description: \"List all monitors\"\n              call: \"dd-monitors.listMonitors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createMonitor\n              description: \"Create a monitor\"\n              call: \"dd-monitors.createMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{monitor_id}\n          name: monitor\n          description: \"Individual monitor operations\"\
  \n          operations:\n            - method: GET\n              name: getMonitor\n              description: \"Get a monitor\"\n              call: \"dd-monitors.getMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: updateMonitor\n              description: \"Update a monitor\"\n              call: \"dd-monitors.updateMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: deleteMonitor\n              description: \"Delete a monitor\"\n              call: \"dd-monitors.deleteMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{monitor_id}/mute\n          name: monitor-mute\n          description: \"Mute a monitor\"\n          operations:\n            - method: POST\n              name: muteMonitor\n\
  \              description: \"Mute a monitor\"\n              call: \"dd-monitors.muteMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Active metrics\"\n          operations:\n            - method: GET\n              name: listActiveMetrics\n              description: \"List active metrics\"\n              call: \"dd-metrics.listActiveMetrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/query/timeseries\n          name: metrics-timeseries\n          description: \"Query timeseries\"\n          operations:\n            - method: POST\n              name: queryMetricsTimeseries\n              description: \"Query timeseries data\"\n              call: \"dd-metrics.queryMetricsTimeseries\"\n              outputParameters:\n                - type: object\n          \
  \        mapping: \"$.\"\n        - path: /v1/metrics/series\n          name: metrics-submit\n          description: \"Submit metrics\"\n          operations:\n            - method: POST\n              name: submitMetrics\n              description: \"Submit metrics\"\n              call: \"dd-metrics.submitMetrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts/coverage\n          name: hosts-coverage\n          description: \"Host coverage\"\n          operations:\n            - method: GET\n              name: GetCSMHostsAndContainersCoverageAnalysis\n              description: \"Get hosts coverage\"\n              call: \"dd-hosts.GetCSMHostsAndContainersCoverageAnalysis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboard-lists/{dashboard_list_id}/dashboards\n          name: dashboard-list-items\n          description: \"\
  Dashboard list items\"\n          operations:\n            - method: GET\n              name: GetDashboardListItems\n              description: \"Get dashboards in a list\"\n              call: \"dd-dashboards.GetDashboardListItems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: dd-monitoring-alerting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted monitoring and alerting workflows.\"\n      tools:\n        - name: list-monitors\n          description: \"List all monitors\"\n          call: \"dd-monitors.listMonitors\"\n          hints:\n            readOnly: true\n        - name: get-monitor\n          description: \"Get a monitor by ID\"\n          call: \"dd-monitors.getMonitor\"\n          hints:\n            readOnly: true\n        - name: create-monitor\n          description: \"Create a new monitor\"\n          call: \"dd-monitors.createMonitor\"\
  \n        - name: update-monitor\n          description: \"Edit an existing monitor\"\n          call: \"dd-monitors.updateMonitor\"\n          hints:\n            idempotent: true\n        - name: delete-monitor\n          description: \"Delete a monitor\"\n          call: \"dd-monitors.deleteMonitor\"\n          hints:\n            destructive: true\n        - name: mute-monitor\n          description: \"Mute a monitor to suppress notifications\"\n          call: \"dd-monitors.muteMonitor\"\n        - name: unmute-monitor\n          description: \"Unmute a monitor to resume notifications\"\n          call: \"dd-monitors.unmuteMonitor\"\n        - name: validate-monitor\n          description: \"Validate a monitor configuration\"\n          call: \"dd-monitors.validateMonitor\"\n          hints:\n            readOnly: true\n        - name: submit-metrics\n          description: \"Submit metric data points\"\n          call: \"dd-metrics.submitMetrics\"\n        - name: query-timeseries\n\
  \          description: \"Query timeseries metric data\"\n          call: \"dd-metrics.queryMetricsTimeseries\"\n          hints:\n            readOnly: true\n        - name: query-scalar\n          description: \"Query scalar metric data\"\n          call: \"dd-metrics.queryMetricsScalar\"\n          hints:\n            readOnly: true\n        - name: list-active-metrics\n          description: \"List active metrics\"\n          call: \"dd-metrics.listActiveMetrics\"\n          hints:\n            readOnly: true\n        - name: get-hosts-coverage\n          description: \"Get CSM hosts and containers coverage\"\n          call: \"dd-hosts.GetCSMHostsAndContainersCoverageAnalysis\"\n          hints:\n            readOnly: true\n        - name: get-dashboard-list-items\n          description: \"Fetch dashboards in a dashboard list\"\n          call: \"dd-dashboards.GetDashboardListItems\"\n          hints:\n            readOnly: true\n        - name: add-dashboard-list-items\n        \
  \  description: \"Add dashboards to a dashboard list\"\n          call: \"dd-dashboards.CreateDashboardListItems\"\n"
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
