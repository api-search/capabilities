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
- message publishing
- email
- create a platform application for mobile push
- list topics
- create platform application
- get attributes of an sns topic
- get sms attributes
- delete topic
- list subscriptions for a specific topic
- get subscription attributes
- get attributes of a subscription
- list subscriptions by topic
- subscribe
- unsubscribe
- subscription management
- list tags for an sns resource
- list tags
- delete an sns topic
- unsubscribe from a topic
- add tags to an sns resource
- publish batch
- sms
- create topic
- create a subscription
- notifications
- publish a message to a topic
- list subscriptions
- check if a phone number has opted out of sms
- create a new sns topic
- get sms messaging attributes
- list all sns topics
- create a subscription to a topic
- topic management
- push notifications
- set attributes on an sns topic
- get topic attributes
- tag resource
- publish up to 10 messages in a batch
- messaging
- aws
- publish a message to a topic or endpoint
- check phone opted out
- pub/sub
- set topic attributes
- publish
- amazon
- list all subscriptions
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
