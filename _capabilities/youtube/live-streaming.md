---
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
- manage live broadcasts
- remove moderator
- transition broadcast
- remove a live chat moderator
- create a new live video stream
- create a new live broadcast
- live streaming
- bind broadcast
- list live chat moderators
- delete a live chat message
- list broadcasts
- add moderator
- delete a live broadcast
- delete a live stream
- list streams
- delete stream
- list moderators
- update stream
- send chat message
- update live broadcast settings
- streaming
- list live streams
- list live chat messages
- videos
- add a live chat moderator
- list live video streams
- list messages in live chat
- send a message to live chat
- youtube
- update broadcast
- video
- manage live chat messages
- list youtube live broadcasts
- google
- delete broadcast
- create stream
- social
- bind a broadcast to a video stream
- live chat
- delete a broadcast
- delete chat message
- transition broadcast status (testing, live, complete)
- list chat messages
- list live broadcasts
- update broadcast settings
- manage live chat moderators
- create a new live stream
- update stream settings
- create a new live broadcast event
- media
- manage live video streams
- broadcasting
- create broadcast
- send a live chat message
slug: live-streaming
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
