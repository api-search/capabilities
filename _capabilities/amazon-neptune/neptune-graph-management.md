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
- start bulk data load
- rdf
- data management
- execute graph queries
- execute gremlin query
- execute an opencypher query
- list all neptune db clusters in the account
- start a neptune bulk data load job from s3
- Graph Developer
- execute opencypher query
- writes gremlin, sparql, and opencypher queries against neptune
- graph analytics, vector search, and ml model training and inference
- data streaming
- graph database management, querying, and data streaming
- bulk data loading operations
- Data Scientist
- Graph Database Administrator
- get graph change stream
- list clusters
- get real-time property graph change stream records
- neptune
- amazon neptune
- graph database
- neptune db cluster management
- start a bulk data load from s3
- bulk loading
- list all neptune db clusters
- ML Engineer
- get property graph change stream records
- trains and deploys neptune ml graph neural network models
- start load job
- gremlin
- list neptune clusters
- machine learning
- graph analytics
- graph change stream operations
- performs graph analytics and builds ml models on graph data
- execute a gremlin graph traversal query
- execute sparql query
- execute an opencypher query against property graph
- manages neptune clusters, instances, and infrastructure
- aws
- get propertygraph stream
- database
- execute a sparql query against rdf graph
- property graph
- sparql
- execute a sparql query against rdf data
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
