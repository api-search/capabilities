---
categories:
- messaging
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
- post a message to a channel.
- list files
- list stars
- manage reminders
- list conversations.
- manage reminders.
- search
- post message
- search workspace.
- communication
- collaboration
- post a message.
- list custom emoji.
- list emoji
- slack
- search messages
- list conversations
- add reaction
- search messages and files.
- manage channel bookmarks.
- manage bookmarks
- manage lists.
- manage canvases.
- productivity
- add a reaction.
- messaging
- pin a message.
- manage canvases
- list files.
- t1
- manage lists
- team communication
- add pin
- conversation management.
- message management.
- list starred items.
- chat
- file management.
- bots
slug: messaging-communication
source_filename: messaging-communication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Slack Messaging and Communication\"\n  description: \"Unified workflow for messaging and communication including posting messages, managing conversations, sharing files, reacting, searching, and organizing with pins and stars. Used by app developers building communication integrations.\"\n  tags:\n    - Slack\n    - Messaging\n    - Communication\n    - Chat\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SLACK_BOT_TOKEN: SLACK_BOT_TOKEN\n\ncapability:\n  consumes:\n    - import: slack-chat\n      location: ./shared/chat.yaml\n    - import: slack-conversations\n      location: ./shared/conversations.yaml\n    - import: slack-files\n      location: ./shared/files.yaml\n    - import: slack-pins\n      location: ./shared/pins.yaml\n    - import: slack-reactions\n      location: ./shared/reactions.yaml\n    - import: slack-stars\n      location: ./shared/stars.yaml\n    - import:\
  \ slack-search\n      location: ./shared/search.yaml\n    - import: slack-emoji\n      location: ./shared/emoji.yaml\n    - import: slack-bookmarks\n      location: ./shared/bookmarks.yaml\n    - import: slack-canvases\n      location: ./shared/canvases.yaml\n    - import: slack-lists\n      location: ./shared/lists.yaml\n    - import: slack-reminders\n      location: ./shared/reminders.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: messaging-api\n      description: \"Unified REST API for Slack messaging and communication.\"\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: \"Message management.\"\n          operations:\n            - method: POST\n              name: post-message\n              description: \"Post a message.\"\n              call: \"slack-chat.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/conversations\n          name:\
  \ conversations\n          description: \"Conversation management.\"\n          operations:\n            - method: GET\n              name: list-conversations\n              description: \"List conversations.\"\n              call: \"slack-conversations.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/files\n          name: files\n          description: \"File management.\"\n          operations:\n            - method: GET\n              name: list-files\n              description: \"List files.\"\n              call: \"slack-files.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Search messages and files.\"\n          operations:\n            - method: GET\n              name: search\n              description: \"Search workspace.\"\n              call: \"slack-search.list\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Slack messaging.\"\n      tools:\n        - name: post-message\n          description: \"Post a message to a channel.\"\n          hints:\n            readOnly: false\n          call: \"slack-chat.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-conversations\n          description: \"List conversations.\"\n          hints:\n            readOnly: true\n          call: \"slack-conversations.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-files\n          description: \"List files.\"\n          hints:\n            readOnly: true\n          call: \"slack-files.list\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: add-pin\n          description: \"Pin a message.\"\n          hints:\n            readOnly: false\n          call: \"slack-pins.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-reaction\n          description: \"Add a reaction.\"\n          hints:\n            readOnly: false\n          call: \"slack-reactions.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stars\n          description: \"List starred items.\"\n          hints:\n            readOnly: true\n          call: \"slack-stars.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-messages\n          description: \"Search messages and files.\"\n          hints:\n            readOnly: true\n          call: \"slack-search.list\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-emoji\n          description: \"List custom emoji.\"\n          hints:\n            readOnly: true\n          call: \"slack-emoji.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-bookmarks\n          description: \"Manage channel bookmarks.\"\n          hints:\n            readOnly: false\n          call: \"slack-bookmarks.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-canvases\n          description: \"Manage canvases.\"\n          hints:\n            readOnly: false\n          call: \"slack-canvases.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-lists\n          description: \"Manage lists.\"\n          hints:\n            readOnly: false\n          call: \"slack-lists.list\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: manage-reminders\n          description: \"Manage reminders.\"\n          hints:\n            readOnly: false\n          call: \"slack-reminders.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/slack/refs/heads/main/capabilities/messaging-communication.yaml
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
