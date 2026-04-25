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
- hadoop
- scripting
- kill a running pig job
- list pig jobs
- Data Engineer
- get job
- list all pig data processing jobs
- submit pig script
- list jobs
- validate a pig latin script for syntax errors
- big data
- apache
- apache pig
- get status and details of a pig job
- data analysis
- validate script
- builds etl pipelines using pig latin scripts
- get job logs
- get execution logs for a pig job
- Data Analyst
- runs ad-hoc data analysis jobs on hadoop clusters
- etl
- open source
- submit a pig latin script for execution
- kill job
- submit job
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
