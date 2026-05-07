---
categories: []
consumed_apis: []
description: Reference OpenAPI definition describing the typical shape of a chat platform API. Captures the vocabulary used for conversations, messages, and participants and serves as a profiling baseline for cataloguing concrete chat platform APIs.
layout: capability
name: Reference Chat API
operations:
- description: List conversations
  method: GET
  name: listconversations
  path: /conversations
- description: Create a conversation
  method: POST
  name: createconversation
  path: /conversations
- description: Get a conversation
  method: GET
  name: getconversation
  path: /conversations/{conversationId}
- description: List messages in a conversation
  method: GET
  name: listmessages
  path: /conversations/{conversationId}/messages
- description: Send a message
  method: POST
  name: sendmessage
  path: /conversations/{conversationId}/messages
- description: List participants
  method: GET
  name: listparticipants
  path: /conversations/{conversationId}/participants
- description: Add a participant
  method: POST
  name: addparticipant
  path: /conversations/{conversationId}/participants
personas: []
provider_name: Chat
provider_slug: chat
search_terms:
- list messages in a conversation
- get a conversation
- conversations
- customer support
- listparticipants
- api
- conversational ai
- list conversations
- create a conversation
- sendmessage
- list participants
- chat
- getconversation
- add a participant
- createconversation
- addparticipant
- listmessages
- send a message
- messaging
- real-time
- listconversations
slug: chat-capability
source_filename: chat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reference Chat API\n  description: Reference OpenAPI definition describing the typical shape of a chat platform API. Captures the vocabulary used\n    for conversations, messages, and participants and serves as a profiling baseline for cataloguing concrete chat platform\n    APIs.\n  tags:\n  - Chat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chat\n    baseUri: https://api.example.com/v1/chat\n    description: Reference Chat API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHAT_TOKEN}}'\n    resources:\n    - name: conversations\n      path: /conversations\n      operations:\n      - name: listconversations\n        method: GET\n        description: List conversations\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconversation\n        method: POST\n        description: Create a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid\n      path: /conversations/{conversationId}\n      operations:\n      - name: getconversation\n        method: GET\n        description: Get a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid-messages\n      path: /conversations/{conversationId}/messages\n      operations:\n      - name: listmessages\n        method: GET\n        description: List messages in a conversation\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n        - name: limit\n\
  \          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sendmessage\n        method: POST\n        description: Send a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid-participants\n      path: /conversations/{conversationId}/participants\n      operations:\n      - name: listparticipants\n        method: GET\n        description: List participants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addparticipant\n        method: POST\n        description: Add a participant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n\
  \    namespace: chat-rest\n    description: REST adapter for Reference Chat API.\n    resources:\n    - path: /conversations\n      name: listconversations\n      operations:\n      - method: GET\n        name: listconversations\n        description: List conversations\n        call: chat.listconversations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations\n      name: createconversation\n      operations:\n      - method: POST\n        name: createconversation\n        description: Create a conversation\n        call: chat.createconversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}\n      name: getconversation\n      operations:\n      - method: GET\n        name: getconversation\n        description: Get a conversation\n        call: chat.getconversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/messages\n\
  \      name: listmessages\n      operations:\n      - method: GET\n        name: listmessages\n        description: List messages in a conversation\n        call: chat.listmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/messages\n      name: sendmessage\n      operations:\n      - method: POST\n        name: sendmessage\n        description: Send a message\n        call: chat.sendmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/participants\n      name: listparticipants\n      operations:\n      - method: GET\n        name: listparticipants\n        description: List participants\n        call: chat.listparticipants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/participants\n      name: addparticipant\n      operations:\n      - method: POST\n        name: addparticipant\n\
  \        description: Add a participant\n        call: chat.addparticipant\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chat-mcp\n    transport: http\n    description: MCP adapter for Reference Chat API for AI agent use.\n    tools:\n    - name: listconversations\n      description: List conversations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chat.listconversations\n      with:\n        cursor: tools.cursor\n        limit: tools.limit\n      inputParameters:\n      - name: cursor\n        type: string\n        description: cursor\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconversation\n      description: Create a conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chat.createconversation\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconversation\n      description: Get a conversation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chat.getconversation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmessages\n      description: List messages in a conversation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chat.listmessages\n      with:\n        cursor: tools.cursor\n        limit: tools.limit\n      inputParameters:\n      - name: cursor\n        type: string\n        description: cursor\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendmessage\n      description: Send a message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n     \
  \ call: chat.sendmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listparticipants\n      description: List participants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chat.listparticipants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addparticipant\n      description: Add a participant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chat.addparticipant\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHAT_TOKEN: CHAT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chat/refs/heads/main/capabilities/chat-capability.yaml
tags:
- Chat
- API
tools:
- description: List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconversations
- description: Create a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconversation
- description: Get a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconversation
- description: List messages in a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmessages
- description: Send a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendmessage
- description: List participants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listparticipants
- description: Add a participant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addparticipant
---
