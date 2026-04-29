---
categories: []
consumed_apis:
- kafka-rest-proxy
- kafka-connect
description: Workflow capability for data engineers and platform architects to manage Kafka topics, produce and consume messages, and manage connectors via Kafka REST Proxy and Connect APIs.
layout: capability
name: Apache Kafka Event Streaming
operations:
- description: ''
  method: GET
  name: list-topics
  path: /v1/topics
- description: ''
  method: POST
  name: produce-message
  path: /v1/topics
- description: ''
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: ''
  method: POST
  name: create-connector
  path: /v1/connectors
personas: []
provider_name: Apache Kafka
provider_slug: apache-kafka
search_terms:
- apache kafka
- list topics
- pub-sub
- data engineering
- get connector status
- event streaming
- list connectors
- list all kafka connect connectors
- create connector
- platform architecture
- messaging
- architects who design and manage kafka cluster topology and connectivity
- produce message
- distributed systems
- Platform Architect
- engineers who build data pipelines using kafka topics and connectors
- Data Engineer
- get the status of a specific kafka connect connector
- restart connector
- produce a message to a kafka topic via the rest proxy
- restart a failed kafka connect connector
- list all kafka topics in the cluster
- open source
- create a new kafka connect connector for data integration
slug: event-streaming
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Kafka Event Streaming\"\n  description: \"Workflow capability for data engineers and platform architects to manage Kafka topics, produce and consume messages, and manage connectors via Kafka REST Proxy and Connect APIs.\"\n  tags:\n    - Apache Kafka\n    - Data Engineering\n    - Event Streaming\n    - Platform Architecture\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      KAFKA_REST_URL: KAFKA_REST_URL\n      KAFKA_CONNECT_URL: KAFKA_CONNECT_URL\n\ncapability:\n  consumes:\n    - import: kafka-rest-proxy\n      location: ./shared/kafka-rest-proxy.yaml\n    - import: kafka-connect\n      location: ./shared/kafka-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: kafka-event-streaming-api\n      description: \"Unified REST API for Apache Kafka event streaming management.\"\n      resources:\n        - path: /v1/topics\n          name: topics\n\
  \          operations:\n            - method: GET\n              name: list-topics\n              call: \"kafka-rest-proxy.list-topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: produce-message\n              call: \"kafka-rest-proxy.produce-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connectors\n          name: connectors\n          operations:\n            - method: GET\n              name: list-connectors\n              call: \"kafka-connect.list-connectors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connector\n              call: \"kafka-connect.create-connector\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: kafka-event-streaming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Kafka event streaming management.\"\n      tools:\n        - name: list-topics\n          description: List all Kafka topics in the cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kafka-rest-proxy.list-topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: produce-message\n          description: Produce a message to a Kafka topic via the REST Proxy\n          hints:\n            readOnly: false\n          call: \"kafka-rest-proxy.produce-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connectors\n          description: List all Kafka Connect connectors\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kafka-connect.list-connectors\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connector\n          description: Create a new Kafka Connect connector for data integration\n          hints:\n            readOnly: false\n          call: \"kafka-connect.create-connector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connector-status\n          description: Get the status of a specific Kafka Connect connector\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kafka-connect.get-connector-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-connector\n          description: Restart a failed Kafka Connect connector\n          hints:\n            readOnly: false\n          call: \"kafka-connect.restart-connector\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-kafka/refs/heads/main/capabilities/event-streaming.yaml
tags:
- Apache Kafka
- Data Engineering
- Event Streaming
- Platform Architecture
tools:
- description: List all Kafka topics in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-topics
- description: Produce a message to a Kafka topic via the REST Proxy
  hints:
    readOnly: false
  name: produce-message
- description: List all Kafka Connect connectors
  hints:
    openWorld: true
    readOnly: true
  name: list-connectors
- description: Create a new Kafka Connect connector for data integration
  hints:
    readOnly: false
  name: create-connector
- description: Get the status of a specific Kafka Connect connector
  hints:
    openWorld: true
    readOnly: true
  name: get-connector-status
- description: Restart a failed Kafka Connect connector
  hints:
    readOnly: false
  name: restart-connector
---
