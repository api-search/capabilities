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
- get entity
- ai operations
- look up an entity by display name and type
- cloud monitoring
- automation
- query entity types
- get entity details with relationships
- query metric data for entities
- lookup entity
- query metric data points for entities
- list entity types
- query metric data
- look up an entity by its display name and type
- application security
- list events affecting entities
- list monitored entities matching a selector expression
- list events for entities
- query metrics for entity performance
- get entity type
- analytics
- apm
- get a specific entity type definition
- list all available entity types in the environment
- observability
- developer
- get entity type definition
- ingest a deployment or custom event for an entity
- ingest deployment events
- query monitored entities
- intelligence
- list entities
- digital experience management
- topology
- entity management
- look up entity by name
- list entities matching a selector
- application performance monitoring
- query entity events
- list all entity types
- infrastructure
- get entity details including topology relationships
- list events
- get the definition of a specific entity type
- dynatrace
- ingest a deployment or custom event
- ingest event
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
