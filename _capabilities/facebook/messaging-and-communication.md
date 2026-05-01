---
categories:
- messaging
consumed_apis:
- messenger-api
- whatsapp-api
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
- creates and publishes visual and text content.
- whatsapp messaging.
- send a messenger message.
- manages day-to-day ad campaign optimization.
- campaign management and audience targeting.
- advertising
- facebook
- plans and executes advertising campaigns.
- send a whatsapp message.
- Social Media Manager
- send whatsapp message
- list conversations
- performance tracking and insights.
- whatsapp template management.
- direct messaging and customer communication.
- list whatsapp message templates.
- list messenger conversations.
- send a message via facebook messenger.
- Content Creator
- manage advertising campaigns and performance.
- customer messaging across messenger and whatsapp.
- Ad Operations
- Marketing Manager
- list templates
- social networking
- list messenger conversations
- customer communication
- create a whatsapp message template.
- messenger messaging.
- whatsapp
- handles customer inquiries via messaging channels.
- messenger
- messaging
- conversation management.
- send messenger message
- Customer Support
- send a message via whatsapp business.
- social media
- list whatsapp templates
- manage content across facebook, instagram, and threads.
- publishing and managing content across platforms.
- Conversational Commerce
- create whatsapp template
- manages content and engagement across meta platforms.
- content publishing
slug: messaging-and-communication
source_filename: messaging-and-communication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Facebook Messaging and Communication\n  description: >-\n    Workflow capability for customer messaging across Messenger and WhatsApp.\n    Combines Messenger Platform API for Facebook/Instagram messaging with\n    WhatsApp Business API for business communication. Used by customer support\n    teams and conversational commerce platforms.\n  tags:\n    - Facebook\n    - Messaging\n    - Customer Communication\n    - WhatsApp\n    - Messenger\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MESSENGER_PAGE_TOKEN: MESSENGER_PAGE_TOKEN\n      WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: messenger-api\n      location: ./shared/messenger-api.yaml\n    - import: whatsapp-api\n      location: ./shared/whatsapp-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: messaging-api\n      description: \"Unified REST API for cross-platform\
  \ messaging.\"\n      resources:\n        - path: /v1/messenger-messages\n          name: messenger-messages\n          description: \"Messenger messaging.\"\n          operations:\n            - method: POST\n              name: send-messenger-message\n              description: \"Send a Messenger message.\"\n              call: \"messenger-api.send-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/whatsapp-messages\n          name: whatsapp-messages\n          description: \"WhatsApp messaging.\"\n          operations:\n            - method: POST\n              name: send-whatsapp-message\n              description: \"Send a WhatsApp message.\"\n              call: \"whatsapp-api.send-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/conversations\n          name: conversations\n          description: \"Conversation management.\"\
  \n          operations:\n            - method: GET\n              name: list-conversations\n              description: \"List Messenger conversations.\"\n              call: \"messenger-api.list-conversations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/templates\n          name: templates\n          description: \"WhatsApp template management.\"\n          operations:\n            - method: GET\n              name: list-templates\n              description: \"List WhatsApp message templates.\"\n              call: \"whatsapp-api.list-templates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted customer messaging.\"\n      tools:\n        - name: send-messenger-message\n          description: \"Send a message via Facebook\
  \ Messenger.\"\n          hints:\n            readOnly: false\n          call: \"messenger-api.send-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-whatsapp-message\n          description: \"Send a message via WhatsApp Business.\"\n          hints:\n            readOnly: false\n          call: \"whatsapp-api.send-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messenger-conversations\n          description: \"List Messenger conversations.\"\n          hints:\n            readOnly: true\n          call: \"messenger-api.list-conversations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-whatsapp-templates\n          description: \"List WhatsApp message templates.\"\n          hints:\n            readOnly: true\n          call: \"whatsapp-api.list-templates\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-whatsapp-template\n          description: \"Create a WhatsApp message template.\"\n          hints:\n            readOnly: false\n          call: \"whatsapp-api.create-template\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
