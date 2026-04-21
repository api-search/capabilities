---
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
- connects iot devices via mqtt to kafka using zilla
- event-driven
- multi-protocol
- apache kafka topic management and event streaming
- consume events from a kafka topic via zilla http gateway
- iot
- kafka
- Platform Engineer
- event-driven application patterns with kafka as the backbone
- aklivity
- expose kafka topics as rest apis and manage event-driven integrations
- real-time
- API Developer
- api gateway
- apache kafka
- consume events from kafka
- kafka proxy
- builds rest apis backed by kafka topics using zilla
- produce event
- multi-protocol api gateway for kafka access
- produce kafka event
- produce an event to kafka
- consume events
- kafka event production and consumption
- configures and manages zilla gateway deployments for kafka access
- IoT Developer
- consume kafka events
- produce an event to a kafka topic via zilla http gateway
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
