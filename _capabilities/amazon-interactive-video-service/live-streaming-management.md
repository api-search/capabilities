---
categories: []
consumed_apis: []
description: Unified capability for Developer, Media Engineer to manage managed live streaming with low latency for interactive applications operations.
layout: capability
name: Amazon Interactive Video Service - Live Streaming Management
operations:
- description: List Channels
  method: GET
  name: list-channels
  path: /v1/resources
personas: []
provider_name: Amazon Interactive Video Service
provider_slug: amazon-interactive-video-service
search_terms:
- manages amazon interactive video service resources and operations
- managed live streaming with low latency for interactive applications.
- video
- stop stream
- get channel
- list channels
- amazon interactive video service get channel
- amazon interactive video service list channels
- amazon interactive video service resources
- amazon interactive video service delete channel
- amazon interactive video service list stream keys
- delete channel
- list recordings
- Media Engineer
- create stream key
- create channel
- media
- Developer
- list stream keys
- amazon interactive video service create stream key
- aws
- live streaming
- amazon interactive video service stop stream
- real-time
- amazon interactive video service create channel
- amazon interactive video service list recordings
slug: live-streaming-management
source_filename: live-streaming-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Interactive Video Service - Live Streaming Management\n  description: Unified capability for Developer, Media Engineer to manage managed live streaming with low latency for interactive\n    applications operations.\n  tags:\n  - Live Streaming\n  - Video\n  - AWS\n  - Media\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ivs\n    baseUri: https://ivs.us-east-1.amazonaws.com\n    description: Amazon Interactive Video Service REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: resources\n      path: /\n      description: Amazon Interactive Video Service resources\n      operations:\n      - name: list-channels\n        method: GET\n\
  \        description: List Channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: live-streaming-management-api\n    description: Unified REST API for live streaming management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Interactive Video Service resources\n      operations:\n      - method: GET\n        name: list-channels\n        description: List Channels\n        call: ivs.list-channels\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: live-streaming-management-mcp\n    transport: http\n    description: MCP server for AI-assisted live streaming management.\n    tools:\n    - name: list-channels\n      description: Amazon Interactive Video Service List Channels\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: ivs.list-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-channel\n      description: Amazon Interactive Video Service Create Channel\n      hints:\n        readOnly: false\n      call: ivs.create-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-channel\n      description: Amazon Interactive Video Service Delete Channel\n      hints:\n        readOnly: false\n      call: ivs.delete-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-channel\n      description: Amazon Interactive Video Service Get Channel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ivs.get-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stream-keys\n      description: Amazon Interactive Video Service List Stream Keys\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ivs.list-stream-keys\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-stream-key\n      description: Amazon Interactive Video Service Create Stream Key\n      hints:\n        readOnly: false\n      call: ivs.create-stream-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-stream\n      description: Amazon Interactive Video Service Stop Stream\n      hints:\n        readOnly: false\n      call: ivs.stop-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recordings\n      description: Amazon Interactive Video Service List Recordings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ivs.list-recordings\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-interactive-video-service/refs/heads/main/capabilities/live-streaming-management.yaml
tags:
- Live Streaming
- Video
- Media
tools:
- description: Amazon Interactive Video Service List Channels
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: Amazon Interactive Video Service Create Channel
  hints:
    readOnly: false
  name: create-channel
- description: Amazon Interactive Video Service Delete Channel
  hints:
    readOnly: false
  name: delete-channel
- description: Amazon Interactive Video Service Get Channel
  hints:
    openWorld: true
    readOnly: true
  name: get-channel
- description: Amazon Interactive Video Service List Stream Keys
  hints:
    openWorld: true
    readOnly: true
  name: list-stream-keys
- description: Amazon Interactive Video Service Create Stream Key
  hints:
    readOnly: false
  name: create-stream-key
- description: Amazon Interactive Video Service Stop Stream
  hints:
    readOnly: false
  name: stop-stream
- description: Amazon Interactive Video Service List Recordings
  hints:
    openWorld: true
    readOnly: true
  name: list-recordings
---
