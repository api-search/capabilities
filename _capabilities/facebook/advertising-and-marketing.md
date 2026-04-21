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
- list custom audiences.
- manages day-to-day ad campaign optimization.
- create custom audience
- create a new custom audience.
- facebook
- advertising
- performance insights.
- social media
- handles customer inquiries via messaging channels.
- campaign management and audience targeting.
- audience management.
- Customer Support
- direct messaging and customer communication.
- plans and executes advertising campaigns.
- manage content across facebook, instagram, and threads.
- content publishing
- create campaign
- get advertising performance insights.
- messaging
- campaign management.
- get insights
- customer messaging across messenger and whatsapp.
- Marketing Manager
- list all advertising campaigns.
- create a new advertising campaign.
- get ad insights
- list custom audiences
- campaigns
- list custom audiences for targeting.
- Social Media Manager
- Ad Operations
- manages content and engagement across meta platforms.
- list advertising campaigns.
- Content Creator
- list audiences
- social networking
- performance tracking and insights.
- creates and publishes visual and text content.
- publishing and managing content across platforms.
- Conversational Commerce
- list campaigns
- manage advertising campaigns and performance.
- create a campaign.
- get advertising insights.
- marketing
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
