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
- engineers running large-scale graph algorithms with giraph on hadoop
- get metrics
- list jobs
- big data
- get giraph job
- get yarn cluster capacity metrics for running giraph jobs
- get detailed status of a specific giraph job
- giraph graph processing jobs
- get yarn cluster metrics
- Data Engineer
- list all giraph graph processing jobs running on yarn
- iterative bsp graph algorithm execution at scale
- cluster capacity metrics
- get cluster metrics
- apache
- monitor giraph graph processing jobs on hadoop yarn
- retired
- list giraph jobs
- hadoop
- bsp
- list all giraph graph processing jobs
- monitoring
- job status tracking and cluster capacity monitoring
- graph processing
- apache giraph
- open source
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
