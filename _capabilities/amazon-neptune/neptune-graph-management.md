---
categories: []
consumed_apis:
- management
- data
- loader
- streams
description: Workflow capability for managing Neptune graph databases, executing queries across Gremlin, SPARQL, and openCypher, and monitoring data streams. Used by graph database administrators and developers.
layout: capability
name: Amazon Neptune Graph Data Management
operations:
- description: List all Neptune DB clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Execute a Gremlin graph traversal query
  method: POST
  name: execute-gremlin-query
  path: /v1/queries
- description: Execute a SPARQL query against RDF graph
  method: POST
  name: execute-sparql-query
  path: /v1/queries
- description: Execute an openCypher query
  method: POST
  name: execute-opencypher-query
  path: /v1/queries
- description: Start a bulk data load from S3
  method: POST
  name: start-load-job
  path: /v1/loader
- description: Get property graph change stream records
  method: GET
  name: get-propertygraph-stream
  path: /v1/streams
personas: []
provider_name: Amazon Neptune
provider_slug: amazon-neptune
search_terms:
- graph database
- list neptune clusters
- bulk data loading operations
- start load job
- writes gremlin, sparql, and opencypher queries against neptune
- trains and deploys neptune ml graph neural network models
- execute a gremlin graph traversal query
- execute sparql query
- get property graph change stream records
- start a bulk data load from s3
- machine learning
- execute a sparql query against rdf graph
- execute gremlin query
- graph database management, querying, and data streaming
- list clusters
- neptune db cluster management
- sparql
- gremlin
- data management
- bulk loading
- execute graph queries
- get real-time property graph change stream records
- neptune
- database
- execute opencypher query
- start a neptune bulk data load job from s3
- graph analytics
- execute a sparql query against rdf data
- aws
- rdf
- execute an opencypher query
- get propertygraph stream
- list all neptune db clusters
- get graph change stream
- graph analytics, vector search, and ml model training and inference
- property graph
- ML Engineer
- execute an opencypher query against property graph
- graph change stream operations
- start bulk data load
- manages neptune clusters, instances, and infrastructure
- Graph Developer
- amazon neptune
- Graph Database Administrator
- Data Scientist
- data streaming
- performs graph analytics and builds ml models on graph data
- list all neptune db clusters in the account
slug: neptune-graph-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Neptune Graph Data Management\n  description: Workflow capability for managing Neptune graph databases, executing queries across Gremlin, SPARQL, and openCypher, and monitoring data streams. Used by graph database administrators \n    and developers.\n  tags:\n  - Amazon Neptune\n  - AWS\n  - Graph Database\n  - Data Management\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: management\n    location: ./shared/management.yaml\n  - import: data\n    location: ./shared/data.yaml\n  - import: loader\n    location: ./shared/loader.yaml\n  - import: streams\n    location: ./shared/streams.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: neptune-graph-management-api\n    description: Unified REST API for Neptune graph database management.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n     \
  \ description: Neptune DB cluster management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all Neptune DB clusters\n        call: management.describeDBClusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries\n      name: queries\n      description: Execute graph queries\n      operations:\n      - method: POST\n        name: execute-gremlin-query\n        description: Execute a Gremlin graph traversal query\n        call: data.executeGremlinQuery\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: execute-sparql-query\n        description: Execute a SPARQL query against RDF graph\n        call: data.executeSparqlQuery\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: execute-opencypher-query\n        description: Execute an openCypher query\n        call: data.executeOpenCypherQuery\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loader\n      name: loader\n      description: Bulk data loading operations\n      operations:\n      - method: POST\n        name: start-load-job\n        description: Start a bulk data load from S3\n        call: loader.startLoaderJob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/streams\n      name: streams\n      description: Graph change stream operations\n      operations:\n      - method: GET\n        name: get-propertygraph-stream\n        description: Get property graph change stream records\n        call: streams.getPropertygraphStream\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: neptune-graph-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Neptune graph database management.\n    tools:\n    - name: list-neptune-clusters\n      description:\
  \ List all Neptune DB clusters in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: management.describeDBClusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-gremlin-query\n      description: Execute a Gremlin graph traversal query\n      hints:\n        readOnly: true\n      call: data.executeGremlinQuery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-sparql-query\n      description: Execute a SPARQL query against RDF data\n      hints:\n        readOnly: true\n      call: data.executeSparqlQuery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-opencypher-query\n      description: Execute an openCypher query against property graph\n      hints:\n        readOnly: true\n      call: data.executeOpenCypherQuery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-bulk-data-load\n      description:\
  \ Start a Neptune bulk data load job from S3\n      hints:\n        readOnly: false\n      call: loader.startLoaderJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-graph-change-stream\n      description: Get real-time property graph change stream records\n      hints:\n        readOnly: true\n      call: streams.getPropertygraphStream\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-neptune/refs/heads/main/capabilities/neptune-graph-management.yaml
tags:
- Amazon Neptune
- AWS
- Graph Database
- Data Management
tools:
- description: List all Neptune DB clusters in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-neptune-clusters
- description: Execute a Gremlin graph traversal query
  hints:
    readOnly: true
  name: execute-gremlin-query
- description: Execute a SPARQL query against RDF data
  hints:
    readOnly: true
  name: execute-sparql-query
- description: Execute an openCypher query against property graph
  hints:
    readOnly: true
  name: execute-opencypher-query
- description: Start a Neptune bulk data load job from S3
  hints:
    readOnly: false
  name: start-bulk-data-load
- description: Get real-time property graph change stream records
  hints:
    readOnly: true
  name: get-graph-change-stream
---
