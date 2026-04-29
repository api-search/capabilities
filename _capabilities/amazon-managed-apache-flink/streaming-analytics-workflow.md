---
categories: []
consumed_apis:
- managed-apache-flink
description: Workflow capability for data engineers and analysts to build, manage, and monitor Apache Flink streaming analytics applications on AWS.
layout: capability
name: Amazon Managed Service for Apache Flink - Streaming Analytics Workflow
operations:
- description: Create a streaming application
  method: POST
  name: create-application
  path: /v1/applications
- description: List all streaming applications
  method: GET
  name: list-applications
  path: /v1/applications
personas: []
provider_name: Amazon Managed Service for Apache Flink
provider_slug: amazon-managed-apache-flink
search_terms:
- create application
- flink streaming applications
- create a new apache flink streaming analytics application on aws
- create streaming application
- list applications
- Data Engineer
- start streaming application
- get application details
- aws
- create a streaming application
- streaming analytics
- get configuration and status details of a flink application
- stop a running flink streaming application
- start a flink application to begin real-time stream processing
- real-time processing
- big data
- stop streaming application
- apache flink
- list all streaming applications
- amazon
- list streaming applications
- list all flink streaming analytics applications
- Analytics Engineer
slug: streaming-analytics-workflow
source_filename: streaming-analytics-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Managed Service for Apache Flink - Streaming Analytics Workflow\"\n  description: \"Workflow capability for data engineers and analysts to build, manage, and monitor Apache Flink streaming analytics applications on AWS.\"\n  tags:\n    - Amazon\n    - Apache Flink\n    - Streaming Analytics\n    - Real-Time Processing\n    - Big Data\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: managed-apache-flink\n      location: ./shared/managed-apache-flink.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: streaming-analytics-api\n      description: \"Unified REST API for Apache Flink streaming analytics workflows.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n\
  \          description: \"Flink streaming applications\"\n          operations:\n            - method: POST\n              name: create-application\n              description: \"Create a streaming application\"\n              call: \"managed-apache-flink.create-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-applications\n              description: \"List all streaming applications\"\n              call: \"managed-apache-flink.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: streaming-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Flink streaming analytics.\"\n      tools:\n        - name: create-streaming-application\n          description: \"Create a new Apache Flink streaming analytics application\
  \ on AWS\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-apache-flink.create-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-streaming-applications\n          description: \"List all Flink streaming analytics applications\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-apache-flink.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-details\n          description: \"Get configuration and status details of a Flink application\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-apache-flink.describe-application\"\n          with:\n            ApplicationName: \"tools.ApplicationName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-streaming-application\n          description: \"Start a Flink application to begin real-time stream processing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"managed-apache-flink.start-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-streaming-application\n          description: \"Stop a running Flink streaming application\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"managed-apache-flink.stop-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-managed-apache-flink/refs/heads/main/capabilities/streaming-analytics-workflow.yaml
tags:
- Amazon
- Apache Flink
- Streaming Analytics
- Real-Time Processing
- Big Data
tools:
- description: Create a new Apache Flink streaming analytics application on AWS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-streaming-application
- description: List all Flink streaming analytics applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-streaming-applications
- description: Get configuration and status details of a Flink application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-application-details
- description: Start a Flink application to begin real-time stream processing
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-streaming-application
- description: Stop a running Flink streaming application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-streaming-application
---
