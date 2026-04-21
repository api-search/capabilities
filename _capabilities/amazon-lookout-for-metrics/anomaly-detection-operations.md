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
- delete a detector
- list anomalies
- get anomaly feedback
- anomaly alerts
- list alerts
- aws
- metrics
- configuration and management of anomaly alert notifications
- get anomaly group
- list all metrics that contributed to an anomaly group
- retrieve previously submitted anomaly detection feedback
- activate an anomaly detector to begin monitoring metrics
- ml-powered detection of anomalies in business and operational metrics
- get anomaly group details
- monitoring
- workflow for managing anomaly detectors, monitoring anomalies, configuring alerts, and providing feedback
- create detector
- anomaly detection
- activate anomaly detector
- list anomaly detectors
- Operations Engineer
- create a new anomaly detector for a set of business metrics
- Data Scientist
- get feedback
- list anomaly group related metrics
- list detectors
- get configuration and status details of an anomaly detector
- put feedback
- create anomaly detector
- list all configured anomaly detectors
- create an alert to receive notifications when anomalies are detected
- submit feedback on anomaly detections to improve ml model accuracy
- submit feedback
- create an alert
- get detector
- list all anomaly detectors
- anomaly group results
- deactivate anomaly detector
- list all alerts
- describe anomaly detector
- get anomaly
- stop an anomaly detector from monitoring metrics
- update detector configuration
- single anomaly group
- get detector details
- monitoring and assessment of metric data quality
- submit anomaly feedback
- update detector
- get full details of a specific anomaly group including contributing metrics
- list summaries of detected anomaly groups for investigation
- detection feedback
- business intelligence
- list anomaly group summaries
- create alert
- machine learning
- amazon
- list all configured anomaly alerts
- operations
- delete detector
- manage anomaly detectors
- manages anomaly detector configuration, metric sets, and feedback to improve ml model accuracy
- single anomaly detector
- create a new anomaly detector
- monitors anomaly alerts, investigates anomaly groups, and manages detector lifecycle
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
