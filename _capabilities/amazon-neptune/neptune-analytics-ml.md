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
- property graph
- create a neptune analytics graph for graph analytics workloads
- machine learning
- data streaming
- database
- manages neptune clusters, instances, and infrastructure
- writes gremlin, sparql, and opencypher queries against neptune
- list neptune analytics graphs for in-memory graph analysis
- sparql
- aws
- create analytics graph
- Graph Database Administrator
- ML Engineer
- list analytics graphs
- neptune
- gremlin
- list neptune ml training jobs
- list ml jobs
- rdf
- trains and deploys neptune ml graph neural network models
- list neptune analytics graphs
- amazon neptune
- list ml training jobs
- neptune ml training job management
- create ml inference endpoint
- Data Scientist
- performs graph analytics and builds ml models on graph data
- graph analytics, vector search, and ml model training and inference
- graph analytics
- Graph Developer
- graph database management, querying, and data streaming
- neptune analytics graph management
- list neptune ml graph neural network training jobs
- graph database
- create a neptune ml inference endpoint for predictions
- bulk loading
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
