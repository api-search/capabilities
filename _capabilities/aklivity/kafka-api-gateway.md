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
- consume kafka events
- API Developer
- kafka
- connects iot devices via mqtt to kafka using zilla
- apache kafka
- consume events
- iot
- configures and manages zilla gateway deployments for kafka access
- produce an event to a kafka topic via zilla http gateway
- api gateway
- produce kafka event
- Platform Engineer
- multi-protocol api gateway for kafka access
- consume events from a kafka topic via zilla http gateway
- multi-protocol
- IoT Developer
- expose kafka topics as rest apis and manage event-driven integrations
- event-driven
- produce an event to kafka
- kafka proxy
- kafka event production and consumption
- apache kafka topic management and event streaming
- consume events from kafka
- produce event
- real-time
- builds rest apis backed by kafka topics using zilla
- aklivity
- event-driven application patterns with kafka as the backbone
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
