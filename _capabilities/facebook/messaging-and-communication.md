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
- list messenger conversations.
- send a messenger message.
- create whatsapp template
- manage advertising campaigns and performance.
- publishing and managing content across platforms.
- messenger
- send a message via facebook messenger.
- Conversational Commerce
- direct messaging and customer communication.
- list whatsapp templates
- social networking
- facebook
- social media
- whatsapp template management.
- campaign management and audience targeting.
- performance tracking and insights.
- Marketing Manager
- send messenger message
- messenger messaging.
- creates and publishes visual and text content.
- advertising
- Social Media Manager
- manages day-to-day ad campaign optimization.
- Customer Support
- content publishing
- conversation management.
- customer communication
- list templates
- manage content across facebook, instagram, and threads.
- plans and executes advertising campaigns.
- whatsapp
- send whatsapp message
- list messenger conversations
- customer messaging across messenger and whatsapp.
- whatsapp messaging.
- messaging
- send a message via whatsapp business.
- manages content and engagement across meta platforms.
- Ad Operations
- list whatsapp message templates.
- send a whatsapp message.
- create a whatsapp message template.
- Content Creator
- handles customer inquiries via messaging channels.
- list conversations
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
