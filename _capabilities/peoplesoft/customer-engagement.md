---
categories:
- crm-sales
consumed_apis:
- crm
- chatbot
- notification-framework
description: Unified workflow for CRM users combining customer management, case management, sales, chatbot integration, and notifications across PeopleSoft CRM, Chatbot Integration, and Notification Framework APIs.
layout: capability
name: PeopleSoft Customer Engagement
operations:
- description: Retrieve customer records.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Retrieve details for a specific customer.
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: Retrieve support and service cases.
  method: GET
  name: list-cases
  path: /v1/cases
- description: Create a new support or service case.
  method: POST
  name: create-case
  path: /v1/cases
- description: Retrieve sales opportunities.
  method: GET
  name: list-opportunities
  path: /v1/opportunities
- description: Retrieve available chatbot intents.
  method: GET
  name: list-intents
  path: /v1/intents
- description: Process a chatbot intent fulfillment request.
  method: POST
  name: fulfill-intent
  path: /v1/intent-fulfillments
- description: Retrieve notifications for the current user.
  method: GET
  name: list-notifications
  path: /v1/notifications
- description: Send a notification via email, text, or in-app channels.
  method: POST
  name: send-notification
  path: /v1/notifications
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- retrieve available chatbot intents.
- send a notification via email, text, or in-app channels.
- erp
- chatbot intents
- chatbot intent fulfillments
- list cases
- peopletools platform services.
- notification management
- retrieve sales opportunities.
- list notifications
- financial management
- create case
- create a new support or service case.
- fulfill intent
- send notification
- campus solutions.
- individual customer details
- retrieve support and service cases.
- crm
- retrieve details for a specific customer.
- financial and supply chain management.
- hcm
- support and service cases
- chatbot
- case management
- human capital management.
- sales
- list customers
- supply chain management
- sales opportunities
- peoplesoft
- customer engagement
- get customer
- enterprise software
- list opportunities
- retrieve notifications for the current user.
- retrieve customer records.
- process a chatbot intent fulfillment request.
- list intents
- customer records
- campus solutions
slug: customer-engagement
tags:
- PeopleSoft
- CRM
- Customer Engagement
- Case Management
- Sales
- Chatbot
tools:
- description: Retrieve customer records.
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Retrieve details for a specific customer.
  hints:
    openWorld: true
    readOnly: true
  name: get-customer
- description: Retrieve support and service cases.
  hints:
    openWorld: true
    readOnly: true
  name: list-cases
- description: Create a new support or service case.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-case
- description: Retrieve sales opportunities.
  hints:
    openWorld: true
    readOnly: true
  name: list-opportunities
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
---
