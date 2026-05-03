---
categories: []
consumed_apis:
- messaging
- contacts
description: Unified communications platform capability combining Rainbow CPaaS messaging, contacts, and directory. Used by developers building enterprise communication applications with chat, group collaboration, presence awareness, and contact management. Powered by Alcatel-Lucent Enterprise Rainbow APIs.
layout: capability
name: Rainbow Communications Platform
operations:
- description: Send a message to a contact or group
  method: POST
  name: send-message
  path: /v1/messages
- description: List user conversations
  method: GET
  name: list-conversations
  path: /v1/conversations
- description: List group chat rooms
  method: GET
  name: list-bubbles
  path: /v1/bubbles
- description: Create a new group chat room
  method: POST
  name: create-bubble
  path: /v1/bubbles
- description: Search Rainbow directory
  method: GET
  name: search-contacts
  path: /v1/contacts
- description: Get contact profile and presence
  method: GET
  name: get-contact
  path: /v1/contacts/{id}
- description: Get own profile
  method: GET
  name: get-my-profile
  path: /v1/users/me
- description: Update presence status
  method: PUT
  name: update-presence
  path: /v1/users/me/presence
personas: []
provider_name: Rainbow
provider_slug: rainbow
search_terms:
- get own profile
- get rainbow contact profile including presence status and contact details
- list recent conversations for the authenticated rainbow user
- video
- create bubble
- send a chat message to a rainbow contact (1-to-1) or into a group bubble. supports text messages via rest api.
- list conversations
- send message
- get contact profile and presence
- get my profile
- list user conversations
- user presence management
- unified communications
- create a new rainbow group chat room (bubble) with optional members
- voice
- presence
- get message history for a specific rainbow conversation
- contacts
- update presence
- get contact
- update presence status
- group chat rooms
- get the authenticated rainbow user's own profile
- telephony
- chat
- create a new group chat room
- messaging
- communications
- collaboration
- update presence status in rainbow (online, away, busy, dnd)
- list group chat rooms
- contact directory search
- get conversation messages
- search rainbow enterprise directory for contacts by name, email, or phone
- search rainbow directory
- list group chat rooms (bubbles) the user belongs to in rainbow
- list bubbles
- authenticated user's profile
- send and retrieve chat messages
- cpaas
- send a message to a contact or group
- search contacts
- individual contact profiles
- list and manage conversations
slug: communications-platform
source_filename: communications-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Rainbow Communications Platform\n  description: >-\n    Unified communications platform capability combining Rainbow CPaaS messaging,\n    contacts, and directory. Used by developers building enterprise communication\n    applications with chat, group collaboration, presence awareness, and\n    contact management. Powered by Alcatel-Lucent Enterprise Rainbow APIs.\n  tags:\n    - Communications\n    - CPaaS\n    - Messaging\n    - Chat\n    - Contacts\n    - Presence\n    - Collaboration\n    - Unified Communications\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAINBOW_BEARER_TOKEN: RAINBOW_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: messaging\n      location: ./shared/messaging.yaml\n    - import: contacts\n      location: ./shared/contacts.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: communications-platform-api\n      description:\
  \ Unified REST API for Rainbow CPaaS communications and collaboration.\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: Send and retrieve chat messages\n          operations:\n            - method: POST\n              name: send-message\n              description: Send a message to a contact or group\n              call: \"messaging.send-message\"\n              with:\n                content: \"rest.content\"\n                to: \"rest.to\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/conversations\n          name: conversations\n          description: List and manage conversations\n          operations:\n            - method: GET\n              name: list-conversations\n              description: List user conversations\n              call: \"messaging.list-conversations\"\n              with:\n                limit: \"rest.limit\"\
  \n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bubbles\n          name: bubbles\n          description: Group chat rooms\n          operations:\n            - method: GET\n              name: list-bubbles\n              description: List group chat rooms\n              call: \"messaging.list-bubbles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bubble\n              description: Create a new group chat room\n              call: \"messaging.create-bubble\"\n              with:\n                name: \"rest.name\"\n                topic: \"rest.topic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts\n          name: contacts\n          description: Contact directory search\n        \
  \  operations:\n            - method: GET\n              name: search-contacts\n              description: Search Rainbow directory\n              call: \"contacts.search-contacts\"\n              with:\n                search: \"rest.search\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/{id}\n          name: contact-detail\n          description: Individual contact profiles\n          operations:\n            - method: GET\n              name: get-contact\n              description: Get contact profile and presence\n              call: \"contacts.get-contact\"\n              with:\n                contactId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/me\n          name: my-profile\n          description: Authenticated user's profile\n          operations:\n           \
  \ - method: GET\n              name: get-my-profile\n              description: Get own profile\n              call: \"contacts.get-my-profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/me/presence\n          name: my-presence\n          description: User presence management\n          operations:\n            - method: PUT\n              name: update-presence\n              description: Update presence status\n              call: \"contacts.update-presence\"\n              with:\n                presence: \"rest.presence\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: communications-platform-mcp\n      transport: http\n      description: MCP server for AI-assisted enterprise communications and collaboration.\n      tools:\n        - name: send-message\n\
  \          description: >-\n            Send a chat message to a Rainbow contact (1-to-1) or into a\n            group bubble. Supports text messages via REST API.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"messaging.send-message\"\n          with:\n            content: \"tools.content\"\n            to: \"tools.to\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-conversations\n          description: List recent conversations for the authenticated Rainbow user\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"messaging.list-conversations\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-conversation-messages\n          description: Get message\
  \ history for a specific Rainbow conversation\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"messaging.get-conversation-messages\"\n          with:\n            conversationId: \"tools.conversationId\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bubbles\n          description: List group chat rooms (bubbles) the user belongs to in Rainbow\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"messaging.list-bubbles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bubble\n          description: Create a new Rainbow group chat room (bubble) with optional members\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"messaging.create-bubble\"\n          with:\n            name: \"tools.name\"\n \
  \           topic: \"tools.topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-contacts\n          description: Search Rainbow enterprise directory for contacts by name, email, or phone\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"contacts.search-contacts\"\n          with:\n            search: \"tools.search\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contact\n          description: Get Rainbow contact profile including presence status and contact details\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"contacts.get-contact\"\n          with:\n            contactId: \"tools.contactId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-my-profile\n          description:\
  \ Get the authenticated Rainbow user's own profile\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"contacts.get-my-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-presence\n          description: Update presence status in Rainbow (online, away, busy, dnd)\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"contacts.update-presence\"\n          with:\n            presence: \"tools.presence\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rainbow/refs/heads/main/capabilities/communications-platform.yaml
tags:
- Communications
- CPaaS
- Messaging
- Chat
- Contacts
- Presence
- Collaboration
- Unified Communications
tools:
- description: Send a chat message to a Rainbow contact (1-to-1) or into a group bubble. Supports text messages via REST API.
  hints:
    destructive: false
    readOnly: false
  name: send-message
- description: List recent conversations for the authenticated Rainbow user
  hints:
    openWorld: false
    readOnly: true
  name: list-conversations
- description: Get message history for a specific Rainbow conversation
  hints:
    openWorld: false
    readOnly: true
  name: get-conversation-messages
- description: List group chat rooms (bubbles) the user belongs to in Rainbow
  hints:
    openWorld: false
    readOnly: true
  name: list-bubbles
- description: Create a new Rainbow group chat room (bubble) with optional members
  hints:
    destructive: false
    readOnly: false
  name: create-bubble
- description: Search Rainbow enterprise directory for contacts by name, email, or phone
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: Get Rainbow contact profile including presence status and contact details
  hints:
    openWorld: false
    readOnly: true
  name: get-contact
- description: Get the authenticated Rainbow user's own profile
  hints:
    openWorld: false
    readOnly: true
  name: get-my-profile
- description: Update presence status in Rainbow (online, away, busy, dnd)
  hints:
    idempotent: true
    readOnly: false
  name: update-presence
---
