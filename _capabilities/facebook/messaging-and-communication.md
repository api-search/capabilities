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
- creates and publishes visual and text content.
- manage content across facebook, instagram, and threads.
- send whatsapp message
- conversation management.
- list whatsapp templates
- send a message via whatsapp business.
- Ad Operations
- messaging
- send messenger message
- direct messaging and customer communication.
- manages day-to-day ad campaign optimization.
- Conversational Commerce
- performance tracking and insights.
- whatsapp
- list whatsapp message templates.
- whatsapp template management.
- facebook
- Social Media Manager
- content publishing
- list messenger conversations.
- Customer Support
- social networking
- whatsapp messaging.
- customer messaging across messenger and whatsapp.
- send a whatsapp message.
- advertising
- Marketing Manager
- handles customer inquiries via messaging channels.
- list messenger conversations
- messenger messaging.
- manage advertising campaigns and performance.
- list templates
- publishing and managing content across platforms.
- customer communication
- manages content and engagement across meta platforms.
- send a message via facebook messenger.
- create a whatsapp message template.
- messenger
- plans and executes advertising campaigns.
- campaign management and audience targeting.
- list conversations
- social media
- create whatsapp template
- send a messenger message.
- Content Creator
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
