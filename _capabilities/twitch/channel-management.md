---
categories: []
consumed_apis: []
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
- get chat settings for a broadcaster
- chat message sending
- send a message to channel chat
- streaming
- create a new poll
- video
- subscriber information
- get broadcaster subscriptions
- create a new poll on a broadcaster's channel
- channel configuration
- send a message to a twitch channel chat
- channel management
- get channel information
- create clip
- get channel subscriber information
- create poll
- get active and past polls for a broadcaster
- send chat message
- get the current chat settings for a broadcaster's channel
- gaming
- get channel information and configuration for a broadcaster
- chat
- entertainment
- live video
- get subscriber information for a broadcaster's channel
- get polls
- create a clip from a broadcaster's live stream
- get active and past polls
- broadcasting
- get chat settings
- twitch
- moderation
- chat configuration
- channel polls management
slug: channel-management
source_filename: channel-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twitch Channel Management\n  description: Workflow capability for Twitch broadcasters to manage their channels, including chat configuration, polls,\n    subscriptions, moderation, and channel points. Used by broadcaster tools, chatbots, and channel management dashboards.\n  tags:\n  - Twitch\n  - Channel Management\n  - Broadcasting\n  - Chat\n  - Moderation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWITCH_ACCESS_TOKEN: TWITCH_ACCESS_TOKEN\n    TWITCH_CLIENT_ID: TWITCH_CLIENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: twitch-helix\n    baseUri: https://api.twitch.tv/helix\n    description: Twitch Helix REST API\n    authentication:\n      type: bearer\n      token: '{{TWITCH_ACCESS_TOKEN}}'\n    resources:\n    - name: streams\n      path: /streams\n      description: Live stream information\n      operations:\n      - name: get-streams\n        method: GET\n        description:\
  \ Get information about active streams\n        inputParameters:\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter by game/category ID\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Filter by stream language\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: Filter by user ID\n        - name: user_login\n          in: query\n          type: string\n          required: false\n          description: Filter by user login name\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      description: Channel\
  \ information and management\n      operations:\n      - name: get-channel-information\n        method: GET\n        description: Get information about one or more channels\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the broadcaster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User information and management\n      operations:\n      - name: get-users\n        method: GET\n        description: Get information about users\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: User ID\n        - name: login\n          in: query\n          type: string\n          required: false\n          description: User login name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clips\n      path: /clips\n      description: Clip creation and retrieval\n      operations:\n      - name: get-clips\n        method: GET\n        description: Get clips for a broadcaster, game, or by clip ID\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: false\n          description: Filter clips by broadcaster\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter clips by game\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Clip ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-clip\n        method: POST\n        description: Create a clip from a live stream\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: ID of the broadcaster to clip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos\n      path: /videos\n      description: Video management\n      operations:\n      - name: get-videos\n        method: GET\n        description: Get video information by ID, user, or game\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Video ID\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: Filter by user ID\n        - name: game_id\n          in: query\n         \
  \ type: string\n          required: false\n          description: Filter by game ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-channels\n      path: /search/channels\n      description: Search for channels\n      operations:\n      - name: search-channels\n        method: GET\n        description: Search for channels by name\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: live_only\n          in: query\n          type: boolean\n          required: false\n          description: Filter to live-only\
  \ channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: games\n      path: /games\n      description: Game/category information\n      operations:\n      - name: get-games\n        method: GET\n        description: Get game information by ID or name\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Game ID\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Game name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-top-games\n        method: GET\n        description: Get the most popular games/categories on Twitch\n        inputParameters:\n        - name: first\n          in: query\n          type: integer\n          required: false\n      \
  \    description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat\n      path: /chat\n      description: Chat settings and emotes\n      operations:\n      - name: get-chat-settings\n        method: GET\n        description: Get chat settings for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-chat-message\n        method: POST\n        description: Send a chat message on behalf of a user\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: ID of the channel to send to\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            broadcaster_id: '{{tools.broadcaster_id}}'\n            sender_id: '{{tools.sender_id}}'\n            message: '{{tools.message}}'\n    - name: subscriptions\n      path: /subscriptions\n      description: Subscription information\n      operations:\n      - name: get-broadcaster-subscriptions\n        method: GET\n        description: Get subscription information for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ polls\n      path: /polls\n      description: Channel polls\n      operations:\n      - name: get-polls\n        method: GET\n        description: Get active or past polls for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-poll\n        method: POST\n        description: Create a poll for a broadcaster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            broadcaster_id: '{{tools.broadcaster_id}}'\n            title: '{{tools.title}}'\n            choices: '{{tools.choices}}'\n            duration: '{{tools.duration}}'\n    - name: analytics\n      path: /analytics/games\n\
  \      description: Game analytics\n      operations:\n      - name: get-game-analytics\n        method: GET\n        description: Get analytics data for game developers\n        inputParameters:\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter by game ID\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Report type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: twitch-channel-management-api\n    description: Unified REST API for Twitch channel management.\n    resources:\n    - path: /v1/channel\n      name: channel\n      description: Channel configuration\n      operations:\n      - method: GET\n        name: get-channel-information\n        description: Get channel information\n        call: twitch-helix.get-channel-information\n\
  \        with:\n          broadcaster_id: rest.broadcaster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat-settings\n      name: chat-settings\n      description: Chat configuration\n      operations:\n      - method: GET\n        name: get-chat-settings\n        description: Get chat settings for a broadcaster\n        call: twitch-helix.get-chat-settings\n        with:\n          broadcaster_id: rest.broadcaster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/polls\n      name: polls\n      description: Channel polls management\n      operations:\n      - method: GET\n        name: get-polls\n        description: Get active and past polls\n        call: twitch-helix.get-polls\n        with:\n          broadcaster_id: rest.broadcaster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-poll\n        description: Create a\
  \ new poll\n        call: twitch-helix.create-poll\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscriber information\n      operations:\n      - method: GET\n        name: get-broadcaster-subscriptions\n        description: Get channel subscriber information\n        call: twitch-helix.get-broadcaster-subscriptions\n        with:\n          broadcaster_id: rest.broadcaster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat-messages\n      name: chat-messages\n      description: Chat message sending\n      operations:\n      - method: POST\n        name: send-chat-message\n        description: Send a message to channel chat\n        call: twitch-helix.send-chat-message\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: twitch-channel-management-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Twitch channel management.\n    tools:\n    - name: get-channel-information\n      description: Get channel information and configuration for a broadcaster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-channel-information\n      with:\n        broadcaster_id: tools.broadcaster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-chat-settings\n      description: Get the current chat settings for a broadcaster's channel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-chat-settings\n      with:\n        broadcaster_id: tools.broadcaster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-chat-message\n      description: Send a message to a Twitch channel chat\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twitch-helix.send-chat-message\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-polls\n      description: Get active and past polls for a broadcaster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-polls\n      with:\n        broadcaster_id: tools.broadcaster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-poll\n      description: Create a new poll on a broadcaster's channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twitch-helix.create-poll\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-broadcaster-subscriptions\n      description: Get subscriber information for a broadcaster's channel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-broadcaster-subscriptions\n      with:\n        broadcaster_id: tools.broadcaster_id\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: create-clip\n      description: Create a clip from a broadcaster's live stream\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twitch-helix.create-clip\n      with:\n        broadcaster_id: tools.broadcaster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
