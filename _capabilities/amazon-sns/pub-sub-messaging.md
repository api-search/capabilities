---
categories:
- messaging
consumed_apis: []
description: Pub/sub messaging workflow combining topic management, subscription lifecycle, message publishing, mobile push, and SMS operations. Used by developers and platform engineers for event-driven architectures and notification systems.
layout: capability
name: Amazon SNS Pub/Sub Messaging
operations:
- description: List all SNS topics
  method: GET
  name: list-topics
  path: /v1/topics
- description: Create a new SNS topic
  method: POST
  name: create-topic
  path: /v1/topics
- description: List all subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Create a subscription
  method: POST
  name: subscribe
  path: /v1/subscriptions
- description: Publish a message to a topic
  method: POST
  name: publish
  path: /v1/messages
personas: []
provider_name: Amazon SNS
provider_slug: amazon-sns
search_terms:
- create a new sns topic
- get attributes of an sns topic
- aws
- set topic attributes
- push notifications
- get attributes of a subscription
- list topics
- amazon
- create a subscription to a topic
- publish up to 10 messages in a batch
- list tags for an sns resource
- create topic
- add tags to an sns resource
- unsubscribe from a topic
- create platform application
- get topic attributes
- get subscription attributes
- publish
- list subscriptions for a specific topic
- set attributes on an sns topic
- unsubscribe
- pub/sub
- get sms attributes
- check phone opted out
- list all subscriptions
- sms
- list subscriptions
- publish batch
- delete topic
- publish a message to a topic
- subscribe
- publish a message to a topic or endpoint
- messaging
- get sms messaging attributes
- create a subscription
- create a platform application for mobile push
- tag resource
- subscription management
- list tags
- list all sns topics
- notifications
- message publishing
- email
- delete an sns topic
- check if a phone number has opted out of sms
- topic management
- list subscriptions by topic
slug: pub-sub-messaging
source_filename: pub-sub-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon SNS Pub/Sub Messaging\n  description: Pub/sub messaging workflow combining topic management, subscription lifecycle, message publishing, mobile push,\n    and SMS operations. Used by developers and platform engineers for event-driven architectures and notification systems.\n  tags:\n  - Amazon\n  - AWS\n  - Messaging\n  - Notifications\n  - Pub/Sub\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-sns\n    baseUri: https://sns.us-east-1.amazonaws.com\n    description: Amazon SNS pub/sub messaging service\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: topics\n      path: /\n      description: Topic management\
  \ operations\n      operations:\n      - name: create-topic\n        method: POST\n        description: Create a new SNS topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-topic\n        method: POST\n        description: Delete an SNS topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-topics\n        method: POST\n        description: List all SNS topics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-topic-attributes\n        method: POST\n        description: Get attributes of an SNS topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-topic-attributes\n        method: POST\n        description:\
  \ Set attributes on an SNS topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /\n      description: Subscription lifecycle operations\n      operations:\n      - name: subscribe\n        method: POST\n        description: Create a subscription to a topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: confirm-subscription\n        method: POST\n        description: Confirm a pending subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unsubscribe\n        method: POST\n        description: Unsubscribe from a topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-subscriptions\n\
  \        method: POST\n        description: List all subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-subscriptions-by-topic\n        method: POST\n        description: List subscriptions for a specific topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-subscription-attributes\n        method: POST\n        description: Get attributes of a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-subscription-attributes\n        method: POST\n        description: Set attributes on a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publishing\n      path: /\n      description:\
  \ Message publishing operations\n      operations:\n      - name: publish\n        method: POST\n        description: Publish a message to a topic or directly to an endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-batch\n        method: POST\n        description: Publish up to 10 messages in a single batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /\n      description: Resource tagging operations\n      operations:\n      - name: tag-resource\n        method: POST\n        description: Add tags to an SNS resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untag-resource\n        method: POST\n        description: Remove tags from an SNS resource\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-tags-for-resource\n        method: POST\n        description: List tags for an SNS resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: platform-applications\n      path: /\n      description: Mobile push platform application operations\n      operations:\n      - name: create-platform-application\n        method: POST\n        description: Create a platform application for mobile push\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sms\n      path: /\n      description: SMS operations\n      operations:\n      - name: get-sms-attributes\n        method: POST\n        description: Get SMS messaging attributes\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: check-if-phone-number-is-opted-out\n        method: POST\n        description: Check if a phone number has opted out of SMS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sns-pubsub-api\n    description: Unified REST API for Amazon SNS pub/sub messaging.\n    resources:\n    - path: /v1/topics\n      name: topics\n      description: Topic management\n      operations:\n      - method: GET\n        name: list-topics\n        description: List all SNS topics\n        call: amazon-sns.list-topics\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-topic\n        description: Create a new SNS topic\n        call: amazon-sns.create-topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/subscriptions\n      name: subscriptions\n      description: Subscription management\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List all subscriptions\n        call: amazon-sns.list-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: subscribe\n        description: Create a subscription\n        call: amazon-sns.subscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Message publishing\n      operations:\n      - method: POST\n        name: publish\n        description: Publish a message to a topic\n        call: amazon-sns.publish\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sns-pubsub-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon SNS pub/sub messaging.\n\
  \    tools:\n    - name: list-topics\n      description: List all SNS topics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-sns.list-topics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-topic\n      description: Create a new SNS topic\n      hints:\n        readOnly: false\n      call: amazon-sns.create-topic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-topic\n      description: Delete an SNS topic\n      hints:\n        destructive: true\n      call: amazon-sns.delete-topic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topic-attributes\n      description: Get attributes of an SNS topic\n      hints:\n        readOnly: true\n      call: amazon-sns.get-topic-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-topic-attributes\n      description: Set attributes on an SNS topic\n      hints:\n\
  \        readOnly: false\n        idempotent: true\n      call: amazon-sns.set-topic-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe\n      description: Create a subscription to a topic\n      hints:\n        readOnly: false\n      call: amazon-sns.subscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unsubscribe\n      description: Unsubscribe from a topic\n      hints:\n        destructive: true\n      call: amazon-sns.unsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List all subscriptions\n      hints:\n        readOnly: true\n      call: amazon-sns.list-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions-by-topic\n      description: List subscriptions for a specific topic\n      hints:\n        readOnly: true\n      call: amazon-sns.list-subscriptions-by-topic\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subscription-attributes\n      description: Get attributes of a subscription\n      hints:\n        readOnly: true\n      call: amazon-sns.get-subscription-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish\n      description: Publish a message to a topic or endpoint\n      hints:\n        readOnly: false\n      call: amazon-sns.publish\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-batch\n      description: Publish up to 10 messages in a batch\n      hints:\n        readOnly: false\n      call: amazon-sns.publish-batch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-platform-application\n      description: Create a platform application for mobile push\n      hints:\n        readOnly: false\n      call: amazon-sns.create-platform-application\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: get-sms-attributes\n      description: Get SMS messaging attributes\n      hints:\n        readOnly: true\n      call: amazon-sns.get-sms-attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-phone-opted-out\n      description: Check if a phone number has opted out of SMS\n      hints:\n        readOnly: true\n      call: amazon-sns.check-if-phone-number-is-opted-out\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: List tags for an SNS resource\n      hints:\n        readOnly: true\n      call: amazon-sns.list-tags-for-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tag-resource\n      description: Add tags to an SNS resource\n      hints:\n        readOnly: false\n      call: amazon-sns.tag-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-sns/refs/heads/main/capabilities/pub-sub-messaging.yaml
tags:
- Amazon
- Messaging
- Notifications
- Pub/Sub
tools:
- description: List all SNS topics
  hints:
    openWorld: true
    readOnly: true
  name: list-topics
- description: Create a new SNS topic
  hints:
    readOnly: false
  name: create-topic
- description: Delete an SNS topic
  hints:
    destructive: true
  name: delete-topic
- description: Get attributes of an SNS topic
  hints:
    readOnly: true
  name: get-topic-attributes
- description: Set attributes on an SNS topic
  hints:
    idempotent: true
    readOnly: false
  name: set-topic-attributes
- description: Create a subscription to a topic
  hints:
    readOnly: false
  name: subscribe
- description: Unsubscribe from a topic
  hints:
    destructive: true
  name: unsubscribe
- description: List all subscriptions
  hints:
    readOnly: true
  name: list-subscriptions
- description: List subscriptions for a specific topic
  hints:
    readOnly: true
  name: list-subscriptions-by-topic
- description: Get attributes of a subscription
  hints:
    readOnly: true
  name: get-subscription-attributes
- description: Publish a message to a topic or endpoint
  hints:
    readOnly: false
  name: publish
- description: Publish up to 10 messages in a batch
  hints:
    readOnly: false
  name: publish-batch
- description: Create a platform application for mobile push
  hints:
    readOnly: false
  name: create-platform-application
- description: Get SMS messaging attributes
  hints:
    readOnly: true
  name: get-sms-attributes
- description: Check if a phone number has opted out of SMS
  hints:
    readOnly: true
  name: check-phone-opted-out
- description: List tags for an SNS resource
  hints:
    readOnly: true
  name: list-tags
- description: Add tags to an SNS resource
  hints:
    readOnly: false
  name: tag-resource
---
