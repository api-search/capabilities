---
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
- builds etl pipelines using pig latin scripts
- runs ad-hoc data analysis jobs on hadoop clusters
- submit pig script
- hadoop
- apache pig
- get execution logs for a pig job
- get job
- list pig jobs
- scripting
- submit a pig latin script for execution
- get job logs
- etl
- apache
- list jobs
- open source
- validate a pig latin script for syntax errors
- data analysis
- Data Engineer
- validate script
- kill a running pig job
- kill job
- big data
- list all pig data processing jobs
- submit job
- get status and details of a pig job
- Data Analyst
slug: pig-workflow
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
