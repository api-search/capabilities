---
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
- muteMonitor
- delete a monitor
- metrics
- get dashboard list items
- datadog
- visualizations
- analytics
- deleteMonitor
- query scalar metric data
- add dashboard list items
- unmute a monitor to resume notifications
- mute a monitor
- get monitor
- mute monitor
- updateMonitor
- validate monitor
- query scalar
- validate a monitor configuration
- unmute monitor
- edit an existing monitor
- query timeseries metric data
- listMonitors
- get hosts coverage
- dashboards
- submit metric data points
- platform
- query timeseries data
- t1
- delete monitor
- dashboard list items
- submitMetrics
- query timeseries
- submit metrics
- create monitor
- alerting
- GetDashboardListItems
- list all monitors
- getMonitor
- create a monitor
- list active metrics
- get dashboards in a list
- monitoring
- GetCSMHostsAndContainersCoverageAnalysis
- active metrics
- list monitors
- update monitor
- infrastructure
- get a monitor
- listActiveMetrics
- createMonitor
- update a monitor
- get csm hosts and containers coverage
- fetch dashboards in a dashboard list
- add dashboards to a dashboard list
- host coverage
- queryMetricsTimeseries
- mute a monitor to suppress notifications
- create a new monitor
- get a monitor by id
- monitor management
- individual monitor operations
slug: monitoring-and-alerting
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
