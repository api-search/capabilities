---
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
- manage items within playlists
- update playlist details
- list playlist items
- manage video captions
- manage youtube playlists
- google
- playlists
- list playlists
- upload caption
- delete video
- delete playlist
- create a new playlist
- list items in a playlist
- delete caption
- list youtube videos matching criteria
- delete a playlist
- delete a video
- remove playlist item
- list captions
- list videos
- add a video to a playlist
- update video
- upload video
- video
- update caption
- social
- upload a new caption track
- update playlist
- create playlist
- upload a caption track
- update a caption track
- delete a caption track
- remove a video from a playlist
- streaming
- delete a video from youtube
- list videos matching criteria
- media
- youtube
- upload a new video to youtube
- manage youtube videos
- content management
- list caption tracks for a video
- videos
- add playlist item
- list youtube playlists
- update video metadata
- captions
- upload a new video
slug: content-management
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
