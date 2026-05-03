---
categories: []
consumed_apis:
- streamyard
description: Unified capability for managing StreamYard live streaming and recording operations. Designed for content creators, media teams, and broadcast automation platforms. Covers the full broadcast lifecycle from creation through multi-platform destination setup, live monitoring, and post-broadcast recording access.
layout: capability
name: StreamYard Live Streaming
operations:
- description: List all broadcasts
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new broadcast
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Get broadcast details and status
  method: GET
  name: get-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: Update broadcast metadata
  method: PATCH
  name: update-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: Delete a broadcast
  method: DELETE
  name: delete-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: List destinations for a broadcast
  method: GET
  name: list-broadcast-destinations
  path: /v1/broadcasts/{broadcastId}/destinations
- description: Add a streaming destination
  method: POST
  name: add-broadcast-destination
  path: /v1/broadcasts/{broadcastId}/destinations
- description: List connected platform accounts
  method: GET
  name: list-destinations
  path: /v1/destinations
- description: List all recordings
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: Get recording details and download URL
  method: GET
  name: get-recording
  path: /v1/recordings/{recordingId}
personas: []
provider_name: StreamYard
provider_slug: streamyard
search_terms:
- broadcasting
- connected streaming platform accounts
- video
- create a new live stream or recording session
- get a recording with its time-limited download url
- delete a broadcast permanently
- get broadcast details and status
- list destinations for a broadcast
- list all recordings
- create a new broadcast
- multi-platform streaming destinations
- get recording
- list all recordings from completed broadcasts
- list the streaming platforms added to a specific broadcast
- list connected destinations
- add a streaming destination
- add broadcast destination
- get broadcast
- single recording access
- update a broadcast title, description, or scheduled time
- recordings
- list connected platform accounts
- get recording download
- list destinations
- single broadcast management
- list recordings
- create broadcast
- update broadcast metadata
- list broadcast destinations
- live streaming
- list broadcasts
- get recording details and download url
- broadcast lifecycle management
- list all broadcasts in the streamyard account including live and completed
- delete a broadcast
- multi-streaming
- delete broadcast
- add a streaming platform (youtube, facebook, linkedin, twitch) to a broadcast
- list all broadcasts
- post-broadcast recordings
- list all connected streaming platform accounts available for broadcasting
- update broadcast
- get details and current status of a broadcast
slug: live-streaming
source_filename: live-streaming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StreamYard Live Streaming\"\n  description: >-\n    Unified capability for managing StreamYard live streaming and recording\n    operations. Designed for content creators, media teams, and broadcast\n    automation platforms. Covers the full broadcast lifecycle from creation\n    through multi-platform destination setup, live monitoring, and post-broadcast\n    recording access.\n  tags:\n    - Broadcasting\n    - Live Streaming\n    - Multi-Streaming\n    - Recordings\n    - Video\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STREAMYARD_ACCESS_TOKEN: STREAMYARD_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: streamyard\n      location: ./shared/streamyard-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: streamyard-live-streaming-api\n      description: \"Unified REST API for StreamYard live streaming and recording management.\"\n     \
  \ resources:\n        - path: /v1/broadcasts\n          name: broadcasts\n          description: \"Broadcast lifecycle management\"\n          operations:\n            - method: GET\n              name: list-broadcasts\n              description: \"List all broadcasts\"\n              call: \"streamyard.list-broadcasts\"\n              with:\n                page: \"rest.page\"\n                perPage: \"rest.perPage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-broadcast\n              description: \"Create a new broadcast\"\n              call: \"streamyard.create-broadcast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/broadcasts/{broadcastId}\n          name: broadcast\n          description: \"Single broadcast management\"\n          operations:\n            - method: GET\n              name: get-broadcast\n\
  \              description: \"Get broadcast details and status\"\n              call: \"streamyard.get-broadcast\"\n              with:\n                broadcastId: \"rest.broadcastId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-broadcast\n              description: \"Update broadcast metadata\"\n              call: \"streamyard.update-broadcast\"\n              with:\n                broadcastId: \"rest.broadcastId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-broadcast\n              description: \"Delete a broadcast\"\n              call: \"streamyard.delete-broadcast\"\n              with:\n                broadcastId: \"rest.broadcastId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/broadcasts/{broadcastId}/destinations\n\
  \          name: broadcast-destinations\n          description: \"Multi-platform streaming destinations\"\n          operations:\n            - method: GET\n              name: list-broadcast-destinations\n              description: \"List destinations for a broadcast\"\n              call: \"streamyard.list-broadcast-destinations\"\n              with:\n                broadcastId: \"rest.broadcastId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-broadcast-destination\n              description: \"Add a streaming destination\"\n              call: \"streamyard.add-broadcast-destination\"\n              with:\n                broadcastId: \"rest.broadcastId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/destinations\n          name: destinations\n          description: \"Connected streaming platform accounts\"\
  \n          operations:\n            - method: GET\n              name: list-destinations\n              description: \"List connected platform accounts\"\n              call: \"streamyard.list-destinations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recordings\n          name: recordings\n          description: \"Post-broadcast recordings\"\n          operations:\n            - method: GET\n              name: list-recordings\n              description: \"List all recordings\"\n              call: \"streamyard.list-recordings\"\n              with:\n                page: \"rest.page\"\n                perPage: \"rest.perPage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recordings/{recordingId}\n          name: recording\n          description: \"Single recording access\"\n          operations:\n            - method: GET\n        \
  \      name: get-recording\n              description: \"Get recording details and download URL\"\n              call: \"streamyard.get-recording\"\n              with:\n                recordingId: \"rest.recordingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: streamyard-live-streaming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted StreamYard broadcast management.\"\n      tools:\n        - name: list-broadcasts\n          description: \"List all broadcasts in the StreamYard account including live and completed\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamyard.list-broadcasts\"\n          with:\n            page: \"tools.page\"\n            perPage: \"tools.perPage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-broadcast\n\
  \          description: \"Create a new live stream or recording session\"\n          hints:\n            readOnly: false\n          call: \"streamyard.create-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-broadcast\n          description: \"Get details and current status of a broadcast\"\n          hints:\n            readOnly: true\n          call: \"streamyard.get-broadcast\"\n          with:\n            broadcastId: \"tools.broadcastId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-broadcast\n          description: \"Update a broadcast title, description, or scheduled time\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"streamyard.update-broadcast\"\n          with:\n            broadcastId: \"tools.broadcastId\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: delete-broadcast\n          description: \"Delete a broadcast permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"streamyard.delete-broadcast\"\n          with:\n            broadcastId: \"tools.broadcastId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-broadcast-destinations\n          description: \"List the streaming platforms added to a specific broadcast\"\n          hints:\n            readOnly: true\n          call: \"streamyard.list-broadcast-destinations\"\n          with:\n            broadcastId: \"tools.broadcastId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-broadcast-destination\n          description: \"Add a streaming platform (YouTube, Facebook, LinkedIn, Twitch) to a broadcast\"\n          hints:\n            readOnly: false\n          call: \"streamyard.add-broadcast-destination\"\
  \n          with:\n            broadcastId: \"tools.broadcastId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connected-destinations\n          description: \"List all connected streaming platform accounts available for broadcasting\"\n          hints:\n            readOnly: true\n          call: \"streamyard.list-destinations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-recordings\n          description: \"List all recordings from completed broadcasts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamyard.list-recordings\"\n          with:\n            page: \"tools.page\"\n            perPage: \"tools.perPage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recording-download\n          description: \"Get a recording with its time-limited download\
  \ URL\"\n          hints:\n            readOnly: true\n          call: \"streamyard.get-recording\"\n          with:\n            recordingId: \"tools.recordingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/streamyard/refs/heads/main/capabilities/live-streaming.yaml
tags:
- Broadcasting
- Live Streaming
- Multi-Streaming
- Recordings
- Video
tools:
- description: List all broadcasts in the StreamYard account including live and completed
  hints:
    openWorld: true
    readOnly: true
  name: list-broadcasts
- description: Create a new live stream or recording session
  hints:
    readOnly: false
  name: create-broadcast
- description: Get details and current status of a broadcast
  hints:
    readOnly: true
  name: get-broadcast
- description: Update a broadcast title, description, or scheduled time
  hints:
    idempotent: true
    readOnly: false
  name: update-broadcast
- description: Delete a broadcast permanently
  hints:
    destructive: true
    readOnly: false
  name: delete-broadcast
- description: List the streaming platforms added to a specific broadcast
  hints:
    readOnly: true
  name: list-broadcast-destinations
- description: Add a streaming platform (YouTube, Facebook, LinkedIn, Twitch) to a broadcast
  hints:
    readOnly: false
  name: add-broadcast-destination
- description: List all connected streaming platform accounts available for broadcasting
  hints:
    readOnly: true
  name: list-connected-destinations
- description: List all recordings from completed broadcasts
  hints:
    openWorld: true
    readOnly: true
  name: list-recordings
- description: Get a recording with its time-limited download URL
  hints:
    readOnly: true
  name: get-recording-download
---
