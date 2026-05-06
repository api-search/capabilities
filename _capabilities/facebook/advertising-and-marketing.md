---
categories:
- customer-engagement
consumed_apis: []
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
- create a campaign.
- list all advertising campaigns.
- manage advertising campaigns and performance.
- manage content across facebook, instagram, and threads.
- Customer Support
- get advertising insights.
- manages day-to-day ad campaign optimization.
- audience management.
- customer messaging across messenger and whatsapp.
- social networking
- campaigns
- plans and executes advertising campaigns.
- marketing
- Conversational Commerce
- create a new advertising campaign.
- campaign management and audience targeting.
- direct messaging and customer communication.
- performance insights.
- get advertising performance insights.
- campaign management.
- get ad insights
- list audiences
- list custom audiences for targeting.
- Social Media Manager
- list campaigns
- create custom audience
- publishing and managing content across platforms.
- Ad Operations
- messaging
- create a new custom audience.
- facebook
- advertising
- Marketing Manager
- creates and publishes visual and text content.
- Content Creator
- list advertising campaigns.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
- social media
- list custom audiences.
- create campaign
- list custom audiences
- manages content and engagement across meta platforms.
- get insights
- content publishing
slug: advertising-and-marketing
source_filename: advertising-and-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Facebook Advertising and Marketing\n  description: Workflow capability for managing advertising campaigns across Facebook and Instagram. Combines Marketing API\n    for campaign management with Graph API for content insights and Instagram API for visual ad performance. Used by marketing\n    managers and ad operations teams.\n  tags:\n  - Facebook\n  - Advertising\n  - Marketing\n  - Campaigns\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACEBOOK_MARKETING_TOKEN: FACEBOOK_MARKETING_TOKEN\n    FACEBOOK_ACCESS_TOKEN: FACEBOOK_ACCESS_TOKEN\n    INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Facebook Marketing API v21.0.\n    authentication:\n      type: bearer\n      token: '{{FACEBOOK_MARKETING_TOKEN}}'\n    resources:\n    - name: campaigns\n      path: /\n\
  \      description: Campaign management.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List campaigns for an ad account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new campaign.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /\n      description: Performance insights.\n      operations:\n      - name: get-account-insights\n        method: GET\n        description: Get advertising insights for an ad account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audiences\n      path: /\n      description: Audience management.\n      operations:\n      - name: list-custom-audiences\n\
  \        method: GET\n        description: List custom audiences.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-custom-audience\n        method: POST\n        description: Create a custom audience.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: graph-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Facebook Graph API v21.0.\n    authentication:\n      type: bearer\n      token: '{{FACEBOOK_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /\n      description: User profile operations.\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Get the current authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \    - name: get-user\n        method: GET\n        description: Get a user by ID.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posts\n      path: /\n      description: Post operations.\n      operations:\n      - name: get-user-feed\n        method: GET\n        description: Get posts from a user's feed.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-post\n        method: POST\n        description: Create a new post.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-post\n        method: DELETE\n        description: Delete a post.\n        inputParameters:\n        - name: post_id\n          in: path\n          type: string\n          required: true\n          description: Post ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /\n      description: Comment operations.\n      operations:\n      - name: get-post-comments\n        method: GET\n        description: Get comments on a post.\n        inputParameters:\n        - name: post_id\n          in: path\n          type: string\n          required: true\n          description: Post ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-comment\n        method: POST\n        description: Create a comment on a post.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: instagram-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Instagram API via Graph API v21.0.\n    authentication:\n      type: bearer\n      token: '{{INSTAGRAM_ACCESS_TOKEN}}'\n    resources:\n    - name: media\n      path: /\n      description: Media management.\n      operations:\n      - name: list-media\n        method: GET\n        description: List Instagram media.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-media\n        method: POST\n        description: Create an Instagram media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-media\n        method: POST\n        description: Publish a\
  \ media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /\n      description: Account insights.\n      operations:\n      - name: get-insights\n        method: GET\n        description: Get Instagram account insights.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: advertising-api\n    description: Unified REST API for Facebook advertising and marketing.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description: Campaign management.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List advertising campaigns.\n        call: marketing-api.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name:\
  \ create-campaign\n        description: Create a campaign.\n        call: marketing-api.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights\n      name: insights\n      description: Performance insights.\n      operations:\n      - method: GET\n        name: get-insights\n        description: Get advertising insights.\n        call: marketing-api.get-account-insights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n      name: audiences\n      description: Audience management.\n      operations:\n      - method: GET\n        name: list-audiences\n        description: List custom audiences.\n        call: marketing-api.list-custom-audiences\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: advertising-mcp\n    transport: http\n    description: MCP server for AI-assisted advertising management.\n    tools:\n\
  \    - name: list-campaigns\n      description: List all advertising campaigns.\n      hints:\n        readOnly: true\n      call: marketing-api.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new advertising campaign.\n      hints:\n        readOnly: false\n      call: marketing-api.create-campaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ad-insights\n      description: Get advertising performance insights.\n      hints:\n        readOnly: true\n      call: marketing-api.get-account-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-audiences\n      description: List custom audiences for targeting.\n      hints:\n        readOnly: true\n      call: marketing-api.list-custom-audiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-custom-audience\n      description:\
  \ Create a new custom audience.\n      hints:\n        readOnly: false\n      call: marketing-api.create-custom-audience\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
