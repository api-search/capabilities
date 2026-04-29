---
categories: []
consumed_apis:
- youtube-live
description: Workflow for managing YouTube live events including scheduling broadcasts, linking streams, managing live chat, and moderating live interactions. Designed for live event producers, streaming teams, and broadcast operators.
layout: capability
name: YouTube Live Streaming
operations:
- description: List live broadcasts
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new live broadcast
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Update broadcast settings
  method: PUT
  name: update-broadcast
  path: /v1/broadcasts
- description: Delete a broadcast
  method: DELETE
  name: delete-broadcast
  path: /v1/broadcasts
- description: List live streams
  method: GET
  name: list-streams
  path: /v1/streams
- description: Create a new live stream
  method: POST
  name: create-stream
  path: /v1/streams
- description: Update stream settings
  method: PUT
  name: update-stream
  path: /v1/streams
- description: Delete a live stream
  method: DELETE
  name: delete-stream
  path: /v1/streams
- description: List live chat messages
  method: GET
  name: list-chat-messages
  path: /v1/chat-messages
- description: Send a live chat message
  method: POST
  name: send-chat-message
  path: /v1/chat-messages
- description: Delete a live chat message
  method: DELETE
  name: delete-chat-message
  path: /v1/chat-messages
- description: List live chat moderators
  method: GET
  name: list-moderators
  path: /v1/chat-moderators
- description: Add a live chat moderator
  method: POST
  name: add-moderator
  path: /v1/chat-moderators
- description: Remove a live chat moderator
  method: DELETE
  name: remove-moderator
  path: /v1/chat-moderators
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- add a live chat moderator
- manage live broadcasts
- delete a live broadcast
- google
- transition broadcast status (testing, live, complete)
- create stream
- create a new live video stream
- video
- list live broadcasts
- delete broadcast
- list chat messages
- create a new live broadcast
- delete a broadcast
- update broadcast
- youtube
- live streaming
- bind broadcast
- videos
- remove a live chat moderator
- transition broadcast
- bind a broadcast to a video stream
- update stream
- create a new live stream
- send a live chat message
- streaming
- delete a live chat message
- update broadcast settings
- delete a live stream
- live chat
- update live broadcast settings
- remove moderator
- list streams
- manage live chat messages
- send chat message
- manage live chat moderators
- list broadcasts
- media
- list moderators
- send a message to live chat
- list live video streams
- delete chat message
- add moderator
- list messages in live chat
- delete stream
- list youtube live broadcasts
- broadcasting
- create broadcast
- list live chat messages
- update stream settings
- social
- create a new live broadcast event
- manage live video streams
- list live chat moderators
- list live streams
slug: live-streaming
source_filename: live-streaming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"YouTube Live Streaming\"\n  description: \"Workflow for managing YouTube live events including scheduling broadcasts, linking streams, managing live chat, and moderating live interactions. Designed for live event producers, streaming teams, and broadcast operators.\"\n  tags:\n    - YouTube\n    - Live Streaming\n    - Broadcasting\n    - Live Chat\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: youtube-live\n      location: ./shared/live-streaming.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: live-streaming-api\n      description: \"Unified REST API for YouTube live streaming workflows.\"\n      resources:\n        - path: /v1/broadcasts\n          name: broadcasts\n          description: \"Manage live broadcasts\"\n          operations:\n            - method: GET\n\
  \              name: list-broadcasts\n              description: \"List live broadcasts\"\n              call: \"youtube-live.list-live-broadcasts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-broadcast\n              description: \"Create a new live broadcast\"\n              call: \"youtube-live.insert-live-broadcast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-broadcast\n              description: \"Update broadcast settings\"\n              call: \"youtube-live.update-live-broadcast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-broadcast\n              description: \"Delete a broadcast\"\n              call: \"youtube-live.delete-live-broadcast\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/streams\n          name: streams\n          description: \"Manage live video streams\"\n          operations:\n            - method: GET\n              name: list-streams\n              description: \"List live streams\"\n              call: \"youtube-live.list-live-streams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-stream\n              description: \"Create a new live stream\"\n              call: \"youtube-live.insert-live-stream\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-stream\n              description: \"Update stream settings\"\n              call: \"youtube-live.update-live-stream\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-stream\n              description: \"Delete a live stream\"\n              call: \"youtube-live.delete-live-stream\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat-messages\n          name: chat-messages\n          description: \"Manage live chat messages\"\n          operations:\n            - method: GET\n              name: list-chat-messages\n              description: \"List live chat messages\"\n              call: \"youtube-live.list-live-chat-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-chat-message\n              description: \"Send a live chat message\"\n              call: \"youtube-live.insert-live-chat-message\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-chat-message\n              description: \"Delete a live chat message\"\n              call: \"youtube-live.delete-live-chat-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat-moderators\n          name: chat-moderators\n          description: \"Manage live chat moderators\"\n          operations:\n            - method: GET\n              name: list-moderators\n              description: \"List live chat moderators\"\n              call: \"youtube-live.list-live-chat-moderators\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-moderator\n              description: \"Add a live chat moderator\"\n              call: \"youtube-live.insert-live-chat-moderator\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-moderator\n              description: \"Remove a live chat moderator\"\n              call: \"youtube-live.delete-live-chat-moderator\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: live-streaming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted YouTube live streaming management.\"\n      tools:\n        - name: list-broadcasts\n          description: \"List YouTube live broadcasts\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-live.list-live-broadcasts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-broadcast\n          description: \"Create a new live broadcast event\"\n          hints:\n            readOnly: false\n     \
  \       idempotent: false\n          call: \"youtube-live.insert-live-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-broadcast\n          description: \"Update live broadcast settings\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-live.update-live-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-broadcast\n          description: \"Delete a live broadcast\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-live.delete-live-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bind-broadcast\n          description: \"Bind a broadcast to a video stream\"\n          hints:\n            readOnly: false\n            idempotent: true\n    \
  \      call: \"youtube-live.bind-live-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: transition-broadcast\n          description: \"Transition broadcast status (testing, live, complete)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-live.transition-live-broadcast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-streams\n          description: \"List live video streams\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-live.list-live-streams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-stream\n          description: \"Create a new live video stream\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-live.insert-live-stream\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-chat-messages\n          description: \"List messages in live chat\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-live.list-live-chat-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-chat-message\n          description: \"Send a message to live chat\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-live.insert-live-chat-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-chat-message\n          description: \"Delete a live chat message\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-live.delete-live-chat-message\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-moderators\n          description: \"List live chat moderators\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-live.list-live-chat-moderators\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-moderator\n          description: \"Add a live chat moderator\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-live.insert-live-chat-moderator\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-moderator\n          description: \"Remove a live chat moderator\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-live.delete-live-chat-moderator\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/live-streaming.yaml
tags:
- YouTube
- Live Streaming
- Broadcasting
- Live Chat
tools:
- description: List YouTube live broadcasts
  hints:
    idempotent: true
    readOnly: true
  name: list-broadcasts
- description: Create a new live broadcast event
  hints:
    idempotent: false
    readOnly: false
  name: create-broadcast
- description: Update live broadcast settings
  hints:
    idempotent: true
    readOnly: false
  name: update-broadcast
- description: Delete a live broadcast
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-broadcast
- description: Bind a broadcast to a video stream
  hints:
    idempotent: true
    readOnly: false
  name: bind-broadcast
- description: Transition broadcast status (testing, live, complete)
  hints:
    idempotent: false
    readOnly: false
  name: transition-broadcast
- description: List live video streams
  hints:
    idempotent: true
    readOnly: true
  name: list-streams
- description: Create a new live video stream
  hints:
    idempotent: false
    readOnly: false
  name: create-stream
- description: List messages in live chat
  hints:
    idempotent: true
    readOnly: true
  name: list-chat-messages
- description: Send a message to live chat
  hints:
    idempotent: false
    readOnly: false
  name: send-chat-message
- description: Delete a live chat message
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-chat-message
- description: List live chat moderators
  hints:
    idempotent: true
    readOnly: true
  name: list-moderators
- description: Add a live chat moderator
  hints:
    idempotent: false
    readOnly: false
  name: add-moderator
- description: Remove a live chat moderator
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-moderator
---
