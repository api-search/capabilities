---
categories:
- messaging
consumed_apis: []
description: Message queuing workflow for managing SQS queues, sending and receiving messages, batch operations, dead-letter queue management, and access control. Used by developers and DevOps engineers for microservices decoupling and asynchronous processing.
layout: capability
name: Amazon SQS Message Queuing
operations:
- description: List all SQS queues
  method: GET
  name: list-queues
  path: /v1/queues
- description: Create a new SQS queue
  method: POST
  name: create-queue
  path: /v1/queues
- description: Send a message to a queue
  method: POST
  name: send-message
  path: /v1/messages
- description: List dead-letter queue source queues
  method: GET
  name: list-dlq-sources
  path: /v1/dead-letter-queues
personas: []
provider_name: Amazon SQS
provider_slug: amazon-sqs
search_terms:
- create a new standard or fifo queue
- get the url of a queue by name
- delete message
- start moving messages from a dead-letter queue
- create queue
- distributed systems
- add permission
- delete a message from a queue
- get queue attributes
- start message move task
- send a message to a queue
- list queues
- message operations
- remove permission
- amazon
- queue
- delete all messages in a queue
- send message
- get attributes for a queue
- purge queue
- dead-letter queue management
- delete an sqs queue
- set attributes for a queue
- receive message
- list dead letter source queues
- list all sqs queues
- list dead-letter queue source queues
- delete message batch
- delete up to 10 messages in a batch
- list tags for a queue
- set queue attributes
- remove a permission from a queue
- list queues that feed a dead-letter queue
- queue management
- send message batch
- cloud
- add a permission to a queue
- receive messages from a queue
- change message visibility
- aws
- delete queue
- send up to 10 messages in a batch
- change the visibility timeout of a message
- create a new sqs queue
- tag queue
- list dlq sources
- add tags to a queue
- messaging
- get queue url
- list queue tags
- microservices
slug: message-queuing
source_filename: message-queuing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon SQS Message Queuing\n  description: Message queuing workflow for managing SQS queues, sending and receiving messages, batch operations, dead-letter\n    queue management, and access control. Used by developers and DevOps engineers for microservices decoupling and asynchronous\n    processing.\n  tags:\n  - Amazon\n  - AWS\n  - Messaging\n  - Queue\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-sqs\n    baseUri: https://sqs.us-east-1.amazonaws.com\n    description: Amazon SQS message queuing service\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: queues\n      path: /\n      description: Queue management\
  \ operations\n      operations:\n      - name: create-queue\n        method: POST\n        description: Create a new standard or FIFO queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Action: CreateQueue\n            QueueName: '{{tools.queue_name}}'\n      - name: delete-queue\n        method: POST\n        description: Delete an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-queues\n        method: POST\n        description: List all SQS queues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-queue-url\n        method: POST\n        description: Get the URL of an existing queue by name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-queue-attributes\n        method: POST\n        description: Get attributes for an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-queue-attributes\n        method: POST\n        description: Set attributes for an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: purge-queue\n        method: POST\n        description: Delete all messages in a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /\n      description: Message operations\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to an SQS queue\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: receive-message\n        method: POST\n        description: Receive messages from an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message\n        method: POST\n        description: Delete a message from a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message-batch\n        method: POST\n        description: Send up to 10 messages to a queue in a single batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message-batch\n        method: POST\n        description: Delete up to 10 messages from a queue in a single batch\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: change-message-visibility\n        method: POST\n        description: Change the visibility timeout of a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /\n      description: Queue tagging operations\n      operations:\n      - name: list-queue-tags\n        method: POST\n        description: List tags for an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tag-queue\n        method: POST\n        description: Add tags to an SQS queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untag-queue\n        method: POST\n        description: Remove tags from an SQS queue\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dead-letter\n      path: /\n      description: Dead-letter queue operations\n      operations:\n      - name: list-dead-letter-source-queues\n        method: POST\n        description: List queues that have a dead-letter queue configured\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-message-move-task\n        method: POST\n        description: Start moving messages from a dead-letter queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-message-move-tasks\n        method: POST\n        description: List message move tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \  - name: cancel-message-move-task\n        method: POST\n        description: Cancel a running message move task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions\n      path: /\n      description: Queue permission operations\n      operations:\n      - name: add-permission\n        method: POST\n        description: Add a permission to a queue for a specific principal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-permission\n        method: POST\n        description: Remove a permission from a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sqs-queuing-api\n    description: Unified REST API for Amazon SQS message queuing operations.\n    resources:\n\
  \    - path: /v1/queues\n      name: queues\n      description: Queue management\n      operations:\n      - method: GET\n        name: list-queues\n        description: List all SQS queues\n        call: amazon-sqs.list-queues\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-queue\n        description: Create a new SQS queue\n        call: amazon-sqs.create-queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Message operations\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a message to a queue\n        call: amazon-sqs.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dead-letter-queues\n      name: dead-letter\n      description: Dead-letter queue management\n      operations:\n      - method: GET\n        name: list-dlq-sources\n\
  \        description: List dead-letter queue source queues\n        call: amazon-sqs.list-dead-letter-source-queues\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sqs-queuing-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon SQS message queuing.\n    tools:\n    - name: list-queues\n      description: List all SQS queues\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-sqs.list-queues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-queue\n      description: Create a new standard or FIFO queue\n      hints:\n        readOnly: false\n      call: amazon-sqs.create-queue\n      with:\n        queue_name: tools.queue_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-queue\n      description: Delete an SQS queue\n      hints:\n        destructive: true\n      call: amazon-sqs.delete-queue\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-queue-url\n      description: Get the URL of a queue by name\n      hints:\n        readOnly: true\n      call: amazon-sqs.get-queue-url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-queue-attributes\n      description: Get attributes for a queue\n      hints:\n        readOnly: true\n      call: amazon-sqs.get-queue-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-queue-attributes\n      description: Set attributes for a queue\n      hints:\n        readOnly: false\n        idempotent: true\n      call: amazon-sqs.set-queue-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purge-queue\n      description: Delete all messages in a queue\n      hints:\n        destructive: true\n      call: amazon-sqs.purge-queue\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: send-message\n      description: Send a message to a queue\n      hints:\n        readOnly: false\n      call: amazon-sqs.send-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: receive-message\n      description: Receive messages from a queue\n      hints:\n        readOnly: true\n      call: amazon-sqs.receive-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-message\n      description: Delete a message from a queue\n      hints:\n        destructive: true\n      call: amazon-sqs.delete-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-message-batch\n      description: Send up to 10 messages in a batch\n      hints:\n        readOnly: false\n      call: amazon-sqs.send-message-batch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-message-batch\n      description: Delete up to 10 messages in a batch\n     \
  \ hints:\n        destructive: true\n      call: amazon-sqs.delete-message-batch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: change-message-visibility\n      description: Change the visibility timeout of a message\n      hints:\n        readOnly: false\n        idempotent: true\n      call: amazon-sqs.change-message-visibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dead-letter-source-queues\n      description: List queues that feed a dead-letter queue\n      hints:\n        readOnly: true\n      call: amazon-sqs.list-dead-letter-source-queues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-message-move-task\n      description: Start moving messages from a dead-letter queue\n      hints:\n        readOnly: false\n      call: amazon-sqs.start-message-move-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queue-tags\n      description:\
  \ List tags for a queue\n      hints:\n        readOnly: true\n      call: amazon-sqs.list-queue-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tag-queue\n      description: Add tags to a queue\n      hints:\n        readOnly: false\n      call: amazon-sqs.tag-queue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-permission\n      description: Add a permission to a queue\n      hints:\n        readOnly: false\n      call: amazon-sqs.add-permission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-permission\n      description: Remove a permission from a queue\n      hints:\n        destructive: true\n      call: amazon-sqs.remove-permission\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-sqs/refs/heads/main/capabilities/message-queuing.yaml
tags:
- Amazon
- Messaging
- Queue
tools:
- description: List all SQS queues
  hints:
    openWorld: true
    readOnly: true
  name: list-queues
- description: Create a new standard or FIFO queue
  hints:
    readOnly: false
  name: create-queue
- description: Delete an SQS queue
  hints:
    destructive: true
  name: delete-queue
- description: Get the URL of a queue by name
  hints:
    readOnly: true
  name: get-queue-url
- description: Get attributes for a queue
  hints:
    readOnly: true
  name: get-queue-attributes
- description: Set attributes for a queue
  hints:
    idempotent: true
    readOnly: false
  name: set-queue-attributes
- description: Delete all messages in a queue
  hints:
    destructive: true
  name: purge-queue
- description: Send a message to a queue
  hints:
    readOnly: false
  name: send-message
- description: Receive messages from a queue
  hints:
    readOnly: true
  name: receive-message
- description: Delete a message from a queue
  hints:
    destructive: true
  name: delete-message
- description: Send up to 10 messages in a batch
  hints:
    readOnly: false
  name: send-message-batch
- description: Delete up to 10 messages in a batch
  hints:
    destructive: true
  name: delete-message-batch
- description: Change the visibility timeout of a message
  hints:
    idempotent: true
    readOnly: false
  name: change-message-visibility
- description: List queues that feed a dead-letter queue
  hints:
    readOnly: true
  name: list-dead-letter-source-queues
- description: Start moving messages from a dead-letter queue
  hints:
    readOnly: false
  name: start-message-move-task
- description: List tags for a queue
  hints:
    readOnly: true
  name: list-queue-tags
- description: Add tags to a queue
  hints:
    readOnly: false
  name: tag-queue
- description: Add a permission to a queue
  hints:
    readOnly: false
  name: add-permission
- description: Remove a permission from a queue
  hints:
    destructive: true
  name: remove-permission
---
