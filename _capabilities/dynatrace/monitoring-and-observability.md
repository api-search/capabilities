---
categories:
- monitoring
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
- logs
- monitoring
- ops engineering
- get metric descriptor
- list entities
- export logs for bulk retrieval
- analytics
- ingest log records into dynatrace grail
- search logs
- export logs
- delete custom metric
- search log records
- ai operations
- list events from the dynatrace environment
- get details of a specific monitored entity
- get entity details
- application security
- dynatrace
- ingest log records
- ingest custom metric data points via mint protocol
- list events
- list metrics
- ingest custom metrics
- ingest logs
- export log records
- get entity
- list monitored entities matching a selector
- aggregate log data grouped by specified fields
- observability
- search logs using dql queries
- list all available metrics
- apm
- query metric data
- list metric descriptors
- ingest logs into grail
- query metric data with selectors and time ranges
- aggregate logs by dimensions
- automation
- digital experience management
- metrics
- get descriptor for a specific metric
- delete a custom metric from the environment
- query metric data points
- get the descriptor for a specific metric
- cloud monitoring
- query metric data points with selectors and time ranges
- export log records for bulk retrieval
- query events
- query monitored entities
- list entities matching a selector
- search log records using dql queries
- application performance monitoring
- aggregate logs
- delete a custom metric
- list all available metric descriptors
- aggregate log data
- intelligence
- ingest custom metrics via mint protocol
slug: monitoring-and-observability
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Dynatrace Monitoring And Observability\"\n  description: \"Unified monitoring and observability workflow combining metrics, logs, events, and entity data for ops engineers managing infrastructure health and performance.\"\n  tags:\n    - Dynatrace\n    - Monitoring\n    - Observability\n    - Ops Engineering\n    - Metrics\n    - Logs\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n      DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\n\ncapability:\n  consumes:\n    - import: metrics-v2\n      location: ./shared/metrics-v2.yaml\n    - import: log-monitoring-v2\n      location: ./shared/log-monitoring-v2.yaml\n    - import: events-v2\n      location: ./shared/events-v2.yaml\n    - import: entities-v2\n      location: ./shared/entities-v2.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: monitoring-observability-api\n\
  \      description: \"Unified REST API for Dynatrace monitoring and observability workflows.\"\n      resources:\n        - path: /v1/metrics\n          name: metrics\n          description: \"List metric descriptors\"\n          operations:\n            - method: GET\n              name: list-metrics\n              description: \"List all available metrics\"\n              call: \"metrics-v2.list-metrics\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                metricSelector: \"rest.metricSelector\"\n                fields: \"rest.fields\"\n                writtenSince: \"rest.writtenSince\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/{metricKey}\n          name: metric-descriptor\n          description: \"Get metric descriptor\"\n          operations:\n            - method: GET\n              name: get-metric-descriptor\n\
  \              description: \"Get descriptor for a specific metric\"\n              call: \"metrics-v2.get-metric-descriptor\"\n              with:\n                metricKey: \"rest.metricKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-custom-metric\n              description: \"Delete a custom metric\"\n              call: \"metrics-v2.delete-custom-metric\"\n              with:\n                metricKey: \"rest.metricKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/query\n          name: metric-query\n          description: \"Query metric data points\"\n          operations:\n            - method: GET\n              name: query-metric-data\n              description: \"Query metric data with selectors and time ranges\"\n              call: \"metrics-v2.query-metric-data\"\n         \
  \     with:\n                metricSelector: \"rest.metricSelector\"\n                resolution: \"rest.resolution\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                entitySelector: \"rest.entitySelector\"\n                mzSelector: \"rest.mzSelector\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/ingest\n          name: metric-ingest\n          description: \"Ingest custom metrics\"\n          operations:\n            - method: POST\n              name: ingest-custom-metrics\n              description: \"Ingest custom metrics via MINT protocol\"\n              call: \"metrics-v2.ingest-custom-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/search\n          name: log-search\n          description: \"Search log records\"\n          operations:\n            - method: GET\n     \
  \         name: search-logs\n              description: \"Search logs using DQL queries\"\n              call: \"log-monitoring-v2.search-logs\"\n              with:\n                nextSliceKey: \"rest.nextSliceKey\"\n                limit: \"rest.limit\"\n                query: \"rest.query\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                sort: \"rest.sort\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/ingest\n          name: log-ingest\n          description: \"Ingest log records\"\n          operations:\n            - method: POST\n              name: ingest-logs\n              description: \"Ingest logs into Grail\"\n              call: \"log-monitoring-v2.ingest-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/aggregate\n          name:\
  \ log-aggregate\n          description: \"Aggregate log data\"\n          operations:\n            - method: GET\n              name: aggregate-logs\n              description: \"Aggregate logs by dimensions\"\n              call: \"log-monitoring-v2.aggregate-logs\"\n              with:\n                query: \"rest.query\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                groupBy: \"rest.groupBy\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/export\n          name: log-export\n          description: \"Export log records\"\n          operations:\n            - method: GET\n              name: export-logs\n              description: \"Export logs for bulk retrieval\"\n              call: \"log-monitoring-v2.export-logs\"\n              with:\n                nextSliceKey: \"rest.nextSliceKey\"\n                pageSize: \"rest.pageSize\"\
  \n                query: \"rest.query\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                sort: \"rest.sort\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Query events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List events\"\n              call: \"events-v2.list-events\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                eventSelector: \"rest.eventSelector\"\n                entitySelector: \"rest.entitySelector\"\n                eventType: \"rest.eventType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/entities\n          name: entities\n          description: \"Query monitored entities\"\n          operations:\n            - method: GET\n              name: list-entities\n              description: \"List entities matching a selector\"\n              call: \"entities-v2.list-entities\"\n              with:\n                entitySelector: \"rest.entitySelector\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                fields: \"rest.fields\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/{entityId}\n          name: entity-detail\n          description: \"Get entity details\"\n          operations:\n            - method: GET\n              name: get-entity\n              description: \"Get entity details\"\n              call: \"entities-v2.get-entity\"\n \
  \             with:\n                entityId: \"rest.entityId\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: monitoring-observability-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Dynatrace monitoring and observability.\"\n      tools:\n        - name: list-metrics\n          description: \"List all available metric descriptors\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"metrics-v2.list-metrics\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            metricSelector: \"tools.metricSelector\"\n            fields: \"tools.fields\"\n            writtenSince: \"tools.writtenSince\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metric-descriptor\n\
  \          description: \"Get the descriptor for a specific metric\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"metrics-v2.get-metric-descriptor\"\n          with:\n            metricKey: \"tools.metricKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-metric-data\n          description: \"Query metric data points with selectors and time ranges\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"metrics-v2.query-metric-data\"\n          with:\n            metricSelector: \"tools.metricSelector\"\n            resolution: \"tools.resolution\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            entitySelector: \"tools.entitySelector\"\n            mzSelector: \"tools.mzSelector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-custom-metrics\n\
  \          description: \"Ingest custom metric data points via MINT protocol\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"metrics-v2.ingest-custom-metrics\"\n          with:\n            metric_lines: \"tools.metric_lines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-custom-metric\n          description: \"Delete a custom metric from the environment\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          call: \"metrics-v2.delete-custom-metric\"\n          with:\n            metricKey: \"tools.metricKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-logs\n          description: \"Search log records using DQL queries\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  log-monitoring-v2.search-logs\"\n          with:\n            nextSliceKey: \"tools.nextSliceKey\"\n            limit: \"tools.limit\"\n            query: \"tools.query\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            sort: \"tools.sort\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-logs\n          description: \"Ingest log records into Dynatrace Grail\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"log-monitoring-v2.ingest-logs\"\n          with:\n            log_records: \"tools.log_records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: aggregate-logs\n          description: \"Aggregate log data grouped by specified fields\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-monitoring-v2.aggregate-logs\"\
  \n          with:\n            query: \"tools.query\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            groupBy: \"tools.groupBy\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-logs\n          description: \"Export log records for bulk retrieval\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-monitoring-v2.export-logs\"\n          with:\n            nextSliceKey: \"tools.nextSliceKey\"\n            pageSize: \"tools.pageSize\"\n            query: \"tools.query\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            sort: \"tools.sort\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: \"List events from the Dynatrace environment\"\n          hints:\n      \
  \      readOnly: true\n            openWorld: true\n          call: \"events-v2.list-events\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            eventSelector: \"tools.eventSelector\"\n            entitySelector: \"tools.entitySelector\"\n            eventType: \"tools.eventType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-entities\n          description: \"List monitored entities matching a selector\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.list-entities\"\n          with:\n            entitySelector: \"tools.entitySelector\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            fields: \"tools.fields\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity\n          description: \"Get details of a specific monitored entity\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.get-entity\"\n          with:\n            entityId: \"tools.entityId\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dynatrace/refs/heads/main/capabilities/monitoring-and-observability.yaml
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
