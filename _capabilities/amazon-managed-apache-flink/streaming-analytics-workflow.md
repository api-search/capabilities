---
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
- list applications
- Data Engineer
- Analytics Engineer
- real-time processing
- get application details
- stop streaming application
- list all flink streaming analytics applications
- create streaming application
- big data
- start streaming application
- list all streaming applications
- list streaming applications
- create a streaming application
- apache flink
- streaming analytics
- flink streaming applications
- create application
- stop a running flink streaming application
- aws
- create a new apache flink streaming analytics application on aws
- start a flink application to begin real-time stream processing
- amazon
- get configuration and status details of a flink application
slug: streaming-analytics-workflow
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
