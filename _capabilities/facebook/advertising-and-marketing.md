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
- campaign management.
- list all advertising campaigns.
- advertising
- manage advertising campaigns and performance.
- get advertising insights.
- list advertising campaigns.
- get ad insights
- list campaigns
- create a new advertising campaign.
- campaigns
- Marketing Manager
- create campaign
- customer messaging across messenger and whatsapp.
- get insights
- manage content across facebook, instagram, and threads.
- Social Media Manager
- facebook
- handles customer inquiries via messaging channels.
- performance tracking and insights.
- direct messaging and customer communication.
- campaign management and audience targeting.
- plans and executes advertising campaigns.
- social networking
- Conversational Commerce
- get advertising performance insights.
- messaging
- create custom audience
- social media
- Customer Support
- manages day-to-day ad campaign optimization.
- create a new custom audience.
- marketing
- performance insights.
- audience management.
- create a campaign.
- list audiences
- list custom audiences for targeting.
- Content Creator
- Ad Operations
- creates and publishes visual and text content.
- content publishing
- publishing and managing content across platforms.
- list custom audiences
- list custom audiences.
- manages content and engagement across meta platforms.
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
