---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Rocketmq Workflow
operations: []
personas: []
provider_name: Apache RocketMQ
provider_slug: apache-rocketmq
search_terms:
- end-to-end workflow for producing and consuming rocketmq messages
- developer building messaging applications with rocketmq
- messaging
- high-throughput event streaming for real-time processing
- engineer managing rocketmq clusters and topics
- cloud native
- streaming
- apache
- pub-sub
- reliable message delivery between producers and consumers
- message queue
- open source
slug: rocketmq-workflow
source_filename: rocketmq-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache RocketMQ Messaging Workflow\ndescription: Workflow capability for producing and consuming messages with Apache RocketMQ.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache RocketMQ REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-rocketmq/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/rocketmq-api.yaml\nworkflow:\n  name: rocketmq-workflow\n  description: Manage topics, send and receive messages, and monitor broker health with Apache RocketMQ.\n  steps:\n    - name: create-topic\n      description: Create a message topic\n      api: Apache RocketMQ REST API\n      operation: createTopic\n    - name: create-consumer-group\n      description: Create a consumer group\n      api: Apache RocketMQ REST API\n      operation: createConsumerGroup\n    - name: send-message\n      description: Send a message to a topic\n      api: Apache RocketMQ REST API\n      operation: sendMessage\n    - name: receive-messages\n      description:\
  \ Receive messages from a topic\n      api: Apache RocketMQ REST API\n      operation: receiveMessages\n    - name: acknowledge-message\n      description: Acknowledge message consumption\n      api: Apache RocketMQ REST API\n      operation: acknowledgeMessage\nexposes:\n  - type: rest\n    port: 8081\n    paths:\n      - /topics\n      - /topics/{topic}\n      - /messages\n      - /messages/receive\n      - /messages/ack\n      - /consumer-groups\n      - /brokers\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-topics\n        description: List RocketMQ topics\n        operation: listTopics\n      - name: create-topic\n        description: Create a RocketMQ topic\n        operation: createTopic\n      - name: send-message\n        description: Send a message to a topic\n        operation: sendMessage\n      - name: receive-messages\n        description: Pull messages from a topic\n        operation: receiveMessages\n      - name: acknowledge-message\n        description:\
  \ Acknowledge message consumption\n        operation: acknowledgeMessage\n      - name: list-consumer-groups\n        description: List consumer groups\n        operation: listConsumerGroups\n      - name: create-consumer-group\n        description: Create a consumer group\n        operation: createConsumerGroup\n      - name: list-brokers\n        description: List cluster brokers\n        operation: listBrokers\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-rocketmq/refs/heads/main/capabilities/rocketmq-workflow.yaml
tags: []
tools: []
---
