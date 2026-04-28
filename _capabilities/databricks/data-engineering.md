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
- import a notebook or workspace object.
- data engineering
- edit cluster
- list job runs
- cloud computing
- data governance
- databricks
- unity catalog
- visualize
- get job run
- cluster lifecycle management.
- list runs for a job.
- lakehouse
- create a new job.
- list all clusters.
- get details of a specific run.
- analytics
- create cluster
- create job
- model serving
- get job
- security
- list clusters
- delete job
- export a notebook or workspace object.
- clean rooms
- mlflow
- cancel a running job.
- cancel job run
- list all databricks clusters.
- delete a workspace object.
- list workspace objects
- delta lake
- workspace object management.
- trigger a job run immediately.
- list objects in a workspace directory.
- ai
- start a terminated cluster.
- create a new spark cluster.
- terminate a running cluster.
- get job details.
- identity management
- list all jobs.
- get cluster
- start cluster
- big data
- data analytics
- list workspace objects.
- list jobs
- etl
- job orchestration.
- terminate cluster
- delete a job.
- import workspace object
- machine learning
- export workspace object
- get cluster details.
- apache spark
- sql
- edit cluster configuration.
- run job now
- list all databricks jobs.
- delete workspace object
- create a new cluster.
- data
- vector search
- delta sharing
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
