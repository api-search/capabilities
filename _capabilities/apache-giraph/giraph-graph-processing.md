---
categories:
- monitoring
consumed_apis: []
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
- get yarn cluster metrics
- hadoop
- list all giraph graph processing jobs
- get giraph job
- monitor giraph graph processing jobs on hadoop yarn
- iterative bsp graph algorithm execution at scale
- monitoring
- open source
- get cluster metrics
- engineers running large-scale graph algorithms with giraph on hadoop
- bsp
- get yarn cluster capacity metrics for running giraph jobs
- big data
- list giraph jobs
- apache
- get metrics
- graph processing
- retired
- list all giraph graph processing jobs running on yarn
- list jobs
- apache giraph
- Data Engineer
- get detailed status of a specific giraph job
- job status tracking and cluster capacity monitoring
- cluster capacity metrics
- giraph graph processing jobs
slug: giraph-graph-processing
source_filename: giraph-graph-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Giraph Graph Processing\n  description: Capability for monitoring Apache Giraph graph processing jobs on Hadoop YARN — tracking job status, completion\n    progress, and cluster capacity. Designed for data engineers running large-scale graph algorithms. Note - Apache Giraph\n    has been retired.\n  tags:\n  - Apache Giraph\n  - Graph Processing\n  - Big Data\n  - Hadoop\n  - Monitoring\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YARN_RESOURCEMANAGER_URL: YARN_RESOURCEMANAGER_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: giraph-job\n    baseUri: http://localhost:8088\n    description: YARN ResourceManager REST API for Giraph job monitoring\n    resources:\n    - name: jobs\n      path: /ws/v1/cluster/apps\n      description: Giraph job management via YARN\n      operations:\n      - name: list-giraph-jobs\n        method: GET\n        description: List all Giraph graph\
  \ processing jobs on YARN\n        inputParameters:\n        - name: applicationTypes\n          in: query\n          type: string\n          required: false\n          description: Filter by application type\n        - name: states\n          in: query\n          type: string\n          required: false\n          description: Filter by job state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-giraph-job\n        method: GET\n        description: Get details of a specific Giraph job\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: YARN application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster\n      path: /ws/v1/cluster/metrics\n      description: YARN cluster metrics\n      operations:\n     \
  \ - name: get-cluster-metrics\n        method: GET\n        description: Get YARN cluster metrics for Giraph job capacity\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: giraph-processing-api\n    description: REST API for Apache Giraph graph processing job monitoring.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Giraph graph processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all Giraph graph processing jobs\n        call: giraph-job.list-giraph-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cluster/metrics\n      name: metrics\n      description: Cluster capacity metrics\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get YARN cluster metrics\n\
  \        call: giraph-job.get-cluster-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: giraph-processing-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Giraph graph processing monitoring.\n    tools:\n    - name: list-giraph-jobs\n      description: List all Giraph graph processing jobs running on YARN\n      hints:\n        readOnly: true\n        openWorld: true\n      call: giraph-job.list-giraph-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-giraph-job\n      description: Get detailed status of a specific Giraph job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: giraph-job.get-giraph-job\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster-metrics\n      description: Get YARN cluster capacity metrics for running Giraph jobs\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: giraph-job.get-cluster-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
