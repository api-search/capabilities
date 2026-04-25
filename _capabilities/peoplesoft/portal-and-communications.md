---
consumed_apis:
- interaction-hub
- notification-framework
- chatbot
description: Unified workflow for content managers combining portal content management, branding, chatbot integration, and notification services across PeopleSoft Interaction Hub, Chatbot Integration, and Notification Framework APIs.
layout: capability
name: PeopleSoft Portal And Communications
operations:
- description: Retrieve portal content items.
  method: GET
  name: list-content
  path: /v1/content
- description: Create a new portal content item.
  method: POST
  name: create-content
  path: /v1/content
- description: Retrieve available branding themes.
  method: GET
  name: list-themes
  path: /v1/themes
- description: Retrieve notifications for the current user.
  method: GET
  name: list-notifications
  path: /v1/notifications
- description: Send a notification via email, text, or in-app channels.
  method: POST
  name: send-notification
  path: /v1/notifications
- description: Retrieve available chatbot intents.
  method: GET
  name: list-intents
  path: /v1/intents
- description: Process a chatbot intent fulfillment request.
  method: POST
  name: fulfill-intent
  path: /v1/intent-fulfillments
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- financial management
- campus solutions
- chatbot intents
- retrieve available chatbot intents.
- erp
- retrieve portal content items.
- branding themes
- retrieve notifications for the current user.
- list notifications
- process a chatbot intent fulfillment request.
- enterprise software
- hcm
- list intents
- notifications
- campus solutions.
- chatbot
- portal
- create a new portal content item.
- communications
- portal content items
- retrieve available branding themes.
- send a notification via email, text, or in-app channels.
- fulfill intent
- crm
- send notification
- peopletools platform services.
- human capital management.
- supply chain management
- list themes
- peoplesoft
- create content
- notification management
- financial and supply chain management.
- list content
- chatbot intent fulfillments
- content management
slug: portal-and-communications
tags:
- PeopleSoft
- Portal
- Content Management
- Communications
- Notifications
- Chatbot
tools:
- description: Retrieve portal content items.
  hints:
    openWorld: true
    readOnly: true
  name: list-content
- description: Create a new portal content item.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-content
- description: Retrieve available branding themes.
  hints:
    openWorld: true
    readOnly: true
  name: list-themes
- description: Retrieve notifications for the current user.
  hints:
    openWorld: true
    readOnly: true
  name: list-notifications
- description: Send a notification via email, text, or in-app channels.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-notification
- description: Retrieve available chatbot intents.
  hints:
    openWorld: true
    readOnly: true
  name: list-intents
- description: Process a chatbot intent fulfillment request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfill-intent
---
