---
categories: []
consumed_apis:
- ivs
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
- delete channel
- amazon interactive video service list stream keys
- list channels
- amazon interactive video service create stream key
- media
- amazon interactive video service create channel
- list recordings
- Developer
- amazon interactive video service get channel
- live streaming
- aws
- amazon interactive video service resources
- amazon interactive video service list channels
- managed live streaming with low latency for interactive applications.
- amazon interactive video service delete channel
- amazon interactive video service stop stream
- create stream key
- real-time
- Media Engineer
- stop stream
- list stream keys
- get channel
- amazon interactive video service list recordings
- create channel
- manages amazon interactive video service resources and operations
- video
slug: live-streaming-management
source_filename: live-streaming-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon Interactive Video Service - Live Streaming Management\n  description: Unified capability for Developer, Media Engineer to manage managed live streaming with low latency for interactive applications operations.\n  tags:\n    - Live Streaming\n    - Video\n    - AWS\n    - Media\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: ivs\n      location: ./shared/ivs.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: live-streaming-management-api\n      description: Unified REST API for live streaming management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon Interactive Video Service resources\n          operations:\n            - method: GET\n              name: list-channels\n\
  \              description: List Channels\n              call: \"ivs.list-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: live-streaming-management-mcp\n      transport: http\n      description: MCP server for AI-assisted live streaming management.\n      tools:\n        - name: list-channels\n          description: Amazon Interactive Video Service List Channels\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ivs.list-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-channel\n          description: Amazon Interactive Video Service Create Channel\n          hints:\n            readOnly: false\n            \n          call: \"ivs.create-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-channel\n\
  \          description: Amazon Interactive Video Service Delete Channel\n          hints:\n            readOnly: false\n            \n          call: \"ivs.delete-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-channel\n          description: Amazon Interactive Video Service Get Channel\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ivs.get-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-stream-keys\n          description: Amazon Interactive Video Service List Stream Keys\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ivs.list-stream-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-stream-key\n          description: Amazon Interactive Video Service Create Stream Key\n          hints:\n\
  \            readOnly: false\n            \n          call: \"ivs.create-stream-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-stream\n          description: Amazon Interactive Video Service Stop Stream\n          hints:\n            readOnly: false\n            \n          call: \"ivs.stop-stream\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-recordings\n          description: Amazon Interactive Video Service List Recordings\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ivs.list-recordings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-interactive-video-service/refs/heads/main/capabilities/live-streaming-management.yaml
tags:
- Live Streaming
- Video
- AWS
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
