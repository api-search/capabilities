---
categories:
- data-engineering
consumed_apis: []
description: Workflow for submitting, monitoring, and managing Pig Latin data analysis jobs on Hadoop clusters.
layout: capability
name: Apache Pig Data Processing Workflow
operations:
- description: List Pig jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Submit Pig script
  method: POST
  name: submit-job
  path: /v1/jobs
personas: []
provider_name: Apache Pig
provider_slug: apache-pig
search_terms:
- submit job
- kill a running pig job
- list jobs
- hadoop
- etl
- scripting
- get execution logs for a pig job
- runs ad-hoc data analysis jobs on hadoop clusters
- list pig jobs
- big data
- apache pig
- kill job
- get job
- Data Analyst
- submit a pig latin script for execution
- data analysis
- open source
- get job logs
- validate a pig latin script for syntax errors
- Data Engineer
- builds etl pipelines using pig latin scripts
- validate script
- apache
- submit pig script
- get status and details of a pig job
- list all pig data processing jobs
slug: pig-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Pig Data Processing Workflow\"\n  description: \"Workflow for submitting, monitoring, and managing Pig Latin data analysis jobs on Hadoop clusters.\"\n  tags:\n    - Apache Pig\n    - Big Data\n    - Data Analysis\n    - Hadoop\n    - ETL\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      PIG_API_KEY: PIG_API_KEY\ncapability:\n  consumes:\n    - type: http\n      namespace: pig\n      baseUri: https://localhost:8080/pig\n      description: \"Apache Pig REST API\"\n      resources:\n        - name: jobs\n          path: /jobs\n          description: \"Pig job management\"\n          operations:\n            - name: listJobs\n              method: GET\n              description: \"List Pig jobs\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n            -\
  \ name: submitJob\n              method: POST\n              description: \"Submit a Pig script\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pig-api\n      description: \"Unified REST API for Pig data processing.\"\n      resources:\n        - path: /v1/jobs\n          name: jobs\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List Pig jobs\"\n              call: \"pig.listJobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-job\n              description: \"Submit Pig script\"\n              call: \"pig.submitJob\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n\
  \      port: 9090\n      namespace: pig-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Pig data processing.\"\n      tools:\n        - name: list-jobs\n          description: \"List all Pig data processing jobs\"\n          hints:\n            readOnly: true\n          call: \"pig.listJobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-job\n          description: \"Submit a Pig Latin script for execution\"\n          hints:\n            readOnly: false\n          call: \"pig.submitJob\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job\n          description: \"Get status and details of a Pig job\"\n          hints:\n            readOnly: true\n          call: \"pig.getJob\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kill-job\n          description: \"Kill a running Pig\
  \ job\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"pig.killJob\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-logs\n          description: \"Get execution logs for a Pig job\"\n          hints:\n            readOnly: true\n          call: \"pig.getJobLogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-script\n          description: \"Validate a Pig Latin script for syntax errors\"\n          hints:\n            readOnly: true\n          call: \"pig.validateScript\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-pig/refs/heads/main/capabilities/pig-workflow.yaml
tags:
- Apache Pig
- Big Data
- Data Analysis
- Hadoop
- ETL
tools:
- description: List all Pig data processing jobs
  hints:
    readOnly: true
  name: list-jobs
- description: Submit a Pig Latin script for execution
  hints:
    readOnly: false
  name: submit-job
- description: Get status and details of a Pig job
  hints:
    readOnly: true
  name: get-job
- description: Kill a running Pig job
  hints:
    destructive: true
    readOnly: false
  name: kill-job
- description: Get execution logs for a Pig job
  hints:
    readOnly: true
  name: get-job-logs
- description: Validate a Pig Latin script for syntax errors
  hints:
    readOnly: true
  name: validate-script
---
