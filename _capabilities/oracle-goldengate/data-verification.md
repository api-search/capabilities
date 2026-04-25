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
- oracle goldengate
- enterprise
- list process metrics
- get veridata server information
- data verification
- database connections for verification
- compare groups
- compliance
- create a new comparison job
- replication process metrics
- get server info
- create group
- database
- list jobs
- create job
- create connection
- execute a comparison job
- get details of out-of-sync data
- repair job
- create a new veridata database connection
- list comparison jobs
- get comparison job statistics
- get out of sync data
- comparison jobs
- get job statistics
- data quality
- real-time replication
- run job
- list compare groups
- create a new compare group
- data integration
- list groups
- cdc
- list connections
- list replication process performance metrics
- data synchronization
- repair out-of-sync data identified by a comparison job
- list compare groups for data verification
- get goldengate process performance metrics for monitoring replication health
- list veridata database connections
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
