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
- list all jobs.
- import a notebook or workspace object.
- delta lake
- vector search
- analytics
- data
- apache spark
- delete a workspace object.
- get job
- visualize
- data governance
- list jobs
- create a new job.
- clean rooms
- create a new spark cluster.
- list workspace objects.
- export a notebook or workspace object.
- trigger a job run immediately.
- cancel job run
- data analytics
- delete job
- delete workspace object
- terminate cluster
- list all clusters.
- create job
- big data
- get details of a specific run.
- machine learning
- unity catalog
- list workspace objects
- run job now
- delta sharing
- export workspace object
- data engineering
- cancel a running job.
- security
- get cluster
- edit cluster
- sql
- cluster lifecycle management.
- list runs for a job.
- identity management
- create cluster
- model serving
- get cluster details.
- get job run
- list all databricks jobs.
- start cluster
- etl
- list job runs
- list objects in a workspace directory.
- import workspace object
- databricks
- create a new cluster.
- get job details.
- list all databricks clusters.
- delete a job.
- terminate a running cluster.
- workspace object management.
- lakehouse
- job orchestration.
- start a terminated cluster.
- ai
- edit cluster configuration.
- mlflow
- cloud computing
- list clusters
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
