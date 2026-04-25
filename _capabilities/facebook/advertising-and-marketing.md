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
- list custom audiences for targeting.
- performance tracking and insights.
- manage content across facebook, instagram, and threads.
- content publishing
- list audiences
- creates and publishes visual and text content.
- get insights
- campaigns
- marketing
- list custom audiences
- Conversational Commerce
- social media
- manages day-to-day ad campaign optimization.
- get advertising performance insights.
- social networking
- Customer Support
- list custom audiences.
- audience management.
- Marketing Manager
- Ad Operations
- manages content and engagement across meta platforms.
- direct messaging and customer communication.
- list all advertising campaigns.
- manage advertising campaigns and performance.
- list campaigns
- create custom audience
- Content Creator
- campaign management and audience targeting.
- messaging
- create a new custom audience.
- create campaign
- facebook
- campaign management.
- performance insights.
- create a campaign.
- advertising
- get advertising insights.
- get ad insights
- publishing and managing content across platforms.
- customer messaging across messenger and whatsapp.
- create a new advertising campaign.
- handles customer inquiries via messaging channels.
- Social Media Manager
- list advertising campaigns.
- plans and executes advertising campaigns.
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
