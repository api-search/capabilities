---
categories: []
consumed_apis:
- typesense-search
- typesense-vector
description: Unified search and discovery workflow combining Typesense full-text search, vector search, and conversational AI search. Used by application developers to deliver instant, relevant, and AI-powered search experiences.
layout: capability
name: Typesense Search and Discovery
operations:
- description: Search documents in a collection with faceting and filtering
  method: GET
  name: search-collection
  path: /v1/search
- description: Execute multiple searches across collections
  method: POST
  name: multi-search
  path: /v1/multi-search
- description: Perform vector similarity search
  method: GET
  name: vector-search
  path: /v1/vector-search
- description: List all search collections
  method: GET
  name: list-collections
  path: /v1/collections
- description: Create a new search collection
  method: POST
  name: create-collection
  path: /v1/collections
personas: []
provider_name: Typesense
provider_slug: typesense
search_terms:
- perform semantic vector similarity search in typesense
- list all typesense search collections
- search engine
- execute multiple typesense searches across different collections in one request
- typo tolerance
- open source
- search collection
- index document
- search documents in a collection with faceting and filtering
- index a new document into a typesense collection
- typesense
- multi vector search
- full-text search
- search
- execute multiple searches across collections
- perform vector similarity search
- create a new typesense collection with a defined schema
- multi search
- vector search
- ai search
- get schema and statistics for a typesense collection
- search documents in a typesense collection with full-text, filters, and facets
- collection management
- discovery
- semantic vector search
- list all search collections
- multi-collection search
- get collection
- create a new search collection
- create collection
- execute multiple vector searches simultaneously across typesense collections
- full-text document search
- list collections
slug: search-and-discovery
source_filename: search-and-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Typesense Search and Discovery\"\n  description: >-\n    Unified search and discovery workflow combining Typesense full-text search,\n    vector search, and conversational AI search. Used by application developers\n    to deliver instant, relevant, and AI-powered search experiences.\n  tags:\n    - Typesense\n    - Search\n    - Discovery\n    - Vector Search\n    - AI Search\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TYPESENSE_API_KEY: TYPESENSE_API_KEY\n      TYPESENSE_HOST: TYPESENSE_HOST\n\ncapability:\n  consumes:\n    - import: typesense-search\n      location: ./shared/search-api.yaml\n    - import: typesense-vector\n      location: ./shared/vector-search-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: typesense-search-discovery-api\n      description: \"Unified REST API for Typesense search and discovery.\"\n      resources:\n     \
  \   - path: /v1/search\n          name: search\n          description: \"Full-text document search\"\n          operations:\n            - method: GET\n              name: search-collection\n              description: \"Search documents in a collection with faceting and filtering\"\n              call: \"typesense-search.search-collection\"\n              with:\n                collectionName: \"rest.collection\"\n                q: \"rest.q\"\n                query_by: \"rest.query_by\"\n                filter_by: \"rest.filter_by\"\n                sort_by: \"rest.sort_by\"\n                facet_by: \"rest.facet_by\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/multi-search\n          name: multi-search\n          description: \"Multi-collection search\"\n          operations:\n            - method: POST\n              name: multi-search\n              description: \"Execute multiple searches across collections\"\
  \n              call: \"typesense-search.multi-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vector-search\n          name: vector-search\n          description: \"Semantic vector search\"\n          operations:\n            - method: GET\n              name: vector-search\n              description: \"Perform vector similarity search\"\n              call: \"typesense-vector.vector-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: \"Collection management\"\n          operations:\n            - method: GET\n              name: list-collections\n              description: \"List all search collections\"\n              call: \"typesense-search.list-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: POST\n              name: create-collection\n              description: \"Create a new search collection\"\n              call: \"typesense-search.create-collection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: typesense-search-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted search and content discovery with Typesense.\"\n      tools:\n        - name: search-collection\n          description: \"Search documents in a Typesense collection with full-text, filters, and facets\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"typesense-search.search-collection\"\n          with:\n            collectionName: \"tools.collection\"\n            q: \"tools.q\"\n            query_by: \"tools.query_by\"\n            filter_by: \"tools.filter_by\"\n            sort_by: \"tools.sort_by\"\
  \n            facet_by: \"tools.facet_by\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: multi-search\n          description: \"Execute multiple Typesense searches across different collections in one request\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"typesense-search.multi-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vector-search\n          description: \"Perform semantic vector similarity search in Typesense\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"typesense-vector.vector-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: multi-vector-search\n          description: \"Execute multiple vector searches simultaneously across Typesense collections\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"typesense-vector.multi-vector-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collections\n          description: \"List all Typesense search collections\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"typesense-search.list-collections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-collection\n          description: \"Get schema and statistics for a Typesense collection\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"typesense-search.get-collection\"\n          with:\n            collectionName: \"tools.collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: index-document\n          description: \"Index a new document into a Typesense collection\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"typesense-search.index-document\"\n          with:\n            collectionName: \"tools.collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-collection\n          description: \"Create a new Typesense collection with a defined schema\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"typesense-search.create-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/typesense/refs/heads/main/capabilities/search-and-discovery.yaml
tags:
- Typesense
- Search
- Discovery
- Vector Search
- AI Search
tools:
- description: Search documents in a Typesense collection with full-text, filters, and facets
  hints:
    openWorld: true
    readOnly: true
  name: search-collection
- description: Execute multiple Typesense searches across different collections in one request
  hints:
    openWorld: true
    readOnly: true
  name: multi-search
- description: Perform semantic vector similarity search in Typesense
  hints:
    openWorld: true
    readOnly: true
  name: vector-search
- description: Execute multiple vector searches simultaneously across Typesense collections
  hints:
    openWorld: true
    readOnly: true
  name: multi-vector-search
- description: List all Typesense search collections
  hints:
    openWorld: true
    readOnly: true
  name: list-collections
- description: Get schema and statistics for a Typesense collection
  hints:
    openWorld: true
    readOnly: true
  name: get-collection
- description: Index a new document into a Typesense collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: index-document
- description: Create a new Typesense collection with a defined schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-collection
---
