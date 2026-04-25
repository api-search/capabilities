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
- performance tracking and insights.
- manage content across facebook, instagram, and threads.
- list whatsapp message templates.
- list whatsapp templates
- creates and publishes visual and text content.
- send messenger message
- content publishing
- Conversational Commerce
- list conversations
- social media
- customer communication
- manages day-to-day ad campaign optimization.
- social networking
- create a whatsapp message template.
- Customer Support
- send whatsapp message
- Marketing Manager
- Ad Operations
- whatsapp template management.
- manages content and engagement across meta platforms.
- direct messaging and customer communication.
- messenger messaging.
- send a message via facebook messenger.
- whatsapp
- manage advertising campaigns and performance.
- whatsapp messaging.
- list messenger conversations
- list templates
- Content Creator
- campaign management and audience targeting.
- list messenger conversations.
- messaging
- conversation management.
- send a whatsapp message.
- facebook
- send a messenger message.
- advertising
- send a message via whatsapp business.
- messenger
- publishing and managing content across platforms.
- create whatsapp template
- customer messaging across messenger and whatsapp.
- handles customer inquiries via messaging channels.
- Social Media Manager
- plans and executes advertising campaigns.
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
