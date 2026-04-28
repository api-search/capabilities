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
- create a new custom audience.
- create a campaign.
- manage advertising campaigns and performance.
- performance insights.
- publishing and managing content across platforms.
- create campaign
- campaigns
- campaign management.
- Conversational Commerce
- direct messaging and customer communication.
- audience management.
- social networking
- facebook
- list advertising campaigns.
- social media
- campaign management and audience targeting.
- performance tracking and insights.
- list custom audiences
- marketing
- advertising
- list custom audiences for targeting.
- create custom audience
- Marketing Manager
- Social Media Manager
- list campaigns
- creates and publishes visual and text content.
- create a new advertising campaign.
- manages day-to-day ad campaign optimization.
- Customer Support
- content publishing
- get advertising performance insights.
- list custom audiences.
- manage content across facebook, instagram, and threads.
- plans and executes advertising campaigns.
- customer messaging across messenger and whatsapp.
- get insights
- get ad insights
- messaging
- manages content and engagement across meta platforms.
- Ad Operations
- list audiences
- get advertising insights.
- Content Creator
- handles customer inquiries via messaging channels.
- list all advertising campaigns.
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
