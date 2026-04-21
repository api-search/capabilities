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
- audience segment management
- create journey
- aws
- send messages
- list apps
- list automated customer journey workflows
- voice
- integrates messaging apis and manages endpoints
- create a multi-step automated customer engagement journey
- communications
- list campaigns
- push notifications
- manages campaigns, segments, and journeys
- list audience segments
- create a new pinpoint application
- Marketing Manager
- campaigns
- create campaign
- list customer journeys
- list campaigns for an application
- analytics
- send transactional messages
- segmentation
- create a new customer audience segment based on attributes or imported data
- customer journey workflow management
- multi-channel customer engagement workflow
- list journeys
- list audience segments for targeting campaigns and journeys
- journeys
- email
- create a new audience segment
- pinpoint application management
- messaging
- create a new pinpoint application for customer engagement
- create a new marketing campaign
- list marketing campaigns for a pinpoint application
- marketing
- create app
- amazon
- create segment
- create a new multi-channel marketing campaign
- Growth Engineer
- sms
- list segments
- list all pinpoint applications
- create a new customer journey
- customer engagement
- marketing campaign management
- send transactional messages (confirmations, alerts, notifications) to customer endpoints
- create audience segment
- send transactional messages to customer endpoints
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
