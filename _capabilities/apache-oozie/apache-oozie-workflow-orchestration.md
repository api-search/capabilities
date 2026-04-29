---
categories:
- data-engineering
consumed_apis:
- oozie
description: Workflow capability for orchestrating Hadoop data processing pipelines using Apache Oozie. Covers workflow, coordinator, and bundle job lifecycle management for data engineers and Hadoop pipeline operators running scheduled and event-driven data processing.
layout: capability
name: Apache Oozie Workflow Orchestration
operations:
- description: Get Oozie system mode (NORMAL, SAFEMODE, NOWEBSERVICE).
  method: GET
  name: get-status
  path: /v1/admin/status
- description: Get Oozie system configuration properties.
  method: GET
  name: get-configuration
  path: /v1/admin/configuration
- description: Submit a workflow, coordinator, or bundle job.
  method: POST
  name: submit-job
  path: /v1/jobs
- description: List jobs with filters and pagination.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Apply a bulk action to multiple matching jobs.
  method: PUT
  name: bulk-action
  path: /v1/jobs
- description: Get job information, definition, logs, or DAG.
  method: GET
  name: get-job
  path: /v1/jobs/{jobId}
- description: Apply a lifecycle action to a job.
  method: PUT
  name: manage-job
  path: /v1/jobs/{jobId}
personas: []
provider_name: Apache Oozie
provider_slug: apache-oozie
search_terms:
- kill job
- resume job
- operators monitoring and managing oozie job execution in production hadoop environments.
- orchestration
- system configuration access.
- big data
- system status and administration.
- get detailed information about a specific oozie job including status, actions, and timeline.
- terminate an oozie job immediately.
- submit an oozie workflow job to execute a hadoop data pipeline. pass an xml configuration with oozie.wf.application.path pointing to the hdfs workflow directory.
- start job
- get apache oozie system configuration properties for troubleshooting and verification.
- get job log
- engineers building and managing hadoop data processing pipelines using oozie workflows.
- get the current apache oozie system mode. returns normal, safemode, or nowebservice.
- scheduling
- rerun a completed or failed oozie workflow job, optionally skipping specific nodes.
- list jobs
- get job information, definition, logs, or dag.
- workflow
- suspend a running oozie job, pausing execution until resumed.
- hadoop
- submit job
- building reliable data pipelines for batch processing of large datasets on hadoop.
- Data Engineer
- get oozie system configuration properties.
- submit a workflow, coordinator, or bundle job.
- rerun job
- workflow orchestration
- apache oozie
- start a submitted but not yet running oozie job.
- kill multiple oozie jobs matching specified filter criteria.
- Hadoop Pipeline Operator
- manage job
- job submission and bulk management.
- apply a lifecycle action to a job.
- scheduling and executing directed acyclic graphs of hadoop processing actions.
- apache
- get job info
- suspend job
- get system config
- single job management.
- get job
- bulk kill jobs
- get configuration
- end-to-end workflow orchestration for hadoop data pipelines covering job submission, monitoring, and lifecycle management.
- java
- bulk action
- pipeline management
- get status
- get oozie system mode (normal, safemode, nowebservice).
- list jobs with filters and pagination.
- get system status
- resume a suspended oozie job.
- data engineering
- submit workflow job
- apply a bulk action to multiple matching jobs.
- retrieve execution logs for a specific oozie job for debugging and monitoring.
- list oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.
- open source
slug: apache-oozie-workflow-orchestration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apache Oozie Workflow Orchestration\n  description: Workflow capability for orchestrating Hadoop data processing pipelines using Apache Oozie. Covers workflow, coordinator, and bundle job lifecycle management for data engineers and Hadoop pipeline operators running scheduled and event-driven data processing.\n  tags:\n    - Apache Oozie\n    - Hadoop\n    - Workflow Orchestration\n    - Data Engineering\n    - Pipeline Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OOZIE_URL: OOZIE_URL\n\ncapability:\n  consumes:\n    - import: oozie\n      location: ./shared/apache-oozie.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: oozie-orchestration-api\n      description: Unified REST API for Apache Oozie Hadoop workflow orchestration.\n      resources:\n        - path: /v1/admin/status\n          name: admin-status\n          description: System status\
  \ and administration.\n          operations:\n            - method: GET\n              name: get-status\n              description: Get Oozie system mode (NORMAL, SAFEMODE, NOWEBSERVICE).\n              call: \"oozie.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/admin/configuration\n          name: admin-config\n          description: System configuration access.\n          operations:\n            - method: GET\n              name: get-configuration\n              description: Get Oozie system configuration properties.\n              call: \"oozie.get-configuration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs\n          name: jobs\n          description: Job submission and bulk management.\n          operations:\n            - method: POST\n              name: submit-job\n              description: Submit a workflow,\
  \ coordinator, or bundle job.\n              call: \"oozie.submit-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-jobs\n              description: List jobs with filters and pagination.\n              call: \"oozie.get-jobs\"\n              with:\n                filter: \"rest.filter\"\n                offset: \"rest.offset\"\n                len: \"rest.len\"\n                jobtype: \"rest.jobtype\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: bulk-action\n              description: Apply a bulk action to multiple matching jobs.\n              call: \"oozie.bulk-job-action\"\n              with:\n                action: \"rest.action\"\n                filter: \"rest.filter\"\n                jobtype: \"rest.jobtype\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobId}\n          name: job-detail\n          description: Single job management.\n          operations:\n            - method: GET\n              name: get-job\n              description: Get job information, definition, logs, or DAG.\n              call: \"oozie.get-job-info\"\n              with:\n                job-id: \"rest.jobId\"\n                show: \"rest.show\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: manage-job\n              description: Apply a lifecycle action to a job.\n              call: \"oozie.manage-job\"\n              with:\n                job-id: \"rest.jobId\"\n                action: \"rest.action\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: oozie-orchestration-mcp\n  \
  \    transport: http\n      description: MCP server for AI-assisted Apache Oozie Hadoop workflow orchestration.\n      tools:\n        - name: get-system-status\n          description: Get the current Apache Oozie system mode. Returns NORMAL, SAFEMODE, or NOWEBSERVICE.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"oozie.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-system-config\n          description: Get Apache Oozie system configuration properties for troubleshooting and verification.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"oozie.get-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-workflow-job\n          description: Submit an Oozie workflow job to execute a Hadoop data pipeline. Pass an XML configuration with oozie.wf.application.path\
  \ pointing to the HDFS workflow directory.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"oozie.submit-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: List Oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"oozie.get-jobs\"\n          with:\n            filter: \"tools.filter\"\n            jobtype: \"tools.jobtype\"\n            offset: \"tools.offset\"\n            len: \"tools.len\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job-info\n          description: Get detailed information about a specific Oozie job including status, actions, and timeline.\n          hints:\n            readOnly: true\n            openWorld: false\n  \
  \        call: \"oozie.get-job-info\"\n          with:\n            job-id: \"tools.jobId\"\n            show: \"tools.show\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job-log\n          description: Retrieve execution logs for a specific Oozie job for debugging and monitoring.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"oozie.get-job-info\"\n          with:\n            job-id: \"tools.jobId\"\n            show: \"log\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-job\n          description: Start a submitted but not yet running Oozie job.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"oozie.manage-job\"\n          with:\n            job-id: \"tools.jobId\"\n            action: \"start\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n\n        - name: suspend-job\n          description: Suspend a running Oozie job, pausing execution until resumed.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"oozie.manage-job\"\n          with:\n            job-id: \"tools.jobId\"\n            action: \"suspend\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resume-job\n          description: Resume a suspended Oozie job.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"oozie.manage-job\"\n          with:\n            job-id: \"tools.jobId\"\n            action: \"resume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: kill-job\n          description: Terminate an Oozie job immediately.\n      \
  \    hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"oozie.manage-job\"\n          with:\n            job-id: \"tools.jobId\"\n            action: \"kill\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rerun-job\n          description: Rerun a completed or failed Oozie workflow job, optionally skipping specific nodes.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"oozie.manage-job\"\n          with:\n            job-id: \"tools.jobId\"\n            action: \"rerun\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: bulk-kill-jobs\n          description: Kill multiple Oozie jobs matching specified filter criteria.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n\
  \          call: \"oozie.bulk-job-action\"\n          with:\n            action: \"kill\"\n            filter: \"tools.filter\"\n            jobtype: \"tools.jobtype\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-oozie/refs/heads/main/capabilities/apache-oozie-workflow-orchestration.yaml
tags:
- Apache Oozie
- Hadoop
- Workflow Orchestration
- Data Engineering
- Pipeline Management
tools:
- description: Get the current Apache Oozie system mode. Returns NORMAL, SAFEMODE, or NOWEBSERVICE.
  hints:
    openWorld: false
    readOnly: true
  name: get-system-status
- description: Get Apache Oozie system configuration properties for troubleshooting and verification.
  hints:
    openWorld: false
    readOnly: true
  name: get-system-config
- description: Submit an Oozie workflow job to execute a Hadoop data pipeline. Pass an XML configuration with oozie.wf.application.path pointing to the HDFS workflow directory.
  hints:
    openWorld: false
    readOnly: false
  name: submit-workflow-job
- description: List Oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.
  hints:
    openWorld: false
    readOnly: true
  name: list-jobs
- description: Get detailed information about a specific Oozie job including status, actions, and timeline.
  hints:
    openWorld: false
    readOnly: true
  name: get-job-info
- description: Retrieve execution logs for a specific Oozie job for debugging and monitoring.
  hints:
    openWorld: false
    readOnly: true
  name: get-job-log
- description: Start a submitted but not yet running Oozie job.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-job
- description: Suspend a running Oozie job, pausing execution until resumed.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suspend-job
- description: Resume a suspended Oozie job.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resume-job
- description: Terminate an Oozie job immediately.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: kill-job
- description: Rerun a completed or failed Oozie workflow job, optionally skipping specific nodes.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rerun-job
- description: Kill multiple Oozie jobs matching specified filter criteria.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: bulk-kill-jobs
---
