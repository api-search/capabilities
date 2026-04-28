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
- create a new live broadcast
- manage live broadcasts
- list live chat messages
- create a new live stream
- broadcasting
- create stream
- delete broadcast
- send a live chat message
- manage live chat moderators
- remove moderator
- update live broadcast settings
- list messages in live chat
- google
- list live video streams
- create broadcast
- delete stream
- update stream
- add a live chat moderator
- transition broadcast
- send chat message
- list live chat moderators
- add moderator
- bind broadcast
- remove a live chat moderator
- social
- manage live video streams
- delete a broadcast
- delete a live stream
- update broadcast
- video
- youtube
- create a new live video stream
- update stream settings
- live streaming
- manage live chat messages
- list moderators
- list broadcasts
- bind a broadcast to a video stream
- transition broadcast status (testing, live, complete)
- live chat
- list live broadcasts
- list streams
- media
- delete chat message
- send a message to live chat
- list live streams
- videos
- update broadcast settings
- list chat messages
- list youtube live broadcasts
- create a new live broadcast event
- delete a live chat message
- delete a live broadcast
- streaming
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
