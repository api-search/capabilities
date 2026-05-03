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
- aklivity
- multi-protocol
- Platform Engineer
- api gateway
- consume events from a kafka topic via zilla http gateway
- multi-protocol api gateway for kafka access
- produce an event to kafka
- kafka proxy
- expose kafka topics as rest apis and manage event-driven integrations
- iot
- consume events
- real-time
- connects iot devices via mqtt to kafka using zilla
- apache kafka
- kafka
- apache kafka topic management and event streaming
- produce an event to a kafka topic via zilla http gateway
- event-driven
- configures and manages zilla gateway deployments for kafka access
- IoT Developer
- consume events from kafka
- event-driven application patterns with kafka as the backbone
- produce kafka event
- consume kafka events
- API Developer
- builds rest apis backed by kafka topics using zilla
- produce event
- kafka event production and consumption
slug: kafka-api-gateway
source_filename: kafka-api-gateway.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Aklivity Kafka API Gateway\"\n  description: \"Workflow for exposing Apache Kafka topics as REST APIs and managing event-driven integrations via Zilla. Enables HTTP, MQTT, and gRPC clients to produce and consume Kafka events without Kafka client libraries.\"\n  tags:\n    - Aklivity\n    - Kafka\n    - API Gateway\n    - Event-Driven\n    - Multi-Protocol\n    - Real-Time\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      KAFKA_BOOTSTRAP_SERVERS: KAFKA_BOOTSTRAP_SERVERS\n      ZILLA_HOST: ZILLA_HOST\n      ZILLA_PORT: ZILLA_PORT\ncapability:\n  consumes:\n    - import: zilla-gateway\n      location: ./shared/zilla-gateway.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: kafka-api-gateway-api\n      description: \"Unified REST API for Kafka event production and consumption via Zilla.\"\n      resources:\n        - path: /v1/events\n          name: events\n   \
  \       description: \"Kafka event production and consumption\"\n          operations:\n            - method: POST\n              name: produce-event\n              description: \"Produce an event to Kafka\"\n              call: \"zilla-gateway.produce-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: consume-events\n              description: \"Consume events from Kafka\"\n              call: \"zilla-gateway.consume-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: kafka-api-gateway-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Kafka event streaming via Zilla gateway.\"\n      tools:\n        - name: produce-kafka-event\n          description: \"Produce an event to a Kafka topic via Zilla HTTP gateway\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n          call: \"zilla-gateway.produce-message\"\n          with:\n            key: \"tools.key\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: consume-kafka-events\n          description: \"Consume events from a Kafka topic via Zilla HTTP gateway\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zilla-gateway.consume-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aklivity/refs/heads/main/capabilities/kafka-api-gateway.yaml
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
