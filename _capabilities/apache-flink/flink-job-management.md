---
consumed_apis:
- flink-rest
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
- get performance metrics for a flink job
- real-time analytics
- Data Engineer
- get job
- list jobs
- monitoring
- list all flink jobs
- shutdown cluster
- list all taskmanagers
- job performance metrics
- shut down the flink cluster
- get metrics for a flink job
- big data
- apache
- get details of a specific job
- get job metrics
- list all taskmanagers in the flink cluster
- data engineering
- Platform Operator
- stateful computing
- job management
- stream processing
- taskmanager management
- metrics, checkpoints, and cluster health monitoring
- apache flink
- list taskmanagers
- list flink jobs
- get flink job
- list all flink streaming and batch jobs
- get detailed status and information for a specific flink job
- manage and monitor flink streaming and batch jobs
- batch processing
- flink job management
- engineers submitting and monitoring flink streaming and batch jobs
- job submission, tracking, and lifecycle management
- open source
- operators managing the flink cluster and ensuring job reliability
slug: flink-job-management
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
