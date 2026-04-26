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
- manage channel bookmarks.
- add reaction
- manage reminders
- chat
- list conversations.
- collaboration
- search messages
- post message
- message management.
- post a message.
- manage canvases.
- messaging
- list emoji
- list conversations
- team communication
- search workspace.
- list starred items.
- productivity
- manage reminders.
- list stars
- list files
- manage bookmarks
- search messages and files.
- search
- file management.
- manage lists
- add pin
- manage canvases
- list files.
- add a reaction.
- bots
- conversation management.
- slack
- list custom emoji.
- communication
- manage lists.
- post a message to a channel.
- pin a message.
- t1
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
