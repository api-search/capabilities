---
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
- start load job
- data management
- aws
- neptune db cluster management
- execute opencypher query
- graph database management, querying, and data streaming
- trains and deploys neptune ml graph neural network models
- execute sparql query
- graph change stream operations
- execute a gremlin graph traversal query
- Data Scientist
- get property graph change stream records
- execute gremlin query
- performs graph analytics and builds ml models on graph data
- Graph Developer
- rdf
- bulk loading
- sparql
- list neptune clusters
- neptune
- graph analytics
- manages neptune clusters, instances, and infrastructure
- get propertygraph stream
- property graph
- list all neptune db clusters in the account
- writes gremlin, sparql, and opencypher queries against neptune
- list clusters
- list all neptune db clusters
- execute graph queries
- execute a sparql query against rdf graph
- start bulk data load
- start a bulk data load from s3
- Graph Database Administrator
- start a neptune bulk data load job from s3
- ML Engineer
- graph database
- database
- execute an opencypher query against property graph
- machine learning
- data streaming
- amazon neptune
- bulk data loading operations
- gremlin
- execute a sparql query against rdf data
- graph analytics, vector search, and ml model training and inference
- get real-time property graph change stream records
- get graph change stream
- execute an opencypher query
slug: neptune-graph-management
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
