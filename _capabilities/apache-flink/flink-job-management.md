---
categories:
- monitoring
consumed_apis: []
description: Unified capability for managing and monitoring Apache Flink streaming and batch jobs — submitting, tracking, monitoring metrics, and managing the cluster. Designed for data engineers and platform operators.
layout: capability
name: Apache Flink Job Management
operations:
- description: List all Flink jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get details of a specific job
  method: GET
  name: get-job
  path: /v1/jobs
- description: List all TaskManagers
  method: GET
  name: list-taskmanagers
  path: /v1/taskmanagers
- description: Get metrics for a Flink job
  method: GET
  name: get-job-metrics
  path: /v1/jobs/{jobid}/metrics
personas: []
provider_name: Apache Flink
provider_slug: apache-flink
search_terms:
- get job
- list all taskmanagers
- list jobs
- get detailed status and information for a specific flink job
- stateful computing
- list flink jobs
- metrics, checkpoints, and cluster health monitoring
- big data
- get flink job
- manage and monitor flink streaming and batch jobs
- get performance metrics for a flink job
- real-time analytics
- list taskmanagers
- Data Engineer
- data engineering
- apache
- monitoring
- get metrics for a flink job
- apache flink
- list all taskmanagers in the flink cluster
- open source
- operators managing the flink cluster and ensuring job reliability
- list all flink streaming and batch jobs
- shutdown cluster
- Platform Operator
- taskmanager management
- job submission, tracking, and lifecycle management
- job performance metrics
- stream processing
- flink job management
- get details of a specific job
- batch processing
- shut down the flink cluster
- get job metrics
- job management
- engineers submitting and monitoring flink streaming and batch jobs
- list all flink jobs
slug: flink-job-management
source_filename: flink-job-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Flink Job Management\n  description: Unified capability for managing and monitoring Apache Flink streaming and batch jobs — submitting, tracking,\n    monitoring metrics, and managing the cluster. Designed for data engineers and platform operators.\n  tags:\n  - Apache Flink\n  - Stream Processing\n  - Job Management\n  - Data Engineering\n  - Monitoring\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FLINK_JOBMANAGER_URL: FLINK_JOBMANAGER_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: flink-rest\n    baseUri: http://localhost:8081\n    description: Apache Flink JobManager REST API\n    resources:\n    - name: jobs\n      path: /jobs\n      description: Manage Flink jobs\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List all Flink jobs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get details of a specific Flink job\n        inputParameters:\n        - name: jobid\n          in: path\n          type: string\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster\n      path: /cluster\n      description: Cluster management operations\n      operations:\n      - name: shutdown-cluster\n        method: DELETE\n        description: Shut down the Flink cluster\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskmanagers\n      path: /taskmanagers\n      description: TaskManager management\n      operations:\n      - name: list-taskmanagers\n        method: GET\n        description:\
  \ List all TaskManagers in the cluster\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /jobs/{jobid}/metrics\n      description: Job metrics access\n      operations:\n      - name: get-job-metrics\n        method: GET\n        description: Get metrics for a specific Flink job\n        inputParameters:\n        - name: jobid\n          in: path\n          type: string\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flink-management-api\n    description: Unified REST API for Apache Flink job management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Flink job management\n      operations:\n      - method: GET\n        name: list-jobs\n\
  \        description: List all Flink jobs\n        call: flink-rest.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-job\n        description: Get details of a specific job\n        call: flink-rest.get-job\n        with:\n          jobid: rest.jobid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/taskmanagers\n      name: taskmanagers\n      description: TaskManager management\n      operations:\n      - method: GET\n        name: list-taskmanagers\n        description: List all TaskManagers\n        call: flink-rest.list-taskmanagers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobid}/metrics\n      name: metrics\n      description: Job performance metrics\n      operations:\n      - method: GET\n        name: get-job-metrics\n        description: Get metrics for a Flink job\n        call: flink-rest.get-job-metrics\n\
  \        with:\n          jobid: rest.jobid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: flink-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Flink job management.\n    tools:\n    - name: list-flink-jobs\n      description: List all Flink streaming and batch jobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flink-rest.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flink-job\n      description: Get detailed status and information for a specific Flink job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flink-rest.get-job\n      with:\n        jobid: tools.jobid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-taskmanagers\n      description: List all TaskManagers in the Flink cluster\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: flink-rest.list-taskmanagers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-metrics\n      description: Get performance metrics for a Flink job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flink-rest.get-job-metrics\n      with:\n        jobid: tools.jobid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdown-cluster\n      description: Shut down the Flink cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flink-rest.shutdown-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-flink/refs/heads/main/capabilities/flink-job-management.yaml
tags:
- Apache Flink
- Stream Processing
- Job Management
- Data Engineering
- Monitoring
tools:
- description: List all Flink streaming and batch jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-flink-jobs
- description: Get detailed status and information for a specific Flink job
  hints:
    openWorld: true
    readOnly: true
  name: get-flink-job
- description: List all TaskManagers in the Flink cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-taskmanagers
- description: Get performance metrics for a Flink job
  hints:
    openWorld: true
    readOnly: true
  name: get-job-metrics
- description: Shut down the Flink cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdown-cluster
---
