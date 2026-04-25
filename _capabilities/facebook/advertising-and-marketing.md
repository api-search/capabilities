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
- manages content and engagement across meta platforms.
- Content Creator
- performance insights.
- Social Media Manager
- Marketing Manager
- campaigns
- social media
- plans and executes advertising campaigns.
- performance tracking and insights.
- list custom audiences.
- list custom audiences
- get advertising performance insights.
- campaign management.
- facebook
- list campaigns
- direct messaging and customer communication.
- content publishing
- manage content across facebook, instagram, and threads.
- get ad insights
- manage advertising campaigns and performance.
- create campaign
- customer messaging across messenger and whatsapp.
- creates and publishes visual and text content.
- messaging
- create a campaign.
- create a new advertising campaign.
- manages day-to-day ad campaign optimization.
- publishing and managing content across platforms.
- social networking
- get advertising insights.
- get insights
- audience management.
- Ad Operations
- create a new custom audience.
- create custom audience
- campaign management and audience targeting.
- advertising
- list audiences
- list custom audiences for targeting.
- list all advertising campaigns.
- handles customer inquiries via messaging channels.
- marketing
- Customer Support
- Conversational Commerce
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
