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
- Marketing Manager
- Ad Operations
- send a message via whatsapp business.
- manages content and engagement across meta platforms.
- messenger
- social networking
- send a messenger message.
- send messenger message
- facebook
- send a whatsapp message.
- Conversational Commerce
- social media
- messenger messaging.
- manage advertising campaigns and performance.
- send a message via facebook messenger.
- customer communication
- whatsapp messaging.
- customer messaging across messenger and whatsapp.
- manages day-to-day ad campaign optimization.
- list whatsapp templates
- advertising
- manage content across facebook, instagram, and threads.
- Social Media Manager
- create whatsapp template
- messaging
- list conversations
- list messenger conversations.
- performance tracking and insights.
- direct messaging and customer communication.
- content publishing
- Content Creator
- plans and executes advertising campaigns.
- list templates
- whatsapp template management.
- Customer Support
- handles customer inquiries via messaging channels.
- creates and publishes visual and text content.
- whatsapp
- campaign management and audience targeting.
- conversation management.
- list messenger conversations
- create a whatsapp message template.
- publishing and managing content across platforms.
- send whatsapp message
- list whatsapp message templates.
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
