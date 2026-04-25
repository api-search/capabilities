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
- Platform Engineer
- connects iot devices via mqtt to kafka using zilla
- multi-protocol
- expose kafka topics as rest apis and manage event-driven integrations
- multi-protocol api gateway for kafka access
- configures and manages zilla gateway deployments for kafka access
- api gateway
- kafka proxy
- apache kafka
- apache kafka topic management and event streaming
- produce event
- consume events from a kafka topic via zilla http gateway
- consume kafka events
- builds rest apis backed by kafka topics using zilla
- real-time
- IoT Developer
- aklivity
- consume events from kafka
- produce an event to a kafka topic via zilla http gateway
- produce kafka event
- event-driven
- kafka
- iot
- produce an event to kafka
- kafka event production and consumption
- event-driven application patterns with kafka as the backbone
- API Developer
- consume events
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
