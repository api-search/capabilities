---
categories:
- customer-engagement
consumed_apis:
- retail-media-api
description: Unified retail media advertising workflow combining campaign management, audience targeting, performance analytics, and custom reporting for advertisers on the Albertsons Media Collective platform. Designed for brand managers and media planners managing grocery retail advertising campaigns.
layout: capability
name: Albertsons Retail Media Advertising
operations:
- description: List all advertising campaigns with status and budget details.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a new advertising campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get campaign details by identifier.
  method: GET
  name: get-campaign
  path: /v1/campaigns/{campaignId}
- description: Retrieve near-real-time performance metrics.
  method: GET
  name: list-performance-metrics
  path: /v1/performance
- description: List audience segments for campaign targeting.
  method: GET
  name: list-audiences
  path: /v1/audiences
- description: Generate a custom performance report.
  method: POST
  name: generate-report
  path: /v1/reports
personas: []
provider_name: albertsons
provider_slug: albertsons
search_terms:
- campaign performance metrics.
- generate report
- plans and optimizes retail media campaigns, analyzes performance metrics, and generates reports for advertising clients.
- get campaign details by identifier.
- campaign detail retrieval.
- digital advertising within retail environments, leveraging shopper purchase data for targeting.
- advertising
- audience targeting segments.
- retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
- list audience targeting segments available on albertsons media collective based on shopper purchase behavior.
- retrieve near-real-time performance metrics.
- generate a custom performance report.
- food
- create a new advertising campaign with budget, audience targeting, and scheduling on albertsons media collective.
- pharmacy
- list performance metrics
- performance analytics
- manages advertising campaigns and budgets on behalf of consumer brands advertising in the albertsons network.
- advertising campaign management.
- list all advertising campaigns with status and budget details.
- consumer goods
- retail media
- list audience segments for campaign targeting.
- list all advertising campaigns on the albertsons media collective with status, budget, and targeting details.
- campaign creation, management, and performance optimization for brands.
- list campaigns
- custom performance report generation.
- campaigns
- get detailed information about a specific advertising campaign by its identifier.
- generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
- Brand Manager
- grocery
- list audiences
- unified retail media advertising workflow for campaign management, audience targeting, performance analytics, and reporting.
- analytics
- create campaign
- retail
- albertsons
- audience targeting
- create a new advertising campaign.
- get campaign
- Media Planner
slug: retail-media-advertising
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Albertsons Retail Media Advertising\"\n  description: \"Unified retail media advertising workflow combining campaign management, audience targeting, performance analytics, and custom reporting for advertisers on the Albertsons Media Collective platform. Designed for brand managers and media planners managing grocery retail advertising campaigns.\"\n  tags:\n    - Albertsons\n    - Retail Media\n    - Advertising\n    - Campaigns\n    - Performance Analytics\n    - Audience Targeting\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALBERTSONS_API_TOKEN: ALBERTSONS_API_TOKEN\n\ncapability:\n  consumes:\n    - import: retail-media-api\n      location: ./shared/retail-media-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: albertsons-advertising-api\n      description: \"Unified REST API for retail media advertising on the Albertsons Media Collective.\"\
  \n      resources:\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Advertising campaign management.\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List all advertising campaigns with status and budget details.\"\n              call: \"retail-media-api.list-campaigns\"\n              with:\n                status: \"rest.status\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create a new advertising campaign.\"\n              call: \"retail-media-api.create-campaign\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/campaigns/{campaignId}\n          name: campaign-detail\n          description:\
  \ \"Campaign detail retrieval.\"\n          operations:\n            - method: GET\n              name: get-campaign\n              description: \"Get campaign details by identifier.\"\n              call: \"retail-media-api.get-campaign\"\n              with:\n                campaignId: \"rest.campaignId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/performance\n          name: performance\n          description: \"Campaign performance metrics.\"\n          operations:\n            - method: GET\n              name: list-performance-metrics\n              description: \"Retrieve near-real-time performance metrics.\"\n              call: \"retail-media-api.list-performance-metrics\"\n              with:\n                campaignId: \"rest.campaignId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                granularity: \"rest.granularity\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences\n          name: audiences\n          description: \"Audience targeting segments.\"\n          operations:\n            - method: GET\n              name: list-audiences\n              description: \"List audience segments for campaign targeting.\"\n              call: \"retail-media-api.list-audiences\"\n              with:\n                category: \"rest.category\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Custom performance report generation.\"\n          operations:\n            - method: POST\n              name: generate-report\n              description: \"Generate a custom performance report.\"\n              call: \"retail-media-api.generate-report\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: albertsons-advertising-mcp\n      transport: http\n      description: \"MCP server for AI-assisted retail media advertising management on the Albertsons Media Collective.\"\n      tools:\n        - name: list-campaigns\n          description: \"List all advertising campaigns on the Albertsons Media Collective with status, budget, and targeting details.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"retail-media-api.list-campaigns\"\n          with:\n            status: \"tools.status\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-campaign\n          description: \"Create a new advertising campaign with budget, audience targeting, and scheduling on Albertsons Media Collective.\"\n          hints:\n    \
  \        readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"retail-media-api.create-campaign\"\n          with:\n            name: \"tools.name\"\n            budget: \"tools.budget\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            targetAudienceIds: \"tools.targetAudienceIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-campaign\n          description: \"Get detailed information about a specific advertising campaign by its identifier.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"retail-media-api.get-campaign\"\n          with:\n            campaignId: \"tools.campaignId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-performance-metrics\n          description: \"Retrieve near-real-time advertising performance metrics\
  \ including impressions, clicks, conversions, and return on ad spend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"retail-media-api.list-performance-metrics\"\n          with:\n            campaignId: \"tools.campaignId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            granularity: \"tools.granularity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-audiences\n          description: \"List audience targeting segments available on Albertsons Media Collective based on shopper purchase behavior.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"retail-media-api.list-audiences\"\n          with:\n            category: \"tools.category\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-report\n\
  \          description: \"Generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retail-media-api.generate-report\"\n          with:\n            campaignIds: \"tools.campaignIds\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            dimensions: \"tools.dimensions\"\n            metrics: \"tools.metrics\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/albertsons/refs/heads/main/capabilities/retail-media-advertising.yaml
tags:
- Albertsons
- Retail Media
- Advertising
- Campaigns
- Performance Analytics
- Audience Targeting
tools:
- description: List all advertising campaigns on the Albertsons Media Collective with status, budget, and targeting details.
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Create a new advertising campaign with budget, audience targeting, and scheduling on Albertsons Media Collective.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-campaign
- description: Get detailed information about a specific advertising campaign by its identifier.
  hints:
    openWorld: true
    readOnly: true
  name: get-campaign
- description: Retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
  hints:
    openWorld: true
    readOnly: true
  name: list-performance-metrics
- description: List audience targeting segments available on Albertsons Media Collective based on shopper purchase behavior.
  hints:
    openWorld: true
    readOnly: true
  name: list-audiences
- description: Generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
  hints:
    openWorld: false
    readOnly: true
  name: generate-report
---
