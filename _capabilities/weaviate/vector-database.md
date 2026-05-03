---
categories: []
consumed_apis:
- weaviate
description: Unified vector database workflow for managing Weaviate objects, schemas, vector search via GraphQL, backups, and cluster operations. Used by AI engineers, platform operators, and data engineers to build and manage AI-powered applications.
layout: capability
name: Weaviate Vector Database
operations:
- description: Check if Weaviate is ready
  method: GET
  name: check-readiness
  path: /v1/health
- description: List objects in Weaviate
  method: GET
  name: list-objects
  path: /v1/objects
- description: Create a new object
  method: POST
  name: create-object
  path: /v1/objects
- description: Get an object by ID
  method: GET
  name: get-object
  path: /v1/objects/{id}
- description: Delete an object
  method: DELETE
  name: delete-object
  path: /v1/objects/{id}
- description: Execute GraphQL vector search query
  method: POST
  name: graphql-query
  path: /v1/graphql
- description: Get data schema
  method: GET
  name: get-schema
  path: /v1/schema
- description: Create a collection class
  method: POST
  name: create-class
  path: /v1/schema
- description: Batch create objects
  method: POST
  name: batch-create-objects
  path: /v1/batch/objects
- description: Get cluster node information
  method: GET
  name: get-nodes
  path: /v1/nodes
personas: []
provider_name: Weaviate
provider_slug: weaviate
search_terms:
- get data schema
- get cluster nodes
- create weaviate object
- semantic search
- create a collection class
- batch import objects
- execute a graphql vector similarity search query against weaviate
- list objects
- get nodes
- open source
- create class
- get schema
- schema
- check if weaviate is ready
- batch object operations
- vector database
- cluster nodes
- get weaviate object
- graphql
- objects
- check readiness
- create backup
- kubernetes
- application health
- create object
- execute graphql vector search query
- get an object by id
- get object
- get information about all nodes in the weaviate cluster
- list backups
- vector search
- delete an object
- create a new vector object in weaviate with optional vector embedding
- create a new object
- list objects in weaviate
- schema management
- list weaviate objects
- delete weaviate object
- create a backup of weaviate data to a storage backend (s3, gcs, filesystem, azure)
- vector object management
- machine learning
- delete object
- list available backups on a storage backend
- ai
- graphql vector search
- delete a weaviate object by uuid
- create a new collection class in the weaviate schema
- check if the weaviate instance is ready to accept requests
- check weaviate readiness
- individual object operations
- graphql query
- list objects stored in weaviate, optionally filtered by collection class
- import multiple objects to weaviate in a single batch operation
- get the current data schema including all collection classes
- devops
- batch create objects
- get cluster node information
- create collection class
- retrieve a specific weaviate object by its uuid
slug: vector-database
source_filename: vector-database.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Weaviate Vector Database\"\n  description: \"Unified vector database workflow for managing Weaviate objects, schemas, vector search via GraphQL, backups, and cluster operations. Used by AI engineers, platform operators, and data engineers to build and manage AI-powered applications.\"\n  tags:\n    - Vector Database\n    - AI\n    - Machine Learning\n    - Semantic Search\n    - Objects\n    - Schema\n    - GraphQL\n    - DevOps\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEAVIATE_HOST: WEAVIATE_HOST\n      WEAVIATE_API_KEY: WEAVIATE_API_KEY\n\ncapability:\n  consumes:\n    - import: weaviate\n      location: ./shared/weaviate-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: vector-database-api\n      description: \"Unified REST API for Weaviate vector database management.\"\n      resources:\n        - path: /v1/health\n          name: health\n\
  \          description: \"Application health\"\n          operations:\n            - method: GET\n              name: check-readiness\n              description: \"Check if Weaviate is ready\"\n              call: \"weaviate.check-readiness\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/objects\n          name: objects\n          description: \"Vector object management\"\n          operations:\n            - method: GET\n              name: list-objects\n              description: \"List objects in Weaviate\"\n              call: \"weaviate.list-objects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-object\n              description: \"Create a new object\"\n              call: \"weaviate.create-object\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/objects/{id}\n          name: object\n          description: \"Individual object operations\"\n          operations:\n            - method: GET\n              name: get-object\n              description: \"Get an object by ID\"\n              call: \"weaviate.get-object\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-object\n              description: \"Delete an object\"\n              call: \"weaviate.delete-object\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/graphql\n          name: graphql\n          description: \"GraphQL vector search\"\n          operations:\n            - method: POST\n              name: graphql-query\n              description: \"Execute GraphQL\
  \ vector search query\"\n              call: \"weaviate.graphql-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/schema\n          name: schema\n          description: \"Schema management\"\n          operations:\n            - method: GET\n              name: get-schema\n              description: \"Get data schema\"\n              call: \"weaviate.get-schema\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-class\n              description: \"Create a collection class\"\n              call: \"weaviate.create-class\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batch/objects\n          name: batch-objects\n          description: \"Batch object operations\"\n          operations:\n            - method: POST\n              name:\
  \ batch-create-objects\n              description: \"Batch create objects\"\n              call: \"weaviate.batch-create-objects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes\n          name: nodes\n          description: \"Cluster nodes\"\n          operations:\n            - method: GET\n              name: get-nodes\n              description: \"Get cluster node information\"\n              call: \"weaviate.get-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: vector-database-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Weaviate vector database management.\"\n      tools:\n        - name: check-weaviate-readiness\n          description: \"Check if the Weaviate instance is ready to accept requests\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"weaviate.check-readiness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-weaviate-objects\n          description: \"List objects stored in Weaviate, optionally filtered by collection class\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weaviate.list-objects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-weaviate-object\n          description: \"Create a new vector object in Weaviate with optional vector embedding\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weaviate.create-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-weaviate-object\n          description: \"Retrieve a specific Weaviate object by its UUID\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: false\n          call: \"weaviate.get-object\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-weaviate-object\n          description: \"Delete a Weaviate object by UUID\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"weaviate.delete-object\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vector-search\n          description: \"Execute a GraphQL vector similarity search query against Weaviate\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weaviate.graphql-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-schema\n          description: \"Get the current data schema including all collection\
  \ classes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weaviate.get-schema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-collection-class\n          description: \"Create a new collection class in the Weaviate schema\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weaviate.create-class\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-import-objects\n          description: \"Import multiple objects to Weaviate in a single batch operation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weaviate.batch-create-objects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster-nodes\n          description: \"Get information about all nodes in the Weaviate\
  \ cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weaviate.get-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-backup\n          description: \"Create a backup of Weaviate data to a storage backend (s3, gcs, filesystem, azure)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weaviate.create-backup\"\n          with:\n            backend: \"tools.backend\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-backups\n          description: \"List available backups on a storage backend\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weaviate.list-backups\"\n          with:\n            backend: \"tools.backend\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weaviate/refs/heads/main/capabilities/vector-database.yaml
tags:
- Vector Database
- AI
- Machine Learning
- Semantic Search
- Objects
- Schema
- GraphQL
- DevOps
tools:
- description: Check if the Weaviate instance is ready to accept requests
  hints:
    openWorld: false
    readOnly: true
  name: check-weaviate-readiness
- description: List objects stored in Weaviate, optionally filtered by collection class
  hints:
    openWorld: false
    readOnly: true
  name: list-weaviate-objects
- description: Create a new vector object in Weaviate with optional vector embedding
  hints:
    idempotent: false
    readOnly: false
  name: create-weaviate-object
- description: Retrieve a specific Weaviate object by its UUID
  hints:
    openWorld: false
    readOnly: true
  name: get-weaviate-object
- description: Delete a Weaviate object by UUID
  hints:
    destructive: true
    readOnly: false
  name: delete-weaviate-object
- description: Execute a GraphQL vector similarity search query against Weaviate
  hints:
    openWorld: true
    readOnly: true
  name: vector-search
- description: Get the current data schema including all collection classes
  hints:
    openWorld: false
    readOnly: true
  name: get-schema
- description: Create a new collection class in the Weaviate schema
  hints:
    idempotent: false
    readOnly: false
  name: create-collection-class
- description: Import multiple objects to Weaviate in a single batch operation
  hints:
    idempotent: false
    readOnly: false
  name: batch-import-objects
- description: Get information about all nodes in the Weaviate cluster
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster-nodes
- description: Create a backup of Weaviate data to a storage backend (s3, gcs, filesystem, azure)
  hints:
    idempotent: false
    readOnly: false
  name: create-backup
- description: List available backups on a storage backend
  hints:
    openWorld: false
    readOnly: true
  name: list-backups
---
