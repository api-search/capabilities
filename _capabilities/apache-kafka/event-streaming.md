---
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
- platform architecture
- create a new kafka connect connector for data integration
- list connectors
- Platform Architect
- restart connector
- create connector
- event streaming
- messaging
- list topics
- restart a failed kafka connect connector
- list all kafka topics in the cluster
- produce message
- architects who design and manage kafka cluster topology and connectivity
- list all kafka connect connectors
- Data Engineer
- pub-sub
- get the status of a specific kafka connect connector
- produce a message to a kafka topic via the rest proxy
- data engineering
- distributed systems
- get connector status
- apache kafka
- open source
- engineers who build data pipelines using kafka topics and connectors
slug: event-streaming
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
