---
api_specs:
- filename: cloudwatch-openapi.yml
  format: yaml
  label: cloudwatch
  slug: cloudwatch
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/cloudwatch/refs/heads/main/openapi/cloudwatch-openapi.yml
categories:
- monitoring
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
- list anomaly detectors
- observability
- put metric alarm
- retrieve metric data using math expressions
- delete cloudwatch dashboards
- enable actions for alarms
- put anomaly detector
- enable alarm actions
- retrieve metric data with math expressions
- list cloudwatch dashboards
- delete dashboards
- tag resource
- dashboards
- get statistics for a specific metric
- logs
- create or update a metric alarm
- describe anomaly detectors
- list and describe cloudwatch alarms
- list metrics
- disable actions for alarms
- publish metric data points
- cloudwatch metrics operations
- disable alarm actions
- temporarily set the state of an alarm
- get dashboard
- aws
- list alarms
- create or update an anomaly detector
- cloudwatch alarms
- delete one or more alarms
- describe alarms
- create or update an alarm
- get a cloudwatch dashboard
- put metric stream
- list dashboards
- alarms
- delete an anomaly detector
- get metric statistics
- monitoring
- describe alarms for a specific metric
- create or update a composite alarm
- retrieve metric data
- list available metrics
- create or update a dashboard
- describe alarms for metric
- add tags to a cloudwatch resource
- retrieve alarm state change history
- cloudwatch
- create or update a cloudwatch dashboard
- list available cloudwatch metrics
- delete alarms
- list metric streams
- list tags for resource
- metrics
- set alarm state
- delete anomaly detector
- put composite alarm
- describe alarm history
- publish metric data points to cloudwatch
- put metric data
- get metric data
- list tags for a cloudwatch resource
- cloudwatch dashboards
- create or update a metric stream
- put dashboard
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AWS CloudWatch Monitoring and Observability\"\n  description: \"Monitor AWS resources with metrics, alarms, dashboards, anomaly detection, and metric streams. Used by DevOps engineers and SRE teams.\"\n  tags:\n    - AWS\n    - CloudWatch\n    - Monitoring\n    - Observability\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudwatch\n      location: ./shared/cloudwatch.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudwatch-monitoring-api\n      description: \"Unified REST API for CloudWatch monitoring and observability.\"\n      resources:\n        - path: /v1/metrics\n          name: metrics\n          description: \"CloudWatch metrics operations\"\n          operations:\n          \
  \  - method: POST\n              name: put-metric-data\n              description: \"Publish metric data points\"\n              call: \"cloudwatch.put-metric-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-metrics\n              description: \"List available metrics\"\n              call: \"cloudwatch.list-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/data\n          name: metric-data\n          description: \"Retrieve metric data\"\n          operations:\n            - method: POST\n              name: get-metric-data\n              description: \"Retrieve metric data with math expressions\"\n              call: \"cloudwatch.get-metric-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/statistics\n\
  \          name: metric-statistics\n          description: \"Get metric statistics\"\n          operations:\n            - method: POST\n              name: get-metric-statistics\n              description: \"Get statistics for a specific metric\"\n              call: \"cloudwatch.get-metric-statistics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alarms\n          name: alarms\n          description: \"CloudWatch alarms\"\n          operations:\n            - method: GET\n              name: describe-alarms\n              description: \"List alarms\"\n              call: \"cloudwatch.describe-alarms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: put-metric-alarm\n              description: \"Create or update an alarm\"\n              call: \"cloudwatch.put-metric-alarm\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-alarms\n              description: \"Delete alarms\"\n              call: \"cloudwatch.delete-alarms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"CloudWatch dashboards\"\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: \"List dashboards\"\n              call: \"cloudwatch.list-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: put-dashboard\n              description: \"Create or update a dashboard\"\n              call: \"cloudwatch.put-dashboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \    - type: mcp\n      port: 9090\n      namespace: cloudwatch-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AWS CloudWatch monitoring.\"\n      tools:\n        - name: put-metric-data\n          description: \"Publish metric data points to CloudWatch\"\n          hints:\n            readOnly: false\n          call: \"cloudwatch.put-metric-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metric-data\n          description: \"Retrieve metric data using math expressions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudwatch.get-metric-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metric-statistics\n          description: \"Get statistics for a specific metric\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudwatch.get-metric-statistics\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-metrics\n          description: \"List available CloudWatch metrics\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.list-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-metric-alarm\n          description: \"Create or update a metric alarm\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudwatch.put-metric-alarm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-composite-alarm\n          description: \"Create or update a composite alarm\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudwatch.put-composite-alarm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ describe-alarms\n          description: \"List and describe CloudWatch alarms\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.describe-alarms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-alarms-for-metric\n          description: \"Describe alarms for a specific metric\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.describe-alarms-for-metric\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-alarm-history\n          description: \"Retrieve alarm state change history\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.describe-alarm-history\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-alarms\n          description: \"Delete one or more alarms\"\n          hints:\n            destructive: true\n    \
  \        idempotent: true\n          call: \"cloudwatch.delete-alarms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-alarm-state\n          description: \"Temporarily set the state of an alarm\"\n          hints:\n            readOnly: false\n          call: \"cloudwatch.set-alarm-state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enable-alarm-actions\n          description: \"Enable actions for alarms\"\n          hints:\n            readOnly: false\n          call: \"cloudwatch.enable-alarm-actions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disable-alarm-actions\n          description: \"Disable actions for alarms\"\n          hints:\n            readOnly: false\n          call: \"cloudwatch.disable-alarm-actions\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: put-dashboard\n          description: \"Create or update a CloudWatch dashboard\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudwatch.put-dashboard\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dashboard\n          description: \"Get a CloudWatch dashboard\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.get-dashboard\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List CloudWatch dashboards\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.list-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-dashboards\n          description: \"Delete CloudWatch dashboards\"\n          hints:\n            destructive: true\n      \
  \      idempotent: true\n          call: \"cloudwatch.delete-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-anomaly-detector\n          description: \"Create or update an anomaly detector\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudwatch.put-anomaly-detector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-anomaly-detectors\n          description: \"List anomaly detectors\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.describe-anomaly-detectors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-anomaly-detector\n          description: \"Delete an anomaly detector\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudwatch.delete-anomaly-detector\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-metric-stream\n          description: \"Create or update a metric stream\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudwatch.put-metric-stream\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-metric-streams\n          description: \"List metric streams\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.list-metric-streams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tag-resource\n          description: \"Add tags to a CloudWatch resource\"\n          hints:\n            readOnly: false\n          call: \"cloudwatch.tag-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags-for-resource\n          description:\
  \ \"List tags for a CloudWatch resource\"\n          hints:\n            readOnly: true\n          call: \"cloudwatch.list-tags-for-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudwatch/refs/heads/main/capabilities/monitoring-and-observability.yaml
tags:
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
