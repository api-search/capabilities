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
- send a whatsapp message.
- manages day-to-day ad campaign optimization.
- send whatsapp message
- facebook
- advertising
- social media
- list whatsapp message templates.
- handles customer inquiries via messaging channels.
- campaign management and audience targeting.
- send a messenger message.
- Customer Support
- direct messaging and customer communication.
- list messenger conversations.
- create a whatsapp message template.
- manage content across facebook, instagram, and threads.
- plans and executes advertising campaigns.
- content publishing
- messaging
- customer messaging across messenger and whatsapp.
- Marketing Manager
- messenger messaging.
- send a message via whatsapp business.
- messenger
- Social Media Manager
- manages content and engagement across meta platforms.
- Ad Operations
- Content Creator
- social networking
- customer communication
- create whatsapp template
- whatsapp template management.
- list whatsapp templates
- performance tracking and insights.
- whatsapp messaging.
- creates and publishes visual and text content.
- publishing and managing content across platforms.
- send a message via facebook messenger.
- conversation management.
- Conversational Commerce
- send messenger message
- list templates
- manage advertising campaigns and performance.
- list conversations
- whatsapp
- list messenger conversations
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
