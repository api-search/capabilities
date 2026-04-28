---
categories: []
consumed_apis:
- livy-rest-api
description: Workflow capability for data engineers and data scientists to manage interactive Spark sessions and submit batch Spark jobs via Apache Livy REST API.
layout: capability
name: Apache Livy Spark Job Management
operations:
- description: ''
  method: GET
  name: list-sessions
  path: /v1/sessions
- description: ''
  method: POST
  name: create-session
  path: /v1/sessions
- description: ''
  method: POST
  name: run-statement
  path: /v1/sessions/{sessionId}/statements
- description: ''
  method: GET
  name: list-batches
  path: /v1/batches
- description: ''
  method: POST
  name: create-batch
  path: /v1/batches
personas: []
provider_name: Apache Livy
provider_slug: apache-livy
search_terms:
- scientists who use interactive spark sessions for exploratory analysis
- list batches
- get batch state
- create spark session
- run statement
- list sessions
- execute a code statement in an interactive spark session
- data engineering
- submit a batch spark job to the cluster via livy
- engineers who submit and monitor batch spark jobs via livy
- data science
- create batch
- Data Engineer
- list all active interactive spark sessions on the livy server
- list spark sessions
- interactive computing
- open source
- get session state
- Data Scientist
- delete spark session
- delete an interactive spark session
- big data
- create session
- rest
- get the current state of a spark session
- create a new interactive spark session for code execution
- get the current state of a batch spark job
- apache livy
- run spark code
- submit batch spark job
- spark
slug: spark-job-management
tags:
- Apache Livy
- Data Engineering
- Data Science
- Spark
tools:
- description: List all active interactive Spark sessions on the Livy server
  hints:
    openWorld: true
    readOnly: true
  name: list-spark-sessions
- description: Create a new interactive Spark session for code execution
  hints:
    readOnly: false
  name: create-spark-session
- description: Get the current state of a Spark session
  hints:
    openWorld: true
    readOnly: true
  name: get-session-state
- description: Execute a code statement in an interactive Spark session
  hints:
    readOnly: false
  name: run-spark-code
- description: Delete an interactive Spark session
  hints:
    destructive: true
    readOnly: false
  name: delete-spark-session
- description: Submit a batch Spark job to the cluster via Livy
  hints:
    readOnly: false
  name: submit-batch-spark-job
- description: Get the current state of a batch Spark job
  hints:
    openWorld: true
    readOnly: true
  name: get-batch-state
---
