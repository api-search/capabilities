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
- search workspace.
- slack
- add reaction
- search
- manage lists
- add a reaction.
- manage reminders
- productivity
- manage channel bookmarks.
- team communication
- pin a message.
- list emoji
- manage reminders.
- collaboration
- manage canvases
- manage lists.
- conversation management.
- list custom emoji.
- list files.
- manage canvases.
- t1
- file management.
- post a message to a channel.
- message management.
- list conversations.
- add pin
- list files
- list stars
- communication
- list starred items.
- list conversations
- search messages
- messaging
- chat
- post a message.
- post message
- bots
- manage bookmarks
- search messages and files.
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
