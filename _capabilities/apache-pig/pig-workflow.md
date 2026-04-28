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
- kill job
- builds etl pipelines using pig latin scripts
- Data Analyst
- scripting
- data analysis
- submit pig script
- runs ad-hoc data analysis jobs on hadoop clusters
- apache
- get job
- apache pig
- submit a pig latin script for execution
- validate a pig latin script for syntax errors
- open source
- kill a running pig job
- list all pig data processing jobs
- validate script
- list pig jobs
- Data Engineer
- get execution logs for a pig job
- big data
- get job logs
- list jobs
- etl
- hadoop
- get status and details of a pig job
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
