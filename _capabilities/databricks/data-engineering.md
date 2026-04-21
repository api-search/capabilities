---
consumed_apis:
- databricks-api
description: Unified workflow for Databricks data engineering including cluster management, job orchestration, and workspace operations. Used by data engineers and platform administrators.
layout: capability
name: Databricks Data Engineering
operations:
- description: List all clusters.
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new cluster.
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: List all jobs.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create a new job.
  method: POST
  name: create-job
  path: /v1/jobs
- description: List workspace objects.
  method: GET
  name: list-workspace-objects
  path: /v1/workspace
personas: []
provider_name: Databricks
provider_slug: databricks
search_terms:
- list objects in a workspace directory.
- data
- get details of a specific run.
- list clusters
- list all clusters.
- list runs for a job.
- delete job
- sql
- analytics
- ai
- data governance
- list all databricks clusters.
- model serving
- vector search
- cancel a running job.
- visualize
- edit cluster configuration.
- create a new cluster.
- create job
- create a new spark cluster.
- start a terminated cluster.
- terminate cluster
- get job run
- machine learning
- run job now
- cluster lifecycle management.
- delete workspace object
- get job details.
- export a notebook or workspace object.
- lakehouse
- job orchestration.
- mlflow
- list all jobs.
- big data
- terminate a running cluster.
- list jobs
- get cluster details.
- get job
- data analytics
- security
- export workspace object
- trigger a job run immediately.
- delta lake
- identity management
- unity catalog
- delta sharing
- etl
- list job runs
- list workspace objects
- create a new job.
- import a notebook or workspace object.
- delete a job.
- apache spark
- create cluster
- databricks
- edit cluster
- clean rooms
- data engineering
- get cluster
- start cluster
- delete a workspace object.
- cancel job run
- import workspace object
- workspace object management.
- cloud computing
- list all databricks jobs.
- list workspace objects.
slug: data-engineering
tags:
- Databricks
- Data Engineering
- ETL
- Apache Spark
tools:
- description: List all Databricks clusters.
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Create a new Spark cluster.
  hints:
    readOnly: false
  name: create-cluster
- description: Get cluster details.
  hints:
    readOnly: true
  name: get-cluster
- description: Start a terminated cluster.
  hints:
    readOnly: false
  name: start-cluster
- description: Terminate a running cluster.
  hints:
    destructive: true
  name: terminate-cluster
- description: Edit cluster configuration.
  hints:
    idempotent: true
    readOnly: false
  name: edit-cluster
- description: List all Databricks jobs.
  hints:
    readOnly: true
  name: list-jobs
- description: Create a new job.
  hints:
    readOnly: false
  name: create-job
- description: Get job details.
  hints:
    readOnly: true
  name: get-job
- description: Trigger a job run immediately.
  hints:
    readOnly: false
  name: run-job-now
- description: List runs for a job.
  hints:
    readOnly: true
  name: list-job-runs
- description: Get details of a specific run.
  hints:
    readOnly: true
  name: get-job-run
- description: Cancel a running job.
  hints:
    destructive: true
  name: cancel-job-run
- description: Delete a job.
  hints:
    destructive: true
  name: delete-job
- description: List objects in a workspace directory.
  hints:
    readOnly: true
  name: list-workspace-objects
- description: Export a notebook or workspace object.
  hints:
    readOnly: true
  name: export-workspace-object
- description: Import a notebook or workspace object.
  hints:
    readOnly: false
  name: import-workspace-object
- description: Delete a workspace object.
  hints:
    destructive: true
  name: delete-workspace-object
---
