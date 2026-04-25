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
- manages content and engagement across meta platforms.
- Content Creator
- list messenger conversations.
- customer communication
- create whatsapp template
- Social Media Manager
- Marketing Manager
- whatsapp template management.
- social media
- plans and executes advertising campaigns.
- performance tracking and insights.
- facebook
- send a message via whatsapp business.
- send a messenger message.
- messaging
- direct messaging and customer communication.
- manage content across facebook, instagram, and threads.
- manage advertising campaigns and performance.
- creates and publishes visual and text content.
- customer messaging across messenger and whatsapp.
- content publishing
- manages day-to-day ad campaign optimization.
- list whatsapp templates
- list whatsapp message templates.
- conversation management.
- send a whatsapp message.
- publishing and managing content across platforms.
- social networking
- list conversations
- Ad Operations
- list templates
- send messenger message
- messenger
- campaign management and audience targeting.
- whatsapp messaging.
- advertising
- whatsapp
- list messenger conversations
- handles customer inquiries via messaging channels.
- send whatsapp message
- Customer Support
- Conversational Commerce
- create a whatsapp message template.
- messenger messaging.
- send a message via facebook messenger.
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
