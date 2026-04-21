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
- customer journey workflow management
- list audience segments for targeting campaigns and journeys
- audience segment management
- create segment
- integrates messaging apis and manages endpoints
- pinpoint application management
- create a new pinpoint application for customer engagement
- list customer journeys
- create a new customer journey
- marketing campaign management
- email
- journeys
- sms
- list apps
- list audience segments
- list automated customer journey workflows
- create audience segment
- amazon
- customer engagement
- push notifications
- list all pinpoint applications
- communications
- list marketing campaigns for a pinpoint application
- messaging
- create a new audience segment
- campaigns
- create app
- create a new pinpoint application
- multi-channel customer engagement workflow
- manages campaigns, segments, and journeys
- create a new marketing campaign
- voice
- create a new multi-channel marketing campaign
- segmentation
- list campaigns
- create a new customer audience segment based on attributes or imported data
- create a multi-step automated customer engagement journey
- list segments
- send transactional messages to customer endpoints
- list campaigns for an application
- create campaign
- aws
- send transactional messages
- send messages
- Marketing Manager
- analytics
- Growth Engineer
- marketing
- send transactional messages (confirmations, alerts, notifications) to customer endpoints
- list journeys
- create journey
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
