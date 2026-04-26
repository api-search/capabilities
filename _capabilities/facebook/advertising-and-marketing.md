---
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
- get advertising performance insights.
- Ad Operations
- manages content and engagement across meta platforms.
- list custom audiences.
- social networking
- get advertising insights.
- facebook
- Conversational Commerce
- social media
- manage advertising campaigns and performance.
- list custom audiences for targeting.
- list campaigns
- customer messaging across messenger and whatsapp.
- manages day-to-day ad campaign optimization.
- campaigns
- advertising
- manage content across facebook, instagram, and threads.
- Social Media Manager
- get insights
- create a new custom audience.
- messaging
- performance tracking and insights.
- audience management.
- direct messaging and customer communication.
- content publishing
- create custom audience
- Content Creator
- plans and executes advertising campaigns.
- create a campaign.
- list custom audiences
- Customer Support
- marketing
- create campaign
- creates and publishes visual and text content.
- handles customer inquiries via messaging channels.
- campaign management.
- campaign management and audience targeting.
- performance insights.
- list audiences
- create a new advertising campaign.
- publishing and managing content across platforms.
- list all advertising campaigns.
- list advertising campaigns.
- get ad insights
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
