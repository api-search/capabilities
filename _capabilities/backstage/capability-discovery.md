---
categories:
- discovery
- platform
consumed_apis:
- backstage-catalog
description: Workflow capability for platform engineers using Backstage as a single catalog query surface to discover MCP servers, capabilities, and APIs registered in Backstage as a single catalog query surface. Combines kind-based entity queries, entity lookup by name, location inventory, location registration, and free-text search into a unified discovery interface.
layout: capability
name: Backstage Capability Discovery
operations:
- description: Query catalog entities by kind and spec.type filters
  method: GET
  name: query-entities
  path: /api/catalog/entities
- description: Get a specific catalog entity by name
  method: GET
  name: get-entity-by-name
  path: /api/catalog/entities/by-name/{kind}/{namespace}/{name}
- description: List catalog locations registered in Backstage
  method: GET
  name: list-locations
  path: /api/catalog/locations
- description: Register a new catalog location for ingestion
  method: POST
  name: register-location
  path: /api/catalog/locations
- description: Search across the Backstage catalog with free text
  method: GET
  name: search-catalog
  path: /api/search/query
- description: Get a specific catalog location by id
  method: GET
  name: get-location
  path: /api/catalog/locations/{id}
personas:
- Platform Engineer
provider_name: Backstage
provider_slug: backstage
search_terms:
- query catalog entities
- backstage catalog
- discover mcp servers
- discover capabilities
- list backstage entities
- get entity by name
- list catalog locations
- register catalog location
- search across catalog
- backstage discovery
- developer portal catalog
- platform engineer discovery
- spec.type query
- kind filter
- mcp server registry
- api catalog
- single catalog query surface
- internal developer portal
- backstage search
- backstage api
- entity lookup
- onboard new location
- capability discovery
slug: capability-discovery
tags:
- Backstage
- Discovery
- Developer Portal
- Catalog
- MCP
tools:
- description: Query catalog entities by kind and spec.type filters to find MCP servers, APIs, or capabilities
  hints:
    openWorld: false
    readOnly: true
  name: query-entities
- description: Get a specific catalog entity by namespace, kind, and name
  hints:
    openWorld: false
    readOnly: true
  name: get-entity-by-name
- description: List catalog locations currently registered in Backstage
  hints:
    openWorld: false
    readOnly: true
  name: list-locations
- description: Register a new catalog location so Backstage ingests its entities
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: register-location
- description: Search across the Backstage catalog with free text to discover entities
  hints:
    openWorld: false
    readOnly: true
  name: search-catalog
- description: Get a specific Backstage catalog location by its id
  hints:
    openWorld: false
    readOnly: true
  name: get-location
---
