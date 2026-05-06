---
categories:
- messaging
consumed_apis: []
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
- integration
- j2ee
- list available queue managers
- browse messages
- get queue manager
- middleware
- create queue
- list queues
- channel management
- cloud native
- messaging
- queue management
- get queue
- delete a queue
- list queues on a queue manager
- send message
- create a new queue
- delete queue
- list queue managers
- browse messages on a queue
- list channels
- application server
- list channels on a queue manager
- ibm mq
- send a message to a queue
- browse messages on a queue non-destructively
- get queue details
- message operations
- queue manager operations
- microservices
- enterprise java
slug: messaging-and-integration
source_filename: messaging-and-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WebSphere Messaging and Integration\n  description: Workflow for managing IBM MQ messaging infrastructure including queue management, message operations, channels,\n    and topics for integration architects and middleware administrators.\n  tags:\n  - IBM MQ\n  - Messaging\n  - Integration\n  - Queue Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MQ_USERNAME: MQ_USERNAME\n    MQ_PASSWORD: MQ_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: mq-rest\n    baseUri: https://localhost:9443/ibmmq/rest/v2\n    description: IBM MQ REST API for messaging and administration\n    authentication:\n      type: basic\n      username: '{{MQ_USERNAME}}'\n      password: '{{MQ_PASSWORD}}'\n    resources:\n    - name: queue-managers\n      path: /admin/qmgr\n      description: Queue manager administration\n      operations:\n      - name: list-queue-managers\n        method: GET\n \
  \       description: List queue managers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-queue-manager\n        method: GET\n        description: Get queue manager details\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /admin/qmgr/{qmgrName}/queue\n      description: Queue administration\n      operations:\n      - name: list-queues\n        method: GET\n        description: List queues on a queue manager\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: name\n          in: query\n     \
  \     type: string\n          required: false\n          description: Queue name filter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Queue type filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new queue\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: get-queue\n        method: GET\n        description: Get queue details\n        inputParameters:\n        - name: qmgrName\n\
  \          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-queue\n        method: DELETE\n        description: Delete a queue\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /messaging/qmgr/{qmgrName}/queue/{queueName}/message\n      description: Message\
  \ operations\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to a queue\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: browse-messages\n        method: GET\n        description: Browse messages on a queue\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        - name: limit\n          in: query\n  \
  \        type: integer\n          required: false\n          description: Maximum messages to browse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: receive-message\n        method: DELETE\n        description: Destructively get a message from a queue\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /admin/qmgr/{qmgrName}/channel\n      description: Channel administration\n      operations:\n      - name: list-channels\n        method: GET\n        description: List channels\n        inputParameters:\n\
  \        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-channel\n        method: POST\n        description: Create a channel\n        inputParameters:\n        - name: qmgrName\n          in: path\n          type: string\n          required: true\n          description: Queue manager name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: messaging-api\n    description: Unified REST API for IBM MQ messaging operations.\n    resources:\n    - path: /v1/queue-managers\n      name: queue-managers\n     \
  \ description: Queue manager operations\n      operations:\n      - method: GET\n        name: list-queue-managers\n        description: List queue managers\n        call: mq-rest.list-queue-managers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-queue-manager\n        description: Get queue manager details\n        call: mq-rest.get-queue-manager\n        with:\n          qmgrName: rest.qmgrName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Queue management\n      operations:\n      - method: GET\n        name: list-queues\n        description: List queues\n        call: mq-rest.list-queues\n        with:\n          qmgrName: rest.qmgrName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Message operations\n      operations:\n      - method:\
  \ GET\n        name: browse-messages\n        description: Browse messages on a queue\n        call: mq-rest.browse-messages\n        with:\n          qmgrName: rest.qmgrName\n          queueName: rest.queueName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Channel management\n      operations:\n      - method: GET\n        name: list-channels\n        description: List channels\n        call: mq-rest.list-channels\n        with:\n          qmgrName: rest.qmgrName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted IBM MQ messaging management.\n    tools:\n    - name: list-queue-managers\n      description: List available queue managers\n      hints:\n        readOnly: true\n      call: mq-rest.list-queue-managers\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: get-queue-manager\n      description: Get queue manager details\n      hints:\n        readOnly: true\n      call: mq-rest.get-queue-manager\n      with:\n        qmgrName: tools.qmgrName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List queues on a queue manager\n      hints:\n        readOnly: true\n      call: mq-rest.list-queues\n      with:\n        qmgrName: tools.qmgrName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-queue\n      description: Get queue details\n      hints:\n        readOnly: true\n      call: mq-rest.get-queue\n      with:\n        qmgrName: tools.qmgrName\n        queueName: tools.queueName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-queue\n      description: Create a new queue\n      hints:\n        readOnly: false\n      call: mq-rest.create-queue\n      with:\n\
  \        qmgrName: tools.qmgrName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-queue\n      description: Delete a queue\n      hints:\n        readOnly: false\n        destructive: true\n      call: mq-rest.delete-queue\n      with:\n        qmgrName: tools.qmgrName\n        queueName: tools.queueName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-messages\n      description: Browse messages on a queue non-destructively\n      hints:\n        readOnly: true\n      call: mq-rest.browse-messages\n      with:\n        qmgrName: tools.qmgrName\n        queueName: tools.queueName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-message\n      description: Send a message to a queue\n      hints:\n        readOnly: false\n      call: mq-rest.send-message\n      with:\n        qmgrName: tools.qmgrName\n        queueName: tools.queueName\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-channels\n      description: List channels on a queue manager\n      hints:\n        readOnly: true\n      call: mq-rest.list-channels\n      with:\n        qmgrName: tools.qmgrName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
