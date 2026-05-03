---
api_specs:
- filename: spring-data-rest-openapi.yml
  format: yaml
  label: spring-data-rest
  slug: spring-data-rest
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spring-data/refs/heads/main/openapi/spring-data-rest-openapi.yml
categories: []
consumed_apis:
- spring-data-rest
description: Workflow capability for Spring Data REST data access operations. Provides unified CRUD and query access to any Spring Data repository over HAL+JSON. Used by application developers and API consumers to manage data entities through auto-exposed repository endpoints.
layout: capability
name: Spring Data REST - Data Access
operations:
- description: List all exported repositories in the application
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: List resources with pagination and sorting
  method: GET
  name: list-resources
  path: /v1/{repository}
- description: Create a new entity in the repository
  method: POST
  name: create-resource
  path: /v1/{repository}
- description: Retrieve a specific entity by ID
  method: GET
  name: get-resource
  path: /v1/{repository}/{id}
- description: Delete an entity from the repository
  method: DELETE
  name: delete-resource
  path: /v1/{repository}/{id}
- description: Run a repository-defined query
  method: GET
  name: search-repository
  path: /v1/{repository}/search/{method}
personas: []
provider_name: Spring Data
provider_slug: spring-data
search_terms:
- create a new entity in the repository
- run a repository-defined query
- framework
- java
- list entities
- create a new entity in a spring data repository
- get entity
- create entity
- list resources with pagination and sorting
- delete resource
- access individual repository entities
- search repository
- discover all spring data rest repositories available in the running application
- execute repository query methods
- list resources
- delete an entity from a spring data repository by id
- execute a custom query method on a spring data repository
- database
- spring
- discover repositories
- retrieve a specific entity from a repository by its id
- delete entity
- data access
- access a repository collection
- mongodb
- orm
- list all exported repositories in the application
- hateoas
- redis
- discover all available spring data rest repositories
- retrieve a specific entity by id
- rest
- search entities
- jpa
- create resource
- delete an entity from the repository
- list repositories
- list entities from a spring data repository with pagination and sorting
- hypermedia
- get resource
slug: data-access
source_filename: data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spring Data REST - Data Access\"\n  description: >-\n    Workflow capability for Spring Data REST data access operations. Provides\n    unified CRUD and query access to any Spring Data repository over HAL+JSON.\n    Used by application developers and API consumers to manage data entities\n    through auto-exposed repository endpoints.\n  tags:\n    - Data Access\n    - HATEOAS\n    - Hypermedia\n    - REST\n    - Spring\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPRING_DATA_BASE_URL: SPRING_DATA_BASE_URL\n      SPRING_DATA_TOKEN: SPRING_DATA_TOKEN\n\ncapability:\n  consumes:\n    - import: spring-data-rest\n      location: ./shared/spring-data-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: data-access-api\n      description: \"Unified REST API for Spring Data repository access.\"\n      resources:\n        - path: /v1/repositories\n     \
  \     name: repository-discovery\n          description: \"Discover all available Spring Data REST repositories\"\n          operations:\n            - method: GET\n              name: list-repositories\n              description: \"List all exported repositories in the application\"\n              call: \"spring-data-rest.list-repositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/{repository}\n          name: repository-collection\n          description: \"Access a repository collection\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List resources with pagination and sorting\"\n              call: \"spring-data-rest.list-resources\"\n              with:\n                repository: \"rest.repository\"\n                page: \"rest.page\"\n                size: \"rest.size\"\n                sort: \"rest.sort\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-resource\n              description: \"Create a new entity in the repository\"\n              call: \"spring-data-rest.create-resource\"\n              with:\n                repository: \"rest.repository\"\n                payload: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/{repository}/{id}\n          name: repository-item\n          description: \"Access individual repository entities\"\n          operations:\n            - method: GET\n              name: get-resource\n              description: \"Retrieve a specific entity by ID\"\n              call: \"spring-data-rest.get-resource\"\n              with:\n                repository: \"rest.repository\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n            - method: DELETE\n              name: delete-resource\n              description: \"Delete an entity from the repository\"\n              call: \"spring-data-rest.delete-resource\"\n              with:\n                repository: \"rest.repository\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/{repository}/search/{method}\n          name: repository-search\n          description: \"Execute repository query methods\"\n          operations:\n            - method: GET\n              name: search-repository\n              description: \"Run a repository-defined query\"\n              call: \"spring-data-rest.execute-search\"\n              with:\n                repository: \"rest.repository\"\n                method: \"rest.method\"\n                page: \"rest.page\"\n                size: \"rest.size\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: data-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spring Data repository operations.\"\n      tools:\n        - name: discover-repositories\n          description: \"Discover all Spring Data REST repositories available in the running application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-data-rest.list-repositories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-entities\n          description: \"List entities from a Spring Data repository with pagination and sorting\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-data-rest.list-resources\"\n          with:\n            repository: \"tools.repository\"\n            page: \"tools.page\"\n            size: \"\
  tools.size\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-entity\n          description: \"Retrieve a specific entity from a repository by its ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spring-data-rest.get-resource\"\n          with:\n            repository: \"tools.repository\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-entity\n          description: \"Create a new entity in a Spring Data repository\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spring-data-rest.create-resource\"\n          with:\n            repository: \"tools.repository\"\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n       \
  \ - name: delete-entity\n          description: \"Delete an entity from a Spring Data repository by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"spring-data-rest.delete-resource\"\n          with:\n            repository: \"tools.repository\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-entities\n          description: \"Execute a custom query method on a Spring Data repository\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-data-rest.execute-search\"\n          with:\n            repository: \"tools.repository\"\n            method: \"tools.method\"\n            page: \"tools.page\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-data/refs/heads/main/capabilities/data-access.yaml
tags:
- Data Access
- HATEOAS
- Hypermedia
- REST
- Spring
tools:
- description: Discover all Spring Data REST repositories available in the running application
  hints:
    openWorld: true
    readOnly: true
  name: discover-repositories
- description: List entities from a Spring Data repository with pagination and sorting
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Retrieve a specific entity from a repository by its ID
  hints:
    openWorld: false
    readOnly: true
  name: get-entity
- description: Create a new entity in a Spring Data repository
  hints:
    destructive: false
    readOnly: false
  name: create-entity
- description: Delete an entity from a Spring Data repository by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-entity
- description: Execute a custom query method on a Spring Data repository
  hints:
    openWorld: true
    readOnly: true
  name: search-entities
---
