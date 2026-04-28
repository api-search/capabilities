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
- get the current state of a batch spark job
- interactive computing
- scientists who use interactive spark sessions for exploratory analysis
- apache livy
- delete an interactive spark session
- get the current state of a spark session
- run statement
- execute a code statement in an interactive spark session
- open source
- submit a batch spark job to the cluster via livy
- create batch
- rest
- delete spark session
- list spark sessions
- submit batch spark job
- get batch state
- list batches
- Data Engineer
- Data Scientist
- get session state
- data engineering
- spark
- data science
- list sessions
- create a new interactive spark session for code execution
- run spark code
- create session
- big data
- list all active interactive spark sessions on the livy server
- create spark session
- engineers who submit and monitor batch spark jobs via livy
slug: spark-job-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Livy Spark Job Management\"\n  description: \"Workflow capability for data engineers and data scientists to manage interactive Spark sessions and submit batch Spark jobs via Apache Livy REST API.\"\n  tags:\n    - Apache Livy\n    - Data Engineering\n    - Data Science\n    - Spark\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      LIVY_URL: LIVY_URL\n\ncapability:\n  consumes:\n    - import: livy-rest-api\n      location: ./shared/livy-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: livy-spark-management-api\n      description: \"Unified REST API for Apache Livy Spark job management.\"\n      resources:\n        - path: /v1/sessions\n          name: sessions\n          operations:\n            - method: GET\n              name: list-sessions\n              call: \"livy-rest-api.list-sessions\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-session\n              call: \"livy-rest-api.create-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sessions/{sessionId}/statements\n          name: statements\n          operations:\n            - method: POST\n              name: run-statement\n              call: \"livy-rest-api.run-statement\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batches\n          name: batches\n          operations:\n            - method: GET\n              name: list-batches\n              call: \"livy-rest-api.list-batches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-batch\n              call: \"livy-rest-api.create-batch\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: livy-spark-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Livy Spark job management.\"\n      tools:\n        - name: list-spark-sessions\n          description: List all active interactive Spark sessions on the Livy server\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"livy-rest-api.list-sessions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-spark-session\n          description: Create a new interactive Spark session for code execution\n          hints:\n            readOnly: false\n          call: \"livy-rest-api.create-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-session-state\n          description:\
  \ Get the current state of a Spark session\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"livy-rest-api.get-session-state\"\n          with:\n            sessionId: \"tools.session_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-spark-code\n          description: Execute a code statement in an interactive Spark session\n          hints:\n            readOnly: false\n          call: \"livy-rest-api.run-statement\"\n          with:\n            sessionId: \"tools.session_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-spark-session\n          description: Delete an interactive Spark session\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"livy-rest-api.delete-session\"\n          with:\n            sessionId: \"tools.session_id\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n        - name: submit-batch-spark-job\n          description: Submit a batch Spark job to the cluster via Livy\n          hints:\n            readOnly: false\n          call: \"livy-rest-api.create-batch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-batch-state\n          description: Get the current state of a batch Spark job\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"livy-rest-api.get-batch-state\"\n          with:\n            batchId: \"tools.batch_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-livy/refs/heads/main/capabilities/spark-job-management.yaml
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
