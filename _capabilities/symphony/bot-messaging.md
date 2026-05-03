---
categories: []
consumed_apis:
- symphony-agent
- symphony-pod
- symphony-login
description: 'Workflow capability for Symphony bot automation: authenticate bots, send and receive messages, manage rooms and streams, handle real-time events via datafeed, and monitor signals. Composes the Agent API, Pod API, and Login API for end-to-end bot development workflows.'
layout: capability
name: Symphony Bot Messaging
operations:
- description: Authenticate a bot using RSA key
  method: POST
  name: authenticate
  path: /v1/authenticate
- description: Get messages from a stream
  method: GET
  name: get-messages
  path: /v1/messages/{streamId}
- description: Post a message to a stream
  method: POST
  name: post-message
  path: /v1/messages/{streamId}
- description: List active datafeeds
  method: GET
  name: list-datafeeds
  path: /v1/datafeeds
- description: Create a new datafeed for real-time events
  method: POST
  name: create-datafeed
  path: /v1/datafeeds
- description: Create a new Symphony room
  method: POST
  name: create-room
  path: /v1/rooms
- description: Search for rooms
  method: GET
  name: search-rooms
  path: /v1/rooms
- description: Search for users by email or username
  method: GET
  name: search-users
  path: /v1/users
- description: List available signals
  method: GET
  name: list-signals
  path: /v1/signals
- description: Create a new signal
  method: POST
  name: create-signal
  path: /v1/signals
- description: List all streams
  method: GET
  name: list-streams
  path: /v1/streams
- description: List DLP policies
  method: GET
  name: list-dlp-policies
  path: /v1/dlp/policies
personas: []
provider_name: Symphony
provider_slug: symphony
search_terms:
- automation
- signal (keyword alert) management
- list symphony signals (keyword alerts and triggers)
- list streams
- create datafeed
- get messages from a stream
- list dlp policies
- message operations on streams
- search rooms
- create a new datafeed to receive real-time symphony events
- data loss prevention policies
- create a new datafeed for real-time events
- post a message to a symphony stream
- list signals
- list data loss prevention policies for compliance monitoring
- list available signals
- bots
- authenticate
- list active datafeeds
- post a message to a stream
- room management
- financial services
- search users
- list active symphony datafeeds for real-time event processing
- communication
- list datafeeds
- create room
- real-time event datafeed management
- workflows
- authenticate a bot using rsa key
- messaging
- collaboration
- retrieve messages from a symphony stream
- search for users by email or username
- authenticate bot
- datafeed
- symphony
- post message
- stream listing
- secure communication
- bot and app authentication
- real-time
- create a new symphony room
- create a new signal
- create a new symphony room for team collaboration
- create signal
- authenticate a symphony bot using rsa key pair to obtain session token
- search for symphony rooms by name or keyword
- list all streams
- list available symphony streams
- user lookup
- get messages
- create a new symphony signal for keyword monitoring
- search for symphony users by email or username
- search for rooms
slug: bot-messaging
source_filename: bot-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Symphony Bot Messaging\n  description: >-\n    Workflow capability for Symphony bot automation: authenticate bots,\n    send and receive messages, manage rooms and streams, handle real-time\n    events via datafeed, and monitor signals. Composes the Agent API, Pod API,\n    and Login API for end-to-end bot development workflows.\n  tags:\n    - Automation\n    - Bots\n    - Collaboration\n    - Datafeed\n    - Messaging\n    - Real-Time\n    - Symphony\n    - Workflows\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SYMPHONY_SESSION_TOKEN: SYMPHONY_SESSION_TOKEN\n      SYMPHONY_KEY_MANAGER_TOKEN: SYMPHONY_KEY_MANAGER_TOKEN\n      SYMPHONY_BOT_JWT: SYMPHONY_BOT_JWT\n\ncapability:\n  consumes:\n    - import: symphony-agent\n      location: ./shared/agent-api.yaml\n    - import: symphony-pod\n      location: ./shared/pod-api.yaml\n    - import: symphony-login\n      location: ./shared/login-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: symphony-bot-api\n      description: Unified REST API for Symphony bot messaging and automation workflows.\n      resources:\n        - path: /v1/authenticate\n          name: authentication\n          description: Bot and app authentication\n          operations:\n            - method: POST\n              name: authenticate\n              description: Authenticate a bot using RSA key\n              call: \"symphony-login.authenticate-bot\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages/{streamId}\n          name: messages\n          description: Message operations on streams\n          operations:\n            - method: GET\n              name: get-messages\n              description: Get messages from a stream\n              call: \"symphony-agent.get-messages\"\n              with:\n                sid: \"rest.streamId\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: post-message\n              description: Post a message to a stream\n              call: \"symphony-agent.create-message\"\n              with:\n                sid: \"rest.streamId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/datafeeds\n          name: datafeeds\n          description: Real-time event datafeed management\n          operations:\n            - method: GET\n              name: list-datafeeds\n              description: List active datafeeds\n              call: \"symphony-agent.list-datafeeds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-datafeed\n              description: Create a new datafeed for real-time events\n              call: \"symphony-agent.create-datafeed\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rooms\n          name: rooms\n          description: Room management\n          operations:\n            - method: POST\n              name: create-room\n              description: Create a new Symphony room\n              call: \"symphony-pod.create-room\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: search-rooms\n              description: Search for rooms\n              call: \"symphony-pod.search-rooms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: User lookup\n          operations:\n            - method: GET\n              name: search-users\n              description: Search for users by email or username\n              call: \"\
  symphony-pod.search-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/signals\n          name: signals\n          description: Signal (keyword alert) management\n          operations:\n            - method: GET\n              name: list-signals\n              description: List available signals\n              call: \"symphony-agent.list-signals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-signal\n              description: Create a new signal\n              call: \"symphony-agent.create-signal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/streams\n          name: streams\n          description: Stream listing\n          operations:\n            - method: GET\n              name: list-streams\n              description:\
  \ List all streams\n              call: \"symphony-pod.list-streams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dlp/policies\n          name: dlp-policies\n          description: Data Loss Prevention policies\n          operations:\n            - method: GET\n              name: list-dlp-policies\n              description: List DLP policies\n              call: \"symphony-agent.list-dlp-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: symphony-bot-mcp\n      transport: http\n      description: MCP server for AI-assisted Symphony bot messaging and automation.\n      tools:\n        - name: authenticate-bot\n          description: Authenticate a Symphony bot using RSA key pair to obtain session token\n          hints:\n            readOnly: false\n            destructive: false\n          call:\
  \ \"symphony-login.authenticate-bot\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-messages\n          description: Retrieve messages from a Symphony stream\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"symphony-agent.get-messages\"\n          with:\n            sid: \"tools.streamId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: post-message\n          description: Post a message to a Symphony stream\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"symphony-agent.create-message\"\n          with:\n            sid: \"tools.streamId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-datafeeds\n          description: List active Symphony datafeeds for real-time event processing\n          hints:\n      \
  \      readOnly: true\n            openWorld: false\n          call: \"symphony-agent.list-datafeeds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-datafeed\n          description: Create a new datafeed to receive real-time Symphony events\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"symphony-agent.create-datafeed\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-room\n          description: Create a new Symphony room for team collaboration\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"symphony-pod.create-room\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-rooms\n          description: Search for Symphony rooms by name or keyword\n          hints:\n            readOnly: true\n     \
  \       openWorld: false\n          call: \"symphony-pod.search-rooms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-users\n          description: Search for Symphony users by email or username\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"symphony-pod.search-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-streams\n          description: List available Symphony streams\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"symphony-pod.list-streams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-signals\n          description: List Symphony signals (keyword alerts and triggers)\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"symphony-agent.list-signals\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-signal\n          description: Create a new Symphony signal for keyword monitoring\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"symphony-agent.create-signal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dlp-policies\n          description: List Data Loss Prevention policies for compliance monitoring\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"symphony-agent.list-dlp-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/symphony/refs/heads/main/capabilities/bot-messaging.yaml
tags:
- Automation
- Bots
- Collaboration
- Datafeed
- Messaging
- Real-Time
- Symphony
- Workflows
tools:
- description: Authenticate a Symphony bot using RSA key pair to obtain session token
  hints:
    destructive: false
    readOnly: false
  name: authenticate-bot
- description: Retrieve messages from a Symphony stream
  hints:
    openWorld: false
    readOnly: true
  name: get-messages
- description: Post a message to a Symphony stream
  hints:
    destructive: false
    readOnly: false
  name: post-message
- description: List active Symphony datafeeds for real-time event processing
  hints:
    openWorld: false
    readOnly: true
  name: list-datafeeds
- description: Create a new datafeed to receive real-time Symphony events
  hints:
    destructive: false
    readOnly: false
  name: create-datafeed
- description: Create a new Symphony room for team collaboration
  hints:
    destructive: false
    readOnly: false
  name: create-room
- description: Search for Symphony rooms by name or keyword
  hints:
    openWorld: false
    readOnly: true
  name: search-rooms
- description: Search for Symphony users by email or username
  hints:
    openWorld: false
    readOnly: true
  name: search-users
- description: List available Symphony streams
  hints:
    openWorld: false
    readOnly: true
  name: list-streams
- description: List Symphony signals (keyword alerts and triggers)
  hints:
    openWorld: false
    readOnly: true
  name: list-signals
- description: Create a new Symphony signal for keyword monitoring
  hints:
    destructive: false
    readOnly: false
  name: create-signal
- description: List Data Loss Prevention policies for compliance monitoring
  hints:
    openWorld: false
    readOnly: true
  name: list-dlp-policies
---
