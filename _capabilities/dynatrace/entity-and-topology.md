---
categories: []
consumed_apis: []
description: Entity discovery and topology mapping workflow combining entities, metrics, and events for developers understanding service dependencies and infrastructure layout.
layout: capability
name: Dynatrace Entity And Topology
operations:
- description: List entities matching a selector
  method: GET
  name: list-entities
  path: /v1/entities
- description: Get entity details including topology relationships
  method: GET
  name: get-entity
  path: /v1/entities/{entityId}
- description: List all entity types
  method: GET
  name: list-entity-types
  path: /v1/entity-types
- description: Get a specific entity type definition
  method: GET
  name: get-entity-type
  path: /v1/entity-types/{type}
- description: Look up an entity by display name and type
  method: POST
  name: lookup-entity
  path: /v1/entities/lookup
- description: Query metric data for entities
  method: GET
  name: query-metric-data
  path: /v1/metrics/query
- description: List events for entities
  method: GET
  name: list-events
  path: /v1/events
- description: Ingest a deployment or custom event
  method: POST
  name: ingest-event
  path: /v1/events/ingest
personas: []
provider_name: Dynatrace
provider_slug: dynatrace
search_terms:
- analytics
- query metrics for entity performance
- get entity details including topology relationships
- list events
- list entities
- query metric data points for entities
- list events affecting entities
- ingest a deployment or custom event for an entity
- application security
- automation
- ingest a deployment or custom event
- ai operations
- list all entity types
- query monitored entities
- topology
- apm
- get a specific entity type definition
- lookup entity
- cloud monitoring
- list entity types
- look up an entity by its display name and type
- application performance monitoring
- infrastructure
- list entities matching a selector
- list all available entity types in the environment
- get the definition of a specific entity type
- query metric data
- get entity type
- look up entity by name
- get entity type definition
- list monitored entities matching a selector expression
- query entity types
- observability
- get entity
- entity management
- query metric data for entities
- intelligence
- ingest deployment events
- dynatrace
- list events for entities
- digital experience management
- get entity details with relationships
- query entity events
- ingest event
- developer
- look up an entity by display name and type
slug: entity-and-topology
source_filename: entity-and-topology.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynatrace Entity And Topology\n  description: Entity discovery and topology mapping workflow combining entities, metrics, and events for developers understanding\n    service dependencies and infrastructure layout.\n  tags:\n  - Dynatrace\n  - Entity Management\n  - Topology\n  - Developer\n  - Infrastructure\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n    DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: entities-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Entities API v2 for querying monitored entities and entity types.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: entities\n      path: /entities\n      description:\
  \ Query monitored entities\n      operations:\n      - name: list-entities\n        method: GET\n        description: Returns a list of monitored entities matching the specified entity selector.\n        inputParameters:\n        - name: entitySelector\n          in: query\n          type: string\n          required: true\n          description: Entity selector expression, e.g., type(SERVICE).\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of entities to return per page.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include, e.g., +properties,+tags.\n        - name: from\n          in: query\n          type: string\n          required: false\n        \
  \  description: Start of the time range for entity discovery.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range for entity discovery.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order, e.g., +displayName or -lastSeenTms.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-detail\n      path: /entities/{entityId}\n      description: Get a specific entity by ID\n      operations:\n      - name: get-entity\n        method: GET\n        description: Returns the details of a specific monitored entity by its entity ID.\n        inputParameters:\n        - name: entityId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the entity.\n        - name: fields\n          in:\
  \ query\n          type: string\n          required: false\n          description: Additional fields to include.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-types\n      path: /entityTypes\n      description: Query entity type definitions\n      operations:\n      - name: list-entity-types\n        method: GET\n        description: Returns a list of all entity types available in the environment.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n\
  \          in: query\n          type: integer\n          required: false\n          description: Number of entity types to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-type-detail\n      path: /entityTypes/{type}\n      description: Get a specific entity type definition\n      operations:\n      - name: get-entity-type\n        method: GET\n        description: Returns the definition of a specific entity type.\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: The entity type identifier, e.g., SERVICE, HOST.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-lookup\n      path: /entities/lookup\n      description: Look up entity by name\n      operations:\n      - name: lookup-entity\n\
  \        method: POST\n        description: Looks up a specific entity by its display name and type.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n  - type: http\n    namespace: metrics-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Metrics API v2 for querying, ingesting, and managing time-series metrics.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: metrics\n      path: /metrics\n      description: List metric descriptors\n      operations:\n      - name: list-metrics\n        method: GET\n        description: Returns a list of all metrics available in the environment.\n \
  \       inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of metric descriptors to return per page.\n        - name: metricSelector\n          in: query\n          type: string\n          required: false\n          description: Metric selector to filter metrics.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the response.\n        - name: writtenSince\n          in: query\n          type: string\n          required: false\n          description: Filter to metrics written since this time.\n        - name: metricDescriptors\n          in: query\n          type: boolean\n          required: false\n          description: Whether to include descriptor\
  \ details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-descriptor\n      path: /metrics/{metricKey}\n      description: Get or delete a specific metric\n      operations:\n      - name: get-metric-descriptor\n        method: GET\n        description: Returns the descriptor for the specified metric key.\n        inputParameters:\n        - name: metricKey\n          in: path\n          type: string\n          required: true\n          description: The key of the metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-custom-metric\n        method: DELETE\n        description: Deletes the specified custom metric from the environment.\n        inputParameters:\n        - name: metricKey\n          in: path\n          type: string\n          required: true\n          description: The key of\
  \ the custom metric to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-query\n      path: /metrics/query\n      description: Query metric data points\n      operations:\n      - name: query-metric-data\n        method: GET\n        description: Returns data points for the specified metrics.\n        inputParameters:\n        - name: metricSelector\n          in: query\n          type: string\n          required: true\n          description: Metric selector expression.\n        - name: resolution\n          in: query\n          type: string\n          required: false\n          description: Desired time resolution, e.g., 5m, 1h.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description:\
  \ End of the queried time range.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n          description: Filter to entities matching this selector.\n        - name: mzSelector\n          in: query\n          type: string\n          required: false\n          description: Filter to a management zone.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-ingest\n      path: /metrics/ingest\n      description: Ingest custom metrics\n      operations:\n      - name: ingest-custom-metrics\n        method: POST\n        description: Ingests custom metric data points using MINT line protocol.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: text\n          data: '{{tools.metric_lines}}'\n  - type: http\n    namespace:\
  \ events-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Events API v2 for querying and ingesting custom events.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: events\n      path: /events\n      description: Query events\n      operations:\n      - name: list-events\n        method: GET\n        description: Returns a list of events matching the specified filters.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of events to return per page.\n        - name: from\n          in: query\n          type: string\n          required: false\n        \
  \  description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: eventSelector\n          in: query\n          type: string\n          required: false\n          description: Event selector expression.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n          description: Entity selector to filter events by affected entities.\n        - name: eventType\n          in: query\n          type: string\n          required: false\n          description: Filter by event type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-detail\n      path: /events/{eventId}\n      description: Get a specific event\n      operations:\n      - name: get-event\n        method: GET\n        description: Returns the\
  \ details of a specific event by ID.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-ingest\n      path: /events/ingest\n      description: Ingest custom events\n      operations:\n      - name: ingest-event\n        method: POST\n        description: Ingests a custom event into the Dynatrace environment.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            eventType: '{{tools.event_type}}'\n            title: '{{tools.title}}'\n            entitySelector: '{{tools.entity_selector}}'\n            startTime: '{{tools.start_time}}'\n            endTime:\
  \ '{{tools.end_time}}'\n            properties: '{{tools.properties}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: entity-topology-api\n    description: Unified REST API for Dynatrace entity discovery and topology mapping.\n    resources:\n    - path: /v1/entities\n      name: entities\n      description: Query monitored entities\n      operations:\n      - method: GET\n        name: list-entities\n        description: List entities matching a selector\n        call: entities-v2.list-entities\n        with:\n          entitySelector: rest.entitySelector\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          fields: rest.fields\n          from: rest.from\n          to: rest.to\n          sort: rest.sort\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{entityId}\n      name: entity-detail\n      description: Get entity details with relationships\n      operations:\n      - method: GET\n  \
  \      name: get-entity\n        description: Get entity details including topology relationships\n        call: entities-v2.get-entity\n        with:\n          entityId: rest.entityId\n          fields: rest.fields\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entity-types\n      name: entity-types\n      description: Query entity types\n      operations:\n      - method: GET\n        name: list-entity-types\n        description: List all entity types\n        call: entities-v2.list-entity-types\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entity-types/{type}\n      name: entity-type-detail\n      description: Get entity type definition\n      operations:\n      - method: GET\n        name: get-entity-type\n        description: Get a specific entity type definition\n\
  \        call: entities-v2.get-entity-type\n        with:\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/lookup\n      name: entity-lookup\n      description: Look up entity by name\n      operations:\n      - method: POST\n        name: lookup-entity\n        description: Look up an entity by display name and type\n        call: entities-v2.lookup-entity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/query\n      name: metric-query\n      description: Query metrics for entity performance\n      operations:\n      - method: GET\n        name: query-metric-data\n        description: Query metric data for entities\n        call: metrics-v2.query-metric-data\n        with:\n          metricSelector: rest.metricSelector\n          resolution: rest.resolution\n          from: rest.from\n          to: rest.to\n          entitySelector: rest.entitySelector\n    \
  \      mzSelector: rest.mzSelector\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Query entity events\n      operations:\n      - method: GET\n        name: list-events\n        description: List events for entities\n        call: events-v2.list-events\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          from: rest.from\n          to: rest.to\n          eventSelector: rest.eventSelector\n          entitySelector: rest.entitySelector\n          eventType: rest.eventType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/ingest\n      name: event-ingest\n      description: Ingest deployment events\n      operations:\n      - method: POST\n        name: ingest-event\n        description: Ingest a deployment or custom event\n        call: events-v2.ingest-event\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: entity-topology-mcp\n    transport: http\n    description: MCP server for AI-assisted entity discovery and topology mapping.\n    tools:\n    - name: list-entities\n      description: List monitored entities matching a selector expression\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.list-entities\n      with:\n        entitySelector: tools.entitySelector\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        fields: tools.fields\n        from: tools.from\n        to: tools.to\n        sort: tools.sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity\n      description: Get entity details including topology relationships\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.get-entity\n      with:\n        entityId: tools.entityId\n        fields: tools.fields\n        from:\
  \ tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-entity-types\n      description: List all available entity types in the environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.list-entity-types\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-type\n      description: Get the definition of a specific entity type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.get-entity-type\n      with:\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-entity\n      description: Look up an entity by its display name and type\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: entities-v2.lookup-entity\n     \
  \ with:\n        name: tools.name\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-metric-data\n      description: Query metric data points for entities\n      hints:\n        readOnly: true\n        openWorld: true\n      call: metrics-v2.query-metric-data\n      with:\n        metricSelector: tools.metricSelector\n        resolution: tools.resolution\n        from: tools.from\n        to: tools.to\n        entitySelector: tools.entitySelector\n        mzSelector: tools.mzSelector\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List events affecting entities\n      hints:\n        readOnly: true\n        openWorld: true\n      call: events-v2.list-events\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        from: tools.from\n        to: tools.to\n        eventSelector: tools.eventSelector\n        entitySelector: tools.entitySelector\n\
  \        eventType: tools.eventType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-event\n      description: Ingest a deployment or custom event for an entity\n      hints:\n        readOnly: false\n        openWorld: true\n      call: events-v2.ingest-event\n      with:\n        event_type: tools.event_type\n        title: tools.title\n        entity_selector: tools.entity_selector\n        start_time: tools.start_time\n        end_time: tools.end_time\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dynatrace/refs/heads/main/capabilities/entity-and-topology.yaml
tags:
- Dynatrace
- Entity Management
- Topology
- Developer
- Infrastructure
tools:
- description: List monitored entities matching a selector expression
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Get entity details including topology relationships
  hints:
    openWorld: true
    readOnly: true
  name: get-entity
- description: List all available entity types in the environment
  hints:
    openWorld: true
    readOnly: true
  name: list-entity-types
- description: Get the definition of a specific entity type
  hints:
    openWorld: true
    readOnly: true
  name: get-entity-type
- description: Look up an entity by its display name and type
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: lookup-entity
- description: Query metric data points for entities
  hints:
    openWorld: true
    readOnly: true
  name: query-metric-data
- description: List events affecting entities
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: Ingest a deployment or custom event for an entity
  hints:
    openWorld: true
    readOnly: false
  name: ingest-event
---
