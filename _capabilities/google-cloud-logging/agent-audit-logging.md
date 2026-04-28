---
categories:
- logging
- observability
consumed_apis:
- google-cloud-logging-api
description: Workflow capability for SREs and AI Platform Engineers at Ford to maintain a centralized audit log for every agent action, with sink to BigQuery for long-term review. Combines log entry write and list, log-based metrics, log sinks, and bucket retention into a unified interface for tracing AI agent runtime behavior, model calls, and cross-platform AI cost telemetry.
layout: capability
name: Google Cloud Logging Agent Audit Trail
operations:
- description: Write structured audit log entries for agent actions and model calls
  method: POST
  name: write-log-entries
  path: /v2/entries:write
- description: List log entries with a filter for a specific agent or service
  method: POST
  name: list-log-entries
  path: /v2/entries:list
- description: List configured log-based metrics derived from agent audit logs
  method: GET
  name: list-log-based-metrics
  path: /v2/{parent}/metrics
- description: Create a log sink that exports agent audit logs to BigQuery
  method: POST
  name: create-log-sink
  path: /v2/{parent}/sinks
- description: Get retention configuration for a log bucket holding agent audit logs
  method: GET
  name: get-log-bucket-retention
  path: /v2/{parent}/buckets/{bucketId}
personas:
- SRE
- AI Platform Engineer
provider_name: Google Cloud Logging
provider_slug: google-cloud-logging
search_terms:
- write log entries
- list entries with filter
- list log-based metrics
- create log sink
- get log bucket retention
- centralized audit log
- agent audit trail
- bigquery sink
- long-term log review
- ford agent logging
- google cloud logging
- structured logging
- audit log
- log sink to bigquery
- agent action logs
- model call logs
- ai ops
- log retention
- log bucket
- log filter
- cross-platform telemetry
- agent runtime audit
- write structured audit log entries
- export agent audit logs to bigquery
slug: agent-audit-logging
tags:
- Cloud Logging
- Audit Trail
- BigQuery Sink
- Log Retention
- AI Agents
tools:
- description: Write structured audit log entries for agent actions and model calls into Google Cloud Logging
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: write-log-entries
- description: List log entries with a filter for a specific agent or service to review recent actions
  hints:
    openWorld: false
    readOnly: true
  name: list-log-entries
- description: List configured log-based metrics derived from agent audit logs for monitoring and alerting
  hints:
    openWorld: false
    readOnly: true
  name: list-log-based-metrics
- description: Create a log sink that exports agent audit logs to BigQuery for long-term review and analysis
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-log-sink
- description: Get retention configuration for a log bucket holding agent audit logs to verify compliance windows
  hints:
    openWorld: false
    readOnly: true
  name: get-log-bucket-retention
---
