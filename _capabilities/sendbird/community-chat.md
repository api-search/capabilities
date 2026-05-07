---
categories: []
consumed_apis: []
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
- list chat rooms
- manage community members.
- post message
- register a new community member in sendbird.
- moderate ban member
- post a message to a community chat room.
- list messages in a room.
- manage community chat rooms.
- list chat rooms.
- sendbird
- ban a member from a community channel for violation of rules.
- list community members
- list members
- post a message to a room.
- register a new community member.
- community
- create a new chat room.
- list members of the sendbird community.
- create chat room
- list all community chat rooms and channels.
- list messages in a community chat room.
- create room
- list community members.
- chat
- manage messages in a chat room.
- register member
- get member profile
- list room messages
- list rooms
- moderate mute member
- social
- moderation
- create a new community chat room or group channel.
- get the profile of a community member.
- temporarily mute a community member.
slug: community-chat
source_filename: community-chat.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sendbird Community Chat\n  description: Workflow capability for building and managing community chat experiences with Sendbird — covering channel management,\n    user onboarding, message delivery, and community moderation for marketplaces, communities, and social platforms.\n  tags:\n  - Sendbird\n  - Community\n  - Chat\n  - Moderation\n  - Social\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SENDBIRD_API_TOKEN: SENDBIRD_API_TOKEN\n    SENDBIRD_APP_ID: SENDBIRD_APP_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: sendbird-platform\n    baseUri: https://api-{{SENDBIRD_APP_ID}}.sendbird.com/v3\n    description: Sendbird Platform API for managing in-app chat.\n    authentication:\n      type: apikey\n      key: Api-Token\n      value: '{{SENDBIRD_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n      description: Manage Sendbird users.\n\
  \      operations:\n      - name: list-users\n        method: GET\n        description: List users in the Sendbird application.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of users to return.\n        - name: token\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n        - name: nickname\n          in: query\n          type: string\n          required: false\n          description: Filter by nickname.\n        - name: active_mode\n          in: query\n          type: string\n          required: false\n          description: Filter by activation status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_id: '{{tools.user_id}}'\n            nickname: '{{tools.nickname}}'\n            profile_url: '{{tools.profile_url}}'\n    - name: user\n      path: /users/{user_id}\n      description: Manage a specific user.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get a specific user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user's information.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            nickname: '{{tools.nickname}}'\n            profile_url: '{{tools.profile_url}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group-channels\n      path: /group_channels\n      description: Manage group channels.\n      operations:\n      - name: list-group-channels\n        method: GET\n        description: List group channels.\n        inputParameters:\n        - name: limit\n          in: query\n          type:\
  \ integer\n          required: false\n          description: Maximum number of channels to return.\n        - name: token\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group-channel\n        method: POST\n        description: Create a new group channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_ids: '{{tools.user_ids}}'\n            name: '{{tools.name}}'\n            is_distinct: '{{tools.is_distinct}}'\n    - name: messages\n      path: /group_channels/{channel_url}/messages\n      description: Manage channel messages.\n      operations:\n      - name: list-messages\n        method: GET\n        description: List messages\
  \ in a channel.\n        inputParameters:\n        - name: channel_url\n          in: path\n          type: string\n          required: true\n          description: URL of the channel.\n        - name: message_ts\n          in: query\n          type: integer\n          required: false\n          description: Timestamp to fetch messages around.\n        - name: prev_limit\n          in: query\n          type: integer\n          required: false\n          description: Messages before the timestamp.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send a message to a channel.\n        inputParameters:\n        - name: channel_url\n          in: path\n          type: string\n          required: true\n          description: URL of the channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            message_type: '{{tools.message_type}}'\n            user_id: '{{tools.user_id}}'\n            message: '{{tools.message}}'\n    - name: ban-user\n      path: /users/{user_id}/ban\n      description: Ban a user from a channel.\n      operations:\n      - name: ban-user\n        method: POST\n        description: Ban a user from a specific channel.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel_url: '{{tools.channel_url}}'\n            seconds: '{{tools.seconds}}'\n            description: '{{tools.description}}'\n    - name: mute-user\n      path: /users/{user_id}/mute\n    \
  \  description: Mute a user in a channel.\n      operations:\n      - name: mute-user\n        method: POST\n        description: Mute a user in a specific channel.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel_url: '{{tools.channel_url}}'\n            seconds: '{{tools.seconds}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: sendbird-community-api\n    description: Unified REST API for Sendbird community chat management.\n    resources:\n    - path: /v1/members\n      name: members\n      description: Manage community members.\n      operations:\n      - method: GET\n        name: list-members\n        description: List community members.\n    \
  \    call: sendbird-platform.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-member\n        description: Register a new community member.\n        call: sendbird-platform.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms\n      name: rooms\n      description: Manage community chat rooms.\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List chat rooms.\n        call: sendbird-platform.list-group-channels\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-room\n        description: Create a new chat room.\n        call: sendbird-platform.create-group-channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms/{channel_url}/messages\n      name: room-messages\n      description: Manage messages in a\
  \ chat room.\n      operations:\n      - method: GET\n        name: list-room-messages\n        description: List messages in a room.\n        call: sendbird-platform.list-messages\n        with:\n          channel_url: rest.channel_url\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: post-message\n        description: Post a message to a room.\n        call: sendbird-platform.send-message\n        with:\n          channel_url: rest.channel_url\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: sendbird-community-mcp\n    transport: http\n    description: MCP server for AI-assisted Sendbird community management.\n    tools:\n    - name: list-community-members\n      description: List members of the Sendbird community.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-users\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: register-member\n      description: Register a new community member in Sendbird.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: sendbird-platform.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-profile\n      description: Get the profile of a community member.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sendbird-platform.get-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-chat-rooms\n      description: List all community chat rooms and channels.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-group-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-chat-room\n      description: Create a new community chat room or group channel.\n      hints:\n\
  \        readOnly: false\n        openWorld: false\n      call: sendbird-platform.create-group-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-room-messages\n      description: List messages in a community chat room.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-messages\n      with:\n        channel_url: tools.channel_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-message\n      description: Post a message to a community chat room.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: sendbird-platform.send-message\n      with:\n        channel_url: tools.channel_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moderate-ban-member\n      description: Ban a member from a community channel for violation of rules.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: sendbird-platform.ban-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moderate-mute-member\n      description: Temporarily mute a community member.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sendbird-platform.mute-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
