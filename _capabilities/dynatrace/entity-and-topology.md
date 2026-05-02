---
categories: []
consumed_apis:
- entities-v2
- metrics-v2
- events-v2
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
- look up entity by name
- look up an entity by its display name and type
- get entity
- analytics
- list all available entity types in the environment
- list entities
- list entity types
- query entity events
- ingest a deployment or custom event
- cloud monitoring
- query metric data for entities
- list events for entities
- list events
- ingest deployment events
- digital experience management
- get a specific entity type definition
- get entity type definition
- infrastructure
- query metrics for entity performance
- query monitored entities
- query metric data
- application security
- intelligence
- list monitored entities matching a selector expression
- get entity details including topology relationships
- list entities matching a selector
- query metric data points for entities
- lookup entity
- list all entity types
- ai operations
- ingest a deployment or custom event for an entity
- get the definition of a specific entity type
- get entity type
- automation
- ingest event
- entity management
- application performance monitoring
- look up an entity by display name and type
- query entity types
- get entity details with relationships
- apm
- observability
- dynatrace
- list events affecting entities
- topology
- developer
slug: entity-and-topology
source_filename: entity-and-topology.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Dynatrace Entity And Topology\"\n  description: \"Entity discovery and topology mapping workflow combining entities, metrics, and events for developers understanding service dependencies and infrastructure layout.\"\n  tags:\n    - Dynatrace\n    - Entity Management\n    - Topology\n    - Developer\n    - Infrastructure\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n      DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\n\ncapability:\n  consumes:\n    - import: entities-v2\n      location: ./shared/entities-v2.yaml\n    - import: metrics-v2\n      location: ./shared/metrics-v2.yaml\n    - import: events-v2\n      location: ./shared/events-v2.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: entity-topology-api\n      description: \"Unified REST API for Dynatrace entity discovery and topology mapping.\"\n \
  \     resources:\n        - path: /v1/entities\n          name: entities\n          description: \"Query monitored entities\"\n          operations:\n            - method: GET\n              name: list-entities\n              description: \"List entities matching a selector\"\n              call: \"entities-v2.list-entities\"\n              with:\n                entitySelector: \"rest.entitySelector\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                fields: \"rest.fields\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/{entityId}\n          name: entity-detail\n          description: \"Get entity details with relationships\"\n          operations:\n            - method: GET\n              name: get-entity\n              description: \"\
  Get entity details including topology relationships\"\n              call: \"entities-v2.get-entity\"\n              with:\n                entityId: \"rest.entityId\"\n                fields: \"rest.fields\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entity-types\n          name: entity-types\n          description: \"Query entity types\"\n          operations:\n            - method: GET\n              name: list-entity-types\n              description: \"List all entity types\"\n              call: \"entities-v2.list-entity-types\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entity-types/{type}\n          name: entity-type-detail\n          description:\
  \ \"Get entity type definition\"\n          operations:\n            - method: GET\n              name: get-entity-type\n              description: \"Get a specific entity type definition\"\n              call: \"entities-v2.get-entity-type\"\n              with:\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/lookup\n          name: entity-lookup\n          description: \"Look up entity by name\"\n          operations:\n            - method: POST\n              name: lookup-entity\n              description: \"Look up an entity by display name and type\"\n              call: \"entities-v2.lookup-entity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/query\n          name: metric-query\n          description: \"Query metrics for entity performance\"\n          operations:\n            -\
  \ method: GET\n              name: query-metric-data\n              description: \"Query metric data for entities\"\n              call: \"metrics-v2.query-metric-data\"\n              with:\n                metricSelector: \"rest.metricSelector\"\n                resolution: \"rest.resolution\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                entitySelector: \"rest.entitySelector\"\n                mzSelector: \"rest.mzSelector\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Query entity events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List events for entities\"\n              call: \"events-v2.list-events\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                from:\
  \ \"rest.from\"\n                to: \"rest.to\"\n                eventSelector: \"rest.eventSelector\"\n                entitySelector: \"rest.entitySelector\"\n                eventType: \"rest.eventType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/ingest\n          name: event-ingest\n          description: \"Ingest deployment events\"\n          operations:\n            - method: POST\n              name: ingest-event\n              description: \"Ingest a deployment or custom event\"\n              call: \"events-v2.ingest-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: entity-topology-mcp\n      transport: http\n      description: \"MCP server for AI-assisted entity discovery and topology mapping.\"\n      tools:\n        - name: list-entities\n          description: \"List monitored\
  \ entities matching a selector expression\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.list-entities\"\n          with:\n            entitySelector: \"tools.entitySelector\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            fields: \"tools.fields\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity\n          description: \"Get entity details including topology relationships\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.get-entity\"\n          with:\n            entityId: \"tools.entityId\"\n            fields: \"tools.fields\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n        - name: list-entity-types\n          description: \"List all available entity types in the environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.list-entity-types\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity-type\n          description: \"Get the definition of a specific entity type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.get-entity-type\"\n          with:\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-entity\n          description: \"Look up an entity by its display name and type\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n            openWorld: true\n          call: \"entities-v2.lookup-entity\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-metric-data\n          description: \"Query metric data points for entities\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"metrics-v2.query-metric-data\"\n          with:\n            metricSelector: \"tools.metricSelector\"\n            resolution: \"tools.resolution\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            entitySelector: \"tools.entitySelector\"\n            mzSelector: \"tools.mzSelector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: \"List events affecting entities\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"events-v2.list-events\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            eventSelector: \"tools.eventSelector\"\n            entitySelector: \"tools.entitySelector\"\n            eventType: \"tools.eventType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-event\n          description: \"Ingest a deployment or custom event for an entity\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"events-v2.ingest-event\"\n          with:\n            event_type: \"tools.event_type\"\n            title: \"tools.title\"\n            entity_selector: \"tools.entity_selector\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            properties: \"tools.properties\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
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
