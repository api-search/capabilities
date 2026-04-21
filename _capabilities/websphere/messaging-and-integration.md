---
consumed_apis:
- mq-rest
description: Workflow for managing IBM MQ messaging infrastructure including queue management, message operations, channels, and topics for integration architects and middleware administrators.
layout: capability
name: WebSphere Messaging and Integration
operations:
- description: List queue managers
  method: GET
  name: list-queue-managers
  path: /v1/queue-managers
- description: Get queue manager details
  method: GET
  name: get-queue-manager
  path: /v1/queue-managers
- description: List queues
  method: GET
  name: list-queues
  path: /v1/queues
- description: Browse messages on a queue
  method: GET
  name: browse-messages
  path: /v1/messages
- description: List channels
  method: GET
  name: list-channels
  path: /v1/channels
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- get queue manager details
- list available queue managers
- application server
- list channels on a queue manager
- list channels
- delete a queue
- list queues on a queue manager
- browse messages
- channel management
- integration
- create a new queue
- microservices
- browse messages on a queue
- create queue
- ibm mq
- get queue manager
- queue manager operations
- get queue
- cloud native
- messaging
- middleware
- enterprise java
- send message
- queue management
- delete queue
- get queue details
- j2ee
- list queue managers
- list queues
- send a message to a queue
- message operations
- browse messages on a queue non-destructively
slug: messaging-and-integration
tags:
- IBM MQ
- Messaging
- Integration
- Queue Management
tools:
- description: List available queue managers
  hints:
    readOnly: true
  name: list-queue-managers
- description: Get queue manager details
  hints:
    readOnly: true
  name: get-queue-manager
- description: List queues on a queue manager
  hints:
    readOnly: true
  name: list-queues
- description: Get queue details
  hints:
    readOnly: true
  name: get-queue
- description: Create a new queue
  hints:
    readOnly: false
  name: create-queue
- description: Delete a queue
  hints:
    destructive: true
    readOnly: false
  name: delete-queue
- description: Browse messages on a queue non-destructively
  hints:
    readOnly: true
  name: browse-messages
- description: Send a message to a queue
  hints:
    readOnly: false
  name: send-message
- description: List channels on a queue manager
  hints:
    readOnly: true
  name: list-channels
---
