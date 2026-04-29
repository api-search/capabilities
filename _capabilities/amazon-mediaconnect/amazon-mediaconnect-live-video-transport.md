---
categories: []
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
- stop a mediaconnect flow
- list all entitlements
- list all mediaconnect flows for live video transport
- get details of a specific flow
- start flow
- list bridges
- delete a flow
- media
- stop flow
- Broadcast Engineer
- manage live video flows
- list all mediaconnect gateways
- delete flow
- live video transport and distribution
- engineer managing live video workflows
- list all mediaconnect bridges
- list entitlements
- aws
- list gateways
- create a new flow
- start a mediaconnect flow
- flows
- manage individual flow
- list all flow entitlements
- describe flow
- live video transport workflow for broadcast engineers
- media transport
- manage entitlements
- manage bridges
- create a new mediaconnect flow
- list all bridges
- list all flows
- broadcasting
- get flow details
- live video
- create flow
- list flows
slug: amazon-mediaconnect-live-video-transport
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaConnect Live Video Transport\n  description: Workflow capability for live video transport operations including flow management, source configuration, output routing, and entitlement management for broadcast engineers.\n  tags:\n  - AWS\n  - Broadcasting\n  - Live Video\n  - Media Transport\n  - Flows\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mediaconnect\n    location: ./shared/mediaconnect.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediaconnect-transport-api\n    description: Unified REST API for live video transport workflow management.\n    resources:\n    - path: /v1/flows\n      name: flows\n      description: Manage live video flows\n      operations:\n      - method: GET\n        name: list-flows\n\
  \        description: List all flows\n        call: mediaconnect.list-flows\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-flow\n        description: Create a new flow\n        call: mediaconnect.create-flow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{flowArn}\n      name: flow\n      description: Manage individual flow\n      operations:\n      - method: GET\n        name: describe-flow\n        description: Get flow details\n        call: mediaconnect.describe-flow\n        with:\n          flowArn: rest.flowArn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-flow\n        description: Delete a flow\n        call: mediaconnect.delete-flow\n        with:\n          flowArn: rest.flowArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bridges\n     \
  \ name: bridges\n      description: Manage bridges\n      operations:\n      - method: GET\n        name: list-bridges\n        description: List all bridges\n        call: mediaconnect.list-bridges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entitlements\n      name: entitlements\n      description: Manage entitlements\n      operations:\n      - method: GET\n        name: list-entitlements\n        description: List all entitlements\n        call: mediaconnect.list-entitlements\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediaconnect-transport-mcp\n    transport: http\n    description: MCP server for AI-assisted live video transport workflow management.\n    tools:\n    - name: list-flows\n      description: List all MediaConnect flows for live video transport\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconnect.list-flows\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-flow\n      description: Create a new MediaConnect flow\n      hints:\n        readOnly: false\n      call: mediaconnect.create-flow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-flow\n      description: Get details of a specific flow\n      hints:\n        readOnly: true\n      call: mediaconnect.describe-flow\n      with:\n        flowArn: tools.flowArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-flow\n      description: Start a MediaConnect flow\n      hints:\n        readOnly: false\n      call: mediaconnect.start-flow\n      with:\n        flowArn: tools.flowArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-flow\n      description: Stop a MediaConnect flow\n      hints:\n        readOnly: false\n        destructive: false\n      call: mediaconnect.stop-flow\n      with:\n\
  \        flowArn: tools.flowArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bridges\n      description: List all MediaConnect bridges\n      hints:\n        readOnly: true\n      call: mediaconnect.list-bridges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-entitlements\n      description: List all flow entitlements\n      hints:\n        readOnly: true\n      call: mediaconnect.list-entitlements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gateways\n      description: List all MediaConnect gateways\n      hints:\n        readOnly: true\n      call: mediaconnect.list-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediaconnect/refs/heads/main/capabilities/amazon-mediaconnect-live-video-transport.yaml
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
