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
- Platform Engineer
- multi-protocol
- iot
- produce event
- produce kafka event
- aklivity
- apache kafka
- IoT Developer
- produce an event to a kafka topic via zilla http gateway
- event-driven application patterns with kafka as the backbone
- kafka event production and consumption
- consume kafka events
- API Developer
- configures and manages zilla gateway deployments for kafka access
- kafka
- produce an event to kafka
- consume events from kafka
- consume events
- real-time
- consume events from a kafka topic via zilla http gateway
- expose kafka topics as rest apis and manage event-driven integrations
- api gateway
- event-driven
- multi-protocol api gateway for kafka access
- apache kafka topic management and event streaming
- kafka proxy
- builds rest apis backed by kafka topics using zilla
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
