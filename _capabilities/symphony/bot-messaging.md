---
categories: []
consumed_apis: []
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
- real-time event datafeed management
- list available symphony streams
- create signal
- user lookup
- get messages from a stream
- list active datafeeds
- post message
- create a new datafeed for real-time events
- automation
- search rooms
- list available signals
- retrieve messages from a symphony stream
- search for rooms
- list active symphony datafeeds for real-time event processing
- data loss prevention policies
- list datafeeds
- create a new symphony room
- datafeed
- search for symphony users by email or username
- authenticate a bot using rsa key
- create a new signal
- list streams
- room management
- communication
- bots
- collaboration
- symphony
- create a new symphony room for team collaboration
- search users
- search for users by email or username
- authenticate bot
- stream listing
- financial services
- authenticate
- create room
- list all streams
- search for symphony rooms by name or keyword
- secure communication
- list signals
- list dlp policies
- post a message to a stream
- list symphony signals (keyword alerts and triggers)
- get messages
- create a new datafeed to receive real-time symphony events
- list data loss prevention policies for compliance monitoring
- bot and app authentication
- message operations on streams
- authenticate a symphony bot using rsa key pair to obtain session token
- workflows
- post a message to a symphony stream
- create a new symphony signal for keyword monitoring
- create datafeed
- messaging
- real-time
- signal (keyword alert) management
slug: bot-messaging
source_filename: bot-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Symphony Bot Messaging\n  description: 'Workflow capability for Symphony bot automation: authenticate bots, send and receive messages, manage rooms\n    and streams, handle real-time events via datafeed, and monitor signals. Composes the Agent API, Pod API, and Login API\n    for end-to-end bot development workflows.'\n  tags:\n  - Automation\n  - Bots\n  - Collaboration\n  - Datafeed\n  - Messaging\n  - Real-Time\n  - Symphony\n  - Workflows\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYMPHONY_SESSION_TOKEN: SYMPHONY_SESSION_TOKEN\n    SYMPHONY_KEY_MANAGER_TOKEN: SYMPHONY_KEY_MANAGER_TOKEN\n    SYMPHONY_BOT_JWT: SYMPHONY_BOT_JWT\ncapability:\n  consumes:\n  - type: http\n    namespace: symphony-agent\n    baseUri: https://acme.symphony.com\n    description: Symphony Agent API for bot messaging and event streaming\n    authentication:\n      type: apikey\n      key: sessionToken\n      value:\
  \ '{{SYMPHONY_SESSION_TOKEN}}'\n      placement: header\n    resources:\n    - name: health\n      path: /v3/health\n      description: Agent health and connectivity status\n      operations:\n      - name: get-health\n        method: GET\n        description: Check agent health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-extended-health\n        method: GET\n        description: Check extended health status of services and users\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Extended health path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /v4/stream/{sid}/message\n      description: Message operations on streams\n      operations:\n      - name: get-messages\n        method:\
  \ GET\n        description: Get messages from an existing stream\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Stream ID\n        - name: since\n          in: query\n          type: integer\n          required: true\n          description: Timestamp since epoch milliseconds\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        - name: keyManagerToken\n          in: header\n          type: string\n          required: true\n          description: Key manager token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-message\n        method: POST\n        description: Post a message to one existing stream\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n\
  \          required: true\n          description: Stream ID\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        - name: keyManagerToken\n          in: header\n          type: string\n          required: true\n          description: Key manager token\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datafeeds\n      path: /v5/datafeeds\n      description: Real-time event datafeed management\n      operations:\n      - name: list-datafeeds\n        method: GET\n        description: List active datafeeds\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-datafeed\n        method: POST\n        description: Create a new datafeed for real-time events\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: datafeedId\n          type: string\n          value: $.id\n    - name: signals\n      path: /v1/signals\n      description: Signal (keyword alert) management\n      operations:\n      - name: list-signals\n        method: GET\n        description: List available signals\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-signal\n        method: POST\n        description: Create a new signal\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dlp-policies\n      path: /v3/dlp/policies\n      description: Data Loss Prevention policy management\n      operations:\n      - name: list-dlp-policies\n        method: GET\n        description: List DLP policies\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: symphony-pod\n    baseUri: https://acme.symphony.com\n    description: Symphony Pod API for user and room management\n    authentication:\n      type: apikey\n      key: sessionToken\n      value: '{{SYMPHONY_SESSION_TOKEN}}'\n      placement: header\n    resources:\n    - name: users\n      path: /v3/users\n      description: User lookup and management\n      operations:\n      - name: search-users\n        method: GET\n        description: Search for users by email or username\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: User email address\n        - name: username\n          in: query\n          type:\
  \ string\n          required: false\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rooms\n      path: /v3/room\n      description: Room (multi-party stream) management\n      operations:\n      - name: create-room\n        method: POST\n        description: Create a new room\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-rooms\n        method: POST\n        description: Search for rooms\n        inputParameters:\n        - name: sessionToken\n          in: header\n\
  \          type: string\n          required: true\n          description: Session token\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-room-info\n        method: GET\n        description: Get information about a room\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Room ID\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /v1/connection\n      description: User connection management\n      operations:\n      - name: list-connections\n        method: GET\n   \
  \     description: List user connections\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: streams\n      path: /v1/streams/list\n      description: Stream listing and management\n      operations:\n      - name: list-streams\n        method: POST\n        description: List streams for the current user\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-users\n      path: /v2/admin/user/list\n      description: Admin user management\n      operations:\n      - name: list-users-admin\n\
  \        method: GET\n        description: List all users (admin)\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: symphony-login\n    baseUri: https://acme.symphony.com\n    description: Symphony Login API for RSA-based bot authentication\n    resources:\n    - name: pubkey-auth\n      path: /pubkey/authenticate\n      description: RSA public key based authentication\n      operations:\n      - name: authenticate-bot\n        method: POST\n        description: Authenticate with public key to get session token\n        body:\n          type: json\n          data:\n            token: '{{SYMPHONY_BOT_JWT}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: sessionToken\n          type: string\n\
  \          value: $.token\n      - name: authenticate-app\n        method: POST\n        description: Authenticate an app with public key\n        body:\n          type: json\n          data:\n            token: '{{SYMPHONY_BOT_JWT}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: sessionToken\n          type: string\n          value: $.token\n    - name: idm-tokens\n      path: /idm/tokens\n      description: OAuth2 JWT token exchange\n      operations:\n      - name: get-oauth-token\n        method: POST\n        description: Returns a valid OAuth2 access token from a session token\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token\n        - name: scope\n          in: query\n          type: string\n          required: false\n          description: Space-separated list of scopes\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: accessToken\n          type: string\n          value: $.access_token\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: symphony-bot-api\n    description: Unified REST API for Symphony bot messaging and automation workflows.\n    resources:\n    - path: /v1/authenticate\n      name: authentication\n      description: Bot and app authentication\n      operations:\n      - method: POST\n        name: authenticate\n        description: Authenticate a bot using RSA key\n        call: symphony-login.authenticate-bot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages/{streamId}\n      name: messages\n      description: Message operations on streams\n      operations:\n      - method: GET\n        name: get-messages\n        description: Get messages from a stream\n        call: symphony-agent.get-messages\n        with:\n          sid: rest.streamId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: post-message\n        description: Post a message to a stream\n        call: symphony-agent.create-message\n        with:\n          sid: rest.streamId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datafeeds\n      name: datafeeds\n      description: Real-time event datafeed management\n      operations:\n      - method: GET\n        name: list-datafeeds\n        description: List active datafeeds\n        call: symphony-agent.list-datafeeds\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-datafeed\n        description: Create a new datafeed for real-time events\n        call: symphony-agent.create-datafeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms\n      name: rooms\n      description: Room management\n      operations:\n      - method: POST\n        name: create-room\n       \
  \ description: Create a new Symphony room\n        call: symphony-pod.create-room\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: search-rooms\n        description: Search for rooms\n        call: symphony-pod.search-rooms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User lookup\n      operations:\n      - method: GET\n        name: search-users\n        description: Search for users by email or username\n        call: symphony-pod.search-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/signals\n      name: signals\n      description: Signal (keyword alert) management\n      operations:\n      - method: GET\n        name: list-signals\n        description: List available signals\n        call: symphony-agent.list-signals\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-signal\n        description: Create a new signal\n        call: symphony-agent.create-signal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/streams\n      name: streams\n      description: Stream listing\n      operations:\n      - method: GET\n        name: list-streams\n        description: List all streams\n        call: symphony-pod.list-streams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dlp/policies\n      name: dlp-policies\n      description: Data Loss Prevention policies\n      operations:\n      - method: GET\n        name: list-dlp-policies\n        description: List DLP policies\n        call: symphony-agent.list-dlp-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: symphony-bot-mcp\n    transport: http\n    description: MCP server for AI-assisted Symphony bot\
  \ messaging and automation.\n    tools:\n    - name: authenticate-bot\n      description: Authenticate a Symphony bot using RSA key pair to obtain session token\n      hints:\n        readOnly: false\n        destructive: false\n      call: symphony-login.authenticate-bot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-messages\n      description: Retrieve messages from a Symphony stream\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-agent.get-messages\n      with:\n        sid: tools.streamId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-message\n      description: Post a message to a Symphony stream\n      hints:\n        readOnly: false\n        destructive: false\n      call: symphony-agent.create-message\n      with:\n        sid: tools.streamId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datafeeds\n      description: List active\
  \ Symphony datafeeds for real-time event processing\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-agent.list-datafeeds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-datafeed\n      description: Create a new datafeed to receive real-time Symphony events\n      hints:\n        readOnly: false\n        destructive: false\n      call: symphony-agent.create-datafeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-room\n      description: Create a new Symphony room for team collaboration\n      hints:\n        readOnly: false\n        destructive: false\n      call: symphony-pod.create-room\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-rooms\n      description: Search for Symphony rooms by name or keyword\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-pod.search-rooms\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-users\n      description: Search for Symphony users by email or username\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-pod.search-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-streams\n      description: List available Symphony streams\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-pod.list-streams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-signals\n      description: List Symphony signals (keyword alerts and triggers)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-agent.list-signals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-signal\n      description: Create a new Symphony signal for keyword monitoring\n      hints:\n        readOnly: false\n        destructive: false\n     \
  \ call: symphony-agent.create-signal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dlp-policies\n      description: List Data Loss Prevention policies for compliance monitoring\n      hints:\n        readOnly: true\n        openWorld: false\n      call: symphony-agent.list-dlp-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
