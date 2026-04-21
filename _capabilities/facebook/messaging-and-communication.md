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
- conversation management.
- list templates
- send a messenger message.
- messenger messaging.
- advertising
- whatsapp messaging.
- send a message via facebook messenger.
- whatsapp
- Marketing Manager
- list conversations
- customer messaging across messenger and whatsapp.
- manage content across facebook, instagram, and threads.
- whatsapp template management.
- Social Media Manager
- facebook
- handles customer inquiries via messaging channels.
- performance tracking and insights.
- direct messaging and customer communication.
- campaign management and audience targeting.
- send whatsapp message
- send messenger message
- send a whatsapp message.
- list messenger conversations
- plans and executes advertising campaigns.
- social networking
- Conversational Commerce
- messaging
- create a whatsapp message template.
- messenger
- customer communication
- social media
- send a message via whatsapp business.
- Customer Support
- manages day-to-day ad campaign optimization.
- Content Creator
- Ad Operations
- create whatsapp template
- list whatsapp templates
- creates and publishes visual and text content.
- content publishing
- publishing and managing content across platforms.
- list whatsapp message templates.
- manage advertising campaigns and performance.
- list messenger conversations.
- manages content and engagement across meta platforms.
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
