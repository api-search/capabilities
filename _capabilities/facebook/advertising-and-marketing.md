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
- Marketing Manager
- audience management.
- manage advertising campaigns and performance.
- direct messaging and customer communication.
- facebook
- list custom audiences.
- publishing and managing content across platforms.
- create a campaign.
- advertising
- Content Creator
- get advertising insights.
- list custom audiences for targeting.
- get insights
- Social Media Manager
- performance insights.
- Conversational Commerce
- list campaigns
- list all advertising campaigns.
- create a new custom audience.
- list audiences
- campaign management.
- creates and publishes visual and text content.
- get advertising performance insights.
- Customer Support
- marketing
- create a new advertising campaign.
- handles customer inquiries via messaging channels.
- messaging
- plans and executes advertising campaigns.
- create campaign
- manage content across facebook, instagram, and threads.
- manages content and engagement across meta platforms.
- performance tracking and insights.
- campaign management and audience targeting.
- social networking
- campaigns
- content publishing
- list custom audiences
- get ad insights
- Ad Operations
- manages day-to-day ad campaign optimization.
- customer messaging across messenger and whatsapp.
- social media
- create custom audience
- list advertising campaigns.
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
