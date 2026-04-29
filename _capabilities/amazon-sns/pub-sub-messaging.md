---
categories:
- messaging
consumed_apis:
- amazon-sns
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
- list subscriptions for a specific topic
- subscription management
- publish batch
- message publishing
- publish a message to a topic or endpoint
- email
- pub/sub
- delete topic
- list all sns topics
- publish a message to a topic
- create topic
- list tags
- get attributes of an sns topic
- amazon
- create a new sns topic
- check phone opted out
- create platform application
- list tags for an sns resource
- unsubscribe from a topic
- publish up to 10 messages in a batch
- list subscriptions
- notifications
- push notifications
- publish
- get subscription attributes
- check if a phone number has opted out of sms
- subscribe
- set attributes on an sns topic
- list subscriptions by topic
- set topic attributes
- get sms attributes
- get topic attributes
- get sms messaging attributes
- get attributes of a subscription
- messaging
- add tags to an sns resource
- create a subscription
- tag resource
- create a platform application for mobile push
- delete an sns topic
- sms
- aws
- list topics
- unsubscribe
- topic management
- create a subscription to a topic
- list all subscriptions
slug: pub-sub-messaging
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon SNS Pub/Sub Messaging\"\n  description: \"Pub/sub messaging workflow combining topic management, subscription lifecycle, message publishing, mobile push, and SMS operations. Used by developers and platform engineers for event-driven architectures and notification systems.\"\n  tags:\n    - Amazon\n    - AWS\n    - Messaging\n    - Notifications\n    - Pub/Sub\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-sns\n      location: ./shared/sns.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sns-pubsub-api\n      description: \"Unified REST API for Amazon SNS pub/sub messaging.\"\n      resources:\n        - path: /v1/topics\n          name: topics\n          description: \"Topic management\"\
  \n          operations:\n            - method: GET\n              name: list-topics\n              description: \"List all SNS topics\"\n              call: \"amazon-sns.list-topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-topic\n              description: \"Create a new SNS topic\"\n              call: \"amazon-sns.create-topic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Subscription management\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List all subscriptions\"\n              call: \"amazon-sns.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n  \
  \            name: subscribe\n              description: \"Create a subscription\"\n              call: \"amazon-sns.subscribe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: messages\n          description: \"Message publishing\"\n          operations:\n            - method: POST\n              name: publish\n              description: \"Publish a message to a topic\"\n              call: \"amazon-sns.publish\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sns-pubsub-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon SNS pub/sub messaging.\"\n      tools:\n        - name: list-topics\n          description: \"List all SNS topics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-sns.list-topics\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-topic\n          description: \"Create a new SNS topic\"\n          hints:\n            readOnly: false\n          call: \"amazon-sns.create-topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-topic\n          description: \"Delete an SNS topic\"\n          hints:\n            destructive: true\n          call: \"amazon-sns.delete-topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-topic-attributes\n          description: \"Get attributes of an SNS topic\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.get-topic-attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-topic-attributes\n          description: \"Set attributes on an SNS topic\"\n       \
  \   hints:\n            readOnly: false\n            idempotent: true\n          call: \"amazon-sns.set-topic-attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe\n          description: \"Create a subscription to a topic\"\n          hints:\n            readOnly: false\n          call: \"amazon-sns.subscribe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unsubscribe\n          description: \"Unsubscribe from a topic\"\n          hints:\n            destructive: true\n          call: \"amazon-sns.unsubscribe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List all subscriptions\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-subscriptions-by-topic\n          description: \"List subscriptions for a specific topic\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.list-subscriptions-by-topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscription-attributes\n          description: \"Get attributes of a subscription\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.get-subscription-attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish\n          description: \"Publish a message to a topic or endpoint\"\n          hints:\n            readOnly: false\n          call: \"amazon-sns.publish\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-batch\n          description: \"Publish up to 10 messages in a batch\"\n          hints:\n\
  \            readOnly: false\n          call: \"amazon-sns.publish-batch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-platform-application\n          description: \"Create a platform application for mobile push\"\n          hints:\n            readOnly: false\n          call: \"amazon-sns.create-platform-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sms-attributes\n          description: \"Get SMS messaging attributes\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.get-sms-attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-phone-opted-out\n          description: \"Check if a phone number has opted out of SMS\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.check-if-phone-number-is-opted-out\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n          description: \"List tags for an SNS resource\"\n          hints:\n            readOnly: true\n          call: \"amazon-sns.list-tags-for-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tag-resource\n          description: \"Add tags to an SNS resource\"\n          hints:\n            readOnly: false\n          call: \"amazon-sns.tag-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-sns/refs/heads/main/capabilities/pub-sub-messaging.yaml
tags:
- Amazon
- AWS
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
