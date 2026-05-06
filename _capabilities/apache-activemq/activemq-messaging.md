---
categories:
- messaging
consumed_apis: []
description: Unified capability for Apache ActiveMQ messaging operations and broker management. Used by application developers and platform operators to send/receive messages and monitor broker health.
layout: capability
name: Apache ActiveMQ Messaging Workflow
operations:
- description: Send a message to a queue or topic.
  method: POST
  name: send-message
  path: /v1/messages
- description: Receive a message from a queue or topic.
  method: GET
  name: receive-message
  path: /v1/messages
- description: Read a broker JMX MBean attribute.
  method: GET
  name: read-broker-metric
  path: /v1/management/mbeans/{mbean}
personas: []
provider_name: Apache ActiveMQ
provider_slug: apache-activemq
search_terms:
- java
- unified messaging and monitoring capability for activemq.
- apache activemq
- jms
- apache
- monitoring
- message broker
- receive a message from a queue or topic.
- open source
- messaging
- send a message to a queue or topic.
- broker management
- mqtt
- Platform Operator
- send message
- read a broker jmx mbean attribute.
- monitor broker jmx attributes.
- read broker metric
- developers integrating applications with activemq for asynchronous messaging.
- send a message to an activemq queue or topic.
- amqp
- receive message
- stomp
- Application Developer
- produce and consume messages.
- receive a message from an activemq queue or topic.
- read a jmx mbean attribute from the activemq broker for monitoring.
- operators monitoring and managing activemq broker health and performance.
slug: activemq-messaging
source_filename: activemq-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache ActiveMQ Messaging Workflow\n  description: Unified capability for Apache ActiveMQ messaging operations and broker management. Used by application developers\n    and platform operators to send/receive messages and monitor broker health.\n  tags:\n  - Apache ActiveMQ\n  - Messaging\n  - Broker Management\n  - JMS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACTIVEMQ_USERNAME: ACTIVEMQ_USERNAME\n    ACTIVEMQ_PASSWORD: ACTIVEMQ_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: activemq-rest\n    baseUri: http://localhost:8161/api\n    description: Apache ActiveMQ REST and Jolokia management API.\n    authentication:\n      type: basic\n      username: '{{ACTIVEMQ_USERNAME}}'\n      password: '{{ACTIVEMQ_PASSWORD}}'\n    resources:\n    - name: messages\n      path: /message\n      description: Produce and consume messages from queues and topics.\n      operations:\n  \
  \    - name: send-message\n        method: POST\n        description: Send a message to a named destination.\n        inputParameters:\n        - name: destination\n          in: path\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: receive-message\n        method: GET\n        description: Receive a message from a named destination.\n        inputParameters:\n        - name: destination\n          in: path\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: oneShot\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: management\n      path: /jolokia\n      description: Jolokia JMX-HTTP bridge for broker management.\n      operations:\n      - name: read-mbean\n        method: GET\n        description: Read JMX MBean attributes for broker monitoring.\n        inputParameters:\n        - name: mbean\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: activemq-messaging-api\n    description: Unified REST API for ActiveMQ messaging and management.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Produce and consume messages.\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a message to a queue or topic.\n        call: activemq-rest.send-message\n        with:\n          destination: rest.destination\n\
  \          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: receive-message\n        description: Receive a message from a queue or topic.\n        call: activemq-rest.receive-message\n        with:\n          destination: rest.destination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/management/mbeans/{mbean}\n      name: management\n      description: Monitor broker JMX attributes.\n      operations:\n      - method: GET\n        name: read-broker-metric\n        description: Read a broker JMX MBean attribute.\n        call: activemq-rest.read-mbean\n        with:\n          mbean: rest.mbean\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: activemq-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted ActiveMQ messaging and monitoring.\n    tools:\n    - name: send-message\n\
  \      description: Send a message to an ActiveMQ queue or topic.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: activemq-rest.send-message\n      with:\n        destination: tools.destination\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: receive-message\n      description: Receive a message from an ActiveMQ queue or topic.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: activemq-rest.receive-message\n      with:\n        destination: tools.destination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-broker-metric\n      description: Read a JMX MBean attribute from the ActiveMQ broker for monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activemq-rest.read-mbean\n      with:\n        mbean: tools.mbean\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-activemq/refs/heads/main/capabilities/activemq-messaging.yaml
tags:
- Apache ActiveMQ
- Messaging
- Broker Management
- JMS
tools:
- description: Send a message to an ActiveMQ queue or topic.
  hints:
    openWorld: false
    readOnly: false
  name: send-message
- description: Receive a message from an ActiveMQ queue or topic.
  hints:
    openWorld: false
    readOnly: true
  name: receive-message
- description: Read a JMX MBean attribute from the ActiveMQ broker for monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: read-broker-metric
---
