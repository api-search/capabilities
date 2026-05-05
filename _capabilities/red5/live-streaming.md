---
categories: []
consumed_apis:
- red5-server
description: Unified capability for managing live streaming infrastructure on Red5 Pro. Combines the Server API for node-level stream monitoring and control with the Stream Manager 2.0 API for autoscaled cluster orchestration. Used by streaming operations teams to monitor live events, manage stream quality, control recording, and scale streaming capacity.
layout: capability
name: Red5 Live Streaming Management
operations:
- description: Get server information and status
  method: GET
  name: get-server-info
  path: /v1/server
- description: List deployed streaming applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List active streams in an application
  method: GET
  name: list-streams
  path: /v1/applications/{app}/streams
- description: Get stream statistics
  method: GET
  name: get-stream
  path: /v1/applications/{app}/streams/{stream}
- description: Start recording a stream
  method: POST
  name: start-recording
  path: /v1/applications/{app}/streams/{stream}/record/start
- description: Stop recording a stream
  method: POST
  name: stop-recording
  path: /v1/applications/{app}/streams/{stream}/record/stop
personas: []
provider_name: Red5
provider_slug: red5
search_terms:
- get app stats
- stop recording
- start recording
- list active streams in an application
- list streaming apps
- get stream statistics
- live streaming
- get detailed red5 pro server configuration and status
- server health and information
- start recording a live stream to disk storage
- start recording a stream
- individual stream management
- list live streams
- live stream management
- streaming
- stop an active stream recording and finalize the recording file
- media
- list streams
- list all streaming applications deployed on the red5 pro server
- start stream recording
- webrtc
- list applications
- stop stream recording
- streaming application management
- stop recording a stream
- real-time
- check red5 pro server health and get version information
- get server information and status
- list deployed streaming applications
- rtmp
- get detailed statistics for a live stream including bitrate, frame rate, and subscriber count
- video
- get stream
- get stream stats
- red5
- get server health
- list all active live streams in a streaming application
- get server info
- get statistics for a specific streaming application scope
slug: live-streaming
source_filename: live-streaming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red5 Live Streaming Management\"\n  description: >-\n    Unified capability for managing live streaming infrastructure on Red5 Pro.\n    Combines the Server API for node-level stream monitoring and control with\n    the Stream Manager 2.0 API for autoscaled cluster orchestration. Used by\n    streaming operations teams to monitor live events, manage stream quality,\n    control recording, and scale streaming capacity.\n  tags:\n    - Live Streaming\n    - Media\n    - Real-Time\n    - Red5\n    - Streaming\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RED5_ACCESS_TOKEN: RED5_ACCESS_TOKEN\n      RED5_SERVER_HOST: RED5_SERVER_HOST\n\ncapability:\n  consumes:\n    - import: red5-server\n      location: ./shared/server-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: red5-streaming-rest\n      description: \"Unified REST API for Red5 live streaming\
  \ management.\"\n      resources:\n        - path: /v1/server\n          name: server\n          description: \"Server health and information\"\n          operations:\n            - method: GET\n              name: get-server-info\n              description: \"Get server information and status\"\n              call: \"red5-server.get-server-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Streaming application management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List deployed streaming applications\"\n              call: \"red5-server.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{app}/streams\n          name: streams\n          description: \"Live stream management\"\
  \n          operations:\n            - method: GET\n              name: list-streams\n              description: \"List active streams in an application\"\n              call: \"red5-server.list-streams\"\n              with:\n                appName: \"rest.app\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{app}/streams/{stream}\n          name: stream\n          description: \"Individual stream management\"\n          operations:\n            - method: GET\n              name: get-stream\n              description: \"Get stream statistics\"\n              call: \"red5-server.get-stream\"\n              with:\n                appName: \"rest.app\"\n                streamName: \"rest.stream\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{app}/streams/{stream}/record/start\n          name: recording-start\n   \
  \       description: \"Start stream recording\"\n          operations:\n            - method: POST\n              name: start-recording\n              description: \"Start recording a stream\"\n              call: \"red5-server.start-recording\"\n              with:\n                appName: \"rest.app\"\n                streamName: \"rest.stream\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{app}/streams/{stream}/record/stop\n          name: recording-stop\n          description: \"Stop stream recording\"\n          operations:\n            - method: POST\n              name: stop-recording\n              description: \"Stop recording a stream\"\n              call: \"red5-server.stop-recording\"\n              with:\n                appName: \"rest.app\"\n                streamName: \"rest.stream\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n    - type: mcp\n      port: 9080\n      namespace: red5-streaming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Red5 live streaming management.\"\n      tools:\n        - name: get-server-health\n          description: \"Check Red5 Pro server health and get version information\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"red5-server.ping-server\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-server-info\n          description: \"Get detailed Red5 Pro server configuration and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"red5-server.get-server-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-streaming-apps\n          description: \"List all streaming applications deployed on the Red5 Pro server\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"red5-server.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app-stats\n          description: \"Get statistics for a specific streaming application scope\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"red5-server.get-application\"\n          with:\n            appName: \"tools.app_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-live-streams\n          description: \"List all active live streams in a streaming application\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"red5-server.list-streams\"\n          with:\n            appName: \"tools.app_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-stream-stats\n\
  \          description: \"Get detailed statistics for a live stream including bitrate, frame rate, and subscriber count\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"red5-server.get-stream\"\n          with:\n            appName: \"tools.app_name\"\n            streamName: \"tools.stream_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-stream-recording\n          description: \"Start recording a live stream to disk storage\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"red5-server.start-recording\"\n          with:\n            appName: \"tools.app_name\"\n            streamName: \"tools.stream_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-stream-recording\n          description: \"Stop an active stream recording and\
  \ finalize the recording file\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"red5-server.stop-recording\"\n          with:\n            appName: \"tools.app_name\"\n            streamName: \"tools.stream_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red5/refs/heads/main/capabilities/live-streaming.yaml
tags:
- Live Streaming
- Media
- Real-Time
- Red5
- Streaming
tools:
- description: Check Red5 Pro server health and get version information
  hints:
    openWorld: false
    readOnly: true
  name: get-server-health
- description: Get detailed Red5 Pro server configuration and status
  hints:
    openWorld: false
    readOnly: true
  name: get-server-info
- description: List all streaming applications deployed on the Red5 Pro server
  hints:
    openWorld: false
    readOnly: true
  name: list-streaming-apps
- description: Get statistics for a specific streaming application scope
  hints:
    openWorld: false
    readOnly: true
  name: get-app-stats
- description: List all active live streams in a streaming application
  hints:
    openWorld: false
    readOnly: true
  name: list-live-streams
- description: Get detailed statistics for a live stream including bitrate, frame rate, and subscriber count
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-stats
- description: Start recording a live stream to disk storage
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-stream-recording
- description: Stop an active stream recording and finalize the recording file
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-stream-recording
---
