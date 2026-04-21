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
- cancel job run
- delta lake
- import a notebook or workspace object.
- list all databricks clusters.
- data analytics
- terminate a running cluster.
- import workspace object
- clean rooms
- start cluster
- cancel a running job.
- big data
- sql
- unity catalog
- ai
- lakehouse
- start a terminated cluster.
- list workspace objects.
- vector search
- get cluster details.
- identity management
- edit cluster configuration.
- analytics
- cloud computing
- create job
- job orchestration.
- etl
- delete workspace object
- list objects in a workspace directory.
- delete a job.
- get job
- create cluster
- create a new job.
- databricks
- create a new spark cluster.
- get cluster
- data governance
- run job now
- apache spark
- list clusters
- export a notebook or workspace object.
- create a new cluster.
- delete job
- data engineering
- terminate cluster
- data
- delta sharing
- trigger a job run immediately.
- mlflow
- visualize
- list all jobs.
- get job run
- security
- list all clusters.
- delete a workspace object.
- machine learning
- model serving
- cluster lifecycle management.
- get details of a specific run.
- get job details.
- list jobs
- export workspace object
- list job runs
- list workspace objects
- workspace object management.
- edit cluster
- list all databricks jobs.
- list runs for a job.
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
