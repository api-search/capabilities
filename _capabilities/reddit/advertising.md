---
categories: []
consumed_apis: []
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
- content
- marketing
- create an advertising campaign
- reddit
- subreddit research for targeting
- research subreddit
- communities
- list custom targeting audiences for retargeting campaigns
- list campaigns
- list all advertising campaigns for an account
- research a subreddit community to assess ad targeting potential
- advertising
- get trending posts from a subreddit to understand audience interests
- social news
- get subreddit trending
- list custom targeting audiences
- research a subreddit community for ad targeting
- social media
- get ads account
- create campaign
- list custom audiences
- get reddit ads account details and configuration
- custom audience management
- create a new reddit advertising campaign with budget and objective
- get subreddit info
- campaign lifecycle management
slug: advertising
source_filename: advertising.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reddit Advertising\n  description: Unified capability for managing Reddit advertising campaigns. Combines the Reddit Ads API for campaign lifecycle\n    management and the Data API for audience research and targeting intelligence. Used by digital marketers, performance agencies,\n    and brands to create, optimize, and report on Reddit advertising campaigns programmatically.\n  tags:\n  - Advertising\n  - Marketing\n  - Reddit\n  - Social Media\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REDDIT_ADS_ACCESS_TOKEN: REDDIT_ADS_ACCESS_TOKEN\n    REDDIT_ACCESS_TOKEN: REDDIT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: reddit-ads\n    baseUri: https://ads-api.reddit.com/api/v3\n    description: Reddit Ads API for programmatic advertising management\n    authentication:\n      type: bearer\n      token: '{{REDDIT_ADS_ACCESS_TOKEN}}'\n    resources:\n    - name: account\n\
  \      path: /accounts/{account_id}\n      description: Ads account management\n      operations:\n      - name: get-account\n        method: GET\n        description: Get ads account details\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: The ads account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /campaigns\n      description: Campaign management\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List advertising campaigns\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Ads account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n\
  \        method: POST\n        description: Create an advertising campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            campaign_name: '{{tools.campaign_name}}'\n            objective: '{{tools.objective}}'\n            total_budget_amount: '{{tools.budget}}'\n    - name: custom-audiences\n      path: /custom_audiences\n      description: Custom audience management\n      operations:\n      - name: list-custom-audiences\n        method: GET\n        description: List custom targeting audiences\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Ads account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: reddit-data\n    baseUri: https://oauth.reddit.com\n    description: Reddit Data API for accessing platform content and communities\n    authentication:\n      type: bearer\n      token: '{{REDDIT_ACCESS_TOKEN}}'\n    resources:\n    - name: me\n      path: /api/v1/me\n      description: Current user identity and profile\n      operations:\n      - name: get-me\n        method: GET\n        description: Get current authenticated user identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hot-listings\n      path: /r/{subreddit}/hot\n      description: Hot post listings for a subreddit\n      operations:\n      - name: get-hot-listings\n        method: GET\n        description: Get hot posts from a subreddit\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        -\
  \ name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of posts to return (max 100)\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: new-listings\n      path: /r/{subreddit}/new\n      description: New post listings for a subreddit\n      operations:\n      - name: get-new-listings\n        method: GET\n        description: Get newest posts from a subreddit\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of posts to return\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: subreddit-info\n      path: /r/{subreddit}/about\n      description: Subreddit community information\n      operations:\n      - name: get-subreddit-info\n        method: GET\n        description: Get subreddit metadata and configuration\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Reddit search\n      operations:\n      - name: search-submissions\n        method: GET\n        description: Search Reddit submissions\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: sort\n          in: query\n\
  \          type: string\n          required: false\n          description: Sort order (relevance, hot, top, new)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: submit\n      path: /api/submit\n      description: Post submission\n      operations:\n      - name: submit-post\n        method: POST\n        description: Submit a new post to a subreddit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            sr: '{{tools.subreddit}}'\n            title: '{{tools.title}}'\n            text: '{{tools.text}}'\n            kind: self\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: reddit-advertising-rest\n    description:\
  \ Unified REST API for Reddit advertising management.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description: Campaign lifecycle management\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List advertising campaigns\n        call: reddit-ads.list-campaigns\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create an advertising campaign\n        call: reddit-ads.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n      name: audiences\n      description: Custom audience management\n      operations:\n      - method: GET\n        name: list-custom-audiences\n        description: List custom targeting audiences\n        call: reddit-ads.list-custom-audiences\n        with:\n          account_id: rest.account_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subreddits/{subreddit}\n      name: subreddit-research\n      description: Subreddit research for targeting\n      operations:\n      - method: GET\n        name: get-subreddit-info\n        description: Research a subreddit community for ad targeting\n        call: reddit-data.get-subreddit-info\n        with:\n          subreddit: rest.subreddit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: reddit-advertising-mcp\n    transport: http\n    description: MCP server for AI-assisted Reddit advertising management.\n    tools:\n    - name: get-ads-account\n      description: Get Reddit Ads account details and configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reddit-ads.get-account\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-campaigns\n      description: List all advertising campaigns for an account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reddit-ads.list-campaigns\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new Reddit advertising campaign with budget and objective\n      hints:\n        readOnly: false\n        openWorld: false\n      call: reddit-ads.create-campaign\n      with:\n        account_id: tools.account_id\n        campaign_name: tools.campaign_name\n        objective: tools.objective\n        budget: tools.budget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-audiences\n      description: List custom targeting audiences for retargeting campaigns\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reddit-ads.list-custom-audiences\n    \
  \  with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: research-subreddit\n      description: Research a subreddit community to assess ad targeting potential\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.get-subreddit-info\n      with:\n        subreddit: tools.subreddit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subreddit-trending\n      description: Get trending posts from a subreddit to understand audience interests\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.get-hot-listings\n      with:\n        subreddit: tools.subreddit\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
