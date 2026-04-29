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
- list campaigns
- get advertising performance insights.
- list audiences
- performance insights.
- get insights
- Social Media Manager
- social media
- messaging
- campaigns
- list custom audiences.
- facebook
- publishing and managing content across platforms.
- Content Creator
- direct messaging and customer communication.
- list custom audiences
- social networking
- content publishing
- audience management.
- create a new custom audience.
- list custom audiences for targeting.
- performance tracking and insights.
- get ad insights
- Ad Operations
- handles customer inquiries via messaging channels.
- campaign management and audience targeting.
- advertising
- manages day-to-day ad campaign optimization.
- creates and publishes visual and text content.
- marketing
- get advertising insights.
- create campaign
- create a new advertising campaign.
- list advertising campaigns.
- plans and executes advertising campaigns.
- manages content and engagement across meta platforms.
- list all advertising campaigns.
- Marketing Manager
- manage content across facebook, instagram, and threads.
- customer messaging across messenger and whatsapp.
- Customer Support
- create custom audience
- Conversational Commerce
- create a campaign.
- manage advertising campaigns and performance.
- campaign management.
slug: advertising-and-marketing
source_filename: advertising-and-marketing.yaml
source_heading: Capability Spec
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
