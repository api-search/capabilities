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
- apache
- get metrics for a flink job
- big data
- job submission, tracking, and lifecycle management
- list all flink jobs
- monitoring
- list all flink streaming and batch jobs
- list all taskmanagers in the flink cluster
- metrics, checkpoints, and cluster health monitoring
- shut down the flink cluster
- apache flink
- real-time analytics
- get details of a specific job
- taskmanager management
- get performance metrics for a flink job
- Platform Operator
- get job
- operators managing the flink cluster and ensuring job reliability
- batch processing
- data engineering
- Data Engineer
- manage and monitor flink streaming and batch jobs
- get detailed status and information for a specific flink job
- get flink job
- job performance metrics
- list all taskmanagers
- engineers submitting and monitoring flink streaming and batch jobs
- shutdown cluster
- stateful computing
- flink job management
- get job metrics
- list jobs
- list taskmanagers
- stream processing
- list flink jobs
- job management
- open source
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
