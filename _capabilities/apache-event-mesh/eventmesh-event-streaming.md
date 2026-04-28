---
categories: []
consumed_apis:
- eventmesh-admin
description: Unified capability for event-driven architectures using Apache EventMesh — managing topics, subscriptions, and publishing CloudEvents. Designed for platform engineers and developers building distributed event streaming pipelines.
layout: capability
name: Apache EventMesh Event Streaming
operations:
- description: List all EventMesh topics
  method: GET
  name: list-topics
  path: /v1/topics
- description: Create a new EventMesh topic
  method: PUT
  name: create-topic
  path: /v1/topics
- description: Subscribe to EventMesh topics
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: Publish a CloudEvent
  method: POST
  name: publish-event
  path: /v1/events
personas: []
provider_name: Apache EventMesh
provider_slug: apache-event-mesh
search_terms:
- platform engineering
- publish events
- publish event
- list all eventmesh topics
- create topic
- list all topics registered in eventmesh
- cloudevents
- create eventmesh topic
- manage eventmesh topics
- apache
- engineers managing the eventmesh cluster and messaging infrastructure
- pub-sub, request-reply, and broadcast messaging patterns
- Platform Engineer
- subscribe to eventmesh topics
- subscribe to topic
- manage topics, subscriptions, and publish cloudevents
- publish a cloudevent
- publish cloud event
- list topics
- subscribe a consumer to an eventmesh topic
- Developer
- application developers building event-driven services on eventmesh
- create subscription
- open source
- messaging
- publish a cloudevent to an eventmesh topic
- event-driven
- serverless
- manage event subscriptions
- topic management and event publishing via cloudevents
- list eventmesh topics
- pub-sub
- create a new eventmesh topic
- apache eventmesh
slug: eventmesh-event-streaming
tags:
- Apache EventMesh
- Event-Driven
- CloudEvents
- Messaging
- Platform Engineering
tools:
- description: List all topics registered in EventMesh
  hints:
    openWorld: true
    readOnly: true
  name: list-eventmesh-topics
- description: Create a new EventMesh topic
  hints:
    destructive: false
    readOnly: false
  name: create-eventmesh-topic
- description: Subscribe a consumer to an EventMesh topic
  hints:
    destructive: false
    readOnly: false
  name: subscribe-to-topic
- description: Publish a CloudEvent to an EventMesh topic
  hints:
    destructive: false
    readOnly: false
  name: publish-cloud-event
---
