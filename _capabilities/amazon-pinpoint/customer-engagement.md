---
consumed_apis:
- amazon-pinpoint
description: Workflow capability for multi-channel customer engagement using Amazon Pinpoint. Combines campaign management, audience segmentation, customer journeys, and transactional messaging for marketing teams and growth engineers.
layout: capability
name: Amazon Pinpoint Customer Engagement
operations:
- description: List all Pinpoint applications
  method: GET
  name: list-apps
  path: /v1/apps
- description: Create a new Pinpoint application
  method: POST
  name: create-app
  path: /v1/apps
- description: List campaigns for an application
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a new marketing campaign
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: List audience segments
  method: GET
  name: list-segments
  path: /v1/audiences
- description: Create a new audience segment
  method: POST
  name: create-segment
  path: /v1/audiences
- description: List customer journeys
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: Create a new customer journey
  method: POST
  name: create-journey
  path: /v1/journeys
- description: Send transactional messages to customer endpoints
  method: POST
  name: send-messages
  path: /v1/messages
personas: []
provider_name: Amazon Pinpoint
provider_slug: amazon-pinpoint
search_terms:
- integrates messaging apis and manages endpoints
- send transactional messages (confirmations, alerts, notifications) to customer endpoints
- customer engagement
- create a new customer journey
- segmentation
- email
- send messages
- create a new customer audience segment based on attributes or imported data
- pinpoint application management
- analytics
- list audience segments for targeting campaigns and journeys
- send transactional messages
- create campaign
- messaging
- create a multi-step automated customer engagement journey
- list apps
- list segments
- Marketing Manager
- sms
- voice
- communications
- audience segment management
- Growth Engineer
- list campaigns for an application
- campaigns
- journeys
- create app
- manages campaigns, segments, and journeys
- list all pinpoint applications
- send transactional messages to customer endpoints
- list audience segments
- amazon
- create a new pinpoint application for customer engagement
- list marketing campaigns for a pinpoint application
- push notifications
- list automated customer journey workflows
- customer journey workflow management
- marketing campaign management
- list customer journeys
- create a new audience segment
- aws
- list campaigns
- create segment
- create journey
- create a new multi-channel marketing campaign
- multi-channel customer engagement workflow
- create a new marketing campaign
- list journeys
- create audience segment
- create a new pinpoint application
- marketing
slug: customer-engagement
tags:
- Amazon
- AWS
- Marketing
- Customer Engagement
- Campaigns
- Journeys
- Segmentation
- Messaging
tools:
- description: List all Pinpoint applications
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: Create a new Pinpoint application for customer engagement
  hints:
    destructive: false
    readOnly: false
  name: create-app
- description: List marketing campaigns for a Pinpoint application
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Create a new multi-channel marketing campaign
  hints:
    destructive: false
    readOnly: false
  name: create-campaign
- description: List audience segments for targeting campaigns and journeys
  hints:
    openWorld: true
    readOnly: true
  name: list-audience-segments
- description: Create a new customer audience segment based on attributes or imported data
  hints:
    destructive: false
    readOnly: false
  name: create-audience-segment
- description: List automated customer journey workflows
  hints:
    openWorld: true
    readOnly: true
  name: list-journeys
- description: Create a multi-step automated customer engagement journey
  hints:
    destructive: false
    readOnly: false
  name: create-journey
- description: Send transactional messages (confirmations, alerts, notifications) to customer endpoints
  hints:
    destructive: false
    readOnly: false
  name: send-transactional-messages
---
