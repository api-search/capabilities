---
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
- get topic attributes
- pub/sub
- get sms messaging attributes
- create topic
- create a platform application for mobile push
- create a new sns topic
- get sms attributes
- delete an sns topic
- set attributes on an sns topic
- delete topic
- list all subscriptions
- messaging
- publish up to 10 messages in a batch
- publish a message to a topic
- subscribe
- get attributes of an sns topic
- check if a phone number has opted out of sms
- create platform application
- list subscriptions by topic
- list subscriptions for a specific topic
- aws
- list topics
- get attributes of a subscription
- tag resource
- notifications
- check phone opted out
- create a subscription
- get subscription attributes
- publish
- list tags for an sns resource
- unsubscribe from a topic
- publish batch
- list tags
- set topic attributes
- topic management
- sms
- amazon
- create a subscription to a topic
- message publishing
- list all sns topics
- email
- unsubscribe
- list subscriptions
- push notifications
- add tags to an sns resource
- subscription management
- publish a message to a topic or endpoint
slug: pub-sub-messaging
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
