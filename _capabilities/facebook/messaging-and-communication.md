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
- send messenger message
- campaign management and audience targeting.
- whatsapp
- list messenger conversations.
- content publishing
- social media
- Conversational Commerce
- publishing and managing content across platforms.
- list templates
- send a messenger message.
- send a whatsapp message.
- manage content across facebook, instagram, and threads.
- messaging
- advertising
- facebook
- whatsapp template management.
- send a message via facebook messenger.
- creates and publishes visual and text content.
- list conversations
- Customer Support
- messenger
- create whatsapp template
- list whatsapp templates
- Marketing Manager
- list whatsapp message templates.
- Ad Operations
- create a whatsapp message template.
- customer messaging across messenger and whatsapp.
- customer communication
- direct messaging and customer communication.
- messenger messaging.
- Social Media Manager
- plans and executes advertising campaigns.
- social networking
- send whatsapp message
- whatsapp messaging.
- conversation management.
- Content Creator
- manages day-to-day ad campaign optimization.
- send a message via whatsapp business.
- list messenger conversations
- manage advertising campaigns and performance.
- manages content and engagement across meta platforms.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
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
