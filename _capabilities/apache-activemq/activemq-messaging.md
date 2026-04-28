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
- read a jmx mbean attribute from the activemq broker for monitoring.
- monitor broker jmx attributes.
- amqp
- receive message
- produce and consume messages.
- message broker
- developers integrating applications with activemq for asynchronous messaging.
- read broker metric
- receive a message from an activemq queue or topic.
- jms
- apache activemq
- send a message to an activemq queue or topic.
- apache
- stomp
- broker management
- send message
- Application Developer
- read a broker jmx mbean attribute.
- open source
- messaging
- unified messaging and monitoring capability for activemq.
- mqtt
- Platform Operator
- java
- monitoring
- operators monitoring and managing activemq broker health and performance.
- receive a message from a queue or topic.
- send a message to a queue or topic.
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
