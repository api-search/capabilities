---
consumed_apis:
- mediaconnect
description: Workflow capability for live video transport operations including flow management, source configuration, output routing, and entitlement management for broadcast engineers.
layout: capability
name: Amazon MediaConnect Live Video Transport
operations:
- description: List all flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a new flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: Get flow details
  method: GET
  name: describe-flow
  path: /v1/flows/{flowArn}
- description: Delete a flow
  method: DELETE
  name: delete-flow
  path: /v1/flows/{flowArn}
- description: List all bridges
  method: GET
  name: list-bridges
  path: /v1/bridges
- description: List all entitlements
  method: GET
  name: list-entitlements
  path: /v1/entitlements
personas: []
provider_name: Amazon MediaConnect
provider_slug: amazon-mediaconnect
search_terms:
- get details of a specific flow
- engineer managing live video workflows
- get flow details
- live video transport and distribution
- list all flows
- live video transport workflow for broadcast engineers
- create flow
- manage individual flow
- manage bridges
- create a new flow
- describe flow
- list gateways
- delete flow
- list all entitlements
- delete a flow
- live video
- start a mediaconnect flow
- list all flow entitlements
- broadcasting
- manage live video flows
- stop a mediaconnect flow
- list bridges
- list all mediaconnect flows for live video transport
- flows
- list all mediaconnect bridges
- list flows
- list entitlements
- list all mediaconnect gateways
- stop flow
- Broadcast Engineer
- manage entitlements
- media
- aws
- start flow
- list all bridges
- media transport
- create a new mediaconnect flow
slug: amazon-mediaconnect-live-video-transport
tags:
- AWS
- Broadcasting
- Live Video
- Media Transport
- Flows
tools:
- description: List all MediaConnect flows for live video transport
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Create a new MediaConnect flow
  hints:
    readOnly: false
  name: create-flow
- description: Get details of a specific flow
  hints:
    readOnly: true
  name: describe-flow
- description: Start a MediaConnect flow
  hints:
    readOnly: false
  name: start-flow
- description: Stop a MediaConnect flow
  hints:
    destructive: false
    readOnly: false
  name: stop-flow
- description: List all MediaConnect bridges
  hints:
    readOnly: true
  name: list-bridges
- description: List all flow entitlements
  hints:
    readOnly: true
  name: list-entitlements
- description: List all MediaConnect gateways
  hints:
    readOnly: true
  name: list-gateways
---
