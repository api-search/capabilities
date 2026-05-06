---
categories:
- messaging
consumed_apis: []
description: Workflow capability for customer messaging across Messenger and WhatsApp. Combines Messenger Platform API for Facebook/Instagram messaging with WhatsApp Business API for business communication. Used by customer support teams and conversational commerce platforms.
layout: capability
name: Facebook Messaging and Communication
operations:
- description: Send a Messenger message.
  method: POST
  name: send-messenger-message
  path: /v1/messenger-messages
- description: Send a WhatsApp message.
  method: POST
  name: send-whatsapp-message
  path: /v1/whatsapp-messages
- description: List Messenger conversations.
  method: GET
  name: list-conversations
  path: /v1/conversations
- description: List WhatsApp message templates.
  method: GET
  name: list-templates
  path: /v1/templates
personas: []
provider_name: Facebook
provider_slug: facebook
search_terms:
- list whatsapp message templates.
- create a whatsapp message template.
- messenger messaging.
- manage advertising campaigns and performance.
- manage content across facebook, instagram, and threads.
- Customer Support
- manages day-to-day ad campaign optimization.
- send messenger message
- customer messaging across messenger and whatsapp.
- social networking
- plans and executes advertising campaigns.
- send a message via facebook messenger.
- list templates
- Conversational Commerce
- list conversations
- list whatsapp templates
- campaign management and audience targeting.
- direct messaging and customer communication.
- whatsapp template management.
- send a whatsapp message.
- send a messenger message.
- Social Media Manager
- publishing and managing content across platforms.
- Ad Operations
- messaging
- whatsapp
- send whatsapp message
- facebook
- advertising
- create whatsapp template
- messenger
- whatsapp messaging.
- Marketing Manager
- send a message via whatsapp business.
- creates and publishes visual and text content.
- Content Creator
- conversation management.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
- customer communication
- social media
- manages content and engagement across meta platforms.
- list messenger conversations
- list messenger conversations.
- content publishing
slug: messaging-and-communication
source_filename: messaging-and-communication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Facebook Messaging and Communication\n  description: Workflow capability for customer messaging across Messenger and WhatsApp. Combines Messenger Platform API for\n    Facebook/Instagram messaging with WhatsApp Business API for business communication. Used by customer support teams and\n    conversational commerce platforms.\n  tags:\n  - Facebook\n  - Messaging\n  - Customer Communication\n  - WhatsApp\n  - Messenger\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MESSENGER_PAGE_TOKEN: MESSENGER_PAGE_TOKEN\n    WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: messenger-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Messenger Platform API v21.0.\n    authentication:\n      type: bearer\n      token: '{{MESSENGER_PAGE_TOKEN}}'\n    resources:\n    - name: messages\n      path: /\n      description: Message sending.\n  \
  \    operations:\n      - name: send-message\n        method: POST\n        description: Send a message to a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations\n      path: /\n      description: Conversation management.\n      operations:\n      - name: list-conversations\n        method: GET\n        description: List conversations for a page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: whatsapp-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Business API v21.0.\n    authentication:\n      type: bearer\n      token: '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: messages\n      path: /\n      description: Message sending.\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a WhatsApp\
  \ message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /\n      description: Template management.\n      operations:\n      - name: list-templates\n        method: GET\n        description: List message templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-template\n        method: POST\n        description: Create a message template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: messaging-api\n    description: Unified REST API for cross-platform messaging.\n    resources:\n    - path: /v1/messenger-messages\n      name: messenger-messages\n      description: Messenger messaging.\n      operations:\n      - method: POST\n    \
  \    name: send-messenger-message\n        description: Send a Messenger message.\n        call: messenger-api.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/whatsapp-messages\n      name: whatsapp-messages\n      description: WhatsApp messaging.\n      operations:\n      - method: POST\n        name: send-whatsapp-message\n        description: Send a WhatsApp message.\n        call: whatsapp-api.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversations\n      name: conversations\n      description: Conversation management.\n      operations:\n      - method: GET\n        name: list-conversations\n        description: List Messenger conversations.\n        call: messenger-api.list-conversations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n      description: WhatsApp template management.\n   \
  \   operations:\n      - method: GET\n        name: list-templates\n        description: List WhatsApp message templates.\n        call: whatsapp-api.list-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted customer messaging.\n    tools:\n    - name: send-messenger-message\n      description: Send a message via Facebook Messenger.\n      hints:\n        readOnly: false\n      call: messenger-api.send-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-whatsapp-message\n      description: Send a message via WhatsApp Business.\n      hints:\n        readOnly: false\n      call: whatsapp-api.send-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messenger-conversations\n      description: List Messenger conversations.\n      hints:\n        readOnly:\
  \ true\n      call: messenger-api.list-conversations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-whatsapp-templates\n      description: List WhatsApp message templates.\n      hints:\n        readOnly: true\n      call: whatsapp-api.list-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-whatsapp-template\n      description: Create a WhatsApp message template.\n      hints:\n        readOnly: false\n      call: whatsapp-api.create-template\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/facebook/refs/heads/main/capabilities/messaging-and-communication.yaml
tags:
- Facebook
- Messaging
- Customer Communication
- WhatsApp
- Messenger
tools:
- description: Send a message via Facebook Messenger.
  hints:
    readOnly: false
  name: send-messenger-message
- description: Send a message via WhatsApp Business.
  hints:
    readOnly: false
  name: send-whatsapp-message
- description: List Messenger conversations.
  hints:
    readOnly: true
  name: list-messenger-conversations
- description: List WhatsApp message templates.
  hints:
    readOnly: true
  name: list-whatsapp-templates
- description: Create a WhatsApp message template.
  hints:
    readOnly: false
  name: create-whatsapp-template
---
