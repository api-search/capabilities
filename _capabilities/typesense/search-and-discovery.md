---
categories: []
consumed_apis: []
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
- create a new search collection
- full-text search
- execute multiple searches across collections
- search engine
- multi vector search
- open source
- typo tolerance
- typesense
- collection management
- execute multiple vector searches simultaneously across typesense collections
- list all typesense search collections
- index document
- search documents in a typesense collection with full-text, filters, and facets
- discovery
- search collection
- vector search
- list all search collections
- list collections
- search documents in a collection with faceting and filtering
- full-text document search
- execute multiple typesense searches across different collections in one request
- semantic vector search
- perform vector similarity search
- get schema and statistics for a typesense collection
- create collection
- multi-collection search
- search
- index a new document into a typesense collection
- get collection
- multi search
- create a new typesense collection with a defined schema
- ai search
slug: search-and-discovery
source_filename: search-and-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Typesense Search and Discovery\n  description: Unified search and discovery workflow combining Typesense full-text search, vector search, and conversational\n    AI search. Used by application developers to deliver instant, relevant, and AI-powered search experiences.\n  tags:\n  - Typesense\n  - Search\n  - Discovery\n  - Vector Search\n  - AI Search\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TYPESENSE_API_KEY: TYPESENSE_API_KEY\n    TYPESENSE_HOST: TYPESENSE_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: typesense-search\n    baseUri: http://{{TYPESENSE_HOST}}:8108\n    description: Typesense search and collection management\n    authentication:\n      type: apikey\n      key: X-TYPESENSE-API-KEY\n      value: '{{TYPESENSE_API_KEY}}'\n      placement: header\n    resources:\n    - name: collections\n      path: /collections\n      description: Collection management\n   \
  \   operations:\n      - name: list-collections\n        method: GET\n        description: List all collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-collection\n        method: POST\n        description: Create a new collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            fields: '{{tools.fields}}'\n            default_sorting_field: '{{tools.default_sorting_field}}'\n    - name: collection\n      path: /collections/{collectionName}\n      description: Single collection operations\n      operations:\n      - name: get-collection\n        method: GET\n        description: Retrieve a collection by name\n        inputParameters:\n        - name: collectionName\n          in: path\n          type:\
  \ string\n          required: true\n          description: Collection name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-collection\n        method: DELETE\n        description: Delete a collection\n        inputParameters:\n        - name: collectionName\n          in: path\n          type: string\n          required: true\n          description: Collection name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /collections/{collectionName}/documents\n      description: Document indexing and management\n      operations:\n      - name: index-document\n        method: POST\n        description: Index a single document\n        inputParameters:\n        - name: collectionName\n          in: path\n          type: string\n          required: true\n          description: Collection\
  \ name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            document: '{{tools.document}}'\n    - name: search\n      path: /collections/{collectionName}/documents/search\n      description: Search documents in a collection\n      operations:\n      - name: search-collection\n        method: GET\n        description: Search for documents in a collection\n        inputParameters:\n        - name: collectionName\n          in: path\n          type: string\n          required: true\n          description: Collection name\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: query_by\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of fields to search\n        - name: filter_by\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter conditions\n        - name: sort_by\n          in: query\n          type: string\n          required: false\n          description: Sort field and direction\n        - name: facet_by\n          in: query\n          type: string\n          required: false\n          description: Comma-separated facet fields\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: multi-search\n      path: /multi_search\n      description: Search across multiple collections in one request\n      operations:\n      - name: multi-search\n        method: POST\n        description:\
  \ Execute multiple searches in a single request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            searches: '{{tools.searches}}'\n    - name: aliases\n      path: /aliases\n      description: Collection alias management\n      operations:\n      - name: list-aliases\n        method: GET\n        description: List all collection aliases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys\n      path: /keys\n      description: API key management\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: List all API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create\
  \ a new API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n            actions: '{{tools.actions}}'\n            collections: '{{tools.collections}}'\n  - type: http\n    namespace: typesense-vector\n    baseUri: http://{{TYPESENSE_HOST}}:8108\n    description: Typesense vector and hybrid search\n    authentication:\n      type: apikey\n      key: X-TYPESENSE-API-KEY\n      value: '{{TYPESENSE_API_KEY}}'\n      placement: header\n    resources:\n    - name: vector-search\n      path: /collections/{collectionName}/documents/search\n      description: Vector and hybrid search queries\n      operations:\n      - name: vector-search\n        method: GET\n        description: Perform vector or hybrid search on a collection\n        inputParameters:\n        - name: collectionName\n          in: path\n   \
  \       type: string\n          required: true\n          description: Collection name\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query text (use * for pure vector search)\n        - name: query_by\n          in: query\n          type: string\n          required: true\n          description: Fields to search\n        - name: vector_query\n          in: query\n          type: string\n          required: false\n          description: Vector query specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: multi-vector-search\n      path: /multi_search\n      description: Multi-search with vector queries\n      operations:\n      - name: multi-vector-search\n        method: POST\n        description: Execute multiple vector search requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n        body:\n          type: json\n          data:\n            searches: '{{tools.searches}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: typesense-search-discovery-api\n    description: Unified REST API for Typesense search and discovery.\n    resources:\n    - path: /v1/search\n      name: search\n      description: Full-text document search\n      operations:\n      - method: GET\n        name: search-collection\n        description: Search documents in a collection with faceting and filtering\n        call: typesense-search.search-collection\n        with:\n          collectionName: rest.collection\n          q: rest.q\n          query_by: rest.query_by\n          filter_by: rest.filter_by\n          sort_by: rest.sort_by\n          facet_by: rest.facet_by\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/multi-search\n      name: multi-search\n      description: Multi-collection search\n\
  \      operations:\n      - method: POST\n        name: multi-search\n        description: Execute multiple searches across collections\n        call: typesense-search.multi-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vector-search\n      name: vector-search\n      description: Semantic vector search\n      operations:\n      - method: GET\n        name: vector-search\n        description: Perform vector similarity search\n        call: typesense-vector.vector-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: Collection management\n      operations:\n      - method: GET\n        name: list-collections\n        description: List all search collections\n        call: typesense-search.list-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-collection\n  \
  \      description: Create a new search collection\n        call: typesense-search.create-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: typesense-search-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted search and content discovery with Typesense.\n    tools:\n    - name: search-collection\n      description: Search documents in a Typesense collection with full-text, filters, and facets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-search.search-collection\n      with:\n        collectionName: tools.collection\n        q: tools.q\n        query_by: tools.query_by\n        filter_by: tools.filter_by\n        sort_by: tools.sort_by\n        facet_by: tools.facet_by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: multi-search\n      description: Execute multiple Typesense searches across different collections\
  \ in one request\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-search.multi-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vector-search\n      description: Perform semantic vector similarity search in Typesense\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-vector.vector-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: multi-vector-search\n      description: Execute multiple vector searches simultaneously across Typesense collections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-vector.multi-vector-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-collections\n      description: List all Typesense search collections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-search.list-collections\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-collection\n      description: Get schema and statistics for a Typesense collection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: typesense-search.get-collection\n      with:\n        collectionName: tools.collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: index-document\n      description: Index a new document into a Typesense collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: typesense-search.index-document\n      with:\n        collectionName: tools.collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-collection\n      description: Create a new Typesense collection with a defined schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: typesense-search.create-collection\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
