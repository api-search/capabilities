---
categories:
- messaging
consumed_apis:
- activemq-rest
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
- send a message to a queue or topic.
- read broker metric
- read a jmx mbean attribute from the activemq broker for monitoring.
- Platform Operator
- unified messaging and monitoring capability for activemq.
- mqtt
- messaging
- broker management
- operators monitoring and managing activemq broker health and performance.
- developers integrating applications with activemq for asynchronous messaging.
- send a message to an activemq queue or topic.
- stomp
- receive a message from a queue or topic.
- receive message
- monitor broker jmx attributes.
- produce and consume messages.
- jms
- apache
- monitoring
- message broker
- amqp
- Application Developer
- read a broker jmx mbean attribute.
- java
- receive a message from an activemq queue or topic.
- apache activemq
- open source
- send message
slug: activemq-messaging
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Apache ActiveMQ Messaging Workflow\n  description: Unified capability for Apache ActiveMQ messaging operations and \n    broker management. Used by application developers and platform operators to \n    send/receive messages and monitor broker health.\n  tags:\n  - Apache ActiveMQ\n  - Messaging\n  - Broker Management\n  - JMS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    ACTIVEMQ_USERNAME: ACTIVEMQ_USERNAME\n    ACTIVEMQ_PASSWORD: ACTIVEMQ_PASSWORD\ncapability:\n  consumes:\n  - import: activemq-rest\n    location: ./shared/activemq-rest.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: activemq-messaging-api\n    description: Unified REST API for ActiveMQ messaging and management.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Produce and consume messages.\n      operations:\n      - method: POST\n        name: send-message\n        description:\
  \ Send a message to a queue or topic.\n        call: activemq-rest.send-message\n        with:\n          destination: rest.destination\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: receive-message\n        description: Receive a message from a queue or topic.\n        call: activemq-rest.receive-message\n        with:\n          destination: rest.destination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/management/mbeans/{mbean}\n      name: management\n      description: Monitor broker JMX attributes.\n      operations:\n      - method: GET\n        name: read-broker-metric\n        description: Read a broker JMX MBean attribute.\n        call: activemq-rest.read-mbean\n        with:\n          mbean: rest.mbean\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: activemq-messaging-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted ActiveMQ messaging and monitoring.\n    tools:\n    - name: send-message\n      description: Send a message to an ActiveMQ queue or topic.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: activemq-rest.send-message\n      with:\n        destination: tools.destination\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: receive-message\n      description: Receive a message from an ActiveMQ queue or topic.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: activemq-rest.receive-message\n      with:\n        destination: tools.destination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-broker-metric\n      description: Read a JMX MBean attribute from the ActiveMQ broker for \n        monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: activemq-rest.read-mbean\n\
  \      with:\n        mbean: tools.mbean\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
