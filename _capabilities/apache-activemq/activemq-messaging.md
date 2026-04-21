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
- apache
- unified messaging and monitoring capability for activemq.
- amqp
- stomp
- apache activemq
- java
- jms
- read broker metric
- monitoring
- send a message to an activemq queue or topic.
- receive message
- read a jmx mbean attribute from the activemq broker for monitoring.
- Application Developer
- produce and consume messages.
- receive a message from a queue or topic.
- monitor broker jmx attributes.
- send message
- Platform Operator
- messaging
- developers integrating applications with activemq for asynchronous messaging.
- operators monitoring and managing activemq broker health and performance.
- read a broker jmx mbean attribute.
- receive a message from an activemq queue or topic.
- message broker
- send a message to a queue or topic.
- mqtt
- broker management
- open source
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
