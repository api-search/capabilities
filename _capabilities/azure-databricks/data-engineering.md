---
categories:
- data-engineering
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
- list all jobs
- machine learning
- trigger a one-time job run
- create a directory in the workspace
- list workspace objects in a directory
- restart cluster
- list job runs
- get details of a specific cluster
- partially update job settings
- start cluster
- azure
- list node types
- list workspace objects
- delete job
- list jobs
- manage workspace objects
- get job details
- export workspace object
- get job run output
- delete a workspace object
- terminate a running cluster
- get cluster
- manage databricks jobs
- list spark versions
- create a new job
- data engineering
- delete a job
- cancel a running job
- run job now
- import workspace object
- create a new cluster
- list available node types
- databricks
- list all databricks clusters
- list all databricks jobs
- edit cluster
- create cluster
- list all clusters
- list available spark runtime versions
- import a notebook or file into the workspace
- update job
- delete workspace object
- get job run
- create job
- get workspace object status
- delete cluster
- edit cluster configuration
- analytics
- create a new databricks job
- restart a running cluster
- list clusters
- create a new databricks cluster
- start a terminated cluster
- terminate cluster
- permanently delete a cluster
- get job
- export a notebook or file from the workspace
- get status of a workspace object
- get details of a specific job run
- cancel job run
- get the output of a completed job run
- big data
- apache spark
- manage databricks clusters
- create workspace directory
slug: data-engineering
source_filename: data-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Databricks Data Engineering\"\n  description: \"Manage Azure Databricks clusters, jobs, and workspace objects for data engineering workflows. Used by data engineers and platform administrators.\"\n  tags:\n    - Azure\n    - Databricks\n    - Data Engineering\n    - Apache Spark\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DATABRICKS_TOKEN: DATABRICKS_TOKEN\n      DATABRICKS_HOST: DATABRICKS_HOST\n\ncapability:\n  consumes:\n    - import: databricks\n      location: ./shared/databricks.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: databricks-engineering-api\n      description: \"Unified REST API for Azure Databricks data engineering.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"Manage Databricks clusters\"\n          operations:\n            - method: GET\n              name: list-clusters\n\
  \              description: \"List all clusters\"\n              call: \"databricks.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create a new cluster\"\n              call: \"databricks.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Manage Databricks jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List all jobs\"\n              call: \"databricks.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: \"Create a new job\"\n              call: \"databricks.create-job\"\n  \
  \            outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspace\n          name: workspace\n          description: \"Manage workspace objects\"\n          operations:\n            - method: GET\n              name: list-workspace-objects\n              description: \"List workspace objects\"\n              call: \"databricks.list-workspace-objects\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: databricks-engineering-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Databricks data engineering.\"\n      tools:\n        - name: create-cluster\n          description: \"Create a new Databricks cluster\"\n          hints:\n            readOnly: false\n          call: \"databricks.create-cluster\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: list-clusters\n          description: \"List all Databricks clusters\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster\n          description: \"Get details of a specific cluster\"\n          hints:\n            readOnly: true\n          call: \"databricks.get-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edit-cluster\n          description: \"Edit cluster configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"databricks.edit-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-cluster\n          description:\
  \ \"Start a terminated cluster\"\n          hints:\n            readOnly: false\n          call: \"databricks.start-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-cluster\n          description: \"Restart a running cluster\"\n          hints:\n            readOnly: false\n          call: \"databricks.restart-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-cluster\n          description: \"Terminate a running cluster\"\n          hints:\n            destructive: true\n          call: \"databricks.terminate-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cluster\n          description:\
  \ \"Permanently delete a cluster\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"databricks.delete-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spark-versions\n          description: \"List available Spark runtime versions\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-spark-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-node-types\n          description: \"List available node types\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-node-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job\n          description: \"Create a new Databricks job\"\n          hints:\n            readOnly: false\n\
  \          call: \"databricks.create-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List all Databricks jobs\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job\n          description: \"Get job details\"\n          hints:\n            readOnly: true\n          call: \"databricks.get-job\"\n          with:\n            job_id: \"tools.job_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-job\n          description: \"Partially update job settings\"\n          hints:\n            readOnly: false\n          call: \"databricks.update-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-job\n          description:\
  \ \"Delete a job\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"databricks.delete-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-job-now\n          description: \"Trigger a one-time job run\"\n          hints:\n            readOnly: false\n          call: \"databricks.run-job-now\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-runs\n          description: \"List job runs\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-job-runs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-run\n          description: \"Get details of a specific job run\"\n          hints:\n            readOnly: true\n          call: \"databricks.get-job-run\"\n          with:\n            run_id: \"tools.run_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: cancel-job-run\n          description: \"Cancel a running job\"\n          hints:\n            destructive: true\n          call: \"databricks.cancel-job-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-run-output\n          description: \"Get the output of a completed job run\"\n          hints:\n            readOnly: true\n          call: \"databricks.get-job-run-output\"\n          with:\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspace-objects\n          description: \"List workspace objects in a directory\"\n          hints:\n            readOnly: true\n          call: \"databricks.list-workspace-objects\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-workspace-object-status\n          description: \"Get status of a workspace object\"\n          hints:\n            readOnly: true\n          call: \"databricks.get-workspace-object-status\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace-directory\n          description: \"Create a directory in the workspace\"\n          hints:\n            readOnly: false\n          call: \"databricks.create-workspace-directory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-workspace-object\n          description: \"Delete a workspace object\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"databricks.delete-workspace-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-workspace-object\n\
  \          description: \"Import a notebook or file into the workspace\"\n          hints:\n            readOnly: false\n          call: \"databricks.import-workspace-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-workspace-object\n          description: \"Export a notebook or file from the workspace\"\n          hints:\n            readOnly: true\n          call: \"databricks.export-workspace-object\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-databricks/refs/heads/main/capabilities/data-engineering.yaml
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
