---
categories: []
consumed_apis: []
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
- kafka topic listing
- commit consumer offsets to checkpoint consumption progress
- create a consumer instance
- list topics
- list all available kafka topics in the cluster
- produce messages to a topic
- message consumption
- poll messages
- send messages to a kafka topic (supports key, value, headers, and partition targeting)
- message production
- offset management
- list all available kafka topics
- create a kafka consumer instance in a consumer group for message consumption
- kubernetes
- topic partition metadata
- list subscriptions
- create consumer
- get partition metadata including leader and replica info for a topic
- subscribe a consumer to one or more kafka topics
- list the topics a consumer is subscribed to
- consumer group management
- subscribe
- messaging
- get partition metadata for a topic
- check bridge health
- poll for messages
- list consumer subscriptions
- get topic partitions
- poll for messages from subscribed kafka topics (long-poll with configurable timeout)
- operator
- subscribe consumer to topics
- bridge health
- health check
- list partitions
- streaming
- consumer subscriptions
- commit offsets
- kafka
- subscribe to topics
- produce messages
slug: kafka-messaging
source_filename: kafka-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Strimzi Kafka Messaging\n  description: Unified capability for Kafka messaging via the Strimzi Kafka Bridge REST API. Designed for application developers\n    and platform engineers who need to produce and consume Kafka messages without a native Kafka client, manage consumer group\n    subscriptions, and query topic metadata. Ideal for HTTP microservices, serverless functions, and legacy applications integrating\n    with Kafka.\n  tags:\n  - Kafka\n  - Kubernetes\n  - Messaging\n  - Operator\n  - Streaming\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KAFKA_BRIDGE_URL: KAFKA_BRIDGE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: kafka-bridge\n    baseUri: '{{KAFKA_BRIDGE_URL}}'\n    description: Strimzi Kafka Bridge REST API\n    resources:\n    - name: topic-producer\n      path: /topics/{topicname}\n      description: Produce messages to a Kafka topic\n      operations:\n  \
  \    - name: send\n        method: POST\n        description: Send messages to a Kafka topic\n        inputParameters:\n        - name: topicname\n          in: path\n          type: string\n          required: true\n          description: The Kafka topic name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n    - name: consumer-group\n      path: /consumers/{groupid}\n      description: Consumer group management\n      operations:\n      - name: create-consumer\n        method: POST\n        description: Create a Kafka consumer instance\n        inputParameters:\n        - name: groupid\n          in: path\n          type: string\n          required: true\n          description: The consumer group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            format: '{{tools.format}}'\n            auto.offset.reset: '{{tools.autoOffsetReset}}'\n    - name: consumer-subscription\n      path: /consumers/{groupid}/instances/{name}/subscription\n      description: Consumer topic subscriptions\n      operations:\n      - name: subscribe\n        method: POST\n        description: Subscribe consumer to topics\n        inputParameters:\n        - name: groupid\n          in: path\n          type: string\n          required: true\n          description: The consumer group ID\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The consumer instance name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            topics: '{{tools.topics}}'\n\
  \      - name: list-subscriptions\n        method: GET\n        description: List consumer's topic subscriptions\n        inputParameters:\n        - name: groupid\n          in: path\n          type: string\n          required: true\n          description: The consumer group ID\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The consumer instance name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumer-records\n      path: /consumers/{groupid}/instances/{name}/records\n      description: Consumer message polling\n      operations:\n      - name: poll\n        method: GET\n        description: Poll for messages from subscribed topics\n        inputParameters:\n        - name: groupid\n          in: path\n          type: string\n          required: true\n          description: The consumer group ID\n        - name: name\n  \
  \        in: path\n          type: string\n          required: true\n          description: The consumer instance name\n        - name: timeout\n          in: query\n          type: integer\n          required: false\n          description: Poll timeout in milliseconds\n        - name: max_bytes\n          in: query\n          type: integer\n          required: false\n          description: Maximum response bytes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumer-offsets\n      path: /consumers/{groupid}/instances/{name}/offsets\n      description: Offset commit\n      operations:\n      - name: commit\n        method: POST\n        description: Commit consumer offsets\n        inputParameters:\n        - name: groupid\n          in: path\n          type: string\n          required: true\n          description: The consumer group ID\n        - name: name\n          in: path\n          type:\
  \ string\n          required: true\n          description: The consumer instance name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            offsets: '{{tools.offsets}}'\n    - name: topics\n      path: /topics\n      description: Topic listing\n      operations:\n      - name: list-topics\n        method: GET\n        description: List all Kafka topics\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topic-partitions\n      path: /topics/{topicname}/partitions\n      description: Topic partition metadata\n      operations:\n      - name: list-partitions\n        method: GET\n        description: Get partition metadata for a topic\n        inputParameters:\n        - name: topicname\n          in: path\n          type: string\n   \
  \       required: true\n          description: The Kafka topic name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /healthy\n      description: Bridge health check\n      operations:\n      - name: healthy\n        method: GET\n        description: Check if the Bridge is healthy\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: strimzi-kafka-messaging-api\n    description: Unified REST API for Kafka messaging via Strimzi Kafka Bridge.\n    resources:\n    - path: /v1/topics\n      name: topics\n      description: Kafka topic listing\n      operations:\n      - method: GET\n        name: list-topics\n        description: List all available Kafka topics\n        call: kafka-bridge.list-topics\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/topics/{topicname}/partitions\n      name: topic-partitions\n      description: Topic partition metadata\n      operations:\n      - method: GET\n        name: list-partitions\n        description: Get partition metadata for a topic\n        call: kafka-bridge.list-partitions\n        with:\n          topicname: rest.topicname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topics/{topicname}/messages\n      name: topic-messages\n      description: Message production\n      operations:\n      - method: POST\n        name: produce-messages\n        description: Produce messages to a topic\n        call: kafka-bridge.send\n        with:\n          topicname: rest.topicname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumers/{groupid}\n      name: consumers\n      description: Consumer group management\n      operations:\n      - method:\
  \ POST\n        name: create-consumer\n        description: Create a consumer instance\n        call: kafka-bridge.create-consumer\n        with:\n          groupid: rest.groupid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumers/{groupid}/instances/{name}/subscription\n      name: consumer-subscriptions\n      description: Consumer subscriptions\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List consumer subscriptions\n        call: kafka-bridge.list-subscriptions\n        with:\n          groupid: rest.groupid\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: subscribe\n        description: Subscribe consumer to topics\n        call: kafka-bridge.subscribe\n        with:\n          groupid: rest.groupid\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/consumers/{groupid}/instances/{name}/records\n      name: consumer-records\n      description: Message consumption\n      operations:\n      - method: GET\n        name: poll-messages\n        description: Poll for messages\n        call: kafka-bridge.poll\n        with:\n          groupid: rest.groupid\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumers/{groupid}/instances/{name}/offsets\n      name: consumer-offsets\n      description: Offset management\n      operations:\n      - method: POST\n        name: commit-offsets\n        description: Commit offsets\n        call: kafka-bridge.commit\n        with:\n          groupid: rest.groupid\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Bridge health\n      operations:\n      - method: GET\n        name: health-check\n  \
  \      description: Check bridge health\n        call: kafka-bridge.healthy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: strimzi-kafka-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted Kafka messaging via Strimzi Kafka Bridge.\n    tools:\n    - name: list-topics\n      description: List all available Kafka topics in the cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kafka-bridge.list-topics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topic-partitions\n      description: Get partition metadata including leader and replica info for a topic\n      hints:\n        readOnly: true\n      call: kafka-bridge.list-partitions\n      with:\n        topicname: tools.topicname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: produce-messages\n      description: Send messages to a Kafka\
  \ topic (supports key, value, headers, and partition targeting)\n      hints:\n        readOnly: false\n      call: kafka-bridge.send\n      with:\n        topicname: tools.topicname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-consumer\n      description: Create a Kafka consumer instance in a consumer group for message consumption\n      hints:\n        readOnly: false\n      call: kafka-bridge.create-consumer\n      with:\n        groupid: tools.groupid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe-to-topics\n      description: Subscribe a consumer to one or more Kafka topics\n      hints:\n        readOnly: false\n      call: kafka-bridge.subscribe\n      with:\n        groupid: tools.groupid\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List the topics a consumer is subscribed to\n      hints:\n \
  \       readOnly: true\n      call: kafka-bridge.list-subscriptions\n      with:\n        groupid: tools.groupid\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: poll-messages\n      description: Poll for messages from subscribed Kafka topics (long-poll with configurable timeout)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kafka-bridge.poll\n      with:\n        groupid: tools.groupid\n        name: tools.name\n        timeout: tools.timeout\n        max_bytes: tools.max_bytes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: commit-offsets\n      description: Commit consumer offsets to checkpoint consumption progress\n      hints:\n        readOnly: false\n        idempotent: true\n      call: kafka-bridge.commit\n      with:\n        groupid: tools.groupid\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
