---
categories:
- monitoring
consumed_apis:
- lookout-for-metrics
description: Workflow capability for data science and operations teams to manage anomaly detectors, monitor metric anomalies, configure alerts, and provide detection feedback using Amazon Lookout for Metrics.
layout: capability
name: Amazon Lookout for Metrics - Anomaly Detection Operations
operations:
- description: Create a new anomaly detector
  method: POST
  name: create-detector
  path: /v1/detectors
- description: List all anomaly detectors
  method: GET
  name: list-detectors
  path: /v1/detectors
- description: Get detector details
  method: GET
  name: get-detector
  path: /v1/detectors/{id}
- description: Update detector configuration
  method: PUT
  name: update-detector
  path: /v1/detectors/{id}
- description: Delete a detector
  method: DELETE
  name: delete-detector
  path: /v1/detectors/{id}
- description: List anomaly group summaries
  method: GET
  name: list-anomalies
  path: /v1/anomalies
- description: Get anomaly group details
  method: GET
  name: get-anomaly
  path: /v1/anomalies/{id}
- description: Create an alert
  method: POST
  name: create-alert
  path: /v1/alerts
- description: List all alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Submit anomaly feedback
  method: POST
  name: submit-feedback
  path: /v1/feedback
- description: Get anomaly feedback
  method: GET
  name: get-feedback
  path: /v1/feedback
personas: []
provider_name: Amazon Lookout for Metrics
provider_slug: amazon-lookout-for-metrics
search_terms:
- business intelligence
- operations
- list all alerts
- activate an anomaly detector to begin monitoring metrics
- manages anomaly detector configuration, metric sets, and feedback to improve ml model accuracy
- monitoring and assessment of metric data quality
- delete detector
- submit feedback on anomaly detections to improve ml model accuracy
- create detector
- list all configured anomaly alerts
- get feedback
- list anomalies
- list detectors
- update detector
- get anomaly feedback
- put feedback
- configuration and management of anomaly alert notifications
- anomaly alerts
- submit feedback
- create anomaly detector
- update detector configuration
- create an alert
- create alert
- get detector
- amazon
- create a new anomaly detector for a set of business metrics
- list alerts
- get anomaly group details
- list anomaly group related metrics
- workflow for managing anomaly detectors, monitoring anomalies, configuring alerts, and providing feedback
- create a new anomaly detector
- monitoring
- get configuration and status details of an anomaly detector
- list anomaly group summaries
- manage anomaly detectors
- Data Scientist
- list all configured anomaly detectors
- stop an anomaly detector from monitoring metrics
- get full details of a specific anomaly group including contributing metrics
- submit anomaly feedback
- list all metrics that contributed to an anomaly group
- list all anomaly detectors
- anomaly detection
- list summaries of detected anomaly groups for investigation
- get anomaly
- describe anomaly detector
- create an alert to receive notifications when anomalies are detected
- get anomaly group
- detection feedback
- ml-powered detection of anomalies in business and operational metrics
- activate anomaly detector
- single anomaly group
- Operations Engineer
- single anomaly detector
- monitors anomaly alerts, investigates anomaly groups, and manages detector lifecycle
- get detector details
- retrieve previously submitted anomaly detection feedback
- aws
- deactivate anomaly detector
- delete a detector
- metrics
- list anomaly detectors
- anomaly group results
- machine learning
slug: anomaly-detection-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Lookout for Metrics - Anomaly Detection Operations\"\n  description: \"Workflow capability for data science and operations teams to manage anomaly detectors, monitor metric anomalies, configure alerts, and provide detection feedback using Amazon Lookout for Metrics.\"\n  tags:\n    - Amazon\n    - Anomaly Detection\n    - Machine Learning\n    - Metrics\n    - Monitoring\n    - Operations\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: lookout-for-metrics\n      location: ./shared/lookout-for-metrics.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: anomaly-detection-api\n      description: \"Unified REST API for Amazon Lookout for Metrics anomaly detection operations.\"\n      resources:\n\
  \        - path: /v1/detectors\n          name: detectors\n          description: \"Manage anomaly detectors\"\n          operations:\n            - method: POST\n              name: create-detector\n              description: \"Create a new anomaly detector\"\n              call: \"lookout-for-metrics.create-anomaly-detector\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-detectors\n              description: \"List all anomaly detectors\"\n              call: \"lookout-for-metrics.list-anomaly-detectors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/detectors/{id}\n          name: detector\n          description: \"Single anomaly detector\"\n          operations:\n            - method: GET\n              name: get-detector\n              description: \"Get detector details\"\n              call: \"lookout-for-metrics.describe-anomaly-detector\"\
  \n              with:\n                AnomalyDetectorArn: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-detector\n              description: \"Update detector configuration\"\n              call: \"lookout-for-metrics.update-anomaly-detector\"\n              with:\n                AnomalyDetectorArn: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-detector\n              description: \"Delete a detector\"\n              call: \"lookout-for-metrics.delete-anomaly-detector\"\n              with:\n                AnomalyDetectorArn: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/anomalies\n          name: anomalies\n          description: \"Anomaly group results\"\n\
  \          operations:\n            - method: GET\n              name: list-anomalies\n              description: \"List anomaly group summaries\"\n              call: \"lookout-for-metrics.list-anomaly-group-summaries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/anomalies/{id}\n          name: anomaly\n          description: \"Single anomaly group\"\n          operations:\n            - method: GET\n              name: get-anomaly\n              description: \"Get anomaly group details\"\n              call: \"lookout-for-metrics.get-anomaly-group\"\n              with:\n                AnomalyGroupId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Anomaly alerts\"\n          operations:\n            - method: POST\n              name: create-alert\n              description:\
  \ \"Create an alert\"\n              call: \"lookout-for-metrics.create-alert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-alerts\n              description: \"List all alerts\"\n              call: \"lookout-for-metrics.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/feedback\n          name: feedback\n          description: \"Detection feedback\"\n          operations:\n            - method: POST\n              name: submit-feedback\n              description: \"Submit anomaly feedback\"\n              call: \"lookout-for-metrics.put-feedback\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-feedback\n              description: \"Get anomaly feedback\"\n              call: \"lookout-for-metrics.get-feedback\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: anomaly-detection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted anomaly detection and metrics monitoring with Amazon Lookout for Metrics.\"\n      tools:\n        - name: create-anomaly-detector\n          description: \"Create a new anomaly detector for a set of business metrics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"lookout-for-metrics.create-anomaly-detector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-anomaly-detectors\n          description: \"List all configured anomaly detectors\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.list-anomaly-detectors\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-anomaly-detector\n          description: \"Get configuration and status details of an anomaly detector\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.describe-anomaly-detector\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: activate-anomaly-detector\n          description: \"Activate an anomaly detector to begin monitoring metrics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.activate-anomaly-detector\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: deactivate-anomaly-detector\n          description: \"Stop an anomaly detector from monitoring metrics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.deactivate-anomaly-detector\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-anomaly-group-summaries\n          description: \"List summaries of detected anomaly groups for investigation\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.list-anomaly-group-summaries\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-anomaly-group\n\
  \          description: \"Get full details of a specific anomaly group including contributing metrics\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.get-anomaly-group\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n            AnomalyGroupId: \"tools.AnomalyGroupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-anomaly-group-related-metrics\n          description: \"List all metrics that contributed to an anomaly group\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.list-anomaly-group-related-metrics\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n            AnomalyGroupId: \"tools.AnomalyGroupId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: create-alert\n          description: \"Create an alert to receive notifications when anomalies are detected\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"lookout-for-metrics.create-alert\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alerts\n          description: \"List all configured anomaly alerts\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.list-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-feedback\n          description: \"Submit feedback on anomaly detections to improve ML model accuracy\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call:\
  \ \"lookout-for-metrics.put-feedback\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-feedback\n          description: \"Retrieve previously submitted anomaly detection feedback\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-metrics.get-feedback\"\n          with:\n            AnomalyDetectorArn: \"tools.AnomalyDetectorArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lookout-for-metrics/refs/heads/main/capabilities/anomaly-detection-operations.yaml
tags:
- Amazon
- Anomaly Detection
- Machine Learning
- Metrics
- Monitoring
- Operations
tools:
- description: Create a new anomaly detector for a set of business metrics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-anomaly-detector
- description: List all configured anomaly detectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-anomaly-detectors
- description: Get configuration and status details of an anomaly detector
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describe-anomaly-detector
- description: Activate an anomaly detector to begin monitoring metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: activate-anomaly-detector
- description: Stop an anomaly detector from monitoring metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deactivate-anomaly-detector
- description: List summaries of detected anomaly groups for investigation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-anomaly-group-summaries
- description: Get full details of a specific anomaly group including contributing metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-anomaly-group
- description: List all metrics that contributed to an anomaly group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-anomaly-group-related-metrics
- description: Create an alert to receive notifications when anomalies are detected
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-alert
- description: List all configured anomaly alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-alerts
- description: Submit feedback on anomaly detections to improve ML model accuracy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: put-feedback
- description: Retrieve previously submitted anomaly detection feedback
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-feedback
---
