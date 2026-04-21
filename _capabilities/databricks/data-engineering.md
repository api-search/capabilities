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
- get job details.
- visualize
- list workspace objects
- import a notebook or workspace object.
- delete workspace object
- machine learning
- security
- cloud computing
- get job run
- list runs for a job.
- workspace object management.
- delta lake
- start cluster
- list jobs
- job orchestration.
- mlflow
- cluster lifecycle management.
- list clusters
- data governance
- etl
- list all databricks jobs.
- big data
- create a new job.
- trigger a job run immediately.
- data analytics
- list job runs
- delete a job.
- cancel a running job.
- create cluster
- get job
- create a new cluster.
- get details of a specific run.
- list objects in a workspace directory.
- unity catalog
- identity management
- terminate a running cluster.
- get cluster details.
- run job now
- edit cluster
- get cluster
- delete a workspace object.
- terminate cluster
- ai
- data
- analytics
- delete job
- cancel job run
- import workspace object
- lakehouse
- list all databricks clusters.
- create a new spark cluster.
- edit cluster configuration.
- export a notebook or workspace object.
- list workspace objects.
- clean rooms
- sql
- vector search
- model serving
- databricks
- apache spark
- list all jobs.
- export workspace object
- list all clusters.
- data engineering
- delta sharing
- create job
- start a terminated cluster.
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
