---
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
- query entity events
- get entity details including topology relationships
- query metric data for entities
- get entity type definition
- list entity types
- query monitored entities
- list entities matching a selector
- query entity types
- list events for entities
- intelligence
- topology
- look up entity by name
- list events affecting entities
- application performance monitoring
- get entity details with relationships
- get the definition of a specific entity type
- look up an entity by its display name and type
- digital experience management
- get a specific entity type definition
- list monitored entities matching a selector expression
- get entity
- dynatrace
- list all entity types
- ingest a deployment or custom event
- list events
- entity management
- developer
- query metric data
- ingest deployment events
- ingest event
- list all available entity types in the environment
- analytics
- query metrics for entity performance
- look up an entity by display name and type
- get entity type
- cloud monitoring
- infrastructure
- ingest a deployment or custom event for an entity
- application security
- lookup entity
- ai operations
- observability
- list entities
- query metric data points for entities
- apm
- automation
slug: entity-and-topology
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
