---
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
- update detector configuration
- delete a detector
- update detector
- create an alert to receive notifications when anomalies are detected
- anomaly alerts
- list alerts
- list all configured anomaly detectors
- create anomaly detector
- describe anomaly detector
- list all alerts
- ml-powered detection of anomalies in business and operational metrics
- machine learning
- list anomalies
- single anomaly group
- operations
- configuration and management of anomaly alert notifications
- create a new anomaly detector for a set of business metrics
- list anomaly detectors
- list all configured anomaly alerts
- manage anomaly detectors
- stop an anomaly detector from monitoring metrics
- manages anomaly detector configuration, metric sets, and feedback to improve ml model accuracy
- retrieve previously submitted anomaly detection feedback
- list detectors
- get detector details
- get detector
- list summaries of detected anomaly groups for investigation
- monitoring
- anomaly detection
- anomaly group results
- submit anomaly feedback
- submit feedback on anomaly detections to improve ml model accuracy
- Operations Engineer
- list anomaly group summaries
- create an alert
- activate anomaly detector
- get full details of a specific anomaly group including contributing metrics
- create detector
- detection feedback
- create a new anomaly detector
- amazon
- create alert
- get configuration and status details of an anomaly detector
- get anomaly group details
- deactivate anomaly detector
- Data Scientist
- get anomaly feedback
- list all anomaly detectors
- metrics
- get anomaly
- submit feedback
- single anomaly detector
- get feedback
- activate an anomaly detector to begin monitoring metrics
- put feedback
- aws
- business intelligence
- get anomaly group
- monitoring and assessment of metric data quality
- list all metrics that contributed to an anomaly group
- list anomaly group related metrics
- monitors anomaly alerts, investigates anomaly groups, and manages detector lifecycle
- workflow for managing anomaly detectors, monitoring anomalies, configuring alerts, and providing feedback
- delete detector
slug: anomaly-detection-operations
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
