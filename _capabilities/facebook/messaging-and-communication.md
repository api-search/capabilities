---
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
- send whatsapp message
- customer communication
- messenger messaging.
- Customer Support
- messenger
- list messenger conversations
- manage advertising campaigns and performance.
- advertising
- social networking
- publishing and managing content across platforms.
- manages day-to-day ad campaign optimization.
- list messenger conversations.
- conversation management.
- whatsapp
- Social Media Manager
- direct messaging and customer communication.
- facebook
- send messenger message
- whatsapp messaging.
- handles customer inquiries via messaging channels.
- send a message via facebook messenger.
- content publishing
- Ad Operations
- Marketing Manager
- list templates
- list conversations
- send a whatsapp message.
- whatsapp template management.
- create a whatsapp message template.
- Conversational Commerce
- messaging
- manage content across facebook, instagram, and threads.
- Content Creator
- create whatsapp template
- customer messaging across messenger and whatsapp.
- list whatsapp templates
- plans and executes advertising campaigns.
- send a message via whatsapp business.
- creates and publishes visual and text content.
- manages content and engagement across meta platforms.
- send a messenger message.
- campaign management and audience targeting.
- social media
- list whatsapp message templates.
- performance tracking and insights.
slug: messaging-and-communication
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
