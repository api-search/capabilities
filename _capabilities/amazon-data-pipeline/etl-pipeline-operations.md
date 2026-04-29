---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Etl Pipeline Operations
operations: []
personas: []
provider_name: Amazon Data Pipeline
provider_slug: amazon-data-pipeline
search_terms:
- data processing
- etl
- data pipeline
- aws
- automation
- workflows
slug: etl-pipeline-operations
source_filename: etl-pipeline-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-data-pipeline/capabilities/etl-pipeline-operations.yaml\nname: ETL Pipeline Operations\ndescription: Workflow-oriented Naftiko capability for ETL data processing operations using AWS Data Pipeline, covering pipeline creation, definition, activation, and monitoring workflows.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - ETL\n  - Data Processing\n  - Data Pipeline\n  - Automation\n  - Analytics\n\nimports:\n  - url: capabilities/shared/data-pipeline.yaml\n    as: dataPipeline\n\npersonas:\n  - name: Data Engineer\n    description: Engineer building and maintaining data processing pipelines for ETL workflows\n  - name: Data Analyst\n    description: Analyst using pipelines to prepare data for analysis and reporting\n  - name: Platform Engineer\n    description: Engineer automating data movement between AWS storage and compute services\n\nworkflows:\n  - name: Create and Activate Pipeline\n    description:\
  \ Create a new pipeline, define its activities and schedules, validate, and activate it\n    steps:\n      - step: createPipeline\n        capability: dataPipeline\n        description: Create an empty pipeline with name and unique ID\n      - step: putPipelineDefinition\n        capability: dataPipeline\n        description: Define pipeline activities, schedules, and resources\n      - step: validatePipelineDefinition\n        capability: dataPipeline\n        description: Validate the definition before activation\n      - step: activatePipeline\n        capability: dataPipeline\n        description: Activate the pipeline to start processing\n    persona: Data Engineer\n\n  - name: Monitor Pipeline Execution\n    description: Monitor the status and progress of a running pipeline\n    steps:\n      - step: queryObjects\n        capability: dataPipeline\n        description: Query pipeline instances by execution status\n      - step: describeObjects\n        capability: dataPipeline\n \
  \       description: Get detailed status of specific pipeline objects\n    persona: Data Analyst\n\n  - name: Update Pipeline Definition\n    description: Update an existing pipeline definition with new activities or schedules\n    steps:\n      - step: deactivatePipeline\n        capability: dataPipeline\n        description: Pause the pipeline before making changes\n      - step: putPipelineDefinition\n        capability: dataPipeline\n        description: Update the pipeline definition\n      - step: validatePipelineDefinition\n        capability: dataPipeline\n        description: Validate the updated definition\n      - step: activatePipeline\n        capability: dataPipeline\n        description: Reactivate the updated pipeline\n    persona: Data Engineer\n\nrest:\n  port: 8080\n  baseURL: https://datapipeline.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: datapipeline\n\nmcp:\n  port: 9090\n  tools:\n    - name: create_and_activate_pipeline\n      description:\
  \ Create, define, validate, and activate a data processing pipeline\n      workflow: Create and Activate Pipeline\n    - name: monitor_pipeline_execution\n      description: Monitor the status and progress of running pipeline instances\n      workflow: Monitor Pipeline Execution\n    - name: update_pipeline_definition\n      description: Update an active pipeline with a new definition\n      workflow: Update Pipeline Definition\n    - name: list_pipelines\n      description: List all data pipelines\n      operationId: listPipelines\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-data-pipeline/refs/heads/main/capabilities/etl-pipeline-operations.yaml
tags: []
tools: []
---
