---
consumed_apis:
- goldengate-veridata
- goldengate-rest
description: Unified workflow for verifying data consistency between source and target databases. Combines Veridata for data comparison and repair with core GoldenGate monitoring for data quality engineers and DBAs ensuring replication integrity.
layout: capability
name: Oracle GoldenGate Data Verification
operations:
- description: List Veridata database connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List compare groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: List comparison jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: List replication process performance metrics
  method: GET
  name: list-process-metrics
  path: /v1/metrics
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- get comparison job statistics
- repair out-of-sync data identified by a comparison job
- list veridata database connections
- repair job
- get details of out-of-sync data
- list jobs
- create group
- compare groups
- list replication process performance metrics
- get veridata server information
- enterprise
- real-time replication
- get out of sync data
- create a new compare group
- database connections for verification
- data quality
- create job
- database
- get goldengate process performance metrics for monitoring replication health
- compliance
- execute a comparison job
- create a new veridata database connection
- get job statistics
- list connections
- comparison jobs
- data integration
- get server info
- data synchronization
- oracle goldengate
- cdc
- replication process metrics
- list groups
- list process metrics
- run job
- list comparison jobs
- list compare groups for data verification
- create connection
- data verification
- create a new comparison job
- list compare groups
slug: data-verification
tags:
- Oracle GoldenGate
- Data Verification
- Data Quality
- Compliance
tools:
- description: List Veridata database connections
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Create a new Veridata database connection
  hints:
    readOnly: false
  name: create-connection
- description: List compare groups for data verification
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new compare group
  hints:
    readOnly: false
  name: create-group
- description: List comparison jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Create a new comparison job
  hints:
    readOnly: false
  name: create-job
- description: Execute a comparison job
  hints:
    readOnly: false
  name: run-job
- description: Get comparison job statistics
  hints:
    openWorld: true
    readOnly: true
  name: get-job-statistics
- description: Get details of out-of-sync data
  hints:
    openWorld: true
    readOnly: true
  name: get-out-of-sync-data
- description: Repair out-of-sync data identified by a comparison job
  hints:
    destructive: true
    readOnly: false
  name: repair-job
- description: Get Veridata server information
  hints:
    openWorld: true
    readOnly: true
  name: get-server-info
- description: Get GoldenGate process performance metrics for monitoring replication health
  hints:
    openWorld: true
    readOnly: true
  name: list-process-metrics
---
