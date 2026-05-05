---
categories: []
consumed_apis:
- sendbird-platform
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
- list customers and agents in the sendbird application.
- list users (customers and agents).
- customer support
- manage channel messages.
- list users
- send a message.
- create user
- manage a specific user.
- get user
- list messages in a support conversation channel.
- send message
- temporarily mute a user in a channel.
- mute user
- manage support users and customers.
- create a support channel.
- create a new support conversation channel between a customer and agent.
- list channels
- ban user
- chat
- create a new user.
- get details of a specific customer or agent.
- send support message
- send a message to a customer in a support channel.
- list group channels.
- create channel
- sendbird
- ban a disruptive user from a channel.
- manage support conversation channels.
- list messages in a channel.
- create support channel
- list all support conversation channels.
- get user details.
- list messages
- messaging
slug: customer-support-messaging
source_filename: customer-support-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sendbird Customer Support Messaging\"\n  description: >-\n    Workflow capability for customer support messaging using Sendbird — enabling\n    support teams to manage customer conversations, assign agents, send messages,\n    moderate users, and monitor channel activity for customer service operations.\n  tags:\n    - Sendbird\n    - Customer Support\n    - Messaging\n    - Chat\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SENDBIRD_API_TOKEN: SENDBIRD_API_TOKEN\n      SENDBIRD_APP_ID: SENDBIRD_APP_ID\n\ncapability:\n  consumes:\n    - import: sendbird-platform\n      location: ./shared/platform-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sendbird-support-api\n      description: \"Unified REST API for Sendbird customer support messaging.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"Manage\
  \ support users and customers.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users (customers and agents).\"\n              call: \"sendbird-platform.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user.\"\n              call: \"sendbird-platform.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{user_id}\n          name: user\n          description: \"Manage a specific user.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get user details.\"\n              call: \"sendbird-platform.get-user\"\n              with:\n                user_id: \"rest.user_id\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Manage support conversation channels.\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List group channels.\"\n              call: \"sendbird-platform.list-group-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-channel\n              description: \"Create a support channel.\"\n              call: \"sendbird-platform.create-group-channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels/{channel_url}/messages\n          name: messages\n          description: \"Manage channel messages.\"\n          operations:\n            - method: GET\n              name: list-messages\n          \
  \    description: \"List messages in a channel.\"\n              call: \"sendbird-platform.list-messages\"\n              with:\n                channel_url: \"rest.channel_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Send a message.\"\n              call: \"sendbird-platform.send-message\"\n              with:\n                channel_url: \"rest.channel_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sendbird-support-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sendbird customer support.\"\n      tools:\n        - name: list-users\n          description: \"List customers and agents in the Sendbird application.\"\n          hints:\n            readOnly: true\n            openWorld: true\n    \
  \      call: \"sendbird-platform.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get details of a specific customer or agent.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sendbird-platform.get-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-support-channel\n          description: \"Create a new support conversation channel between a customer and agent.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sendbird-platform.create-group-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-channels\n          description: \"List all support conversation channels.\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"sendbird-platform.list-group-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messages\n          description: \"List messages in a support conversation channel.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sendbird-platform.list-messages\"\n          with:\n            channel_url: \"tools.channel_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-support-message\n          description: \"Send a message to a customer in a support channel.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sendbird-platform.send-message\"\n          with:\n            channel_url: \"tools.channel_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ban-user\n \
  \         description: \"Ban a disruptive user from a channel.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sendbird-platform.ban-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mute-user\n          description: \"Temporarily mute a user in a channel.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"sendbird-platform.mute-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
