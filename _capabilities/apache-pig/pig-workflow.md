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
- submit a pig latin script for execution
- validate a pig latin script for syntax errors
- etl
- list pig jobs
- builds etl pipelines using pig latin scripts
- get status and details of a pig job
- Data Engineer
- get execution logs for a pig job
- Data Analyst
- list jobs
- runs ad-hoc data analysis jobs on hadoop clusters
- get job logs
- apache
- submit pig script
- open source
- validate script
- kill job
- get job
- kill a running pig job
- scripting
- data analysis
- big data
- submit job
- apache pig
- list all pig data processing jobs
- hadoop
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
