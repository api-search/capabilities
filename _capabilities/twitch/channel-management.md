---
categories: []
consumed_apis:
- twitch-helix
description: Workflow capability for Twitch broadcasters to manage their channels, including chat configuration, polls, subscriptions, moderation, and channel points. Used by broadcaster tools, chatbots, and channel management dashboards.
layout: capability
name: Twitch Channel Management
operations:
- description: Get channel information
  method: GET
  name: get-channel-information
  path: /v1/channel
- description: Get chat settings for a broadcaster
  method: GET
  name: get-chat-settings
  path: /v1/chat-settings
- description: Get active and past polls
  method: GET
  name: get-polls
  path: /v1/polls
- description: Create a new poll
  method: POST
  name: create-poll
  path: /v1/polls
- description: Get channel subscriber information
  method: GET
  name: get-broadcaster-subscriptions
  path: /v1/subscriptions
- description: Send a message to channel chat
  method: POST
  name: send-chat-message
  path: /v1/chat-messages
personas: []
provider_name: Twitch
provider_slug: twitch
search_terms:
- get the current chat settings for a broadcaster's channel
- get broadcaster subscriptions
- send a message to channel chat
- create a clip from a broadcaster's live stream
- get channel subscriber information
- chat message sending
- create clip
- channel management
- get chat settings
- get active and past polls for a broadcaster
- chat configuration
- get channel information
- channel polls management
- streaming
- get chat settings for a broadcaster
- create poll
- chat
- entertainment
- create a new poll
- send a message to a twitch channel chat
- get active and past polls
- get channel information and configuration for a broadcaster
- channel configuration
- gaming
- live video
- send chat message
- get polls
- broadcasting
- video
- get subscriber information for a broadcaster's channel
- subscriber information
- moderation
- create a new poll on a broadcaster's channel
- twitch
slug: channel-management
source_filename: channel-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Twitch Channel Management\"\n  description: >-\n    Workflow capability for Twitch broadcasters to manage their channels,\n    including chat configuration, polls, subscriptions, moderation, and\n    channel points. Used by broadcaster tools, chatbots, and channel\n    management dashboards.\n  tags:\n    - Twitch\n    - Channel Management\n    - Broadcasting\n    - Chat\n    - Moderation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWITCH_ACCESS_TOKEN: TWITCH_ACCESS_TOKEN\n      TWITCH_CLIENT_ID: TWITCH_CLIENT_ID\n\ncapability:\n  consumes:\n    - import: twitch-helix\n      location: ./shared/helix.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: twitch-channel-management-api\n      description: \"Unified REST API for Twitch channel management.\"\n      resources:\n        - path: /v1/channel\n          name: channel\n          description: \"Channel\
  \ configuration\"\n          operations:\n            - method: GET\n              name: get-channel-information\n              description: \"Get channel information\"\n              call: \"twitch-helix.get-channel-information\"\n              with:\n                broadcaster_id: \"rest.broadcaster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat-settings\n          name: chat-settings\n          description: \"Chat configuration\"\n          operations:\n            - method: GET\n              name: get-chat-settings\n              description: \"Get chat settings for a broadcaster\"\n              call: \"twitch-helix.get-chat-settings\"\n              with:\n                broadcaster_id: \"rest.broadcaster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/polls\n          name: polls\n          description: \"Channel polls\
  \ management\"\n          operations:\n            - method: GET\n              name: get-polls\n              description: \"Get active and past polls\"\n              call: \"twitch-helix.get-polls\"\n              with:\n                broadcaster_id: \"rest.broadcaster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-poll\n              description: \"Create a new poll\"\n              call: \"twitch-helix.create-poll\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Subscriber information\"\n          operations:\n            - method: GET\n              name: get-broadcaster-subscriptions\n              description: \"Get channel subscriber information\"\n              call: \"twitch-helix.get-broadcaster-subscriptions\"\n    \
  \          with:\n                broadcaster_id: \"rest.broadcaster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat-messages\n          name: chat-messages\n          description: \"Chat message sending\"\n          operations:\n            - method: POST\n              name: send-chat-message\n              description: \"Send a message to channel chat\"\n              call: \"twitch-helix.send-chat-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: twitch-channel-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Twitch channel management.\"\n      tools:\n        - name: get-channel-information\n          description: \"Get channel information and configuration for a broadcaster\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"twitch-helix.get-channel-information\"\n          with:\n            broadcaster_id: \"tools.broadcaster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-chat-settings\n          description: \"Get the current chat settings for a broadcaster's channel\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-chat-settings\"\n          with:\n            broadcaster_id: \"tools.broadcaster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-chat-message\n          description: \"Send a message to a Twitch channel chat\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twitch-helix.send-chat-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-polls\n\
  \          description: \"Get active and past polls for a broadcaster\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-polls\"\n          with:\n            broadcaster_id: \"tools.broadcaster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-poll\n          description: \"Create a new poll on a broadcaster's channel\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twitch-helix.create-poll\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-broadcaster-subscriptions\n          description: \"Get subscriber information for a broadcaster's channel\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-broadcaster-subscriptions\"\n          with:\n            broadcaster_id:\
  \ \"tools.broadcaster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-clip\n          description: \"Create a clip from a broadcaster's live stream\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"twitch-helix.create-clip\"\n          with:\n            broadcaster_id: \"tools.broadcaster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitch/refs/heads/main/capabilities/channel-management.yaml
tags:
- Twitch
- Channel Management
- Broadcasting
- Chat
- Moderation
tools:
- description: Get channel information and configuration for a broadcaster
  hints:
    openWorld: true
    readOnly: true
  name: get-channel-information
- description: Get the current chat settings for a broadcaster's channel
  hints:
    openWorld: true
    readOnly: true
  name: get-chat-settings
- description: Send a message to a Twitch channel chat
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-chat-message
- description: Get active and past polls for a broadcaster
  hints:
    openWorld: true
    readOnly: true
  name: get-polls
- description: Create a new poll on a broadcaster's channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-poll
- description: Get subscriber information for a broadcaster's channel
  hints:
    openWorld: true
    readOnly: true
  name: get-broadcaster-subscriptions
- description: Create a clip from a broadcaster's live stream
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-clip
---
