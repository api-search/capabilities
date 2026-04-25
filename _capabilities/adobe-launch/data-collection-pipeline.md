---
consumed_apis:
- event-forwarding
- data-collection
description: Unified workflow for Adobe Experience Platform data collection. Combines Event Forwarding and Data Collection APIs for data engineers managing server-side event routing, Edge Network data ingestion, and media analytics tracking.
layout: capability
name: Adobe Launch Data Collection Pipeline
operations:
- description: List event forwarding properties
  method: GET
  name: list-event-forwarding-properties
  path: /v1/event-forwarding-properties
- description: List event forwarding rules
  method: GET
  name: list-event-forwarding-rules
  path: /v1/event-forwarding-rules
- description: List secrets for a property
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Send an interactive event to Edge Network
  method: POST
  name: send-interactive-event
  path: /v1/events
- description: Send batch events to Edge Network
  method: POST
  name: send-batch-events
  path: /v1/events
personas: []
provider_name: Adobe Launch
provider_slug: adobe-launch
search_terms:
- create a new event forwarding rule
- list secrets
- send batch events
- list server-side event forwarding properties
- send batch events to edge network
- create a new event forwarding property
- end media session
- edge network
- event forwarding rules
- list secrets for a property
- adobe launch
- send an interactive event to edge network
- start a media tracking session
- tag management
- list event forwarding rules
- create secret
- create event forwarding rule
- create event forwarding property
- create a secret for an event forwarding destination
- data collection
- end a media tracking session
- list event forwarding properties
- list event forwarding rules for a property
- send interactive event
- server-side event forwarding properties
- edge network data ingestion
- send an interactive event to adobe edge network
- marketing technology
- list secrets for authenticating with forwarding destinations
- event forwarding
- secrets for event forwarding destinations
- send batch events to adobe edge network
- start media session
slug: data-collection-pipeline
tags:
- Adobe Launch
- Data Collection
- Event Forwarding
- Edge Network
tools:
- description: List server-side event forwarding properties
  hints:
    openWorld: true
    readOnly: true
  name: list-event-forwarding-properties
- description: Create a new event forwarding property
  hints:
    readOnly: false
  name: create-event-forwarding-property
- description: List event forwarding rules for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-event-forwarding-rules
- description: Create a new event forwarding rule
  hints:
    readOnly: false
  name: create-event-forwarding-rule
- description: List secrets for authenticating with forwarding destinations
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Create a secret for an event forwarding destination
  hints:
    readOnly: false
  name: create-secret
- description: Send an interactive event to Adobe Edge Network
  hints:
    readOnly: false
  name: send-interactive-event
- description: Send batch events to Adobe Edge Network
  hints:
    readOnly: false
  name: send-batch-events
- description: Start a media tracking session
  hints:
    readOnly: false
  name: start-media-session
- description: End a media tracking session
  hints:
    readOnly: false
  name: end-media-session
---
