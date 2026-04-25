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
- send a message via whatsapp business.
- performance tracking and insights.
- campaign management and audience targeting.
- manage advertising campaigns and performance.
- direct messaging and customer communication.
- customer messaging across messenger and whatsapp.
- list whatsapp message templates.
- list conversations
- plans and executes advertising campaigns.
- Ad Operations
- list messenger conversations
- social networking
- messenger
- manage content across facebook, instagram, and threads.
- customer communication
- send a whatsapp message.
- messaging
- list templates
- send a message via facebook messenger.
- messenger messaging.
- content publishing
- creates and publishes visual and text content.
- manages day-to-day ad campaign optimization.
- create a whatsapp message template.
- handles customer inquiries via messaging channels.
- advertising
- whatsapp
- Content Creator
- send a messenger message.
- create whatsapp template
- Conversational Commerce
- facebook
- whatsapp template management.
- conversation management.
- Customer Support
- publishing and managing content across platforms.
- Social Media Manager
- send whatsapp message
- list messenger conversations.
- Marketing Manager
- social media
- whatsapp messaging.
- manages content and engagement across meta platforms.
- list whatsapp templates
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
