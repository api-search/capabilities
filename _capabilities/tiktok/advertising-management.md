---
categories: []
consumed_apis: []
description: Unified workflow capability for managing TikTok advertising campaigns. Combines the Business API to enable full campaign lifecycle management including campaign creation, ad group setup, creative publishing, and performance reporting. Designed for marketing agencies, advertisers, and ad tech platforms.
layout: capability
name: TikTok Advertising Management
operations:
- description: Retrieve advertising campaigns
  method: GET
  name: get-campaigns
  path: /v1/campaigns
- description: Create a new advertising campaign
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get ad groups for a campaign
  method: GET
  name: get-ad-groups
  path: /v1/ad-groups
- description: Create a new ad group
  method: POST
  name: create-ad-group
  path: /v1/ad-groups
- description: Get individual ads
  method: GET
  name: get-ads
  path: /v1/ads
- description: Create a new ad
  method: POST
  name: create-ad
  path: /v1/ads
- description: Get advertising performance report
  method: GET
  name: get-report
  path: /v1/reports
- description: List custom targeting audiences
  method: GET
  name: list-custom-audiences
  path: /v1/audiences
personas: []
provider_name: TikTok
provider_slug: tiktok
search_terms:
- get campaigns
- retrieve individual tiktok ads
- create a new tiktok ad creative
- list custom audiences available for ad targeting
- ad group management
- create a new ad group within a tiktok campaign
- tiktok
- get report
- content
- campaigns
- create ad
- marketing
- create ad group
- retrieve ad groups for a tiktok campaign
- get ad groups for a campaign
- e-commerce
- create a new ad group
- commerce
- get ads
- individual ad management
- advertising
- video
- get individual ads
- get tiktok advertising performance metrics and analytics
- create a new ad
- retrieve advertising campaigns
- list custom targeting audiences
- performance
- social media
- create campaign
- list custom audiences
- create a new tiktok advertising campaign
- get ad groups
- retrieve tiktok advertising campaigns for an advertiser
- custom audience management
- create a new advertising campaign
- campaign lifecycle management
- get advertising performance report
- performance reporting
slug: advertising-management
source_filename: advertising-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TikTok Advertising Management\n  description: Unified workflow capability for managing TikTok advertising campaigns. Combines the Business API to enable\n    full campaign lifecycle management including campaign creation, ad group setup, creative publishing, and performance reporting.\n    Designed for marketing agencies, advertisers, and ad tech platforms.\n  tags:\n  - TikTok\n  - Advertising\n  - Campaigns\n  - Marketing\n  - Performance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIKTOK_BUSINESS_ACCESS_TOKEN: TIKTOK_BUSINESS_ACCESS_TOKEN\n    TIKTOK_ADVERTISER_ID: TIKTOK_ADVERTISER_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: tiktok-business\n    baseUri: https://business-api.tiktok.com\n    description: TikTok API for Business - advertising management\n    authentication:\n      type: apikey\n      key: Access-Token\n      value: '{{TIKTOK_BUSINESS_ACCESS_TOKEN}}'\n  \
  \    placement: header\n    resources:\n    - name: campaigns\n      path: /open_api/v1.3/campaign\n      description: Campaign management operations\n      operations:\n      - name: get-campaigns\n        method: GET\n        description: Retrieve advertising campaigns\n        inputParameters:\n        - name: advertiser_id\n          in: query\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new advertising campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n   \
  \       data:\n            advertiser_id: '{{tools.advertiser_id}}'\n            campaign_name: '{{tools.campaign_name}}'\n            objective_type: '{{tools.objective_type}}'\n            budget_mode: '{{tools.budget_mode}}'\n            budget: '{{tools.budget}}'\n    - name: adgroups\n      path: /open_api/v1.3/adgroup\n      description: Ad group management operations\n      operations:\n      - name: get-ad-groups\n        method: GET\n        description: Retrieve ad groups\n        inputParameters:\n        - name: advertiser_id\n          in: query\n          type: string\n          required: true\n        - name: campaign_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ad-group\n        method: POST\n        description: Create a new ad group\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            advertiser_id: '{{tools.advertiser_id}}'\n            campaign_id: '{{tools.campaign_id}}'\n            adgroup_name: '{{tools.adgroup_name}}'\n            placement_type: '{{tools.placement_type}}'\n    - name: ads\n      path: /open_api/v1.3/ad\n      description: Individual ad management\n      operations:\n      - name: get-ads\n        method: GET\n        description: Retrieve individual ads\n        inputParameters:\n        - name: advertiser_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ad\n        method: POST\n        description: Create a new ad\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            advertiser_id: '{{tools.advertiser_id}}'\n            adgroup_id: '{{tools.adgroup_id}}'\n            ad_name: '{{tools.ad_name}}'\n    - name: reporting\n      path: /open_api/v1.3/report/integrated\n      description: Campaign performance reporting\n      operations:\n      - name: get-report\n        method: GET\n        description: Retrieve integrated advertising performance report\n        inputParameters:\n        - name: advertiser_id\n          in: query\n          type: string\n          required: true\n        - name: report_type\n          in: query\n          type: string\n          required: true\n        - name: data_level\n          in: query\n          type: string\n          required: true\n        - name: dimensions\n          in: query\n          type: string\n          required: true\n        - name: metrics\n          in: query\n          type: string\n          required: true\n        - name:\
  \ start_date\n          in: query\n          type: string\n          required: true\n        - name: end_date\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audiences\n      path: /open_api/v1.3/dmp/custom_audience\n      description: Custom audience management\n      operations:\n      - name: list-custom-audiences\n        method: GET\n        description: List custom audiences\n        inputParameters:\n        - name: advertiser_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tiktok-advertising-api\n    description: Unified REST API for TikTok advertising management.\n    resources:\n    - path: /v1/campaigns\n\
  \      name: campaigns\n      description: Campaign lifecycle management\n      operations:\n      - method: GET\n        name: get-campaigns\n        description: Retrieve advertising campaigns\n        call: tiktok-business.get-campaigns\n        with:\n          advertiser_id: rest.advertiser_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a new advertising campaign\n        call: tiktok-business.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ad-groups\n      name: ad-groups\n      description: Ad group management\n      operations:\n      - method: GET\n        name: get-ad-groups\n        description: Get ad groups for a campaign\n        call: tiktok-business.get-ad-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ad-group\n        description:\
  \ Create a new ad group\n        call: tiktok-business.create-ad-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ads\n      name: ads\n      description: Individual ad management\n      operations:\n      - method: GET\n        name: get-ads\n        description: Get individual ads\n        call: tiktok-business.get-ads\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ad\n        description: Create a new ad\n        call: tiktok-business.create-ad\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Performance reporting\n      operations:\n      - method: GET\n        name: get-report\n        description: Get advertising performance report\n        call: tiktok-business.get-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n\
  \      name: audiences\n      description: Custom audience management\n      operations:\n      - method: GET\n        name: list-custom-audiences\n        description: List custom targeting audiences\n        call: tiktok-business.list-custom-audiences\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tiktok-advertising-mcp\n    transport: http\n    description: MCP server for AI-assisted TikTok advertising management.\n    tools:\n    - name: get-campaigns\n      description: Retrieve TikTok advertising campaigns for an advertiser\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-business.get-campaigns\n      with:\n        advertiser_id: tools.advertiser_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new TikTok advertising campaign\n      hints:\n        readOnly: false\n      call: tiktok-business.create-campaign\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ad-groups\n      description: Retrieve ad groups for a TikTok campaign\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-business.get-ad-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ad-group\n      description: Create a new ad group within a TikTok campaign\n      hints:\n        readOnly: false\n      call: tiktok-business.create-ad-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ads\n      description: Retrieve individual TikTok ads\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-business.get-ads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ad\n      description: Create a new TikTok ad creative\n      hints:\n        readOnly: false\n      call: tiktok-business.create-ad\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-report\n      description: Get TikTok advertising performance metrics and analytics\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-business.get-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-audiences\n      description: List custom audiences available for ad targeting\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-business.list-custom-audiences\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tiktok/refs/heads/main/capabilities/advertising-management.yaml
tags:
- TikTok
- Advertising
- Campaigns
- Marketing
- Performance
tools:
- description: Retrieve TikTok advertising campaigns for an advertiser
  hints:
    idempotent: true
    readOnly: true
  name: get-campaigns
- description: Create a new TikTok advertising campaign
  hints:
    readOnly: false
  name: create-campaign
- description: Retrieve ad groups for a TikTok campaign
  hints:
    idempotent: true
    readOnly: true
  name: get-ad-groups
- description: Create a new ad group within a TikTok campaign
  hints:
    readOnly: false
  name: create-ad-group
- description: Retrieve individual TikTok ads
  hints:
    idempotent: true
    readOnly: true
  name: get-ads
- description: Create a new TikTok ad creative
  hints:
    readOnly: false
  name: create-ad
- description: Get TikTok advertising performance metrics and analytics
  hints:
    idempotent: true
    readOnly: true
  name: get-report
- description: List custom audiences available for ad targeting
  hints:
    idempotent: true
    readOnly: true
  name: list-custom-audiences
---
