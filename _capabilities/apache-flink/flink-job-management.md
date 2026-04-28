---
categories:
- monitoring
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
- list all flink streaming and batch jobs
- list flink jobs
- metrics, checkpoints, and cluster health monitoring
- list all flink jobs
- data engineering
- get details of a specific job
- batch processing
- list all taskmanagers in the flink cluster
- stream processing
- Platform Operator
- get metrics for a flink job
- manage and monitor flink streaming and batch jobs
- job management
- job submission, tracking, and lifecycle management
- list taskmanagers
- get detailed status and information for a specific flink job
- apache
- get job
- stateful computing
- taskmanager management
- list all taskmanagers
- open source
- get flink job
- get performance metrics for a flink job
- shutdown cluster
- get job metrics
- monitoring
- Data Engineer
- big data
- apache flink
- list jobs
- operators managing the flink cluster and ensuring job reliability
- job performance metrics
- real-time analytics
- engineers submitting and monitoring flink streaming and batch jobs
- shut down the flink cluster
- flink job management
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
