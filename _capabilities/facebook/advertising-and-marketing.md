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
- campaigns
- audience management.
- Customer Support
- marketing
- create campaign
- create a new advertising campaign.
- advertising
- manage advertising campaigns and performance.
- social networking
- publishing and managing content across platforms.
- campaign management.
- get ad insights
- list custom audiences for targeting.
- create custom audience
- manages day-to-day ad campaign optimization.
- list campaigns
- list custom audiences
- Social Media Manager
- direct messaging and customer communication.
- facebook
- list audiences
- get insights
- get advertising insights.
- list all advertising campaigns.
- get advertising performance insights.
- handles customer inquiries via messaging channels.
- content publishing
- Ad Operations
- create a campaign.
- Marketing Manager
- list custom audiences.
- performance insights.
- create a new custom audience.
- Conversational Commerce
- manage content across facebook, instagram, and threads.
- Content Creator
- messaging
- customer messaging across messenger and whatsapp.
- plans and executes advertising campaigns.
- creates and publishes visual and text content.
- list advertising campaigns.
- manages content and engagement across meta platforms.
- campaign management and audience targeting.
- social media
- performance tracking and insights.
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
