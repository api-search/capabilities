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
- manage live video streams
- delete a live broadcast
- transition broadcast status (testing, live, complete)
- create stream
- create a new live stream
- create a new live broadcast
- transition broadcast
- create a new live video stream
- list chat messages
- manage live chat messages
- manage live chat moderators
- create broadcast
- delete a broadcast
- list moderators
- add moderator
- send a live chat message
- videos
- list live chat messages
- update broadcast
- remove a live chat moderator
- video
- update broadcast settings
- delete a live chat message
- update live broadcast settings
- bind broadcast
- broadcasting
- list live chat moderators
- live chat
- list streams
- delete chat message
- live streaming
- list youtube live broadcasts
- bind a broadcast to a video stream
- create a new live broadcast event
- manage live broadcasts
- send chat message
- media
- add a live chat moderator
- social
- update stream settings
- list live video streams
- update stream
- streaming
- delete broadcast
- send a message to live chat
- list live streams
- google
- list messages in live chat
- list live broadcasts
- youtube
- delete stream
- delete a live stream
- remove moderator
- list broadcasts
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
