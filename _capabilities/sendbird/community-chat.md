---
categories: []
consumed_apis:
- sendbird-platform
description: Workflow capability for building and managing community chat experiences with Sendbird — covering channel management, user onboarding, message delivery, and community moderation for marketplaces, communities, and social platforms.
layout: capability
name: Sendbird Community Chat
operations:
- description: List community members.
  method: GET
  name: list-members
  path: /v1/members
- description: Register a new community member.
  method: POST
  name: register-member
  path: /v1/members
- description: List chat rooms.
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Create a new chat room.
  method: POST
  name: create-room
  path: /v1/rooms
- description: List messages in a room.
  method: GET
  name: list-room-messages
  path: /v1/rooms/{channel_url}/messages
- description: Post a message to a room.
  method: POST
  name: post-message
  path: /v1/rooms/{channel_url}/messages
personas: []
provider_name: Sendbird
provider_slug: sendbird
search_terms:
- get the profile of a community member.
- register member
- list messages in a room.
- list chat rooms
- manage community chat rooms.
- temporarily mute a community member.
- create a new chat room.
- list room messages
- list community members
- register a new community member in sendbird.
- list community members.
- moderation
- community
- post a message to a room.
- ban a member from a community channel for violation of rules.
- list messages in a community chat room.
- create room
- manage messages in a chat room.
- list members of the sendbird community.
- chat
- list all community chat rooms and channels.
- register a new community member.
- post a message to a community chat room.
- list chat rooms.
- create a new community chat room or group channel.
- create chat room
- post message
- social
- moderate ban member
- list members
- get member profile
- moderate mute member
- sendbird
- manage community members.
- list rooms
slug: community-chat
source_filename: community-chat.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sendbird Community Chat\"\n  description: >-\n    Workflow capability for building and managing community chat experiences with\n    Sendbird — covering channel management, user onboarding, message delivery,\n    and community moderation for marketplaces, communities, and social platforms.\n  tags:\n    - Sendbird\n    - Community\n    - Chat\n    - Moderation\n    - Social\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SENDBIRD_API_TOKEN: SENDBIRD_API_TOKEN\n      SENDBIRD_APP_ID: SENDBIRD_APP_ID\n\ncapability:\n  consumes:\n    - import: sendbird-platform\n      location: ./shared/platform-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: sendbird-community-api\n      description: \"Unified REST API for Sendbird community chat management.\"\n      resources:\n        - path: /v1/members\n          name: members\n          description: \"Manage\
  \ community members.\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List community members.\"\n              call: \"sendbird-platform.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-member\n              description: \"Register a new community member.\"\n              call: \"sendbird-platform.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rooms\n          name: rooms\n          description: \"Manage community chat rooms.\"\n          operations:\n            - method: GET\n              name: list-rooms\n              description: \"List chat rooms.\"\n              call: \"sendbird-platform.list-group-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n            - method: POST\n              name: create-room\n              description: \"Create a new chat room.\"\n              call: \"sendbird-platform.create-group-channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rooms/{channel_url}/messages\n          name: room-messages\n          description: \"Manage messages in a chat room.\"\n          operations:\n            - method: GET\n              name: list-room-messages\n              description: \"List messages in a room.\"\n              call: \"sendbird-platform.list-messages\"\n              with:\n                channel_url: \"rest.channel_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: post-message\n              description: \"Post a message to a room.\"\n              call: \"sendbird-platform.send-message\"\n              with:\n  \
  \              channel_url: \"rest.channel_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: sendbird-community-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sendbird community management.\"\n      tools:\n        - name: list-community-members\n          description: \"List members of the Sendbird community.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sendbird-platform.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-member\n          description: \"Register a new community member in Sendbird.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sendbird-platform.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: get-member-profile\n          description: \"Get the profile of a community member.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sendbird-platform.get-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-chat-rooms\n          description: \"List all community chat rooms and channels.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sendbird-platform.list-group-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-chat-room\n          description: \"Create a new community chat room or group channel.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sendbird-platform.create-group-channel\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: list-room-messages\n          description: \"List messages in a community chat room.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sendbird-platform.list-messages\"\n          with:\n            channel_url: \"tools.channel_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-message\n          description: \"Post a message to a community chat room.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sendbird-platform.send-message\"\n          with:\n            channel_url: \"tools.channel_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: moderate-ban-member\n          description: \"Ban a member from a community channel for violation of rules.\"\n          hints:\n            readOnly: false\n            destructive: true\n\
  \            idempotent: true\n          call: \"sendbird-platform.ban-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: moderate-mute-member\n          description: \"Temporarily mute a community member.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"sendbird-platform.mute-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sendbird/refs/heads/main/capabilities/community-chat.yaml
tags:
- Sendbird
- Community
- Chat
- Moderation
- Social
tools:
- description: List members of the Sendbird community.
  hints:
    openWorld: true
    readOnly: true
  name: list-community-members
- description: Register a new community member in Sendbird.
  hints:
    openWorld: false
    readOnly: false
  name: register-member
- description: Get the profile of a community member.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-profile
- description: List all community chat rooms and channels.
  hints:
    openWorld: true
    readOnly: true
  name: list-chat-rooms
- description: Create a new community chat room or group channel.
  hints:
    openWorld: false
    readOnly: false
  name: create-chat-room
- description: List messages in a community chat room.
  hints:
    openWorld: true
    readOnly: true
  name: list-room-messages
- description: Post a message to a community chat room.
  hints:
    openWorld: false
    readOnly: false
  name: post-message
- description: Ban a member from a community channel for violation of rules.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: moderate-ban-member
- description: Temporarily mute a community member.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: moderate-mute-member
---
