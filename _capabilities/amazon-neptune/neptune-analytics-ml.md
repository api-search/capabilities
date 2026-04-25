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
- create a neptune ml inference endpoint for predictions
- list ml training jobs
- list neptune ml training jobs
- amazon neptune
- list ml jobs
- Graph Developer
- create a neptune analytics graph for graph analytics workloads
- performs graph analytics and builds ml models on graph data
- list analytics graphs
- list neptune analytics graphs for in-memory graph analysis
- create analytics graph
- trains and deploys neptune ml graph neural network models
- neptune ml training job management
- Data Scientist
- database
- gremlin
- machine learning
- property graph
- list neptune analytics graphs
- data streaming
- Graph Database Administrator
- create ml inference endpoint
- manages neptune clusters, instances, and infrastructure
- writes gremlin, sparql, and opencypher queries against neptune
- bulk loading
- neptune analytics graph management
- rdf
- list neptune ml graph neural network training jobs
- ML Engineer
- graph database
- sparql
- aws
- graph analytics, vector search, and ml model training and inference
- neptune
- graph database management, querying, and data streaming
- graph analytics
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
