---
categories:
- ci-cd
consumed_apis:
- goldengate-cloud
- goldengate-stream-analytics
description: Unified workflow for managing Oracle GoldenGate cloud deployments in OCI. Combines the OCI Cloud Service API with Stream Analytics for cloud platform administrators managing deployment lifecycle, connections, pipelines, backups, and stream analytics in Oracle Cloud.
layout: capability
name: Oracle GoldenGate Cloud Management
operations:
- description: List OCI GoldenGate deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create a new OCI deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: Get deployment details
  method: GET
  name: get-deployment
  path: /v1/deployments/{deploymentId}
- description: List database and service connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List data replication pipelines
  method: GET
  name: list-pipelines
  path: /v1/pipelines
- description: List deployment backups
  method: GET
  name: list-backups
  path: /v1/backups
- description: List GGSA stream analytics pipelines
  method: GET
  name: list-stream-pipelines
  path: /v1/stream-pipelines
- description: List asynchronous work requests
  method: GET
  name: list-work-requests
  path: /v1/work-requests
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- list backups
- list work requests
- get details of a specific oci deployment
- cdc
- start deployment
- create backup
- start a stopped oci deployment
- unpublish stream pipeline
- stop a running oci deployment
- create a new oci deployment
- create pipeline
- create a new oci goldengate deployment
- restore deployment
- list oci goldengate deployments
- list ggsa stream analytics pipelines
- get work request
- data integration
- data synchronization
- list oci goldengate deployments in a compartment
- get deployment details
- stop deployment
- enterprise
- publish a stream analytics pipeline to the spark runtime
- connection management
- create connection
- oci
- create a deployment backup
- oci goldengate deployment lifecycle management
- upgrade deployment
- list deployments
- async operation tracking
- list connections
- oracle goldengate
- list deployment backups
- stream analytics pipeline management
- start pipeline
- restore a deployment from a backup
- data replication pipelines
- unpublish a stream analytics pipeline
- list stream pipelines
- get deployment
- individual deployment operations
- list data replication pipelines
- list pipelines
- real-time replication
- cloud management
- publish stream pipeline
- create a new data replication pipeline
- create deployment
- upgrade an oci deployment to a newer version
- create a new connection for a source or target system
- list database and service connections
- database
- platform administration
- start a stopped pipeline
- list asynchronous work requests
- check status of an asynchronous operation
- deployment backup management
slug: cloud-management
tags:
- Oracle GoldenGate
- OCI
- Cloud Management
- Platform Administration
tools:
- description: List OCI GoldenGate deployments in a compartment
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Get details of a specific OCI deployment
  hints:
    openWorld: true
    readOnly: true
  name: get-deployment
- description: Create a new OCI GoldenGate deployment
  hints:
    readOnly: false
  name: create-deployment
- description: Start a stopped OCI deployment
  hints:
    readOnly: false
  name: start-deployment
- description: Stop a running OCI deployment
  hints:
    readOnly: false
  name: stop-deployment
- description: Upgrade an OCI deployment to a newer version
  hints:
    readOnly: false
  name: upgrade-deployment
- description: List database and service connections
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Create a new connection for a source or target system
  hints:
    readOnly: false
  name: create-connection
- description: List data replication pipelines
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: Create a new data replication pipeline
  hints:
    readOnly: false
  name: create-pipeline
- description: Start a stopped pipeline
  hints:
    readOnly: false
  name: start-pipeline
- description: List deployment backups
  hints:
    openWorld: true
    readOnly: true
  name: list-backups
- description: Create a deployment backup
  hints:
    readOnly: false
  name: create-backup
- description: Restore a deployment from a backup
  hints:
    readOnly: false
  name: restore-deployment
- description: List GGSA stream analytics pipelines
  hints:
    openWorld: true
    readOnly: true
  name: list-stream-pipelines
- description: Publish a stream analytics pipeline to the Spark runtime
  hints:
    readOnly: false
  name: publish-stream-pipeline
- description: Unpublish a stream analytics pipeline
  hints:
    readOnly: false
  name: unpublish-stream-pipeline
- description: Check status of an asynchronous operation
  hints:
    openWorld: true
    readOnly: true
  name: get-work-request
---
