---
categories: []
consumed_apis:
- kendra
description: Unified workflow capability for Amazon Kendra enterprise search, combining index management, data source connectivity, document indexing, and intelligent query operations for knowledge management and RAG workflows.
layout: capability
name: Amazon Kendra Enterprise Search
operations:
- description: Create a new search index
  method: POST
  name: create-index
  path: /v1/indexes
- description: List all search indexes
  method: GET
  name: list-indexes
  path: /v1/indexes
- description: Search an index with natural language
  method: POST
  name: search
  path: /v1/indexes/{IndexId}/query
- description: Create a data source connector
  method: POST
  name: create-data-source
  path: /v1/indexes/{IndexId}/data-sources
- description: List data source connectors
  method: GET
  name: list-data-sources
  path: /v1/indexes/{IndexId}/data-sources
- description: Add documents to an index
  method: POST
  name: index-documents
  path: /v1/indexes/{IndexId}/documents
personas: []
provider_name: Amazon Kendra
provider_slug: amazon-kendra
search_terms:
- list search indexes
- index documents
- enterprise search
- search
- data source connector management
- list all data source connectors for a kendra index
- configures and maintains data source connectors and index settings
- enterprise knowledge organization and discovery
- knowledge management
- search an amazon kendra index using natural language query
- ai
- search an index with natural language
- integrates kendra search into applications and rag pipelines
- aws
- natural language
- add documents to an index
- IT Administrator
- search index
- search index management
- Developer
- manages enterprise knowledge bases and search indexes
- intelligent search
- list data source connectors
- connect data source
- list indexes
- create index
- machine learning
- create a new amazon kendra enterprise search index
- add documents to an amazon kendra search index
- document management
- intelligent search and information retrieval
- create a data source connector
- list all amazon kendra search indexes
- list data sources
- create a new search index
- connect a data repository (s3, sharepoint, salesforce, etc.) to a kendra index
- unified workflow for search index management, data connectivity, and query operations
- create search index
- list all search indexes
- create data source
- Knowledge Manager
- amazon kendra
slug: amazon-kendra-enterprise-search
source_filename: amazon-kendra-enterprise-search.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Kendra Enterprise Search\"\n  description: \"Unified workflow capability for Amazon Kendra enterprise search, combining index management, data source connectivity, document indexing, and intelligent query operations for knowledge management and RAG workflows.\"\n  tags:\n    - Amazon Kendra\n    - Enterprise Search\n    - Machine Learning\n    - AWS\n    - Knowledge Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: kendra\n      location: ./shared/kendra.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: kendra-search-api\n      description: \"Unified REST API for Amazon Kendra enterprise search operations.\"\n      resources:\n        - path: /v1/indexes\n          name: indexes\n          description: \"\
  Search index management\"\n          operations:\n            - method: POST\n              name: create-index\n              description: \"Create a new search index\"\n              call: \"kendra.create-index\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-indexes\n              description: \"List all search indexes\"\n              call: \"kendra.list-indexes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/indexes/{IndexId}/query\n          name: search\n          description: \"Intelligent search\"\n          operations:\n            - method: POST\n              name: search\n              description: \"Search an index with natural language\"\n              call: \"kendra.query\"\n              with:\n                IndexId: \"rest.IndexId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/indexes/{IndexId}/data-sources\n          name: data-sources\n          description: \"Data source connector management\"\n          operations:\n            - method: POST\n              name: create-data-source\n              description: \"Create a data source connector\"\n              call: \"kendra.create-data-source\"\n              with:\n                IndexId: \"rest.IndexId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-data-sources\n              description: \"List data source connectors\"\n              call: \"kendra.list-data-sources\"\n              with:\n                IndexId: \"rest.IndexId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/indexes/{IndexId}/documents\n          name: documents\n          description: \"Document\
  \ management\"\n          operations:\n            - method: POST\n              name: index-documents\n              description: \"Add documents to an index\"\n              call: \"kendra.batch-put-document\"\n              with:\n                IndexId: \"rest.IndexId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: kendra-search-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Kendra search operations.\"\n      tools:\n        - name: create-search-index\n          description: \"Create a new Amazon Kendra enterprise search index\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"kendra.create-index\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-search-indexes\n          description: \"List all Amazon Kendra search indexes\"\n  \
  \        hints:\n            readOnly: true\n            idempotent: true\n          call: \"kendra.list-indexes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-index\n          description: \"Search an Amazon Kendra index using natural language query\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kendra.query\"\n          with:\n            IndexId: \"tools.IndexId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: connect-data-source\n          description: \"Connect a data repository (S3, SharePoint, Salesforce, etc.) to a Kendra index\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"kendra.create-data-source\"\n          with:\n            IndexId: \"tools.IndexId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-data-sources\n          description: \"List all data source connectors for a Kendra index\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"kendra.list-data-sources\"\n          with:\n            IndexId: \"tools.IndexId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: index-documents\n          description: \"Add documents to an Amazon Kendra search index\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"kendra.batch-put-document\"\n          with:\n            IndexId: \"tools.IndexId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-kendra/refs/heads/main/capabilities/amazon-kendra-enterprise-search.yaml
tags:
- Amazon Kendra
- Enterprise Search
- Machine Learning
- AWS
- Knowledge Management
tools:
- description: Create a new Amazon Kendra enterprise search index
  hints:
    idempotent: false
    readOnly: false
  name: create-search-index
- description: List all Amazon Kendra search indexes
  hints:
    idempotent: true
    readOnly: true
  name: list-search-indexes
- description: Search an Amazon Kendra index using natural language query
  hints:
    openWorld: true
    readOnly: true
  name: search-index
- description: Connect a data repository (S3, SharePoint, Salesforce, etc.) to a Kendra index
  hints:
    idempotent: false
    readOnly: false
  name: connect-data-source
- description: List all data source connectors for a Kendra index
  hints:
    idempotent: true
    readOnly: true
  name: list-data-sources
- description: Add documents to an Amazon Kendra search index
  hints:
    idempotent: false
    readOnly: false
  name: index-documents
---
