---
categories: []
consumed_apis: []
description: Workflow capability for customer support messaging using Sendbird — enabling support teams to manage customer conversations, assign agents, send messages, moderate users, and monitor channel activity for customer service operations.
layout: capability
name: Sendbird Customer Support Messaging
operations:
- description: List users (customers and agents).
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user.
  method: POST
  name: create-user
  path: /v1/users
- description: Get user details.
  method: GET
  name: get-user
  path: /v1/users/{user_id}
- description: List group channels.
  method: GET
  name: list-channels
  path: /v1/channels
- description: Create a support channel.
  method: POST
  name: create-channel
  path: /v1/channels
- description: List messages in a channel.
  method: GET
  name: list-messages
  path: /v1/channels/{channel_url}/messages
- description: Send a message.
  method: POST
  name: send-message
  path: /v1/channels/{channel_url}/messages
personas: []
provider_name: Sendbird
provider_slug: sendbird
search_terms:
- list messages in a support conversation channel.
- sendbird
- list messages
- create support channel
- list messages in a channel.
- list users (customers and agents).
- manage channel messages.
- send support message
- create user
- list all support conversation channels.
- get user details.
- get details of a specific customer or agent.
- send a message to a customer in a support channel.
- ban user
- list customers and agents in the sendbird application.
- messaging
- create a new support conversation channel between a customer and agent.
- temporarily mute a user in a channel.
- send message
- send a message.
- create channel
- list channels
- get user
- chat
- customer support
- create a support channel.
- list users
- ban a disruptive user from a channel.
- manage support users and customers.
- manage support conversation channels.
- list group channels.
- manage a specific user.
- create a new user.
- mute user
slug: customer-support-messaging
source_filename: customer-support-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sendbird Customer Support Messaging\n  description: Workflow capability for customer support messaging using Sendbird — enabling support teams to manage customer\n    conversations, assign agents, send messages, moderate users, and monitor channel activity for customer service operations.\n  tags:\n  - Sendbird\n  - Customer Support\n  - Messaging\n  - Chat\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SENDBIRD_API_TOKEN: SENDBIRD_API_TOKEN\n    SENDBIRD_APP_ID: SENDBIRD_APP_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: sendbird-platform\n    baseUri: https://api-{{SENDBIRD_APP_ID}}.sendbird.com/v3\n    description: Sendbird Platform API for managing in-app chat.\n    authentication:\n      type: apikey\n      key: Api-Token\n      value: '{{SENDBIRD_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n      description: Manage Sendbird\
  \ users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the Sendbird application.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of users to return.\n        - name: token\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n        - name: nickname\n          in: query\n          type: string\n          required: false\n          description: Filter by nickname.\n        - name: active_mode\n          in: query\n          type: string\n          required: false\n          description: Filter by activation status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_id: '{{tools.user_id}}'\n            nickname: '{{tools.nickname}}'\n            profile_url: '{{tools.profile_url}}'\n    - name: user\n      path: /users/{user_id}\n      description: Manage a specific user.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get a specific user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user's information.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            nickname: '{{tools.nickname}}'\n            profile_url: '{{tools.profile_url}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group-channels\n      path: /group_channels\n      description: Manage group channels.\n      operations:\n      - name: list-group-channels\n        method: GET\n        description: List group channels.\n        inputParameters:\n        - name: limit\n   \
  \       in: query\n          type: integer\n          required: false\n          description: Maximum number of channels to return.\n        - name: token\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group-channel\n        method: POST\n        description: Create a new group channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_ids: '{{tools.user_ids}}'\n            name: '{{tools.name}}'\n            is_distinct: '{{tools.is_distinct}}'\n    - name: messages\n      path: /group_channels/{channel_url}/messages\n      description: Manage channel messages.\n      operations:\n      - name: list-messages\n        method: GET\n\
  \        description: List messages in a channel.\n        inputParameters:\n        - name: channel_url\n          in: path\n          type: string\n          required: true\n          description: URL of the channel.\n        - name: message_ts\n          in: query\n          type: integer\n          required: false\n          description: Timestamp to fetch messages around.\n        - name: prev_limit\n          in: query\n          type: integer\n          required: false\n          description: Messages before the timestamp.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send a message to a channel.\n        inputParameters:\n        - name: channel_url\n          in: path\n          type: string\n          required: true\n          description: URL of the channel.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message_type: '{{tools.message_type}}'\n            user_id: '{{tools.user_id}}'\n            message: '{{tools.message}}'\n    - name: ban-user\n      path: /users/{user_id}/ban\n      description: Ban a user from a channel.\n      operations:\n      - name: ban-user\n        method: POST\n        description: Ban a user from a specific channel.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel_url: '{{tools.channel_url}}'\n            seconds: '{{tools.seconds}}'\n            description: '{{tools.description}}'\n    - name: mute-user\n\
  \      path: /users/{user_id}/mute\n      description: Mute a user in a channel.\n      operations:\n      - name: mute-user\n        method: POST\n        description: Mute a user in a specific channel.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel_url: '{{tools.channel_url}}'\n            seconds: '{{tools.seconds}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sendbird-support-api\n    description: Unified REST API for Sendbird customer support messaging.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Manage support users and customers.\n      operations:\n      - method: GET\n        name: list-users\n        description:\
  \ List users (customers and agents).\n        call: sendbird-platform.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user.\n        call: sendbird-platform.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}\n      name: user\n      description: Manage a specific user.\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details.\n        call: sendbird-platform.get-user\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Manage support conversation channels.\n      operations:\n      - method: GET\n        name: list-channels\n        description: List group channels.\n        call: sendbird-platform.list-group-channels\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-channel\n        description: Create a support channel.\n        call: sendbird-platform.create-group-channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels/{channel_url}/messages\n      name: messages\n      description: Manage channel messages.\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages in a channel.\n        call: sendbird-platform.list-messages\n        with:\n          channel_url: rest.channel_url\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send a message.\n        call: sendbird-platform.send-message\n        with:\n          channel_url: rest.channel_url\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: sendbird-support-mcp\n    transport: http\n    description: MCP server for AI-assisted Sendbird customer support.\n    tools:\n    - name: list-users\n      description: List customers and agents in the Sendbird application.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details of a specific customer or agent.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sendbird-platform.get-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-support-channel\n      description: Create a new support conversation channel between a customer and agent.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: sendbird-platform.create-group-channel\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: list-channels\n      description: List all support conversation channels.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-group-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List messages in a support conversation channel.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sendbird-platform.list-messages\n      with:\n        channel_url: tools.channel_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-support-message\n      description: Send a message to a customer in a support channel.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: sendbird-platform.send-message\n      with:\n        channel_url: tools.channel_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ban-user\n      description:\
  \ Ban a disruptive user from a channel.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sendbird-platform.ban-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mute-user\n      description: Temporarily mute a user in a channel.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sendbird-platform.mute-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sendbird/refs/heads/main/capabilities/customer-support-messaging.yaml
tags:
- Sendbird
- Customer Support
- Messaging
- Chat
tools:
- description: List customers and agents in the Sendbird application.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get details of a specific customer or agent.
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: Create a new support conversation channel between a customer and agent.
  hints:
    openWorld: false
    readOnly: false
  name: create-support-channel
- description: List all support conversation channels.
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: List messages in a support conversation channel.
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Send a message to a customer in a support channel.
  hints:
    openWorld: false
    readOnly: false
  name: send-support-message
- description: Ban a disruptive user from a channel.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: ban-user
- description: Temporarily mute a user in a channel.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: mute-user
---
