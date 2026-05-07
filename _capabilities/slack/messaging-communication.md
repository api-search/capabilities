---
categories:
- messaging
consumed_apis: []
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
- list files.
- post a message.
- list stars
- post a message to a channel.
- post message
- manage bookmarks
- manage reminders
- file management.
- slack
- search workspace.
- list emoji
- productivity
- communication
- bots
- collaboration
- pin a message.
- list conversations
- manage channel bookmarks.
- message management.
- manage lists
- t1
- add pin
- conversation management.
- chat
- list conversations.
- add a reaction.
- search messages
- list files
- manage canvases
- manage reminders.
- list custom emoji.
- add reaction
- search
- manage canvases.
- team communication
- messaging
- manage lists.
- search messages and files.
- list starred items.
slug: messaging-communication
source_filename: messaging-communication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Slack Messaging and Communication\n  description: Unified workflow for messaging and communication including posting messages, managing conversations, sharing\n    files, reacting, searching, and organizing with pins and stars. Used by app developers building communication integrations.\n  tags:\n  - Slack\n  - Messaging\n  - Communication\n  - Chat\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SLACK_BOT_TOKEN: SLACK_BOT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name:\
  \ list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name:\
  \ api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n\
  \      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n\
  \    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: messaging-api\n    description: Unified REST API for Slack messaging and communication.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Message management.\n      operations:\n      - method: POST\n        name: post-message\n        description: Post a message.\n        call: slack-chat.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversations\n      name: conversations\n      description: Conversation management.\n      operations:\n      - method: GET\n        name: list-conversations\n        description: List conversations.\n        call: slack-conversations.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files\n      name: files\n      description: File management.\n      operations:\n\
  \      - method: GET\n        name: list-files\n        description: List files.\n        call: slack-files.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Search messages and files.\n      operations:\n      - method: GET\n        name: search\n        description: Search workspace.\n        call: slack-search.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted Slack messaging.\n    tools:\n    - name: post-message\n      description: Post a message to a channel.\n      hints:\n        readOnly: false\n      call: slack-chat.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conversations\n      description: List conversations.\n      hints:\n        readOnly: true\n      call: slack-conversations.list\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-files\n      description: List files.\n      hints:\n        readOnly: true\n      call: slack-files.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-pin\n      description: Pin a message.\n      hints:\n        readOnly: false\n      call: slack-pins.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-reaction\n      description: Add a reaction.\n      hints:\n        readOnly: false\n      call: slack-reactions.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stars\n      description: List starred items.\n      hints:\n        readOnly: true\n      call: slack-stars.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-messages\n      description: Search messages and files.\n      hints:\n        readOnly: true\n      call: slack-search.list\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-emoji\n      description: List custom emoji.\n      hints:\n        readOnly: true\n      call: slack-emoji.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-bookmarks\n      description: Manage channel bookmarks.\n      hints:\n        readOnly: false\n      call: slack-bookmarks.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-canvases\n      description: Manage canvases.\n      hints:\n        readOnly: false\n      call: slack-canvases.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-lists\n      description: Manage lists.\n      hints:\n        readOnly: false\n      call: slack-lists.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-reminders\n      description: Manage reminders.\n      hints:\n        readOnly: false\n    \
  \  call: slack-reminders.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
