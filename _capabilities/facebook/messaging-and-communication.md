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
- list whatsapp templates
- social networking
- list messenger conversations.
- send messenger message
- send a whatsapp message.
- whatsapp template management.
- direct messaging and customer communication.
- customer messaging across messenger and whatsapp.
- creates and publishes visual and text content.
- campaign management and audience targeting.
- manage content across facebook, instagram, and threads.
- manages content and engagement across meta platforms.
- Ad Operations
- customer communication
- content publishing
- whatsapp messaging.
- conversation management.
- send whatsapp message
- social media
- list whatsapp message templates.
- send a message via whatsapp business.
- manage advertising campaigns and performance.
- Social Media Manager
- create a whatsapp message template.
- messaging
- whatsapp
- send a message via facebook messenger.
- advertising
- messenger messaging.
- list templates
- list messenger conversations
- manages day-to-day ad campaign optimization.
- create whatsapp template
- Customer Support
- performance tracking and insights.
- plans and executes advertising campaigns.
- Content Creator
- publishing and managing content across platforms.
- messenger
- facebook
- list conversations
- send a messenger message.
- handles customer inquiries via messaging channels.
- Marketing Manager
- Conversational Commerce
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
