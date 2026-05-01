---
categories: []
consumed_apis:
- youtube-data
description: Workflow for managing community interactions including comments, comment threads, subscriptions, and channel management. Designed for community managers, social media teams, and content moderators.
layout: capability
name: YouTube Community Engagement
operations:
- description: List comments
  method: GET
  name: list-comments
  path: /v1/comments
- description: Post a new comment
  method: POST
  name: create-comment
  path: /v1/comments
- description: Update a comment
  method: PUT
  name: update-comment
  path: /v1/comments
- description: Delete a comment
  method: DELETE
  name: delete-comment
  path: /v1/comments
- description: List comment threads
  method: GET
  name: list-comment-threads
  path: /v1/comment-threads
- description: Create a new comment thread
  method: POST
  name: create-comment-thread
  path: /v1/comment-threads
- description: Update a comment thread
  method: PUT
  name: update-comment-thread
  path: /v1/comment-threads
- description: List subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Subscribe to a channel
  method: POST
  name: subscribe
  path: /v1/subscriptions
- description: Unsubscribe from a channel
  method: DELETE
  name: unsubscribe
  path: /v1/subscriptions
- description: List channels
  method: GET
  name: list-channels
  path: /v1/channels
- description: Update channel settings
  method: PUT
  name: update-channel
  path: /v1/channels
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- list channels
- list channel subscriptions
- create comment
- google
- subscribe to channel
- moderation
- manage channel information
- unsubscribe from a youtube channel
- subscribe to a channel
- media
- update comment
- manage comment threads
- list comment threads
- update comment thread
- manage individual comments
- video
- streaming
- list comments
- update a comment
- manage channel subscriptions
- set moderation status on comments
- delete a comment
- videos
- subscribe to a youtube channel
- list youtube channels
- unsubscribe from a channel
- update channel
- list comments on a video or channel
- subscribe
- set moderation status
- unsubscribe
- community
- unsubscribe from channel
- social
- update an existing comment
- update channel settings
- subscriptions
- create a new comment thread
- comments
- delete comment
- create comment thread
- update a comment thread
- youtube
- list subscriptions
- post a new comment
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"YouTube Community Engagement\"\n  description: \"Workflow for managing community interactions including comments, comment threads, subscriptions, and channel management. Designed for community managers, social media teams, and content moderators.\"\n  tags:\n    - YouTube\n    - Community\n    - Comments\n    - Subscriptions\n    - Moderation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      YOUTUBE_API_KEY: YOUTUBE_API_KEY\n      YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: youtube-data\n      location: ./shared/data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: community-engagement-api\n      description: \"Unified REST API for YouTube community engagement workflows.\"\n      resources:\n        - path: /v1/comments\n          name: comments\n          description: \"Manage individual comments\"\n       \
  \   operations:\n            - method: GET\n              name: list-comments\n              description: \"List comments\"\n              call: \"youtube-data.list-comments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-comment\n              description: \"Post a new comment\"\n              call: \"youtube-data.insert-comment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-comment\n              description: \"Update a comment\"\n              call: \"youtube-data.update-comment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-comment\n              description: \"Delete a comment\"\n              call: \"youtube-data.delete-comment\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/comment-threads\n          name: comment-threads\n          description: \"Manage comment threads\"\n          operations:\n            - method: GET\n              name: list-comment-threads\n              description: \"List comment threads\"\n              call: \"youtube-data.list-comment-threads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-comment-thread\n              description: \"Create a new comment thread\"\n              call: \"youtube-data.insert-comment-thread\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-comment-thread\n              description: \"Update a comment thread\"\n              call: \"youtube-data.update-comment-thread\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Manage channel subscriptions\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List subscriptions\"\n              call: \"youtube-data.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: subscribe\n              description: \"Subscribe to a channel\"\n              call: \"youtube-data.insert-subscription\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: unsubscribe\n              description: \"Unsubscribe from a channel\"\n              call: \"youtube-data.delete-subscription\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Manage channel information\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List channels\"\n              call: \"youtube-data.list-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-channel\n              description: \"Update channel settings\"\n              call: \"youtube-data.update-channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: community-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted YouTube community engagement.\"\n      tools:\n        - name: list-comments\n          description: \"List comments on a video or channel\"\n    \
  \      hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-comment\n          description: \"Post a new comment\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-comment\n          description: \"Update an existing comment\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.update-comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-comment\n          description: \"Delete a comment\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call:\
  \ \"youtube-data.delete-comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-moderation-status\n          description: \"Set moderation status on comments\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.set-comment-moderation-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-comment-threads\n          description: \"List comment threads\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-comment-threads\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-comment-thread\n          description: \"Create a new comment thread\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-comment-thread\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List channel subscriptions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-to-channel\n          description: \"Subscribe to a YouTube channel\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-subscription\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unsubscribe-from-channel\n          description: \"Unsubscribe from a YouTube channel\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-data.delete-subscription\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-channels\n          description: \"List YouTube channels\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-channel\n          description: \"Update channel settings\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.update-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/community-engagement.yaml
tags:
- YouTube
- Community
- Comments
- Subscriptions
- Moderation
tools:
- description: List comments on a video or channel
  hints:
    idempotent: true
    readOnly: true
  name: list-comments
- description: Post a new comment
  hints:
    idempotent: false
    readOnly: false
  name: create-comment
- description: Update an existing comment
  hints:
    idempotent: true
    readOnly: false
  name: update-comment
- description: Delete a comment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-comment
- description: Set moderation status on comments
  hints:
    idempotent: true
    readOnly: false
  name: set-moderation-status
- description: List comment threads
  hints:
    idempotent: true
    readOnly: true
  name: list-comment-threads
- description: Create a new comment thread
  hints:
    idempotent: false
    readOnly: false
  name: create-comment-thread
- description: List channel subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: Subscribe to a YouTube channel
  hints:
    idempotent: false
    readOnly: false
  name: subscribe-to-channel
- description: Unsubscribe from a YouTube channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unsubscribe-from-channel
- description: List YouTube channels
  hints:
    idempotent: true
    readOnly: true
  name: list-channels
- description: Update channel settings
  hints:
    idempotent: true
    readOnly: false
  name: update-channel
---
