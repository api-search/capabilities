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
- apache spark
- ai
- delete a workspace object.
- vector search
- model serving
- export a notebook or workspace object.
- sql
- list workspace objects
- terminate cluster
- delete job
- list workspace objects.
- list job runs
- get cluster details.
- export workspace object
- data governance
- create a new job.
- cancel job run
- create cluster
- list clusters
- list all databricks clusters.
- analytics
- list all clusters.
- job orchestration.
- edit cluster configuration.
- get job
- lakehouse
- delete a job.
- edit cluster
- list runs for a job.
- mlflow
- clean rooms
- start cluster
- get cluster
- import workspace object
- workspace object management.
- create job
- etl
- run job now
- unity catalog
- cancel a running job.
- delete workspace object
- list jobs
- identity management
- machine learning
- data analytics
- data engineering
- list objects in a workspace directory.
- import a notebook or workspace object.
- list all databricks jobs.
- databricks
- list all jobs.
- get details of a specific run.
- create a new cluster.
- delta sharing
- get job run
- big data
- create a new spark cluster.
- start a terminated cluster.
- cloud computing
- security
- trigger a job run immediately.
- terminate a running cluster.
- get job details.
- delta lake
- data
- cluster lifecycle management.
- visualize
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
