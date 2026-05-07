---
categories:
- data-engineering
consumed_apis: []
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
- delete workspace object
- list all jobs.
- delete a workspace object.
- analytics
- trigger a job run immediately.
- create job
- export workspace object
- delta sharing
- get cluster
- terminate a running cluster.
- data engineering
- terminate cluster
- delete a job.
- lakehouse
- ai
- import workspace object
- workspace object management.
- data analytics
- get job
- identity management
- export a notebook or workspace object.
- delta lake
- list all clusters.
- cloud computing
- visualize
- import a notebook or workspace object.
- create a new spark cluster.
- machine learning
- unity catalog
- list clusters
- create a new job.
- start cluster
- run job now
- big data
- apache spark
- sql
- mlflow
- model serving
- list workspace objects
- list job runs
- vector search
- list all databricks jobs.
- job orchestration.
- clean rooms
- list jobs
- get job details.
- get job run
- databricks
- create cluster
- etl
- list workspace objects.
- edit cluster
- list runs for a job.
- cancel a running job.
- cancel job run
- list objects in a workspace directory.
- get details of a specific run.
- data
- data governance
- edit cluster configuration.
- delete job
- security
- create a new cluster.
- cluster lifecycle management.
- get cluster details.
- list all databricks clusters.
- start a terminated cluster.
slug: data-engineering
source_filename: data-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Databricks Data Engineering\n  description: Unified workflow for Databricks data engineering including cluster management, job orchestration, and workspace\n    operations. Used by data engineers and platform administrators.\n  tags:\n  - Databricks\n  - Data Engineering\n  - ETL\n  - Apache Spark\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATABRICKS_TOKEN: DATABRICKS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: databricks-api\n    baseUri: https://adb-example.azuredatabricks.net/api\n    description: Databricks REST API for cluster, job, and workspace management.\n    authentication:\n      type: bearer\n      token: '{{DATABRICKS_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /2.0/clusters\n      description: Cluster lifecycle management.\n      operations:\n      - name: create-cluster\n        method: POST\n        description: Create a new Spark cluster.\n\
  \        body:\n          type: json\n          data:\n            cluster_name: '{{tools.cluster_name}}'\n            spark_version: '{{tools.spark_version}}'\n            node_type_id: '{{tools.node_type_id}}'\n            num_workers: '{{tools.num_workers}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-clusters\n        method: GET\n        description: List all clusters in the workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get details of a specific cluster.\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: string\n          required: true\n          description: The cluster ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: start-cluster\n        method: POST\n        description: Start a terminated cluster.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-cluster\n        method: POST\n        description: Restart an active cluster.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminate-cluster\n        method: POST\n        description: Terminate a running cluster.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: permanent-delete-cluster\n        method: POST\n        description: Permanently delete a cluster.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edit-cluster\n        method: POST\n        description: Edit an existing cluster's configuration.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n            cluster_name: '{{tools.cluster_name}}'\n            spark_version: '{{tools.spark_version}}'\n            node_type_id: '{{tools.node_type_id}}'\n            num_workers: '{{tools.num_workers}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-cluster-events\n        method: POST\n        description: List events\
  \ for a cluster.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /2.1/jobs\n      description: Job lifecycle management.\n      operations:\n      - name: create-job\n        method: POST\n        description: Create a new job.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            tasks: '{{tools.tasks}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-jobs\n        method: GET\n        description: List all jobs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get a specific job.\n       \
  \ inputParameters:\n        - name: job_id\n          in: query\n          type: string\n          required: true\n          description: The job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job\n        method: POST\n        description: Update a job.\n        body:\n          type: json\n          data:\n            job_id: '{{tools.job_id}}'\n            new_settings: '{{tools.new_settings}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-job\n        method: POST\n        description: Delete a job.\n        body:\n          type: json\n          data:\n            job_id: '{{tools.job_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-job-now\n        method: POST\n        description:\
  \ Trigger a job run.\n        body:\n          type: json\n          data:\n            job_id: '{{tools.job_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-job-runs\n        method: GET\n        description: List runs for a job.\n        inputParameters:\n        - name: job_id\n          in: query\n          type: string\n          required: false\n          description: Filter by job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-run\n        method: GET\n        description: Get details of a specific run.\n        inputParameters:\n        - name: run_id\n          in: query\n          type: string\n          required: true\n          description: The run ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: cancel-job-run\n        method: POST\n        description: Cancel a running job.\n        body:\n          type: json\n          data:\n            run_id: '{{tools.run_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace\n      path: /2.0/workspace\n      description: Workspace object management.\n      operations:\n      - name: list-workspace-objects\n        method: GET\n        description: List objects in a workspace directory.\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-workspace-object-status\n        method: GET\n        description: Get status of a workspace object.\n        inputParameters:\n\
  \        - name: path\n          in: query\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-workspace-object\n        method: GET\n        description: Export a workspace object.\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-workspace-object\n        method: POST\n        description: Import a workspace object.\n        body:\n          type: json\n          data:\n            path: '{{tools.path}}'\n            content: '{{tools.content}}'\n            format: '{{tools.format}}'\n            language: '{{tools.language}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-workspace-object\n        method: POST\n        description: Delete a workspace object.\n        body:\n          type: json\n          data:\n            path: '{{tools.path}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: databricks-data-eng-api\n    description: Unified REST API for Databricks data engineering workflows.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: Cluster lifecycle management.\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all clusters.\n        call: databricks-api.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description:\
  \ Create a new cluster.\n        call: databricks-api.create-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Job orchestration.\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all jobs.\n        call: databricks-api.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a new job.\n        call: databricks-api.create-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspace\n      name: workspace\n      description: Workspace object management.\n      operations:\n      - method: GET\n        name: list-workspace-objects\n        description: List workspace objects.\n        call: databricks-api.list-workspace-objects\n        with:\n          path: rest.path\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: databricks-data-eng-mcp\n    transport: http\n    description: MCP server for AI-assisted Databricks data engineering.\n    tools:\n    - name: list-clusters\n      description: List all Databricks clusters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: databricks-api.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Create a new Spark cluster.\n      hints:\n        readOnly: false\n      call: databricks-api.create-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get cluster details.\n      hints:\n        readOnly: true\n      call: databricks-api.get-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-cluster\n      description: Start\
  \ a terminated cluster.\n      hints:\n        readOnly: false\n      call: databricks-api.start-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-cluster\n      description: Terminate a running cluster.\n      hints:\n        destructive: true\n      call: databricks-api.terminate-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edit-cluster\n      description: Edit cluster configuration.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: databricks-api.edit-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List all Databricks jobs.\n      hints:\n        readOnly: true\n      call: databricks-api.list-jobs\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-job\n      description: Create a new job.\n      hints:\n        readOnly: false\n      call: databricks-api.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job\n      description: Get job details.\n      hints:\n        readOnly: true\n      call: databricks-api.get-job\n      with:\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-job-now\n      description: Trigger a job run immediately.\n      hints:\n        readOnly: false\n      call: databricks-api.run-job-now\n      with:\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-runs\n      description: List runs for a job.\n      hints:\n        readOnly: true\n      call: databricks-api.list-job-runs\n      with:\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: get-job-run\n      description: Get details of a specific run.\n      hints:\n        readOnly: true\n      call: databricks-api.get-job-run\n      with:\n        run_id: tools.run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-job-run\n      description: Cancel a running job.\n      hints:\n        destructive: true\n      call: databricks-api.cancel-job-run\n      with:\n        run_id: tools.run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-job\n      description: Delete a job.\n      hints:\n        destructive: true\n      call: databricks-api.delete-job\n      with:\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspace-objects\n      description: List objects in a workspace directory.\n      hints:\n        readOnly: true\n      call: databricks-api.list-workspace-objects\n      with:\n        path: tools.path\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-workspace-object\n      description: Export a notebook or workspace object.\n      hints:\n        readOnly: true\n      call: databricks-api.export-workspace-object\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-workspace-object\n      description: Import a notebook or workspace object.\n      hints:\n        readOnly: false\n      call: databricks-api.import-workspace-object\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-workspace-object\n      description: Delete a workspace object.\n      hints:\n        destructive: true\n      call: databricks-api.delete-workspace-object\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/databricks/refs/heads/main/capabilities/data-engineering.yaml
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
