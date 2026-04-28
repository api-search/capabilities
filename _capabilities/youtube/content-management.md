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
- update video metadata
- delete a caption track
- videos
- delete playlist
- captions
- remove a video from a playlist
- list captions
- create a new playlist
- update a caption track
- list youtube playlists
- list videos matching criteria
- add a video to a playlist
- remove playlist item
- update caption
- list items in a playlist
- youtube
- update playlist details
- update playlist
- list youtube videos matching criteria
- google
- delete a video
- list playlists
- media
- upload a new video to youtube
- manage items within playlists
- streaming
- create playlist
- manage video captions
- playlists
- list videos
- manage youtube videos
- upload a new caption track
- update video
- list caption tracks for a video
- content management
- add playlist item
- delete a playlist
- upload a caption track
- video
- delete video
- upload a new video
- social
- upload caption
- list playlist items
- upload video
- delete a video from youtube
- manage youtube playlists
- delete caption
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
