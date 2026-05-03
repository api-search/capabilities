---
categories: []
consumed_apis:
- reddit-ads
- reddit-data
description: Unified capability for managing Reddit advertising campaigns. Combines the Reddit Ads API for campaign lifecycle management and the Data API for audience research and targeting intelligence. Used by digital marketers, performance agencies, and brands to create, optimize, and report on Reddit advertising campaigns programmatically.
layout: capability
name: Reddit Advertising
operations:
- description: List advertising campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create an advertising campaign
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: List custom targeting audiences
  method: GET
  name: list-custom-audiences
  path: /v1/audiences
- description: Research a subreddit community for ad targeting
  method: GET
  name: get-subreddit-info
  path: /v1/subreddits/{subreddit}
personas: []
provider_name: Reddit
provider_slug: reddit
search_terms:
- list advertising campaigns
- research a subreddit community to assess ad targeting potential
- marketing
- create an advertising campaign
- get reddit ads account details and configuration
- get subreddit info
- list custom targeting audiences for retargeting campaigns
- advertising
- research a subreddit community for ad targeting
- get subreddit trending
- list custom targeting audiences
- social news
- content
- get trending posts from a subreddit to understand audience interests
- list custom audiences
- get ads account
- campaign lifecycle management
- subreddit research for targeting
- create a new reddit advertising campaign with budget and objective
- reddit
- social media
- list all advertising campaigns for an account
- research subreddit
- communities
- list campaigns
- custom audience management
- create campaign
slug: advertising
source_filename: advertising.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Reddit Advertising\"\n  description: >-\n    Unified capability for managing Reddit advertising campaigns. Combines the\n    Reddit Ads API for campaign lifecycle management and the Data API for\n    audience research and targeting intelligence. Used by digital marketers,\n    performance agencies, and brands to create, optimize, and report on Reddit\n    advertising campaigns programmatically.\n  tags:\n    - Advertising\n    - Marketing\n    - Reddit\n    - Social Media\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REDDIT_ADS_ACCESS_TOKEN: REDDIT_ADS_ACCESS_TOKEN\n      REDDIT_ACCESS_TOKEN: REDDIT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: reddit-ads\n      location: ./shared/ads-api.yaml\n    - import: reddit-data\n      location: ./shared/data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: reddit-advertising-rest\n      description:\
  \ \"Unified REST API for Reddit advertising management.\"\n      resources:\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Campaign lifecycle management\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List advertising campaigns\"\n              call: \"reddit-ads.list-campaigns\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create an advertising campaign\"\n              call: \"reddit-ads.create-campaign\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences\n          name: audiences\n          description: \"Custom audience management\"\n          operations:\n            - method: GET\n\
  \              name: list-custom-audiences\n              description: \"List custom targeting audiences\"\n              call: \"reddit-ads.list-custom-audiences\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subreddits/{subreddit}\n          name: subreddit-research\n          description: \"Subreddit research for targeting\"\n          operations:\n            - method: GET\n              name: get-subreddit-info\n              description: \"Research a subreddit community for ad targeting\"\n              call: \"reddit-data.get-subreddit-info\"\n              with:\n                subreddit: \"rest.subreddit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: reddit-advertising-mcp\n      transport: http\n      description: \"MCP server\
  \ for AI-assisted Reddit advertising management.\"\n      tools:\n        - name: get-ads-account\n          description: \"Get Reddit Ads account details and configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reddit-ads.get-account\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-campaigns\n          description: \"List all advertising campaigns for an account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reddit-ads.list-campaigns\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-campaign\n          description: \"Create a new Reddit advertising campaign with budget and objective\"\n          hints:\n            readOnly: false\n\
  \            openWorld: false\n          call: \"reddit-ads.create-campaign\"\n          with:\n            account_id: \"tools.account_id\"\n            campaign_name: \"tools.campaign_name\"\n            objective: \"tools.objective\"\n            budget: \"tools.budget\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-audiences\n          description: \"List custom targeting audiences for retargeting campaigns\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reddit-ads.list-custom-audiences\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: research-subreddit\n          description: \"Research a subreddit community to assess ad targeting potential\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reddit-data.get-subreddit-info\"\
  \n          with:\n            subreddit: \"tools.subreddit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subreddit-trending\n          description: \"Get trending posts from a subreddit to understand audience interests\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reddit-data.get-hot-listings\"\n          with:\n            subreddit: \"tools.subreddit\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reddit/refs/heads/main/capabilities/advertising.yaml
tags:
- Advertising
- Marketing
- Reddit
- Social Media
tools:
- description: Get Reddit Ads account details and configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-ads-account
- description: List all advertising campaigns for an account
  hints:
    openWorld: false
    readOnly: true
  name: list-campaigns
- description: Create a new Reddit advertising campaign with budget and objective
  hints:
    openWorld: false
    readOnly: false
  name: create-campaign
- description: List custom targeting audiences for retargeting campaigns
  hints:
    openWorld: false
    readOnly: true
  name: list-custom-audiences
- description: Research a subreddit community to assess ad targeting potential
  hints:
    openWorld: true
    readOnly: true
  name: research-subreddit
- description: Get trending posts from a subreddit to understand audience interests
  hints:
    openWorld: true
    readOnly: true
  name: get-subreddit-trending
---
