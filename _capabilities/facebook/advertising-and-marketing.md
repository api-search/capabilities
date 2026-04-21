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
- list advertising campaigns.
- list custom audiences for targeting.
- campaign management and audience targeting.
- create a campaign.
- content publishing
- create a new advertising campaign.
- list audiences
- Conversational Commerce
- publishing and managing content across platforms.
- social media
- create a new custom audience.
- create custom audience
- manage content across facebook, instagram, and threads.
- messaging
- advertising
- get insights
- list all advertising campaigns.
- facebook
- creates and publishes visual and text content.
- Customer Support
- Marketing Manager
- Ad Operations
- customer messaging across messenger and whatsapp.
- list campaigns
- performance insights.
- direct messaging and customer communication.
- create campaign
- list custom audiences
- get ad insights
- Social Media Manager
- plans and executes advertising campaigns.
- get advertising insights.
- marketing
- campaigns
- get advertising performance insights.
- social networking
- manages day-to-day ad campaign optimization.
- Content Creator
- list custom audiences.
- manage advertising campaigns and performance.
- manages content and engagement across meta platforms.
- audience management.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
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
