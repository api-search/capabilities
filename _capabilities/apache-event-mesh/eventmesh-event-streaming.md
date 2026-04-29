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
- create subscription
- messaging
- event-driven
- subscribe to eventmesh topics
- publish a cloudevent
- publish events
- cloudevents
- manage event subscriptions
- pub-sub
- publish cloud event
- create a new eventmesh topic
- subscribe to topic
- serverless
- Developer
- publish event
- list topics
- list eventmesh topics
- list all topics registered in eventmesh
- topic management and event publishing via cloudevents
- subscribe a consumer to an eventmesh topic
- manage topics, subscriptions, and publish cloudevents
- apache
- apache eventmesh
- engineers managing the eventmesh cluster and messaging infrastructure
- pub-sub, request-reply, and broadcast messaging patterns
- platform engineering
- create topic
- publish a cloudevent to an eventmesh topic
- Platform Engineer
- manage eventmesh topics
- list all eventmesh topics
- application developers building event-driven services on eventmesh
- create eventmesh topic
- open source
slug: eventmesh-event-streaming
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache EventMesh Event Streaming\"\n  description: \"Unified capability for event-driven architectures using Apache EventMesh — managing topics, subscriptions, and publishing CloudEvents. Designed for platform engineers and developers building distributed event streaming pipelines.\"\n  tags:\n    - Apache EventMesh\n    - Event-Driven\n    - CloudEvents\n    - Messaging\n    - Platform Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      EVENTMESH_BASE_URL: EVENTMESH_BASE_URL\ncapability:\n  consumes:\n    - import: eventmesh-admin\n      location: ./shared/eventmesh-admin.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: eventmesh-streaming-api\n      description: \"Unified REST API for Apache EventMesh event streaming.\"\n      resources:\n        - path: /v1/topics\n          name: topics\n          description: Manage EventMesh topics\n        \
  \  operations:\n            - method: GET\n              name: list-topics\n              description: List all EventMesh topics\n              call: \"eventmesh-admin.list-topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: create-topic\n              description: Create a new EventMesh topic\n              call: \"eventmesh-admin.create-topic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: Manage event subscriptions\n          operations:\n            - method: POST\n              name: create-subscription\n              description: Subscribe to EventMesh topics\n              call: \"eventmesh-admin.create-subscription\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n\
  \          name: events\n          description: Publish events\n          operations:\n            - method: POST\n              name: publish-event\n              description: Publish a CloudEvent\n              call: \"eventmesh-admin.publish-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: eventmesh-streaming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache EventMesh event streaming.\"\n      tools:\n        - name: list-eventmesh-topics\n          description: List all topics registered in EventMesh\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"eventmesh-admin.list-topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-eventmesh-topic\n          description: Create a new EventMesh topic\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n          call: \"eventmesh-admin.create-topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-to-topic\n          description: Subscribe a consumer to an EventMesh topic\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"eventmesh-admin.create-subscription\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-cloud-event\n          description: Publish a CloudEvent to an EventMesh topic\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"eventmesh-admin.publish-event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-event-mesh/refs/heads/main/capabilities/eventmesh-event-streaming.yaml
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
