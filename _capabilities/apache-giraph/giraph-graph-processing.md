---
categories:
- monitoring
consumed_apis:
- giraph-job
description: Capability for monitoring Apache Giraph graph processing jobs on Hadoop YARN — tracking job status, completion progress, and cluster capacity. Designed for data engineers running large-scale graph algorithms. Note - Apache Giraph has been retired.
layout: capability
name: Apache Giraph Graph Processing
operations:
- description: List all Giraph graph processing jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get YARN cluster metrics
  method: GET
  name: get-metrics
  path: /v1/cluster/metrics
personas: []
provider_name: Apache Giraph
provider_slug: apache-giraph
search_terms:
- cluster capacity metrics
- bsp
- engineers running large-scale graph algorithms with giraph on hadoop
- Data Engineer
- get yarn cluster metrics
- list all giraph graph processing jobs
- iterative bsp graph algorithm execution at scale
- get cluster metrics
- get yarn cluster capacity metrics for running giraph jobs
- list all giraph graph processing jobs running on yarn
- retired
- apache giraph
- open source
- apache
- job status tracking and cluster capacity monitoring
- monitoring
- get metrics
- get giraph job
- graph processing
- get detailed status of a specific giraph job
- big data
- list jobs
- hadoop
- monitor giraph graph processing jobs on hadoop yarn
- giraph graph processing jobs
- list giraph jobs
slug: giraph-graph-processing
source_filename: giraph-graph-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Giraph Graph Processing\"\n  description: \"Capability for monitoring Apache Giraph graph processing jobs on Hadoop YARN — tracking job status, completion progress, and cluster capacity. Designed for data engineers running large-scale graph algorithms. Note - Apache Giraph has been retired.\"\n  tags:\n    - Apache Giraph\n    - Graph Processing\n    - Big Data\n    - Hadoop\n    - Monitoring\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      YARN_RESOURCEMANAGER_URL: YARN_RESOURCEMANAGER_URL\ncapability:\n  consumes:\n    - import: giraph-job\n      location: ./shared/giraph-job.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: giraph-processing-api\n      description: \"REST API for Apache Giraph graph processing job monitoring.\"\n      resources:\n        - path: /v1/jobs\n          name: jobs\n          description: Giraph graph processing jobs\n \
  \         operations:\n            - method: GET\n              name: list-jobs\n              description: List all Giraph graph processing jobs\n              call: \"giraph-job.list-giraph-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cluster/metrics\n          name: metrics\n          description: Cluster capacity metrics\n          operations:\n            - method: GET\n              name: get-metrics\n              description: Get YARN cluster metrics\n              call: \"giraph-job.get-cluster-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: giraph-processing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Giraph graph processing monitoring.\"\n      tools:\n        - name: list-giraph-jobs\n          description: List all Giraph graph processing jobs\
  \ running on YARN\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"giraph-job.list-giraph-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-giraph-job\n          description: Get detailed status of a specific Giraph job\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"giraph-job.get-giraph-job\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster-metrics\n          description: Get YARN cluster capacity metrics for running Giraph jobs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"giraph-job.get-cluster-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-giraph/refs/heads/main/capabilities/giraph-graph-processing.yaml
tags:
- Apache Giraph
- Graph Processing
- Big Data
- Hadoop
- Monitoring
tools:
- description: List all Giraph graph processing jobs running on YARN
  hints:
    openWorld: true
    readOnly: true
  name: list-giraph-jobs
- description: Get detailed status of a specific Giraph job
  hints:
    openWorld: true
    readOnly: true
  name: get-giraph-job
- description: Get YARN cluster capacity metrics for running Giraph jobs
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-metrics
---
