---
categories:
- customer-engagement
consumed_apis:
- marketing-api
- graph-api
- instagram-api
description: Workflow capability for managing advertising campaigns across Facebook and Instagram. Combines Marketing API for campaign management with Graph API for content insights and Instagram API for visual ad performance. Used by marketing managers and ad operations teams.
layout: capability
name: Facebook Advertising and Marketing
operations:
- description: List advertising campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get advertising insights.
  method: GET
  name: get-insights
  path: /v1/insights
- description: List custom audiences.
  method: GET
  name: list-audiences
  path: /v1/audiences
personas: []
provider_name: Facebook
provider_slug: facebook
search_terms:
- creates and publishes visual and text content.
- manage content across facebook, instagram, and threads.
- list advertising campaigns.
- Ad Operations
- messaging
- direct messaging and customer communication.
- create custom audience
- manages day-to-day ad campaign optimization.
- marketing
- create a new advertising campaign.
- Conversational Commerce
- performance tracking and insights.
- create campaign
- Content Creator
- audience management.
- facebook
- Social Media Manager
- content publishing
- campaign management.
- Customer Support
- list audiences
- social networking
- customer messaging across messenger and whatsapp.
- advertising
- Marketing Manager
- get advertising insights.
- create a campaign.
- handles customer inquiries via messaging channels.
- manage advertising campaigns and performance.
- publishing and managing content across platforms.
- list custom audiences.
- manages content and engagement across meta platforms.
- get advertising performance insights.
- list all advertising campaigns.
- get ad insights
- list custom audiences for targeting.
- create a new custom audience.
- plans and executes advertising campaigns.
- list campaigns
- campaign management and audience targeting.
- get insights
- list custom audiences
- social media
- performance insights.
- campaigns
slug: advertising-and-marketing
tags:
- Facebook
- Advertising
- Marketing
- Campaigns
tools:
- description: List all advertising campaigns.
  hints:
    readOnly: true
  name: list-campaigns
- description: Create a new advertising campaign.
  hints:
    readOnly: false
  name: create-campaign
- description: Get advertising performance insights.
  hints:
    readOnly: true
  name: get-ad-insights
- description: List custom audiences for targeting.
  hints:
    readOnly: true
  name: list-custom-audiences
- description: Create a new custom audience.
  hints:
    readOnly: false
  name: create-custom-audience
---
