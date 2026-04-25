---
consumed_apis:
- metrics-v2
- log-monitoring-v2
- events-v2
- entities-v2
description: Unified monitoring and observability workflow combining metrics, logs, events, and entity data for ops engineers managing infrastructure health and performance.
layout: capability
name: Dynatrace Monitoring And Observability
operations:
- description: List all available metrics
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Get descriptor for a specific metric
  method: GET
  name: get-metric-descriptor
  path: /v1/metrics/{metricKey}
- description: Delete a custom metric
  method: DELETE
  name: delete-custom-metric
  path: /v1/metrics/{metricKey}
- description: Query metric data with selectors and time ranges
  method: GET
  name: query-metric-data
  path: /v1/metrics/query
- description: Ingest custom metrics via MINT protocol
  method: POST
  name: ingest-custom-metrics
  path: /v1/metrics/ingest
- description: Search logs using DQL queries
  method: GET
  name: search-logs
  path: /v1/logs/search
- description: Ingest logs into Grail
  method: POST
  name: ingest-logs
  path: /v1/logs/ingest
- description: Aggregate logs by dimensions
  method: GET
  name: aggregate-logs
  path: /v1/logs/aggregate
- description: Export logs for bulk retrieval
  method: GET
  name: export-logs
  path: /v1/logs/export
- description: List events
  method: GET
  name: list-events
  path: /v1/events
- description: List entities matching a selector
  method: GET
  name: list-entities
  path: /v1/entities
- description: Get entity details
  method: GET
  name: get-entity
  path: /v1/entities/{entityId}
personas: []
provider_name: Dynatrace
provider_slug: dynatrace
search_terms:
- aggregate logs by dimensions
- list all available metrics
- ops engineering
- get details of a specific monitored entity
- delete a custom metric
- ingest custom metrics via mint protocol
- intelligence
- automation
- list metric descriptors
- ai operations
- query metric data points
- ingest logs
- observability
- export log records
- list metrics
- export log records for bulk retrieval
- list monitored entities matching a selector
- search logs using dql queries
- search log records
- ingest custom metrics
- get descriptor for a specific metric
- search logs
- delete custom metric
- export logs
- get the descriptor for a specific metric
- delete a custom metric from the environment
- list events
- application performance monitoring
- ingest logs into grail
- monitoring
- query metric data points with selectors and time ranges
- query metric data with selectors and time ranges
- get entity details
- ingest custom metric data points via mint protocol
- aggregate log data grouped by specified fields
- list events from the dynatrace environment
- query monitored entities
- digital experience management
- export logs for bulk retrieval
- dynatrace
- aggregate log data
- query events
- search log records using dql queries
- query metric data
- ingest log records into dynatrace grail
- metrics
- logs
- get metric descriptor
- list entities matching a selector
- get entity
- aggregate logs
- analytics
- list all available metric descriptors
- cloud monitoring
- apm
- ingest log records
- list entities
- application security
slug: monitoring-and-observability
tags:
- Dynatrace
- Monitoring
- Observability
- Ops Engineering
- Metrics
- Logs
tools:
- description: List all available metric descriptors
  hints:
    openWorld: true
    readOnly: true
  name: list-metrics
- description: Get the descriptor for a specific metric
  hints:
    openWorld: true
    readOnly: true
  name: get-metric-descriptor
- description: Query metric data points with selectors and time ranges
  hints:
    openWorld: true
    readOnly: true
  name: query-metric-data
- description: Ingest custom metric data points via MINT protocol
  hints:
    openWorld: true
    readOnly: false
  name: ingest-custom-metrics
- description: Delete a custom metric from the environment
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-custom-metric
- description: Search log records using DQL queries
  hints:
    openWorld: true
    readOnly: true
  name: search-logs
- description: Ingest log records into Dynatrace Grail
  hints:
    openWorld: true
    readOnly: false
  name: ingest-logs
- description: Aggregate log data grouped by specified fields
  hints:
    openWorld: true
    readOnly: true
  name: aggregate-logs
- description: Export log records for bulk retrieval
  hints:
    openWorld: true
    readOnly: true
  name: export-logs
- description: List events from the Dynatrace environment
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: List monitored entities matching a selector
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Get details of a specific monitored entity
  hints:
    openWorld: true
    readOnly: true
  name: get-entity
---
