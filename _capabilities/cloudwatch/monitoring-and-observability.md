---
categories:
- monitoring
consumed_apis: []
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
- aws
- delete cloudwatch dashboards
- get a cloudwatch dashboard
- enable actions for alarms
- retrieve alarm state change history
- set alarm state
- get metric data
- disable alarm actions
- delete alarms
- list tags for a cloudwatch resource
- create or update a metric alarm
- put metric data
- list cloudwatch dashboards
- delete dashboards
- disable actions for alarms
- get metric statistics
- retrieve metric data
- cloudwatch dashboards
- describe alarms
- cloudwatch
- dashboards
- metrics
- describe anomaly detectors
- logs
- monitoring
- create or update a composite alarm
- put metric stream
- put composite alarm
- create or update a dashboard
- delete an anomaly detector
- describe alarm history
- create or update a cloudwatch dashboard
- list anomaly detectors
- create or update a metric stream
- list available metrics
- describe alarms for metric
- retrieve metric data with math expressions
- observability
- publish metric data points
- get statistics for a specific metric
- list metric streams
- tag resource
- alarms
- create or update an anomaly detector
- get dashboard
- list metrics
- put anomaly detector
- retrieve metric data using math expressions
- put metric alarm
- cloudwatch alarms
- put dashboard
- cloudwatch metrics operations
- list tags for resource
- describe alarms for a specific metric
- list dashboards
- delete anomaly detector
- list available cloudwatch metrics
- temporarily set the state of an alarm
- enable alarm actions
- list alarms
- list and describe cloudwatch alarms
- create or update an alarm
- add tags to a cloudwatch resource
- publish metric data points to cloudwatch
- delete one or more alarms
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS CloudWatch Monitoring and Observability\n  description: Monitor AWS resources with metrics, alarms, dashboards, anomaly detection, and metric streams. Used by DevOps\n    engineers and SRE teams.\n  tags:\n  - AWS\n  - CloudWatch\n  - Monitoring\n  - Observability\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudwatch\n    baseUri: https://monitoring.{region}.amazonaws.com\n    description: Amazon CloudWatch monitoring API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: metrics\n      path: /\n      description: Manage CloudWatch metrics\n      operations:\n      - name: put-metric-data\n        method: POST\n\
  \        description: Publish metric data points to CloudWatch\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutMetricData)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-metric-data\n        method: POST\n        description: Retrieve metric data using metric math expressions\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (GetMetricData)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-metric-statistics\n        method: POST\n        description: Get statistics for a specific metric\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n\
  \          required: true\n          description: API action (GetMetricStatistics)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-metrics\n        method: POST\n        description: List available metrics\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListMetrics)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alarms\n      path: /\n      description: Manage CloudWatch alarms\n      operations:\n      - name: put-metric-alarm\n        method: POST\n        description: Create or update a metric alarm\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutMetricAlarm)\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-composite-alarm\n        method: POST\n        description: Create or update a composite alarm\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutCompositeAlarm)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-alarms\n        method: POST\n        description: Describe CloudWatch alarms\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeAlarms)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-alarms-for-metric\n        method: POST\n        description:\
  \ Describe alarms for a specific metric\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeAlarmsForMetric)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-alarm-history\n        method: POST\n        description: Retrieve alarm history\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeAlarmHistory)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-alarms\n        method: POST\n        description: Delete one or more alarms\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description:\
  \ API action (DeleteAlarms)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-alarm-state\n        method: POST\n        description: Set the state of an alarm\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (SetAlarmState)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-alarm-actions\n        method: POST\n        description: Enable actions for alarms\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (EnableAlarmActions)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disable-alarm-actions\n\
  \        method: POST\n        description: Disable actions for alarms\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DisableAlarmActions)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /\n      description: Manage CloudWatch dashboards\n      operations:\n      - name: put-dashboard\n        method: POST\n        description: Create or update a dashboard\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutDashboard)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dashboard\n        method: POST\n        description: Get a dashboard\n        inputParameters:\n\
  \        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (GetDashboard)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-dashboards\n        method: POST\n        description: List dashboards\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListDashboards)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dashboards\n        method: POST\n        description: Delete dashboards\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DeleteDashboards)\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: anomaly-detectors\n      path: /\n      description: Manage anomaly detectors\n      operations:\n      - name: put-anomaly-detector\n        method: POST\n        description: Create or update an anomaly detector\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutAnomalyDetector)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-anomaly-detectors\n        method: POST\n        description: Describe anomaly detectors\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeAnomalyDetectors)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n      - name: delete-anomaly-detector\n        method: POST\n        description: Delete an anomaly detector\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DeleteAnomalyDetector)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metric-streams\n      path: /\n      description: Manage metric streams\n      operations:\n      - name: put-metric-stream\n        method: POST\n        description: Create or update a metric stream\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (PutMetricStream)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-metric-streams\n        method:\
  \ POST\n        description: List metric streams\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListMetricStreams)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /\n      description: Manage resource tags\n      operations:\n      - name: tag-resource\n        method: POST\n        description: Add tags to a resource\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (TagResource)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untag-resource\n        method: POST\n        description: Remove tags from a resource\n        inputParameters:\n        - name: Action\n         \
  \ in: query\n          type: string\n          required: true\n          description: API action (UntagResource)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-tags-for-resource\n        method: POST\n        description: List tags for a resource\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListTagsForResource)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloudwatch-monitoring-api\n    description: Unified REST API for CloudWatch monitoring and observability.\n    resources:\n    - path: /v1/metrics\n      name: metrics\n      description: CloudWatch metrics operations\n      operations:\n      - method: POST\n        name: put-metric-data\n\
  \        description: Publish metric data points\n        call: cloudwatch.put-metric-data\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-metrics\n        description: List available metrics\n        call: cloudwatch.list-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/data\n      name: metric-data\n      description: Retrieve metric data\n      operations:\n      - method: POST\n        name: get-metric-data\n        description: Retrieve metric data with math expressions\n        call: cloudwatch.get-metric-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/statistics\n      name: metric-statistics\n      description: Get metric statistics\n      operations:\n      - method: POST\n        name: get-metric-statistics\n        description: Get statistics for a specific metric\n        call: cloudwatch.get-metric-statistics\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alarms\n      name: alarms\n      description: CloudWatch alarms\n      operations:\n      - method: GET\n        name: describe-alarms\n        description: List alarms\n        call: cloudwatch.describe-alarms\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: put-metric-alarm\n        description: Create or update an alarm\n        call: cloudwatch.put-metric-alarm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-alarms\n        description: Delete alarms\n        call: cloudwatch.delete-alarms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: CloudWatch dashboards\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List dashboards\n\
  \        call: cloudwatch.list-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: put-dashboard\n        description: Create or update a dashboard\n        call: cloudwatch.put-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cloudwatch-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS CloudWatch monitoring.\n    tools:\n    - name: put-metric-data\n      description: Publish metric data points to CloudWatch\n      hints:\n        readOnly: false\n      call: cloudwatch.put-metric-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metric-data\n      description: Retrieve metric data using math expressions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudwatch.get-metric-data\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: get-metric-statistics\n      description: Get statistics for a specific metric\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudwatch.get-metric-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-metrics\n      description: List available CloudWatch metrics\n      hints:\n        readOnly: true\n      call: cloudwatch.list-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-metric-alarm\n      description: Create or update a metric alarm\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudwatch.put-metric-alarm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-composite-alarm\n      description: Create or update a composite alarm\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudwatch.put-composite-alarm\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: describe-alarms\n      description: List and describe CloudWatch alarms\n      hints:\n        readOnly: true\n      call: cloudwatch.describe-alarms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-alarms-for-metric\n      description: Describe alarms for a specific metric\n      hints:\n        readOnly: true\n      call: cloudwatch.describe-alarms-for-metric\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-alarm-history\n      description: Retrieve alarm state change history\n      hints:\n        readOnly: true\n      call: cloudwatch.describe-alarm-history\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-alarms\n      description: Delete one or more alarms\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudwatch.delete-alarms\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: set-alarm-state\n      description: Temporarily set the state of an alarm\n      hints:\n        readOnly: false\n      call: cloudwatch.set-alarm-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enable-alarm-actions\n      description: Enable actions for alarms\n      hints:\n        readOnly: false\n      call: cloudwatch.enable-alarm-actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disable-alarm-actions\n      description: Disable actions for alarms\n      hints:\n        readOnly: false\n      call: cloudwatch.disable-alarm-actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-dashboard\n      description: Create or update a CloudWatch dashboard\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudwatch.put-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard\n      description:\
  \ Get a CloudWatch dashboard\n      hints:\n        readOnly: true\n      call: cloudwatch.get-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List CloudWatch dashboards\n      hints:\n        readOnly: true\n      call: cloudwatch.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-dashboards\n      description: Delete CloudWatch dashboards\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudwatch.delete-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-anomaly-detector\n      description: Create or update an anomaly detector\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudwatch.put-anomaly-detector\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-anomaly-detectors\n      description: List anomaly detectors\n\
  \      hints:\n        readOnly: true\n      call: cloudwatch.describe-anomaly-detectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-anomaly-detector\n      description: Delete an anomaly detector\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudwatch.delete-anomaly-detector\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-metric-stream\n      description: Create or update a metric stream\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudwatch.put-metric-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-metric-streams\n      description: List metric streams\n      hints:\n        readOnly: true\n      call: cloudwatch.list-metric-streams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tag-resource\n      description: Add tags to a CloudWatch resource\n      hints:\n\
  \        readOnly: false\n      call: cloudwatch.tag-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags-for-resource\n      description: List tags for a CloudWatch resource\n      hints:\n        readOnly: true\n      call: cloudwatch.list-tags-for-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
