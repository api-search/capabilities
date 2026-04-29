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
- get advertising performance insights.
- customer messaging across messenger and whatsapp.
- Content Creator
- list advertising campaigns.
- create a new advertising campaign.
- list custom audiences.
- create custom audience
- list custom audiences
- Social Media Manager
- direct messaging and customer communication.
- list all advertising campaigns.
- get ad insights
- manages day-to-day ad campaign optimization.
- manage advertising campaigns and performance.
- campaign management and audience targeting.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
- plans and executes advertising campaigns.
- creates and publishes visual and text content.
- list custom audiences for targeting.
- performance insights.
- Customer Support
- facebook
- campaigns
- manages content and engagement across meta platforms.
- social media
- get advertising insights.
- social networking
- Marketing Manager
- campaign management.
- advertising
- marketing
- Ad Operations
- get insights
- create a new custom audience.
- publishing and managing content across platforms.
- content publishing
- list campaigns
- manage content across facebook, instagram, and threads.
- list audiences
- Conversational Commerce
- create a campaign.
- create campaign
- messaging
- audience management.
slug: advertising-and-marketing
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Facebook Advertising and Marketing\n  description: >-\n    Workflow capability for managing advertising campaigns across Facebook and\n    Instagram. Combines Marketing API for campaign management with Graph API for\n    content insights and Instagram API for visual ad performance. Used by\n    marketing managers and ad operations teams.\n  tags:\n    - Facebook\n    - Advertising\n    - Marketing\n    - Campaigns\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACEBOOK_MARKETING_TOKEN: FACEBOOK_MARKETING_TOKEN\n      FACEBOOK_ACCESS_TOKEN: FACEBOOK_ACCESS_TOKEN\n      INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-api\n      location: ./shared/marketing-api.yaml\n    - import: graph-api\n      location: ./shared/graph-api.yaml\n    - import: instagram-api\n      location: ./shared/instagram-api.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8081\n      namespace: advertising-api\n      description: \"Unified REST API for Facebook advertising and marketing.\"\n      resources:\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Campaign management.\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List advertising campaigns.\"\n              call: \"marketing-api.list-campaigns\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create a campaign.\"\n              call: \"marketing-api.create-campaign\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/insights\n          name: insights\n          description: \"Performance insights.\"\n          operations:\n            - method: GET\n      \
  \        name: get-insights\n              description: \"Get advertising insights.\"\n              call: \"marketing-api.get-account-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences\n          name: audiences\n          description: \"Audience management.\"\n          operations:\n            - method: GET\n              name: list-audiences\n              description: \"List custom audiences.\"\n              call: \"marketing-api.list-custom-audiences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: advertising-mcp\n      transport: http\n      description: \"MCP server for AI-assisted advertising management.\"\n      tools:\n        - name: list-campaigns\n          description: \"List all advertising campaigns.\"\n          hints:\n            readOnly: true\n          call: \"marketing-api.list-campaigns\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-campaign\n          description: \"Create a new advertising campaign.\"\n          hints:\n            readOnly: false\n          call: \"marketing-api.create-campaign\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ad-insights\n          description: \"Get advertising performance insights.\"\n          hints:\n            readOnly: true\n          call: \"marketing-api.get-account-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-audiences\n          description: \"List custom audiences for targeting.\"\n          hints:\n            readOnly: true\n          call: \"marketing-api.list-custom-audiences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-custom-audience\n   \
  \       description: \"Create a new custom audience.\"\n          hints:\n            readOnly: false\n          call: \"marketing-api.create-custom-audience\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/facebook/refs/heads/main/capabilities/advertising-and-marketing.yaml
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
