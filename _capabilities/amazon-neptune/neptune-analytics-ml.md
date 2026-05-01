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
- data streaming
- rdf
- gremlin
- amazon neptune
- graph analytics
- neptune ml training job management
- list ml training jobs
- trains and deploys neptune ml graph neural network models
- ML Engineer
- machine learning
- list neptune analytics graphs for in-memory graph analysis
- create a neptune ml inference endpoint for predictions
- graph database management, querying, and data streaming
- graph analytics, vector search, and ml model training and inference
- aws
- Graph Database Administrator
- writes gremlin, sparql, and opencypher queries against neptune
- manages neptune clusters, instances, and infrastructure
- create a neptune analytics graph for graph analytics workloads
- list neptune analytics graphs
- performs graph analytics and builds ml models on graph data
- neptune
- create analytics graph
- list analytics graphs
- property graph
- list neptune ml training jobs
- Data Scientist
- sparql
- database
- neptune analytics graph management
- create ml inference endpoint
- list neptune ml graph neural network training jobs
- bulk loading
- Graph Developer
- graph database
slug: neptune-analytics-ml
source_filename: neptune-analytics-ml.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Neptune Analytics and Machine Learning\n  description: Workflow capability for Neptune Analytics graph analysis, vector search, and Neptune ML graph neural network model training and inference. Used by data scientists and ML engineers.\n  tags:\n  - Amazon Neptune\n  - AWS\n  - Graph Analytics\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: analytics\n    location: ./shared/analytics.yaml\n  - import: ml\n    location: ./shared/ml.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: neptune-analytics-api\n    description: Unified REST API for Neptune Analytics and ML.\n    resources:\n    - path: /v1/graphs\n      name: analytics-graphs\n      description: Neptune Analytics graph management\n      operations:\n      - method: GET\n        name: list-analytics-graphs\n        description:\
  \ List Neptune Analytics graphs\n        call: analytics.listGraphs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ml/jobs\n      name: ml-jobs\n      description: Neptune ML training job management\n      operations:\n      - method: GET\n        name: list-ml-jobs\n        description: List Neptune ML training jobs\n        call: ml.listMLJobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: neptune-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Neptune Analytics and ML operations.\n    tools:\n    - name: list-analytics-graphs\n      description: List Neptune Analytics graphs for in-memory graph analysis\n      hints:\n        readOnly: true\n      call: analytics.listGraphs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-analytics-graph\n      description: Create a Neptune Analytics graph for graph\
  \ analytics workloads\n      hints:\n        readOnly: false\n      call: analytics.createGraph\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ml-training-jobs\n      description: List Neptune ML graph neural network training jobs\n      hints:\n        readOnly: true\n      call: ml.listMLJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ml-inference-endpoint\n      description: Create a Neptune ML inference endpoint for predictions\n      hints:\n        readOnly: false\n      call: ml.createMLEndpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-neptune/refs/heads/main/capabilities/neptune-analytics-ml.yaml
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
