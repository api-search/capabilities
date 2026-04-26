---
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
- operators monitoring and managing oozie job execution in production hadoop environments.
- get apache oozie system configuration properties for troubleshooting and verification.
- list jobs
- bulk kill jobs
- start a submitted but not yet running oozie job.
- resume a suspended oozie job.
- big data
- workflow orchestration
- end-to-end workflow orchestration for hadoop data pipelines covering job submission, monitoring, and lifecycle management.
- engineers building and managing hadoop data processing pipelines using oozie workflows.
- system configuration access.
- kill multiple oozie jobs matching specified filter criteria.
- scheduling and executing directed acyclic graphs of hadoop processing actions.
- submit a workflow, coordinator, or bundle job.
- get the current apache oozie system mode. returns normal, safemode, or nowebservice.
- terminate an oozie job immediately.
- java
- Hadoop Pipeline Operator
- orchestration
- get detailed information about a specific oozie job including status, actions, and timeline.
- apply a lifecycle action to a job.
- get job info
- Data Engineer
- apache
- submit job
- pipeline management
- apply a bulk action to multiple matching jobs.
- rerun a completed or failed oozie workflow job, optionally skipping specific nodes.
- system status and administration.
- hadoop
- data engineering
- submit workflow job
- suspend a running oozie job, pausing execution until resumed.
- get job
- get configuration
- retrieve execution logs for a specific oozie job for debugging and monitoring.
- get status
- manage job
- submit an oozie workflow job to execute a hadoop data pipeline. pass an xml configuration with oozie.wf.application.path pointing to the hdfs workflow directory.
- list oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.
- get job information, definition, logs, or dag.
- single job management.
- apache oozie
- get oozie system configuration properties.
- scheduling
- building reliable data pipelines for batch processing of large datasets on hadoop.
- list jobs with filters and pagination.
- start job
- resume job
- workflow
- get oozie system mode (normal, safemode, nowebservice).
- job submission and bulk management.
- bulk action
- rerun job
- get system config
- kill job
- get job log
- get system status
- open source
- suspend job
slug: apache-oozie-workflow-orchestration
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
