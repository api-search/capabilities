---
categories:
- messaging
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
- queue manager operations
- j2ee
- get queue manager
- create a new queue
- get queue
- delete a queue
- ibm mq
- list channels
- list queue managers
- get queue details
- list queues
- queue management
- microservices
- send message
- delete queue
- list channels on a queue manager
- middleware
- list available queue managers
- messaging
- cloud native
- application server
- message operations
- enterprise java
- list queues on a queue manager
- browse messages on a queue
- browse messages
- send a message to a queue
- channel management
- browse messages on a queue non-destructively
- integration
- get queue manager details
- create queue
slug: messaging-and-integration
source_filename: messaging-and-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WebSphere Messaging and Integration\"\n  description: \"Workflow for managing IBM MQ messaging infrastructure including queue management, message operations, channels, and topics for integration architects and middleware administrators.\"\n  tags:\n    - IBM MQ\n    - Messaging\n    - Integration\n    - Queue Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MQ_USERNAME: MQ_USERNAME\n      MQ_PASSWORD: MQ_PASSWORD\n\ncapability:\n  consumes:\n    - import: mq-rest\n      location: ./shared/mq-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: messaging-api\n      description: \"Unified REST API for IBM MQ messaging operations.\"\n      resources:\n        - path: /v1/queue-managers\n          name: queue-managers\n          description: \"Queue manager operations\"\n          operations:\n            - method: GET\n              name: list-queue-managers\n\
  \              description: \"List queue managers\"\n              call: \"mq-rest.list-queue-managers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-queue-manager\n              description: \"Get queue manager details\"\n              call: \"mq-rest.get-queue-manager\"\n              with:\n                qmgrName: \"rest.qmgrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queues\n          name: queues\n          description: \"Queue management\"\n          operations:\n            - method: GET\n              name: list-queues\n              description: \"List queues\"\n              call: \"mq-rest.list-queues\"\n              with:\n                qmgrName: \"rest.qmgrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n\
  \          name: messages\n          description: \"Message operations\"\n          operations:\n            - method: GET\n              name: browse-messages\n              description: \"Browse messages on a queue\"\n              call: \"mq-rest.browse-messages\"\n              with:\n                qmgrName: \"rest.qmgrName\"\n                queueName: \"rest.queueName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Channel management\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List channels\"\n              call: \"mq-rest.list-channels\"\n              with:\n                qmgrName: \"rest.qmgrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: messaging-mcp\n \
  \     transport: http\n      description: \"MCP server for AI-assisted IBM MQ messaging management.\"\n      tools:\n        - name: list-queue-managers\n          description: \"List available queue managers\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.list-queue-managers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-queue-manager\n          description: \"Get queue manager details\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.get-queue-manager\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-queues\n          description: \"List queues on a queue manager\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.list-queues\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: get-queue\n          description: \"Get queue details\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.get-queue\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n            queueName: \"tools.queueName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-queue\n          description: \"Create a new queue\"\n          hints:\n            readOnly: false\n          call: \"mq-rest.create-queue\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-queue\n          description: \"Delete a queue\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"mq-rest.delete-queue\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n            queueName: \"tools.queueName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-messages\n          description: \"Browse messages on a queue non-destructively\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.browse-messages\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n            queueName: \"tools.queueName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-message\n          description: \"Send a message to a queue\"\n          hints:\n            readOnly: false\n          call: \"mq-rest.send-message\"\n          with:\n            qmgrName: \"tools.qmgrName\"\n            queueName: \"tools.queueName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-channels\n          description: \"List channels on a queue manager\"\n          hints:\n            readOnly: true\n          call: \"mq-rest.list-channels\"\
  \n          with:\n            qmgrName: \"tools.qmgrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/messaging-and-integration.yaml
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
