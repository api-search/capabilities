---
consumed_apis:
- cloudwatch
description: Monitor AWS resources with metrics, alarms, dashboards, anomaly detection, and metric streams. Used by DevOps engineers and SRE teams.
layout: capability
name: AWS CloudWatch Monitoring and Observability
operations:
- description: Publish metric data points
  method: POST
  name: put-metric-data
  path: /v1/metrics
- description: List available metrics
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Retrieve metric data with math expressions
  method: POST
  name: get-metric-data
  path: /v1/metrics/data
- description: Get statistics for a specific metric
  method: POST
  name: get-metric-statistics
  path: /v1/metrics/statistics
- description: List alarms
  method: GET
  name: describe-alarms
  path: /v1/alarms
- description: Create or update an alarm
  method: POST
  name: put-metric-alarm
  path: /v1/alarms
- description: Delete alarms
  method: DELETE
  name: delete-alarms
  path: /v1/alarms
- description: List dashboards
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create or update a dashboard
  method: POST
  name: put-dashboard
  path: /v1/dashboards
personas: []
provider_name: AWS CloudWatch
provider_slug: cloudwatch
search_terms:
- get statistics for a specific metric
- create or update an anomaly detector
- retrieve metric data using math expressions
- list available cloudwatch metrics
- describe alarms
- retrieve alarm state change history
- alarms
- retrieve metric data with math expressions
- put dashboard
- temporarily set the state of an alarm
- tag resource
- describe anomaly detectors
- observability
- describe alarm history
- list metrics
- enable alarm actions
- put metric data
- list and describe cloudwatch alarms
- delete one or more alarms
- list anomaly detectors
- cloudwatch alarms
- delete anomaly detector
- set alarm state
- create or update an alarm
- delete dashboards
- put anomaly detector
- create or update a metric stream
- add tags to a cloudwatch resource
- monitoring
- create or update a metric alarm
- create or update a dashboard
- list tags for a cloudwatch resource
- list cloudwatch dashboards
- cloudwatch metrics operations
- put metric alarm
- publish metric data points
- get metric statistics
- delete cloudwatch dashboards
- get metric data
- retrieve metric data
- publish metric data points to cloudwatch
- describe alarms for metric
- enable actions for alarms
- delete alarms
- list dashboards
- logs
- metrics
- cloudwatch
- aws
- list metric streams
- describe alarms for a specific metric
- cloudwatch dashboards
- disable alarm actions
- disable actions for alarms
- get dashboard
- put metric stream
- list alarms
- dashboards
- list available metrics
- delete an anomaly detector
- list tags for resource
- get a cloudwatch dashboard
- put composite alarm
- create or update a cloudwatch dashboard
- create or update a composite alarm
slug: monitoring-and-observability
tags:
- AWS
- CloudWatch
- Monitoring
- Observability
tools:
- description: Publish metric data points to CloudWatch
  hints:
    readOnly: false
  name: put-metric-data
- description: Retrieve metric data using math expressions
  hints:
    idempotent: true
    readOnly: true
  name: get-metric-data
- description: Get statistics for a specific metric
  hints:
    idempotent: true
    readOnly: true
  name: get-metric-statistics
- description: List available CloudWatch metrics
  hints:
    readOnly: true
  name: list-metrics
- description: Create or update a metric alarm
  hints:
    idempotent: true
    readOnly: false
  name: put-metric-alarm
- description: Create or update a composite alarm
  hints:
    idempotent: true
    readOnly: false
  name: put-composite-alarm
- description: List and describe CloudWatch alarms
  hints:
    readOnly: true
  name: describe-alarms
- description: Describe alarms for a specific metric
  hints:
    readOnly: true
  name: describe-alarms-for-metric
- description: Retrieve alarm state change history
  hints:
    readOnly: true
  name: describe-alarm-history
- description: Delete one or more alarms
  hints:
    destructive: true
    idempotent: true
  name: delete-alarms
- description: Temporarily set the state of an alarm
  hints:
    readOnly: false
  name: set-alarm-state
- description: Enable actions for alarms
  hints:
    readOnly: false
  name: enable-alarm-actions
- description: Disable actions for alarms
  hints:
    readOnly: false
  name: disable-alarm-actions
- description: Create or update a CloudWatch dashboard
  hints:
    idempotent: true
    readOnly: false
  name: put-dashboard
- description: Get a CloudWatch dashboard
  hints:
    readOnly: true
  name: get-dashboard
- description: List CloudWatch dashboards
  hints:
    readOnly: true
  name: list-dashboards
- description: Delete CloudWatch dashboards
  hints:
    destructive: true
    idempotent: true
  name: delete-dashboards
- description: Create or update an anomaly detector
  hints:
    idempotent: true
    readOnly: false
  name: put-anomaly-detector
- description: List anomaly detectors
  hints:
    readOnly: true
  name: describe-anomaly-detectors
- description: Delete an anomaly detector
  hints:
    destructive: true
    idempotent: true
  name: delete-anomaly-detector
- description: Create or update a metric stream
  hints:
    idempotent: true
    readOnly: false
  name: put-metric-stream
- description: List metric streams
  hints:
    readOnly: true
  name: list-metric-streams
- description: Add tags to a CloudWatch resource
  hints:
    readOnly: false
  name: tag-resource
- description: List tags for a CloudWatch resource
  hints:
    readOnly: true
  name: list-tags-for-resource
---
