---
categories:
- api-management
consumed_apis:
- zilla-gateway
description: Workflow for exposing Apache Kafka topics as REST APIs and managing event-driven integrations via Zilla. Enables HTTP, MQTT, and gRPC clients to produce and consume Kafka events without Kafka client libraries.
layout: capability
name: Aklivity Kafka API Gateway
operations:
- description: Produce an event to Kafka
  method: POST
  name: produce-event
  path: /v1/events
- description: Consume events from Kafka
  method: GET
  name: consume-events
  path: /v1/events
personas: []
provider_name: Aklivity
provider_slug: aklivity
search_terms:
- event-driven application patterns with kafka as the backbone
- multi-protocol
- multi-protocol api gateway for kafka access
- iot
- expose kafka topics as rest apis and manage event-driven integrations
- IoT Developer
- API Developer
- connects iot devices via mqtt to kafka using zilla
- consume events from kafka
- apache kafka
- api gateway
- kafka
- builds rest apis backed by kafka topics using zilla
- consume events
- produce an event to a kafka topic via zilla http gateway
- kafka event production and consumption
- kafka proxy
- real-time
- produce an event to kafka
- event-driven
- apache kafka topic management and event streaming
- configures and manages zilla gateway deployments for kafka access
- produce event
- aklivity
- consume kafka events
- consume events from a kafka topic via zilla http gateway
- produce kafka event
- Platform Engineer
slug: kafka-api-gateway
tags:
- Aklivity
- Kafka
- API Gateway
- Event-Driven
- Multi-Protocol
- Real-Time
tools:
- description: Produce an event to a Kafka topic via Zilla HTTP gateway
  hints:
    destructive: false
    readOnly: false
  name: produce-kafka-event
- description: Consume events from a Kafka topic via Zilla HTTP gateway
  hints:
    openWorld: true
    readOnly: true
  name: consume-kafka-events
---
