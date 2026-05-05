---
categories: []
consumed_apis:
- kafka-bridge
description: Unified capability for Kafka messaging via the Strimzi Kafka Bridge REST API. Designed for application developers and platform engineers who need to produce and consume Kafka messages without a native Kafka client, manage consumer group subscriptions, and query topic metadata. Ideal for HTTP microservices, serverless functions, and legacy applications integrating with Kafka.
layout: capability
name: Strimzi Kafka Messaging
operations:
- description: List all available Kafka topics
  method: GET
  name: list-topics
  path: /v1/topics
- description: Get partition metadata for a topic
  method: GET
  name: list-partitions
  path: /v1/topics/{topicname}/partitions
- description: Produce messages to a topic
  method: POST
  name: produce-messages
  path: /v1/topics/{topicname}/messages
- description: Create a consumer instance
  method: POST
  name: create-consumer
  path: /v1/consumers/{groupid}
- description: List consumer subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/consumers/{groupid}/instances/{name}/subscription
- description: Subscribe consumer to topics
  method: POST
  name: subscribe
  path: /v1/consumers/{groupid}/instances/{name}/subscription
- description: Poll for messages
  method: GET
  name: poll-messages
  path: /v1/consumers/{groupid}/instances/{name}/records
- description: Commit offsets
  method: POST
  name: commit-offsets
  path: /v1/consumers/{groupid}/instances/{name}/offsets
- description: Check bridge health
  method: GET
  name: health-check
  path: /v1/health
personas: []
provider_name: Strimzi
provider_slug: strimzi
search_terms:
- list partitions
- create a consumer instance
- subscribe a consumer to one or more kafka topics
- offset management
- check bridge health
- poll for messages from subscribed kafka topics (long-poll with configurable timeout)
- subscribe to topics
- kafka topic listing
- get partition metadata including leader and replica info for a topic
- consumer group management
- get partition metadata for a topic
- streaming
- produce messages
- message consumption
- poll messages
- health check
- commit consumer offsets to checkpoint consumption progress
- commit offsets
- list topics
- bridge health
- get topic partitions
- poll for messages
- subscribe consumer to topics
- message production
- produce messages to a topic
- list all available kafka topics in the cluster
- kafka
- create consumer
- consumer subscriptions
- list the topics a consumer is subscribed to
- create a kafka consumer instance in a consumer group for message consumption
- list all available kafka topics
- topic partition metadata
- list subscriptions
- operator
- list consumer subscriptions
- send messages to a kafka topic (supports key, value, headers, and partition targeting)
- kubernetes
- subscribe
- messaging
slug: kafka-messaging
source_filename: kafka-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Strimzi Kafka Messaging\"\n  description: >-\n    Unified capability for Kafka messaging via the Strimzi Kafka Bridge REST API.\n    Designed for application developers and platform engineers who need to produce\n    and consume Kafka messages without a native Kafka client, manage consumer\n    group subscriptions, and query topic metadata. Ideal for HTTP microservices,\n    serverless functions, and legacy applications integrating with Kafka.\n  tags:\n    - Kafka\n    - Kubernetes\n    - Messaging\n    - Operator\n    - Streaming\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      KAFKA_BRIDGE_URL: KAFKA_BRIDGE_URL\n\ncapability:\n  consumes:\n    - import: kafka-bridge\n      location: ./shared/kafka-bridge-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: strimzi-kafka-messaging-api\n      description: \"Unified REST API for Kafka messaging via Strimzi\
  \ Kafka Bridge.\"\n      resources:\n        - path: /v1/topics\n          name: topics\n          description: \"Kafka topic listing\"\n          operations:\n            - method: GET\n              name: list-topics\n              description: \"List all available Kafka topics\"\n              call: \"kafka-bridge.list-topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/topics/{topicname}/partitions\n          name: topic-partitions\n          description: \"Topic partition metadata\"\n          operations:\n            - method: GET\n              name: list-partitions\n              description: \"Get partition metadata for a topic\"\n              call: \"kafka-bridge.list-partitions\"\n              with:\n                topicname: \"rest.topicname\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/topics/{topicname}/messages\n  \
  \        name: topic-messages\n          description: \"Message production\"\n          operations:\n            - method: POST\n              name: produce-messages\n              description: \"Produce messages to a topic\"\n              call: \"kafka-bridge.send\"\n              with:\n                topicname: \"rest.topicname\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumers/{groupid}\n          name: consumers\n          description: \"Consumer group management\"\n          operations:\n            - method: POST\n              name: create-consumer\n              description: \"Create a consumer instance\"\n              call: \"kafka-bridge.create-consumer\"\n              with:\n                groupid: \"rest.groupid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumers/{groupid}/instances/{name}/subscription\n   \
  \       name: consumer-subscriptions\n          description: \"Consumer subscriptions\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List consumer subscriptions\"\n              call: \"kafka-bridge.list-subscriptions\"\n              with:\n                groupid: \"rest.groupid\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: subscribe\n              description: \"Subscribe consumer to topics\"\n              call: \"kafka-bridge.subscribe\"\n              with:\n                groupid: \"rest.groupid\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumers/{groupid}/instances/{name}/records\n          name: consumer-records\n          description: \"Message consumption\"\
  \n          operations:\n            - method: GET\n              name: poll-messages\n              description: \"Poll for messages\"\n              call: \"kafka-bridge.poll\"\n              with:\n                groupid: \"rest.groupid\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumers/{groupid}/instances/{name}/offsets\n          name: consumer-offsets\n          description: \"Offset management\"\n          operations:\n            - method: POST\n              name: commit-offsets\n              description: \"Commit offsets\"\n              call: \"kafka-bridge.commit\"\n              with:\n                groupid: \"rest.groupid\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"Bridge health\"\n\
  \          operations:\n            - method: GET\n              name: health-check\n              description: \"Check bridge health\"\n              call: \"kafka-bridge.healthy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: strimzi-kafka-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Kafka messaging via Strimzi Kafka Bridge.\"\n      tools:\n        - name: list-topics\n          description: \"List all available Kafka topics in the cluster\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kafka-bridge.list-topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-topic-partitions\n          description: \"Get partition metadata including leader and replica info for a topic\"\n          hints:\n            readOnly: true\n         \
  \ call: \"kafka-bridge.list-partitions\"\n          with:\n            topicname: \"tools.topicname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: produce-messages\n          description: \"Send messages to a Kafka topic (supports key, value, headers, and partition targeting)\"\n          hints:\n            readOnly: false\n          call: \"kafka-bridge.send\"\n          with:\n            topicname: \"tools.topicname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-consumer\n          description: \"Create a Kafka consumer instance in a consumer group for message consumption\"\n          hints:\n            readOnly: false\n          call: \"kafka-bridge.create-consumer\"\n          with:\n            groupid: \"tools.groupid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-to-topics\n       \
  \   description: \"Subscribe a consumer to one or more Kafka topics\"\n          hints:\n            readOnly: false\n          call: \"kafka-bridge.subscribe\"\n          with:\n            groupid: \"tools.groupid\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List the topics a consumer is subscribed to\"\n          hints:\n            readOnly: true\n          call: \"kafka-bridge.list-subscriptions\"\n          with:\n            groupid: \"tools.groupid\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: poll-messages\n          description: \"Poll for messages from subscribed Kafka topics (long-poll with configurable timeout)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"kafka-bridge.poll\"\n          with:\n\
  \            groupid: \"tools.groupid\"\n            name: \"tools.name\"\n            timeout: \"tools.timeout\"\n            max_bytes: \"tools.max_bytes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: commit-offsets\n          description: \"Commit consumer offsets to checkpoint consumption progress\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"kafka-bridge.commit\"\n          with:\n            groupid: \"tools.groupid\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/strimzi/refs/heads/main/capabilities/kafka-messaging.yaml
tags:
- Kafka
- Kubernetes
- Messaging
- Operator
- Streaming
tools:
- description: List all available Kafka topics in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-topics
- description: Get partition metadata including leader and replica info for a topic
  hints:
    readOnly: true
  name: get-topic-partitions
- description: Send messages to a Kafka topic (supports key, value, headers, and partition targeting)
  hints:
    readOnly: false
  name: produce-messages
- description: Create a Kafka consumer instance in a consumer group for message consumption
  hints:
    readOnly: false
  name: create-consumer
- description: Subscribe a consumer to one or more Kafka topics
  hints:
    readOnly: false
  name: subscribe-to-topics
- description: List the topics a consumer is subscribed to
  hints:
    readOnly: true
  name: list-subscriptions
- description: Poll for messages from subscribed Kafka topics (long-poll with configurable timeout)
  hints:
    openWorld: true
    readOnly: true
  name: poll-messages
- description: Commit consumer offsets to checkpoint consumption progress
  hints:
    idempotent: true
    readOnly: false
  name: commit-offsets
---
