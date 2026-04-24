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
- get job information, definition, logs, or dag.
- hadoop
- scheduling
- system status and administration.
- submit a workflow, coordinator, or bundle job.
- apply a bulk action to multiple matching jobs.
- workflow orchestration
- scheduling and executing directed acyclic graphs of hadoop processing actions.
- manage job
- terminate an oozie job immediately.
- get job info
- list jobs with filters and pagination.
- list oozie jobs with optional filtering by user, status, job type (wf/coordinator/bundle), and pagination.
- retrieve execution logs for a specific oozie job for debugging and monitoring.
- get system status
- workflow
- submit an oozie workflow job to execute a hadoop data pipeline. pass an xml configuration with oozie.wf.application.path pointing to the hdfs workflow directory.
- get oozie system configuration properties.
- java
- suspend job
- Hadoop Pipeline Operator
- get job
- building reliable data pipelines for batch processing of large datasets on hadoop.
- apache oozie
- get apache oozie system configuration properties for troubleshooting and verification.
- get configuration
- get the current apache oozie system mode. returns normal, safemode, or nowebservice.
- bulk kill jobs
- engineers building and managing hadoop data processing pipelines using oozie workflows.
- apache
- apply a lifecycle action to a job.
- kill multiple oozie jobs matching specified filter criteria.
- start job
- get status
- get oozie system mode (normal, safemode, nowebservice).
- resume job
- list jobs
- rerun job
- open source
- submit workflow job
- pipeline management
- data engineering
- system configuration access.
- Data Engineer
- end-to-end workflow orchestration for hadoop data pipelines covering job submission, monitoring, and lifecycle management.
- resume a suspended oozie job.
- get system config
- operators monitoring and managing oozie job execution in production hadoop environments.
- kill job
- get job log
- big data
- bulk action
- get detailed information about a specific oozie job including status, actions, and timeline.
- single job management.
- start a submitted but not yet running oozie job.
- orchestration
- suspend a running oozie job, pausing execution until resumed.
- job submission and bulk management.
- submit job
- rerun a completed or failed oozie workflow job, optionally skipping specific nodes.
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
