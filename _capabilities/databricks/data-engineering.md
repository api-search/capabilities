---
categories:
- data-engineering
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
- delta lake
- delete workspace object
- visualize
- create a new job.
- workspace object management.
- databricks
- apache spark
- list all jobs.
- terminate a running cluster.
- list objects in a workspace directory.
- lakehouse
- model serving
- etl
- import workspace object
- vector search
- list all clusters.
- list workspace objects
- export a notebook or workspace object.
- security
- list all databricks clusters.
- create job
- list workspace objects.
- create a new spark cluster.
- start cluster
- trigger a job run immediately.
- delete job
- mlflow
- list jobs
- create a new cluster.
- get cluster details.
- job orchestration.
- ai
- data governance
- machine learning
- create cluster
- get job details.
- get job run
- unity catalog
- edit cluster
- start a terminated cluster.
- terminate cluster
- edit cluster configuration.
- cancel a running job.
- cancel job run
- identity management
- delete a job.
- list runs for a job.
- cloud computing
- list all databricks jobs.
- get cluster
- list clusters
- get details of a specific run.
- analytics
- clean rooms
- data
- get job
- export workspace object
- sql
- data analytics
- run job now
- big data
- data engineering
- import a notebook or workspace object.
- list job runs
- cluster lifecycle management.
- delta sharing
- delete a workspace object.
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
