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
- create flow
- list entitlements
- flows
- broadcasting
- media
- list all entitlements
- list all bridges
- list all flows
- list all mediaconnect flows for live video transport
- manage entitlements
- get flow details
- list bridges
- list all mediaconnect gateways
- start flow
- live video transport workflow for broadcast engineers
- manage bridges
- media transport
- delete flow
- list flows
- create a new mediaconnect flow
- manage individual flow
- get details of a specific flow
- manage live video flows
- delete a flow
- live video transport and distribution
- start a mediaconnect flow
- engineer managing live video workflows
- list all mediaconnect bridges
- list gateways
- aws
- stop a mediaconnect flow
- Broadcast Engineer
- describe flow
- list all flow entitlements
- stop flow
- live video
- create a new flow
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
