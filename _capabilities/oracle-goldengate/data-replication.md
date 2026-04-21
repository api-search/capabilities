---
consumed_apis:
- goldengate-rest
- goldengate-big-data
- goldengate-data-streams
description: Unified workflow for managing real-time data replication across on-premises and cloud environments. Combines the core GoldenGate REST API, Big Data API, and Data Streams API for data integration engineers managing CDC pipelines, extract/replicat processes, and data distribution.
layout: capability
name: Oracle GoldenGate Data Replication
operations:
- description: List all Extract processes
  method: GET
  name: list-extracts
  path: /v1/extracts
- description: Create a new Extract process
  method: POST
  name: create-extract
  path: /v1/extracts
- description: Get a specific Extract process
  method: GET
  name: get-extract
  path: /v1/extracts/{extract}
- description: Delete an Extract process
  method: DELETE
  name: delete-extract
  path: /v1/extracts/{extract}
- description: List all Replicat processes
  method: GET
  name: list-replicats
  path: /v1/replicats
- description: List all big data Replicat processes
  method: GET
  name: list-big-data-replicats
  path: /v1/big-data-replicats
- description: List all data streams
  method: GET
  name: list-data-streams
  path: /v1/data-streams
- description: List available big data target types
  method: GET
  name: list-data-target-types
  path: /v1/data-target-types
- description: List credential domains
  method: GET
  name: list-credential-domains
  path: /v1/credentials
- description: List distribution paths
  method: GET
  name: list-distribution-paths
  path: /v1/distribution-paths
- description: Get service health details
  method: GET
  name: get-service-health
  path: /v1/health
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- list extracts
- list all data streams
- get performance metrics for all running processes
- service health
- create extract
- get service health details
- database
- bigdata get replicat
- issue a command to a replicat process
- list all extract processes from the core goldengate deployment
- list process metrics
- data synchronization
- core issue replicat command
- enterprise
- data replication
- data stream management
- get details of a specific extract process
- core issue extract command
- list available big data target types (kafka, hdfs, mongodb, etc.)
- list all extract processes
- individual extract operations
- extract process management across core and big data deployments
- core get extract
- available big data target types
- core list replicats
- list data distribution paths
- distribution path management
- get details of a specific replicat process
- list big data replicats
- core create replicat
- get data stream
- get extract
- issue a command (start, stop, kill) to an extract
- oracle goldengate
- get service health
- get a specific extract process
- bigdata list replicats
- execute command
- data integration
- core create extract
- list all big data replicat processes
- list all configured data streams
- list credential store domains
- execute a ggsci-style goldengate command
- credential store management
- big data replicat processes
- list credential domains
- delete an extract process
- replicat process management
- list replicats
- list distribution paths
- real-time replication
- list data target types
- create a new data stream for downstream distribution
- delete extract
- get configuration of a specific data stream
- list available big data target types
- cdc
- create data stream
- list data streams
- core get replicat
- create a new replicat process
- get a big data replicat process
- create a new extract process
- list all replicat processes
- core list extracts
slug: data-replication
tags:
- Oracle GoldenGate
- Data Replication
- CDC
- Data Integration
tools:
- description: List all Extract processes from the core GoldenGate deployment
  hints:
    openWorld: true
    readOnly: true
  name: core-list-extracts
- description: Get details of a specific Extract process
  hints:
    openWorld: true
    readOnly: true
  name: core-get-extract
- description: Create a new Extract process
  hints:
    readOnly: false
  name: core-create-extract
- description: Issue a command (START, STOP, KILL) to an Extract
  hints:
    readOnly: false
  name: core-issue-extract-command
- description: List all Replicat processes
  hints:
    openWorld: true
    readOnly: true
  name: core-list-replicats
- description: Get details of a specific Replicat process
  hints:
    openWorld: true
    readOnly: true
  name: core-get-replicat
- description: Create a new Replicat process
  hints:
    readOnly: false
  name: core-create-replicat
- description: Issue a command to a Replicat process
  hints:
    readOnly: false
  name: core-issue-replicat-command
- description: List all big data Replicat processes
  hints:
    openWorld: true
    readOnly: true
  name: bigdata-list-replicats
- description: Get a big data Replicat process
  hints:
    openWorld: true
    readOnly: true
  name: bigdata-get-replicat
- description: List available big data target types (Kafka, HDFS, MongoDB, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-data-target-types
- description: List all configured data streams
  hints:
    openWorld: true
    readOnly: true
  name: list-data-streams
- description: Get configuration of a specific data stream
  hints:
    openWorld: true
    readOnly: true
  name: get-data-stream
- description: Create a new data stream for downstream distribution
  hints:
    readOnly: false
  name: create-data-stream
- description: List data distribution paths
  hints:
    openWorld: true
    readOnly: true
  name: list-distribution-paths
- description: List credential store domains
  hints:
    openWorld: true
    readOnly: true
  name: list-credential-domains
- description: Execute a GGSCI-style GoldenGate command
  hints:
    openWorld: true
    readOnly: false
  name: execute-command
- description: Get performance metrics for all running processes
  hints:
    openWorld: true
    readOnly: true
  name: list-process-metrics
---
