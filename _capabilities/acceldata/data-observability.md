---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Data Observability
operations: []
personas: []
provider_name: Acceldata
provider_slug: acceldata
search_terms:
- intelligence
- data pipeline
- data quality
- observability
- data management
- data observability
- ai agents
slug: data-observability
source_filename: data-observability.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.io/v1alpha1\nkind: WorkflowCapability\nmetadata:\n  name: data-observability\n  version: 1.0.0\n  description: End-to-end data observability workflow for monitoring data quality, tracing lineage, and managing pipeline health across cloud and hybrid environments\n  provider: Acceldata\n  tags:\n    - Data Observability\n    - Data Quality\n    - Pipeline Monitoring\n    - Data Lineage\n    - Alerts\nspec:\n  sharedCapabilities:\n    - acceldata-adoc-api\n  workflow:\n    name: Data Quality Incident Response\n    description: Detect data quality alerts, trace root cause through lineage, and remediate with updated quality rules\n    steps:\n      - id: monitor-alerts\n        name: Monitor Active Alerts\n        description: Continuously poll for open data quality and pipeline alerts\n        operation: listAlerts\n        parameters:\n          status: OPEN\n          severity: [\"HIGH\", \"CRITICAL\"]\n      - id: investigate-dataset\n        name: Investigate\
  \ Affected Dataset\n        description: Retrieve dataset profile and quality score for affected data asset\n        operation: listDatasets\n        dependsOn: [monitor-alerts]\n      - id: trace-lineage\n        name: Trace Data Lineage\n        description: Get upstream lineage to identify root cause data source\n        operation: getDatasetLineage\n        dependsOn: [investigate-dataset]\n      - id: check-pipeline\n        name: Check Pipeline Jobs\n        description: Review recent pipeline job executions for failures or anomalies\n        operation: listPipelineJobs\n        dependsOn: [trace-lineage]\n      - id: create-rule\n        name: Create Remediation Rule\n        description: Create or update data quality rule to prevent recurrence\n        operation: createDataQualityRule\n        dependsOn: [check-pipeline]\n      - id: acknowledge-alert\n        name: Acknowledge Alert\n        description: Acknowledge alert after root cause is identified and rule is created\n  \
  \      operation: acknowledgeAlert\n        dependsOn: [create-rule]\n  mcpTools:\n    - name: list_alerts\n      description: List open data quality and pipeline alerts with optional severity filtering\n      capability: acceldata-adoc-api\n      operation: listAlerts\n    - name: get_dataset_lineage\n      description: Retrieve the full upstream and downstream lineage graph for a dataset\n      capability: acceldata-adoc-api\n      operation: getDatasetLineage\n    - name: list_pipeline_jobs\n      description: List recent pipeline job executions with status and performance metrics\n      capability: acceldata-adoc-api\n      operation: listPipelineJobs\n    - name: create_data_quality_rule\n      description: Create a new data quality rule to monitor a dataset column for anomalies\n      capability: acceldata-adoc-api\n      operation: createDataQualityRule\n    - name: acknowledge_alert\n      description: Acknowledge an alert with a comment after investigation\n      capability: acceldata-adoc-api\n\
  \      operation: acknowledgeAlert\n    - name: list_datasets\n      description: List all monitored datasets with quality scores and profile metadata\n      capability: acceldata-adoc-api\n      operation: listDatasets\n  ports:\n    http: 8080\n    grpc: 9090\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acceldata/refs/heads/main/capabilities/data-observability.yaml
tags: []
tools: []
---
