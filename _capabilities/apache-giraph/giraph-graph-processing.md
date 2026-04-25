---
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
- bsp
- apache giraph
- cluster capacity metrics
- get detailed status of a specific giraph job
- get metrics
- giraph graph processing jobs
- open source
- list jobs
- iterative bsp graph algorithm execution at scale
- get yarn cluster capacity metrics for running giraph jobs
- engineers running large-scale graph algorithms with giraph on hadoop
- apache
- Data Engineer
- monitoring
- graph processing
- list all giraph graph processing jobs running on yarn
- get cluster metrics
- list giraph jobs
- job status tracking and cluster capacity monitoring
- monitor giraph graph processing jobs on hadoop yarn
- get giraph job
- retired
- list all giraph graph processing jobs
- hadoop
- big data
- get yarn cluster metrics
slug: giraph-graph-processing
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
