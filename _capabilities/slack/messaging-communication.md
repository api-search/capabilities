---
consumed_apis:
- slack-chat
- slack-conversations
- slack-files
- slack-pins
- slack-reactions
- slack-stars
- slack-search
- slack-emoji
- slack-bookmarks
- slack-canvases
- slack-lists
- slack-reminders
description: Unified workflow for messaging and communication including posting messages, managing conversations, sharing files, reacting, searching, and organizing with pins and stars. Used by app developers building communication integrations.
layout: capability
name: Slack Messaging and Communication
operations:
- description: Post a message.
  method: POST
  name: post-message
  path: /v1/messages
- description: List conversations.
  method: GET
  name: list-conversations
  path: /v1/conversations
- description: List files.
  method: GET
  name: list-files
  path: /v1/files
- description: Search workspace.
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: Slack
provider_slug: slack
search_terms:
- post a message.
- add a reaction.
- manage lists.
- manage bookmarks
- list conversations.
- pin a message.
- add pin
- search messages
- messaging
- manage reminders.
- manage canvases
- manage lists
- list starred items.
- conversation management.
- productivity
- post a message to a channel.
- list custom emoji.
- team communication
- collaboration
- search
- list conversations
- list stars
- manage canvases.
- slack
- bots
- communication
- search workspace.
- add reaction
- file management.
- message management.
- list files.
- list files
- search messages and files.
- chat
- post message
- t1
- manage reminders
- manage channel bookmarks.
- list emoji
slug: messaging-communication
tags:
- Slack
- Messaging
- Communication
- Chat
tools:
- description: Post a message to a channel.
  hints:
    readOnly: false
  name: post-message
- description: List conversations.
  hints:
    readOnly: true
  name: list-conversations
- description: List files.
  hints:
    readOnly: true
  name: list-files
- description: Pin a message.
  hints:
    readOnly: false
  name: add-pin
- description: Add a reaction.
  hints:
    readOnly: false
  name: add-reaction
- description: List starred items.
  hints:
    readOnly: true
  name: list-stars
- description: Search messages and files.
  hints:
    readOnly: true
  name: search-messages
- description: List custom emoji.
  hints:
    readOnly: true
  name: list-emoji
- description: Manage channel bookmarks.
  hints:
    readOnly: false
  name: manage-bookmarks
- description: Manage canvases.
  hints:
    readOnly: false
  name: manage-canvases
- description: Manage lists.
  hints:
    readOnly: false
  name: manage-lists
- description: Manage reminders.
  hints:
    readOnly: false
  name: manage-reminders
---
