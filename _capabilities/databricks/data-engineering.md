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
- cluster lifecycle management.
- machine learning
- list all clusters.
- mlflow
- list jobs
- delete a job.
- list workspace objects
- analytics
- get job details.
- big data
- trigger a job run immediately.
- list clusters
- create a new cluster.
- delete job
- start a terminated cluster.
- edit cluster
- export a notebook or workspace object.
- data governance
- cancel a running job.
- get cluster details.
- get details of a specific run.
- get job run
- terminate a running cluster.
- list all databricks clusters.
- identity management
- workspace object management.
- import workspace object
- cloud computing
- lakehouse
- visualize
- delete workspace object
- vector search
- list job runs
- cancel job run
- list runs for a job.
- start cluster
- data engineering
- apache spark
- get cluster
- edit cluster configuration.
- job orchestration.
- get job
- export workspace object
- ai
- unity catalog
- import a notebook or workspace object.
- list all databricks jobs.
- create job
- list all jobs.
- list workspace objects.
- create a new spark cluster.
- etl
- data analytics
- list objects in a workspace directory.
- clean rooms
- model serving
- security
- sql
- create a new job.
- delta sharing
- terminate cluster
- delete a workspace object.
- create cluster
- delta lake
- databricks
- run job now
- data
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
