---
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
- execute a code statement in an interactive spark session
- submit a batch spark job to the cluster via livy
- create batch
- list batches
- get the current state of a batch spark job
- list spark sessions
- list sessions
- scientists who use interactive spark sessions for exploratory analysis
- create a new interactive spark session for code execution
- get session state
- submit batch spark job
- run statement
- data science
- list all active interactive spark sessions on the livy server
- delete an interactive spark session
- big data
- Data Scientist
- engineers who submit and monitor batch spark jobs via livy
- delete spark session
- apache livy
- get the current state of a spark session
- create spark session
- Data Engineer
- spark
- get batch state
- rest
- data engineering
- interactive computing
- run spark code
- open source
- create session
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
