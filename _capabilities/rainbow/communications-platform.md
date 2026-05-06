---
categories: []
consumed_apis: []
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
- list user conversations
- group chat rooms
- list group chat rooms (bubbles) the user belongs to in rainbow
- create a new rainbow group chat room (bubble) with optional members
- get contact
- cpaas
- get my profile
- search contacts
- get own profile
- individual contact profiles
- get contact profile and presence
- contacts
- list conversations
- authenticated user's profile
- get rainbow contact profile including presence status and contact details
- get the authenticated rainbow user's own profile
- update presence
- voice
- send and retrieve chat messages
- get message history for a specific rainbow conversation
- list bubbles
- presence
- list recent conversations for the authenticated rainbow user
- get conversation messages
- search rainbow enterprise directory for contacts by name, email, or phone
- telephony
- messaging
- create a new group chat room
- list group chat rooms
- update presence status
- send message
- video
- contact directory search
- chat
- user presence management
- create bubble
- send a chat message to a rainbow contact (1-to-1) or into a group bubble. supports text messages via rest api.
- update presence status in rainbow (online, away, busy, dnd)
- search rainbow directory
- list and manage conversations
- collaboration
- send a message to a contact or group
- unified communications
- communications
slug: communications-platform
source_filename: communications-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rainbow Communications Platform\n  description: Unified communications platform capability combining Rainbow CPaaS messaging, contacts, and directory. Used\n    by developers building enterprise communication applications with chat, group collaboration, presence awareness, and contact\n    management. Powered by Alcatel-Lucent Enterprise Rainbow APIs.\n  tags:\n  - Communications\n  - CPaaS\n  - Messaging\n  - Chat\n  - Contacts\n  - Presence\n  - Collaboration\n  - Unified Communications\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RAINBOW_BEARER_TOKEN: RAINBOW_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: messaging\n    baseUri: https://openrainbow.com/api/rainbow\n    description: Rainbow Messaging REST API\n    authentication:\n      type: bearer\n      token: '{{RAINBOW_BEARER_TOKEN}}'\n    resources:\n    - name: messages\n      path: /enduser/v1.0/messages\n\
  \      description: Send chat messages\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to a contact or bubble\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n            to: '{{tools.to}}'\n            type: '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations\n      path: /enduser/v1.0/conversations\n      description: Manage conversations\n      operations:\n      - name: list-conversations\n        method: GET\n        description: List conversations for the authenticated user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination\
  \ offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversation-messages\n      path: /enduser/v1.0/conversations/{conversationId}/messages\n      description: Get conversation message history\n      operations:\n      - name: get-conversation-messages\n        method: GET\n        description: Get message history for a conversation\n        inputParameters:\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n          description: Conversation ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max messages to return\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 timestamp for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: bubbles\n      path: /enduser/v1.0/bubbles\n      description: Manage group chat rooms\n      operations:\n      - name: list-bubbles\n        method: GET\n        description: List bubbles the user belongs to\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bubble\n        method: POST\n        description: Create a new group chat room\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            topic: '{{tools.topic}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: contacts\n    baseUri:\
  \ https://openrainbow.com/api/rainbow\n    description: Rainbow Contacts REST API\n    authentication:\n      type: bearer\n      token: '{{RAINBOW_BEARER_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /enduser/v1.0/contacts\n      description: Search and manage contacts\n      operations:\n      - name: search-contacts\n        method: GET\n        description: Search contacts by name, email, or phone\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search keyword\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact-detail\n      path: /enduser/v1.0/contacts/{contactId}\n      description: Get\
  \ a specific contact\n      operations:\n      - name: get-contact\n        method: GET\n        description: Get contact profile and presence\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: my-profile\n      path: /enduser/v1.0/users/me\n      description: Authenticated user's profile\n      operations:\n      - name: get-my-profile\n        method: GET\n        description: Get current user's profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: my-presence\n      path: /enduser/v1.0/users/me/presence\n      description: Manage user presence status\n      operations:\n      - name: update-presence\n        method: PUT\n        description: Update\
  \ presence status\n        body:\n          type: json\n          data:\n            presence: '{{tools.presence}}'\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: communications-platform-api\n    description: Unified REST API for Rainbow CPaaS communications and collaboration.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Send and retrieve chat messages\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a message to a contact or group\n        call: messaging.send-message\n        with:\n          content: rest.content\n          to: rest.to\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversations\n      name: conversations\n      description: List and manage\
  \ conversations\n      operations:\n      - method: GET\n        name: list-conversations\n        description: List user conversations\n        call: messaging.list-conversations\n        with:\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bubbles\n      name: bubbles\n      description: Group chat rooms\n      operations:\n      - method: GET\n        name: list-bubbles\n        description: List group chat rooms\n        call: messaging.list-bubbles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bubble\n        description: Create a new group chat room\n        call: messaging.create-bubble\n        with:\n          name: rest.name\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts\n      name: contacts\n      description: Contact directory\
  \ search\n      operations:\n      - method: GET\n        name: search-contacts\n        description: Search Rainbow directory\n        call: contacts.search-contacts\n        with:\n          search: rest.search\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{id}\n      name: contact-detail\n      description: Individual contact profiles\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get contact profile and presence\n        call: contacts.get-contact\n        with:\n          contactId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/me\n      name: my-profile\n      description: Authenticated user's profile\n      operations:\n      - method: GET\n        name: get-my-profile\n        description: Get own profile\n        call: contacts.get-my-profile\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/users/me/presence\n      name: my-presence\n      description: User presence management\n      operations:\n      - method: PUT\n        name: update-presence\n        description: Update presence status\n        call: contacts.update-presence\n        with:\n          presence: rest.presence\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: communications-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted enterprise communications and collaboration.\n    tools:\n    - name: send-message\n      description: Send a chat message to a Rainbow contact (1-to-1) or into a group bubble. Supports text messages via REST\n        API.\n      hints:\n        readOnly: false\n        destructive: false\n      call: messaging.send-message\n      with:\n        content: tools.content\n        to: tools.to\n        type: tools.type\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conversations\n      description: List recent conversations for the authenticated Rainbow user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: messaging.list-conversations\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-conversation-messages\n      description: Get message history for a specific Rainbow conversation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: messaging.get-conversation-messages\n      with:\n        conversationId: tools.conversationId\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bubbles\n      description: List group chat rooms (bubbles) the user belongs to in Rainbow\n      hints:\n        readOnly: true\n        openWorld: false\n      call: messaging.list-bubbles\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bubble\n      description: Create a new Rainbow group chat room (bubble) with optional members\n      hints:\n        readOnly: false\n        destructive: false\n      call: messaging.create-bubble\n      with:\n        name: tools.name\n        topic: tools.topic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-contacts\n      description: Search Rainbow enterprise directory for contacts by name, email, or phone\n      hints:\n        readOnly: true\n        openWorld: true\n      call: contacts.search-contacts\n      with:\n        search: tools.search\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get Rainbow contact profile including presence status and contact details\n      hints:\n        readOnly: true\n        openWorld: false\n      call: contacts.get-contact\n\
  \      with:\n        contactId: tools.contactId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-my-profile\n      description: Get the authenticated Rainbow user's own profile\n      hints:\n        readOnly: true\n        openWorld: false\n      call: contacts.get-my-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-presence\n      description: Update presence status in Rainbow (online, away, busy, dnd)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: contacts.update-presence\n      with:\n        presence: tools.presence\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
