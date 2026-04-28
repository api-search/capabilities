---
categories:
- machine-learning
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
- list ml jobs
- manages neptune clusters, instances, and infrastructure
- list neptune ml training jobs
- list neptune analytics graphs for in-memory graph analysis
- graph database management, querying, and data streaming
- property graph
- create ml inference endpoint
- amazon neptune
- neptune analytics graph management
- neptune ml training job management
- graph analytics, vector search, and ml model training and inference
- list neptune analytics graphs
- database
- create a neptune ml inference endpoint for predictions
- ML Engineer
- Data Scientist
- create analytics graph
- graph database
- bulk loading
- rdf
- graph analytics
- list analytics graphs
- sparql
- neptune
- list neptune ml graph neural network training jobs
- gremlin
- list ml training jobs
- writes gremlin, sparql, and opencypher queries against neptune
- performs graph analytics and builds ml models on graph data
- data streaming
- machine learning
- trains and deploys neptune ml graph neural network models
- aws
- create a neptune analytics graph for graph analytics workloads
- Graph Database Administrator
- Graph Developer
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
