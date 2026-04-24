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
- rdf
- list neptune analytics graphs for in-memory graph analysis
- Graph Developer
- create a neptune analytics graph for graph analytics workloads
- writes gremlin, sparql, and opencypher queries against neptune
- neptune ml training job management
- graph analytics, vector search, and ml model training and inference
- data streaming
- create ml inference endpoint
- graph database management, querying, and data streaming
- Data Scientist
- Graph Database Administrator
- list neptune analytics graphs
- neptune
- list analytics graphs
- amazon neptune
- graph database
- list neptune ml training jobs
- bulk loading
- ML Engineer
- create analytics graph
- neptune analytics graph management
- trains and deploys neptune ml graph neural network models
- gremlin
- machine learning
- graph analytics
- performs graph analytics and builds ml models on graph data
- manages neptune clusters, instances, and infrastructure
- aws
- list ml training jobs
- database
- create a neptune ml inference endpoint for predictions
- property graph
- list neptune ml graph neural network training jobs
- sparql
- list ml jobs
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
