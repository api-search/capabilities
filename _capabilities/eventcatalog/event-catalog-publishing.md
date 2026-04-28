---
categories:
- discovery
- events
consumed_apis:
- eventcatalog-api
description: Workflow capability for platform engineers running enterprise event-driven architectures who need to publish events, services, and domains to a discoverable enterprise event catalog. Combines event schema publishing, domain inventory, service registration, producer/consumer linkage, and AsyncAPI spec ingestion into a unified surface for EDA discovery.
layout: capability
name: EventCatalog Event & Domain Publishing
operations:
- description: Publish an event schema to the catalog
  method: POST
  name: publish-event-schema
  path: /v1/events
- description: List all domains registered in the catalog
  method: GET
  name: list-domains
  path: /v1/domains
- description: Register a service that produces or consumes events
  method: POST
  name: register-service
  path: /v1/services
- description: Link an event to a producer or consumer service
  method: PUT
  name: link-event-producer-consumer
  path: /v1/events/{name}/services
- description: Publish an AsyncAPI spec to onboard events in bulk
  method: POST
  name: publish-asyncapi-spec
  path: /v1/services/{name}/asyncapi
- description: List events available in the catalog
  method: GET
  name: list-events
  path: /v1/events
personas:
- Platform Engineer
provider_name: EventCatalog
provider_slug: eventcatalog
search_terms:
- publish event schema
- list domains
- register service
- link event to producer
- link event to consumer
- publish asyncapi spec
- enterprise event catalog
- event-driven architecture
- eda discovery
- event schema registry
- service registration
- domain inventory
- asyncapi onboarding
- event producers and consumers
- event catalog publishing
- platform engineer events
- discoverable events
- list events
- eventcatalog api
- event documentation
- bulk asyncapi import
- service event linkage
- event catalog
slug: event-catalog-publishing
tags:
- Event Catalog
- AsyncAPI
- EDA
- Discovery
- Schema Registry
tools:
- description: Publish an event schema to the EventCatalog so it is discoverable across the organization
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: publish-event-schema
- description: List all domains currently registered in the EventCatalog
  hints:
    openWorld: false
    readOnly: true
  name: list-domains
- description: Register a service that produces or consumes events in the catalog
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: register-service
- description: Link an event to a producer or consumer service to map dataflow across the catalog
  hints:
    destructive: false
    idempotent: true
    openWorld: false
    readOnly: false
  name: link-event-producer-consumer
- description: Publish an AsyncAPI spec for a service to onboard its events in bulk
  hints:
    destructive: false
    idempotent: true
    openWorld: false
    readOnly: false
  name: publish-asyncapi-spec
- description: List events available in the EventCatalog including their schemas and linked services
  hints:
    openWorld: false
    readOnly: true
  name: list-events
---
