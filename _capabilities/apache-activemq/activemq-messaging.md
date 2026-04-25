---
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
- read a broker jmx mbean attribute.
- monitor broker jmx attributes.
- read a jmx mbean attribute from the activemq broker for monitoring.
- receive a message from an activemq queue or topic.
- operators monitoring and managing activemq broker health and performance.
- Platform Operator
- messaging
- broker management
- mqtt
- java
- stomp
- amqp
- read broker metric
- monitoring
- send a message to a queue or topic.
- open source
- apache activemq
- produce and consume messages.
- developers integrating applications with activemq for asynchronous messaging.
- receive a message from a queue or topic.
- unified messaging and monitoring capability for activemq.
- apache
- send message
- message broker
- receive message
- Application Developer
- jms
- send a message to an activemq queue or topic.
slug: activemq-messaging
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
