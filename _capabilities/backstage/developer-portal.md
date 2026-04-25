---
consumed_apis:
- backstage-catalog
description: Unified developer portal workflow combining the Backstage Software Catalog, Scaffolder, TechDocs, Search, Auth, and Permissions APIs. Serves platform engineers and developers managing internal developer platforms.
layout: capability
name: Backstage Developer Portal
operations:
- description: List all catalog entities
  method: GET
  name: list-entities
  path: /v1/entities
- description: List catalog locations
  method: GET
  name: list-locations
  path: /v1/locations
- description: Register a new catalog location
  method: POST
  name: create-location
  path: /v1/locations
personas: []
provider_name: Backstage
provider_slug: backstage
search_terms:
- list entities
- list all registered catalog locations
- list catalog entities
- unified workflow for managing entities, locations, scaffolding, documentation, and search
- create location
- list locations
- software catalog
- developer portal
- Platform Engineer
- internal developer platform
- register a new catalog location
- scaffolding, documentation, and search to accelerate development
- register catalog location
- delete catalog entity
- central inventory of all software components, apis, and resources
- backstage
- list all entities in the backstage software catalog including components, apis, resources, systems, and users
- engineer building and maintaining the internal developer platform and backstage configuration
- list all catalog entities
- list catalog locations
- open source
- software catalog entities
- register a new catalog location (github repo url, yaml file) to ingest entities
- get a specific catalog entity by kind, namespace, and name
- delete an entity from the software catalog
- catalog locations
- Developer
- software developer using backstage to discover services, bootstrap projects, and read documentation
- get catalog entity
slug: developer-portal
tags:
- Backstage
- Developer Portal
- Internal Developer Platform
- Software Catalog
tools:
- description: List all entities in the Backstage software catalog including components, APIs, resources, systems, and users
  hints:
    openWorld: false
    readOnly: true
  name: list-catalog-entities
- description: Get a specific catalog entity by kind, namespace, and name
  hints:
    openWorld: false
    readOnly: true
  name: get-catalog-entity
- description: Register a new catalog location (GitHub repo URL, YAML file) to ingest entities
  hints:
    openWorld: false
    readOnly: false
  name: register-catalog-location
- description: List all registered catalog locations
  hints:
    openWorld: false
    readOnly: true
  name: list-catalog-locations
- description: Delete an entity from the software catalog
  hints:
    destructive: true
    readOnly: false
  name: delete-catalog-entity
---
