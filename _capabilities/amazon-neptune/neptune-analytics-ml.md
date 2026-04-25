---
consumed_apis:
- analytics
- ml
description: Workflow capability for Neptune Analytics graph analysis, vector search, and Neptune ML graph neural network model training and inference. Used by data scientists and ML engineers.
layout: capability
name: Amazon Neptune Analytics and Machine Learning
operations:
- description: List Neptune Analytics graphs
  method: GET
  name: list-analytics-graphs
  path: /v1/graphs
- description: List Neptune ML training jobs
  method: GET
  name: list-ml-jobs
  path: /v1/ml/jobs
personas: []
provider_name: Amazon Neptune
provider_slug: amazon-neptune
search_terms:
- performs graph analytics and builds ml models on graph data
- graph analytics, vector search, and ml model training and inference
- writes gremlin, sparql, and opencypher queries against neptune
- manages neptune clusters, instances, and infrastructure
- machine learning
- neptune
- neptune ml training job management
- database
- list analytics graphs
- list neptune ml graph neural network training jobs
- list ml training jobs
- graph database
- sparql
- data streaming
- create a neptune analytics graph for graph analytics workloads
- Graph Database Administrator
- create a neptune ml inference endpoint for predictions
- Graph Developer
- ML Engineer
- graph database management, querying, and data streaming
- property graph
- graph analytics
- trains and deploys neptune ml graph neural network models
- list neptune ml training jobs
- list neptune analytics graphs for in-memory graph analysis
- list neptune analytics graphs
- Data Scientist
- gremlin
- neptune analytics graph management
- aws
- create ml inference endpoint
- amazon neptune
- bulk loading
- list ml jobs
- create analytics graph
- rdf
slug: neptune-analytics-ml
tags:
- Amazon Neptune
- AWS
- Graph Analytics
- Machine Learning
tools:
- description: List Neptune Analytics graphs for in-memory graph analysis
  hints:
    readOnly: true
  name: list-analytics-graphs
- description: Create a Neptune Analytics graph for graph analytics workloads
  hints:
    readOnly: false
  name: create-analytics-graph
- description: List Neptune ML graph neural network training jobs
  hints:
    readOnly: true
  name: list-ml-training-jobs
- description: Create a Neptune ML inference endpoint for predictions
  hints:
    readOnly: false
  name: create-ml-inference-endpoint
---
