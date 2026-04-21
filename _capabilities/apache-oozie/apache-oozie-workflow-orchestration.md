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
- kill multiple oozie jobs matching specified filter criteria.
- open source
- submit job
- kill job
- java
- get the current apache oozie system mode. returns normal, safemode, or nowebservice.
- scheduling and executing directed acyclic graphs of hadoop processing actions.
- system status and administration.
- building reliable data pipelines for batch processing of large datasets on hadoop.
- start a submitted but not yet running oozie job.
- submit workflow job
- operators monitoring and managing oozie job execution in production hadoop environments.
- workflow
- list jobs
- bulk kill jobs
- get status
- get system config
- list oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.
- get job log
- workflow orchestration
- big data
- apache
- list jobs with filters and pagination.
- rerun a completed or failed oozie workflow job, optionally skipping specific nodes.
- get detailed information about a specific oozie job including status, actions, and timeline.
- suspend a running oozie job, pausing execution until resumed.
- suspend job
- apply a bulk action to multiple matching jobs.
- get apache oozie system configuration properties for troubleshooting and verification.
- retrieve execution logs for a specific oozie job for debugging and monitoring.
- Data Engineer
- submit a workflow, coordinator, or bundle job.
- get oozie system configuration properties.
- get oozie system mode (normal, safemode, nowebservice).
- get job
- get system status
- start job
- get configuration
- get job information, definition, logs, or dag.
- manage job
- rerun job
- submit an oozie workflow job to execute a hadoop data pipeline. pass an xml configuration with oozie.wf.application.path pointing to the hdfs workflow directory.
- bulk action
- terminate an oozie job immediately.
- end-to-end workflow orchestration for hadoop data pipelines covering job submission, monitoring, and lifecycle management.
- job submission and bulk management.
- hadoop
- pipeline management
- resume a suspended oozie job.
- Hadoop Pipeline Operator
- apache oozie
- resume job
- scheduling
- get job info
- system configuration access.
- data engineering
- single job management.
- engineers building and managing hadoop data processing pipelines using oozie workflows.
- orchestration
- apply a lifecycle action to a job.
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
