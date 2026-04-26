---
consumed_apis:
- databricks
description: Manage Azure Databricks clusters, jobs, and workspace objects for data engineering workflows. Used by data engineers and platform administrators.
layout: capability
name: Azure Databricks Data Engineering
operations:
- description: List all clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new cluster
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: List all jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create a new job
  method: POST
  name: create-job
  path: /v1/jobs
- description: List workspace objects
  method: GET
  name: list-workspace-objects
  path: /v1/workspace
personas: []
provider_name: Azure Databricks
provider_slug: azure-databricks
search_terms:
- list all databricks clusters
- restart a running cluster
- list all databricks jobs
- get workspace object status
- machine learning
- get status of a workspace object
- list jobs
- list workspace objects
- analytics
- create a new databricks job
- big data
- list clusters
- delete job
- edit cluster
- permanently delete a cluster
- create a new databricks cluster
- delete cluster
- get job details
- list node types
- get job run
- manage databricks clusters
- partially update job settings
- cancel a running job
- import workspace object
- list spark versions
- edit cluster configuration
- create a directory in the workspace
- create a new cluster
- delete workspace object
- create workspace directory
- update job
- list job runs
- cancel job run
- delete a workspace object
- start cluster
- data engineering
- get the output of a completed job run
- apache spark
- get cluster
- list all clusters
- get details of a specific job run
- delete a job
- get job
- list available spark runtime versions
- trigger a one-time job run
- import a notebook or file into the workspace
- export workspace object
- manage databricks jobs
- manage workspace objects
- terminate a running cluster
- create job
- get job run output
- export a notebook or file from the workspace
- azure
- list all jobs
- get details of a specific cluster
- start a terminated cluster
- list available node types
- list workspace objects in a directory
- terminate cluster
- create cluster
- restart cluster
- create a new job
- databricks
- run job now
slug: data-engineering
tags:
- Azure
- Databricks
- Data Engineering
- Apache Spark
tools:
- description: Create a new Databricks cluster
  hints:
    readOnly: false
  name: create-cluster
- description: List all Databricks clusters
  hints:
    readOnly: true
  name: list-clusters
- description: Get details of a specific cluster
  hints:
    readOnly: true
  name: get-cluster
- description: Edit cluster configuration
  hints:
    idempotent: true
    readOnly: false
  name: edit-cluster
- description: Start a terminated cluster
  hints:
    readOnly: false
  name: start-cluster
- description: Restart a running cluster
  hints:
    readOnly: false
  name: restart-cluster
- description: Terminate a running cluster
  hints:
    destructive: true
  name: terminate-cluster
- description: Permanently delete a cluster
  hints:
    destructive: true
    idempotent: true
  name: delete-cluster
- description: List available Spark runtime versions
  hints:
    readOnly: true
  name: list-spark-versions
- description: List available node types
  hints:
    readOnly: true
  name: list-node-types
- description: Create a new Databricks job
  hints:
    readOnly: false
  name: create-job
- description: List all Databricks jobs
  hints:
    readOnly: true
  name: list-jobs
- description: Get job details
  hints:
    readOnly: true
  name: get-job
- description: Partially update job settings
  hints:
    readOnly: false
  name: update-job
- description: Delete a job
  hints:
    destructive: true
    idempotent: true
  name: delete-job
- description: Trigger a one-time job run
  hints:
    readOnly: false
  name: run-job-now
- description: List job runs
  hints:
    readOnly: true
  name: list-job-runs
- description: Get details of a specific job run
  hints:
    readOnly: true
  name: get-job-run
- description: Cancel a running job
  hints:
    destructive: true
  name: cancel-job-run
- description: Get the output of a completed job run
  hints:
    readOnly: true
  name: get-job-run-output
- description: List workspace objects in a directory
  hints:
    readOnly: true
  name: list-workspace-objects
- description: Get status of a workspace object
  hints:
    readOnly: true
  name: get-workspace-object-status
- description: Create a directory in the workspace
  hints:
    readOnly: false
  name: create-workspace-directory
- description: Delete a workspace object
  hints:
    destructive: true
    idempotent: true
  name: delete-workspace-object
- description: Import a notebook or file into the workspace
  hints:
    readOnly: false
  name: import-workspace-object
- description: Export a notebook or file from the workspace
  hints:
    readOnly: true
  name: export-workspace-object
---
