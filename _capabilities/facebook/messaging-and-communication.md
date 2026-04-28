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
- Marketing Manager
- messenger messaging.
- customer communication
- whatsapp messaging.
- list whatsapp templates
- manage advertising campaigns and performance.
- direct messaging and customer communication.
- facebook
- publishing and managing content across platforms.
- advertising
- Content Creator
- whatsapp
- Social Media Manager
- list conversations
- Conversational Commerce
- whatsapp template management.
- messenger
- list messenger conversations
- list templates
- list whatsapp message templates.
- create a whatsapp message template.
- conversation management.
- creates and publishes visual and text content.
- Customer Support
- send a whatsapp message.
- list messenger conversations.
- send a message via whatsapp business.
- create whatsapp template
- handles customer inquiries via messaging channels.
- send whatsapp message
- messaging
- send messenger message
- plans and executes advertising campaigns.
- manage content across facebook, instagram, and threads.
- send a message via facebook messenger.
- performance tracking and insights.
- campaign management and audience targeting.
- send a messenger message.
- social networking
- content publishing
- social media
- manages day-to-day ad campaign optimization.
- Ad Operations
- customer messaging across messenger and whatsapp.
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
