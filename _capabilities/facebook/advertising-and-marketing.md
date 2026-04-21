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
- social networking
- create custom audience
- direct messaging and customer communication.
- customer messaging across messenger and whatsapp.
- creates and publishes visual and text content.
- campaign management and audience targeting.
- manage content across facebook, instagram, and threads.
- manages content and engagement across meta platforms.
- Ad Operations
- content publishing
- campaign management.
- get advertising performance insights.
- audience management.
- social media
- list all advertising campaigns.
- list custom audiences.
- performance insights.
- list custom audiences for targeting.
- manage advertising campaigns and performance.
- Social Media Manager
- list advertising campaigns.
- list custom audiences
- messaging
- create a new advertising campaign.
- campaigns
- create a new custom audience.
- advertising
- manages day-to-day ad campaign optimization.
- list campaigns
- Customer Support
- performance tracking and insights.
- plans and executes advertising campaigns.
- Content Creator
- get insights
- create campaign
- facebook
- list audiences
- publishing and managing content across platforms.
- handles customer inquiries via messaging channels.
- create a campaign.
- get ad insights
- Marketing Manager
- get advertising insights.
- Conversational Commerce
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
