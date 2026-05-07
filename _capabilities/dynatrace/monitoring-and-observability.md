---
categories:
- monitoring
consumed_apis: []
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
- get entity details
- analytics
- list metric descriptors
- list events from the dynatrace environment
- list events
- list entities
- application security
- automation
- ingest custom metrics
- search log records using dql queries
- ai operations
- get descriptor for a specific metric
- query monitored entities
- search log records
- ingest logs
- aggregate logs
- apm
- get metric descriptor
- monitoring
- query metric data points with selectors and time ranges
- delete custom metric
- cloud monitoring
- export log records
- application performance monitoring
- logs
- list entities matching a selector
- query metric data
- observability
- aggregate log data
- aggregate logs by dimensions
- get entity
- delete a custom metric from the environment
- ingest log records into dynatrace grail
- list monitored entities matching a selector
- intelligence
- get details of a specific monitored entity
- export log records for bulk retrieval
- ingest logs into grail
- dynatrace
- search logs
- search logs using dql queries
- ops engineering
- metrics
- ingest log records
- digital experience management
- export logs for bulk retrieval
- delete a custom metric
- query metric data with selectors and time ranges
- list metrics
- aggregate log data grouped by specified fields
- list all available metrics
- ingest custom metrics via mint protocol
- list all available metric descriptors
- get the descriptor for a specific metric
- query events
- export logs
- ingest custom metric data points via mint protocol
- query metric data points
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynatrace Monitoring And Observability\n  description: Unified monitoring and observability workflow combining metrics, logs, events, and entity data for ops engineers\n    managing infrastructure health and performance.\n  tags:\n  - Dynatrace\n  - Monitoring\n  - Observability\n  - Ops Engineering\n  - Metrics\n  - Logs\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n    DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: metrics-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Metrics API v2 for querying, ingesting, and managing time-series metrics.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: metrics\n      path:\
  \ /metrics\n      description: List metric descriptors\n      operations:\n      - name: list-metrics\n        method: GET\n        description: Returns a list of all metrics available in the environment.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of metric descriptors to return per page.\n        - name: metricSelector\n          in: query\n          type: string\n          required: false\n          description: Metric selector to filter metrics.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the response.\n        - name: writtenSince\n          in: query\n          type: string\n          required: false\n          description:\
  \ Filter to metrics written since this time.\n        - name: metricDescriptors\n          in: query\n          type: boolean\n          required: false\n          description: Whether to include descriptor details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-descriptor\n      path: /metrics/{metricKey}\n      description: Get or delete a specific metric\n      operations:\n      - name: get-metric-descriptor\n        method: GET\n        description: Returns the descriptor for the specified metric key.\n        inputParameters:\n        - name: metricKey\n          in: path\n          type: string\n          required: true\n          description: The key of the metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-custom-metric\n        method: DELETE\n        description: Deletes the\
  \ specified custom metric from the environment.\n        inputParameters:\n        - name: metricKey\n          in: path\n          type: string\n          required: true\n          description: The key of the custom metric to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-query\n      path: /metrics/query\n      description: Query metric data points\n      operations:\n      - name: query-metric-data\n        method: GET\n        description: Returns data points for the specified metrics.\n        inputParameters:\n        - name: metricSelector\n          in: query\n          type: string\n          required: true\n          description: Metric selector expression.\n        - name: resolution\n          in: query\n          type: string\n          required: false\n          description: Desired time resolution, e.g., 5m, 1h.\n        - name: from\n          in: query\n        \
  \  type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n          description: Filter to entities matching this selector.\n        - name: mzSelector\n          in: query\n          type: string\n          required: false\n          description: Filter to a management zone.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-ingest\n      path: /metrics/ingest\n      description: Ingest custom metrics\n      operations:\n      - name: ingest-custom-metrics\n        method: POST\n        description: Ingests custom metric data points using MINT line protocol.\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: text\n          data: '{{tools.metric_lines}}'\n  - type: http\n    namespace: log-monitoring-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Log Monitoring API v2 for searching, ingesting, aggregating, and exporting logs.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: log-search\n      path: /logs/search\n      description: Search log records\n      operations:\n      - name: search-logs\n        method: GET\n        description: Searches log records stored in Grail using a query expression.\n        inputParameters:\n        - name: nextSliceKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of log records to return.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: DQL log search query.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order for results.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the log records.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: log-ingest\n      path: /logs/ingest\n      description: Ingest log records\n      operations:\n      - name: ingest-logs\n        method: POST\n        description: Ingests log records into the Dynatrace Grail data lakehouse.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.log_records}}'\n    - name: log-aggregate\n      path: /logs/aggregate\n      description: Aggregate log data\n      operations:\n      - name: aggregate-logs\n        method: GET\n        description: Returns aggregated log data grouped by specified fields.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Log query for filtering before aggregation.\n        - name: from\n          in: query\n          type: string\n   \
  \       required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: groupBy\n          in: query\n          type: string\n          required: false\n          description: Fields to group the aggregated results by.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: log-export\n      path: /logs/export\n      description: Export log records\n      operations:\n      - name: export-logs\n        method: GET\n        description: Exports log records for bulk retrieval.\n        inputParameters:\n        - name: nextSliceKey\n          in: query\n          type: string\n          required:\
  \ false\n          description: Cursor for the next page of export results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of log records to return per page.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Log export query for filtering.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order for export results.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the exported records.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: events-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Events API v2 for querying and ingesting custom events.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: events\n      path: /events\n      description: Query events\n      operations:\n      - name: list-events\n        method: GET\n        description: Returns a list of events matching the specified filters.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n      \
  \    description: Number of events to return per page.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: eventSelector\n          in: query\n          type: string\n          required: false\n          description: Event selector expression.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n          description: Entity selector to filter events by affected entities.\n        - name: eventType\n          in: query\n          type: string\n          required: false\n          description: Filter by event type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-detail\n      path:\
  \ /events/{eventId}\n      description: Get a specific event\n      operations:\n      - name: get-event\n        method: GET\n        description: Returns the details of a specific event by ID.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-ingest\n      path: /events/ingest\n      description: Ingest custom events\n      operations:\n      - name: ingest-event\n        method: POST\n        description: Ingests a custom event into the Dynatrace environment.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            eventType: '{{tools.event_type}}'\n\
  \            title: '{{tools.title}}'\n            entitySelector: '{{tools.entity_selector}}'\n            startTime: '{{tools.start_time}}'\n            endTime: '{{tools.end_time}}'\n            properties: '{{tools.properties}}'\n  - type: http\n    namespace: entities-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Entities API v2 for querying monitored entities and entity types.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: entities\n      path: /entities\n      description: Query monitored entities\n      operations:\n      - name: list-entities\n        method: GET\n        description: Returns a list of monitored entities matching the specified entity selector.\n        inputParameters:\n        - name: entitySelector\n          in: query\n          type: string\n          required: true\n        \
  \  description: Entity selector expression, e.g., type(SERVICE).\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of entities to return per page.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include, e.g., +properties,+tags.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the time range for entity discovery.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range for entity discovery.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description:\
  \ Sort order, e.g., +displayName or -lastSeenTms.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-detail\n      path: /entities/{entityId}\n      description: Get a specific entity by ID\n      operations:\n      - name: get-entity\n        method: GET\n        description: Returns the details of a specific monitored entity by its entity ID.\n        inputParameters:\n        - name: entityId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the entity.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the time range.\n        - name: to\n          in: query\n          type: string\n          required:\
  \ false\n          description: End of the time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-types\n      path: /entityTypes\n      description: Query entity type definitions\n      operations:\n      - name: list-entity-types\n        method: GET\n        description: Returns a list of all entity types available in the environment.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of entity types to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-type-detail\n      path: /entityTypes/{type}\n      description:\
  \ Get a specific entity type definition\n      operations:\n      - name: get-entity-type\n        method: GET\n        description: Returns the definition of a specific entity type.\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: The entity type identifier, e.g., SERVICE, HOST.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-lookup\n      path: /entities/lookup\n      description: Look up entity by name\n      operations:\n      - name: lookup-entity\n        method: POST\n        description: Looks up a specific entity by its display name and type.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  \
  \          type: '{{tools.type}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: monitoring-observability-api\n    description: Unified REST API for Dynatrace monitoring and observability workflows.\n    resources:\n    - path: /v1/metrics\n      name: metrics\n      description: List metric descriptors\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List all available metrics\n        call: metrics-v2.list-metrics\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          metricSelector: rest.metricSelector\n          fields: rest.fields\n          writtenSince: rest.writtenSince\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{metricKey}\n      name: metric-descriptor\n      description: Get metric descriptor\n      operations:\n      - method: GET\n        name: get-metric-descriptor\n        description: Get descriptor for a specific metric\n\
  \        call: metrics-v2.get-metric-descriptor\n        with:\n          metricKey: rest.metricKey\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-custom-metric\n        description: Delete a custom metric\n        call: metrics-v2.delete-custom-metric\n        with:\n          metricKey: rest.metricKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/query\n      name: metric-query\n      description: Query metric data points\n      operations:\n      - method: GET\n        name: query-metric-data\n        description: Query metric data with selectors and time ranges\n        call: metrics-v2.query-metric-data\n        with:\n          metricSelector: rest.metricSelector\n          resolution: rest.resolution\n          from: rest.from\n          to: rest.to\n          entitySelector: rest.entitySelector\n          mzSelector: rest.mzSelector\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/metrics/ingest\n      name: metric-ingest\n      description: Ingest custom metrics\n      operations:\n      - method: POST\n        name: ingest-custom-metrics\n        description: Ingest custom metrics via MINT protocol\n        call: metrics-v2.ingest-custom-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs/search\n      name: log-search\n      description: Search log records\n      operations:\n      - method: GET\n        name: search-logs\n        description: Search logs using DQL queries\n        call: log-monitoring-v2.search-logs\n        with:\n          nextSliceKey: rest.nextSliceKey\n          limit: rest.limit\n          query: rest.query\n          from: rest.from\n          to: rest.to\n          sort: rest.sort\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs/ingest\n     \
  \ name: log-ingest\n      description: Ingest log records\n      operations:\n      - method: POST\n        name: ingest-logs\n        description: Ingest logs into Grail\n        call: log-monitoring-v2.ingest-logs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs/aggregate\n      name: log-aggregate\n      description: Aggregate log data\n      operations:\n      - method: GET\n        name: aggregate-logs\n        description: Aggregate logs by dimensions\n        call: log-monitoring-v2.aggregate-logs\n        with:\n          query: rest.query\n          from: rest.from\n          to: rest.to\n          groupBy: rest.groupBy\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs/export\n      name: log-export\n      description: Export log records\n      operations:\n      - method: GET\n        name: export-logs\n        description: Export logs for bulk retrieval\n\
  \        call: log-monitoring-v2.export-logs\n        with:\n          nextSliceKey: rest.nextSliceKey\n          pageSize: rest.pageSize\n          query: rest.query\n          from: rest.from\n          to: rest.to\n          sort: rest.sort\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Query events\n      operations:\n      - method: GET\n        name: list-events\n        description: List events\n        call: events-v2.list-events\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          from: rest.from\n          to: rest.to\n          eventSelector: rest.eventSelector\n          entitySelector: rest.entitySelector\n          eventType: rest.eventType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities\n      name: entities\n      description: Query monitored entities\n\
  \      operations:\n      - method: GET\n        name: list-entities\n        description: List entities matching a selector\n        call: entities-v2.list-entities\n        with:\n          entitySelector: rest.entitySelector\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          fields: rest.fields\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{entityId}\n      name: entity-detail\n      description: Get entity details\n      operations:\n      - method: GET\n        name: get-entity\n        description: Get entity details\n        call: entities-v2.get-entity\n        with:\n          entityId: rest.entityId\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: monitoring-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ Dynatrace monitoring and observability.\n    tools:\n    - name: list-metrics\n      description: List all available metric descriptors\n      hints:\n        readOnly: true\n        openWorld: true\n      call: metrics-v2.list-metrics\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        metricSelector: tools.metricSelector\n        fields: tools.fields\n        writtenSince: tools.writtenSince\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metric-descriptor\n      description: Get the descriptor for a specific metric\n      hints:\n        readOnly: true\n        openWorld: true\n      call: metrics-v2.get-metric-descriptor\n      with:\n        metricKey: tools.metricKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-metric-data\n      description: Query metric data points with selectors and time ranges\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: metrics-v2.query-metric-data\n      with:\n        metricSelector: tools.metricSelector\n        resolution: tools.resolution\n        from: tools.from\n        to: tools.to\n        entitySelector: tools.entitySelector\n        mzSelector: tools.mzSelector\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-custom-metrics\n      description: Ingest custom metric data points via MINT protocol\n      hints:\n        readOnly: false\n        openWorld: true\n      call: metrics-v2.ingest-custom-metrics\n      with:\n        metric_lines: tools.metric_lines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-custom-metric\n      description: Delete a custom metric from the environment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      call: metrics-v2.delete-custom-metric\n      with:\n        metricKey: tools.metricKey\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-logs\n      description: Search log records using DQL queries\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-monitoring-v2.search-logs\n      with:\n        nextSliceKey: tools.nextSliceKey\n        limit: tools.limit\n        query: tools.query\n        from: tools.from\n        to: tools.to\n        sort: tools.sort\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-logs\n      description: Ingest log records into Dynatrace Grail\n      hints:\n        readOnly: false\n        openWorld: true\n      call: log-monitoring-v2.ingest-logs\n      with:\n        log_records: tools.log_records\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aggregate-logs\n      description: Aggregate log data grouped by specified fields\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-monitoring-v2.aggregate-logs\n\
  \      with:\n        query: tools.query\n        from: tools.from\n        to: tools.to\n        groupBy: tools.groupBy\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-logs\n      description: Export log records for bulk retrieval\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-monitoring-v2.export-logs\n      with:\n        nextSliceKey: tools.nextSliceKey\n        pageSize: tools.pageSize\n        query: tools.query\n        from: tools.from\n        to: tools.to\n        sort: tools.sort\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List events from the Dynatrace environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: events-v2.list-events\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        from: tools.from\n  \
  \      to: tools.to\n        eventSelector: tools.eventSelector\n        entitySelector: tools.entitySelector\n        eventType: tools.eventType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-entities\n      description: List monitored entities matching a selector\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.list-entities\n      with:\n        entitySelector: tools.entitySelector\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        fields: tools.fields\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity\n      description: Get details of a specific monitored entity\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.get-entity\n      with:\n        entityId: tools.entityId\n        fields: tools.fields\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n"
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
