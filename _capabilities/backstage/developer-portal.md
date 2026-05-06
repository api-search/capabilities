---
categories:
- api-management
consumed_apis: []
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
- list all entities in the backstage software catalog including components, apis, resources, systems, and users
- software catalog entities
- list catalog entities
- Developer
- software developer using backstage to discover services, bootstrap projects, and read documentation
- developer portal
- engineer building and maintaining the internal developer platform and backstage configuration
- list all catalog entities
- internal developer platform
- register a new catalog location
- list all registered catalog locations
- list entities
- list locations
- catalog locations
- delete catalog entity
- register catalog location
- open source
- backstage
- delete an entity from the software catalog
- create location
- get catalog entity
- central inventory of all software components, apis, and resources
- register a new catalog location (github repo url, yaml file) to ingest entities
- get a specific catalog entity by kind, namespace, and name
- list catalog locations
- Platform Engineer
- software catalog
- unified workflow for managing entities, locations, scaffolding, documentation, and search
- scaffolding, documentation, and search to accelerate development
slug: developer-portal
source_filename: developer-portal.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Backstage Developer Portal\n  description: Unified developer portal workflow combining the Backstage Software Catalog, Scaffolder, TechDocs, Search, Auth,\n    and Permissions APIs. Serves platform engineers and developers managing internal developer platforms.\n  tags:\n  - Backstage\n  - Developer Portal\n  - Internal Developer Platform\n  - Software Catalog\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BACKSTAGE_TOKEN: BACKSTAGE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: backstage-catalog\n    baseUri: https://backstage.example.com/api/catalog\n    description: Backstage Software Catalog API\n    authentication:\n      type: bearer\n      token: '{{BACKSTAGE_TOKEN}}'\n    resources:\n    - name: entities\n      path: /entities\n      description: Catalog entity management\n      operations:\n      - name: list-entities\n        method: GET\n        description: List all\
  \ entities in the catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-entity-by-ref\n        method: GET\n        description: Get a single entity by its entity ref\n        inputParameters:\n        - name: kind\n          in: path\n          type: string\n          required: true\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-entity\n        method: DELETE\n        description: Delete an entity from the catalog\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      description: Catalog location management\n      operations:\n      - name: list-locations\n        method: GET\n        description: List all registered catalog locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-location\n        method: POST\n        description: Register a new catalog location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.location_type}}'\n            target: '{{tools.location_target}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: backstage-portal-api\n    description: Unified REST API for Backstage developer portal management.\n    resources:\n    - path: /v1/entities\n      name:\
  \ entities\n      description: Software catalog entities\n      operations:\n      - method: GET\n        name: list-entities\n        description: List all catalog entities\n        call: backstage-catalog.list-entities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Catalog locations\n      operations:\n      - method: GET\n        name: list-locations\n        description: List catalog locations\n        call: backstage-catalog.list-locations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-location\n        description: Register a new catalog location\n        call: backstage-catalog.create-location\n        with:\n          location_type: rest.location_type\n          location_target: rest.location_target\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace:\
  \ backstage-portal-mcp\n    transport: http\n    description: MCP server for AI-assisted Backstage developer portal management.\n    tools:\n    - name: list-catalog-entities\n      description: List all entities in the Backstage software catalog including components, APIs, resources, systems, and\n        users\n      hints:\n        readOnly: true\n        openWorld: false\n      call: backstage-catalog.list-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-catalog-entity\n      description: Get a specific catalog entity by kind, namespace, and name\n      hints:\n        readOnly: true\n        openWorld: false\n      call: backstage-catalog.get-entity-by-ref\n      with:\n        kind: tools.kind\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-catalog-location\n      description: Register a new catalog location (GitHub repo URL, YAML file)\
  \ to ingest entities\n      hints:\n        readOnly: false\n        openWorld: false\n      call: backstage-catalog.create-location\n      with:\n        location_type: tools.location_type\n        location_target: tools.location_target\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-catalog-locations\n      description: List all registered catalog locations\n      hints:\n        readOnly: true\n        openWorld: false\n      call: backstage-catalog.list-locations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-catalog-entity\n      description: Delete an entity from the software catalog\n      hints:\n        readOnly: false\n        destructive: true\n      call: backstage-catalog.delete-entity\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/backstage/refs/heads/main/capabilities/developer-portal.yaml
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
