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
- detection feedback
- create a new anomaly detector
- submit anomaly feedback
- delete detector
- business intelligence
- Operations Engineer
- get configuration and status details of an anomaly detector
- metrics
- anomaly detection
- configuration and management of anomaly alert notifications
- submit feedback on anomaly detections to improve ml model accuracy
- list anomaly group related metrics
- get detector details
- list anomaly detectors
- put feedback
- workflow for managing anomaly detectors, monitoring anomalies, configuring alerts, and providing feedback
- create anomaly detector
- Data Scientist
- monitoring
- single anomaly group
- get anomaly group details
- manages anomaly detector configuration, metric sets, and feedback to improve ml model accuracy
- anomaly group results
- list all configured anomaly detectors
- list anomalies
- get anomaly
- monitors anomaly alerts, investigates anomaly groups, and manages detector lifecycle
- anomaly alerts
- retrieve previously submitted anomaly detection feedback
- update detector
- list summaries of detected anomaly groups for investigation
- single anomaly detector
- get anomaly group
- list alerts
- stop an anomaly detector from monitoring metrics
- delete a detector
- get feedback
- list detectors
- get full details of a specific anomaly group including contributing metrics
- update detector configuration
- list all metrics that contributed to an anomaly group
- machine learning
- get detector
- create an alert to receive notifications when anomalies are detected
- list all alerts
- create an alert
- activate anomaly detector
- ml-powered detection of anomalies in business and operational metrics
- submit feedback
- aws
- manage anomaly detectors
- activate an anomaly detector to begin monitoring metrics
- amazon
- monitoring and assessment of metric data quality
- describe anomaly detector
- get anomaly feedback
- operations
- create a new anomaly detector for a set of business metrics
- create detector
- list all anomaly detectors
- list all configured anomaly alerts
- deactivate anomaly detector
- create alert
- list anomaly group summaries
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
