---
categories:
- content-management
consumed_apis:
- youtube-data
description: Unified workflow for managing YouTube video content lifecycle including uploading, updating, organizing into playlists, managing captions, and moderating comments. Designed for content creators, media teams, and platform administrators.
layout: capability
name: YouTube Content Management
operations:
- description: List videos matching criteria
  method: GET
  name: list-videos
  path: /v1/videos
- description: Upload a new video
  method: POST
  name: upload-video
  path: /v1/videos
- description: Update video metadata
  method: PUT
  name: update-video
  path: /v1/videos
- description: Delete a video
  method: DELETE
  name: delete-video
  path: /v1/videos
- description: List playlists
  method: GET
  name: list-playlists
  path: /v1/playlists
- description: Create a new playlist
  method: POST
  name: create-playlist
  path: /v1/playlists
- description: Update playlist details
  method: PUT
  name: update-playlist
  path: /v1/playlists
- description: Delete a playlist
  method: DELETE
  name: delete-playlist
  path: /v1/playlists
- description: List items in a playlist
  method: GET
  name: list-playlist-items
  path: /v1/playlist-items
- description: Add a video to a playlist
  method: POST
  name: add-playlist-item
  path: /v1/playlist-items
- description: Remove a video from a playlist
  method: DELETE
  name: remove-playlist-item
  path: /v1/playlist-items
- description: List caption tracks for a video
  method: GET
  name: list-captions
  path: /v1/captions
- description: Upload a caption track
  method: POST
  name: upload-caption
  path: /v1/captions
- description: Update a caption track
  method: PUT
  name: update-caption
  path: /v1/captions
- description: Delete a caption track
  method: DELETE
  name: delete-caption
  path: /v1/captions
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- playlists
- list captions
- delete caption
- delete a video
- google
- update video metadata
- update playlist
- manage youtube playlists
- manage items within playlists
- manage video captions
- upload a new video to youtube
- media
- create playlist
- upload video
- update video
- list videos
- list videos matching criteria
- list playlist items
- delete a caption track
- upload a new caption track
- content management
- video
- streaming
- delete playlist
- videos
- upload a new video
- list items in a playlist
- delete a video from youtube
- delete video
- add playlist item
- add a video to a playlist
- list caption tracks for a video
- delete a playlist
- upload a caption track
- remove playlist item
- list youtube playlists
- update a caption track
- captions
- create a new playlist
- remove a video from a playlist
- upload caption
- list youtube videos matching criteria
- update playlist details
- manage youtube videos
- social
- list playlists
- update caption
- youtube
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"YouTube Content Management\"\n  description: \"Unified workflow for managing YouTube video content lifecycle including uploading, updating, organizing into playlists, managing captions, and moderating comments. Designed for content creators, media teams, and platform administrators.\"\n  tags:\n    - YouTube\n    - Content Management\n    - Video\n    - Playlists\n    - Captions\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      YOUTUBE_API_KEY: YOUTUBE_API_KEY\n      YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: youtube-data\n      location: ./shared/data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: content-management-api\n      description: \"Unified REST API for YouTube content management workflows.\"\n      resources:\n        - path: /v1/videos\n          name: videos\n          description: \"Manage YouTube\
  \ videos\"\n          operations:\n            - method: GET\n              name: list-videos\n              description: \"List videos matching criteria\"\n              call: \"youtube-data.list-videos\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-video\n              description: \"Upload a new video\"\n              call: \"youtube-data.insert-video\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-video\n              description: \"Update video metadata\"\n              call: \"youtube-data.update-video\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-video\n              description: \"Delete a video\"\n              call: \"youtube-data.delete-video\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/playlists\n          name: playlists\n          description: \"Manage YouTube playlists\"\n          operations:\n            - method: GET\n              name: list-playlists\n              description: \"List playlists\"\n              call: \"youtube-data.list-playlists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-playlist\n              description: \"Create a new playlist\"\n              call: \"youtube-data.insert-playlist\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-playlist\n              description: \"Update playlist details\"\n              call: \"youtube-data.update-playlist\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-playlist\n              description: \"Delete a playlist\"\n              call: \"youtube-data.delete-playlist\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/playlist-items\n          name: playlist-items\n          description: \"Manage items within playlists\"\n          operations:\n            - method: GET\n              name: list-playlist-items\n              description: \"List items in a playlist\"\n              call: \"youtube-data.list-playlist-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-playlist-item\n              description: \"Add a video to a playlist\"\n              call: \"youtube-data.insert-playlist-item\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n            - method: DELETE\n              name: remove-playlist-item\n              description: \"Remove a video from a playlist\"\n              call: \"youtube-data.delete-playlist-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/captions\n          name: captions\n          description: \"Manage video captions\"\n          operations:\n            - method: GET\n              name: list-captions\n              description: \"List caption tracks for a video\"\n              call: \"youtube-data.list-captions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-caption\n              description: \"Upload a caption track\"\n              call: \"youtube-data.insert-caption\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: PUT\n              name: update-caption\n              description: \"Update a caption track\"\n              call: \"youtube-data.update-caption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-caption\n              description: \"Delete a caption track\"\n              call: \"youtube-data.delete-caption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted YouTube content management.\"\n      tools:\n        - name: list-videos\n          description: \"List YouTube videos matching criteria\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-videos\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: upload-video\n          description: \"Upload a new video to YouTube\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-video\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-video\n          description: \"Update video metadata\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.update-video\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-video\n          description: \"Delete a video from YouTube\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-data.delete-video\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-playlists\n\
  \          description: \"List YouTube playlists\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-playlists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-playlist\n          description: \"Create a new playlist\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-playlist\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-playlist\n          description: \"Update playlist details\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.update-playlist\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-playlist\n          description: \"Delete a playlist\"\n          hints:\n            readOnly: false\n         \
  \   destructive: true\n            idempotent: true\n          call: \"youtube-data.delete-playlist\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-playlist-items\n          description: \"List items in a playlist\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-playlist-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-playlist-item\n          description: \"Add a video to a playlist\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-playlist-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-playlist-item\n          description: \"Remove a video from a playlist\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent:\
  \ true\n          call: \"youtube-data.delete-playlist-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-captions\n          description: \"List caption tracks for a video\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-data.list-captions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-caption\n          description: \"Upload a new caption track\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-data.insert-caption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-caption\n          description: \"Update a caption track\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-data.update-caption\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: delete-caption\n          description: \"Delete a caption track\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-data.delete-caption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/content-management.yaml
tags:
- YouTube
- Content Management
- Video
- Playlists
- Captions
tools:
- description: List YouTube videos matching criteria
  hints:
    idempotent: true
    readOnly: true
  name: list-videos
- description: Upload a new video to YouTube
  hints:
    idempotent: false
    readOnly: false
  name: upload-video
- description: Update video metadata
  hints:
    idempotent: true
    readOnly: false
  name: update-video
- description: Delete a video from YouTube
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-video
- description: List YouTube playlists
  hints:
    idempotent: true
    readOnly: true
  name: list-playlists
- description: Create a new playlist
  hints:
    idempotent: false
    readOnly: false
  name: create-playlist
- description: Update playlist details
  hints:
    idempotent: true
    readOnly: false
  name: update-playlist
- description: Delete a playlist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-playlist
- description: List items in a playlist
  hints:
    idempotent: true
    readOnly: true
  name: list-playlist-items
- description: Add a video to a playlist
  hints:
    idempotent: false
    readOnly: false
  name: add-playlist-item
- description: Remove a video from a playlist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-playlist-item
- description: List caption tracks for a video
  hints:
    idempotent: true
    readOnly: true
  name: list-captions
- description: Upload a new caption track
  hints:
    idempotent: false
    readOnly: false
  name: upload-caption
- description: Update a caption track
  hints:
    idempotent: true
    readOnly: false
  name: update-caption
- description: Delete a caption track
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-caption
---
