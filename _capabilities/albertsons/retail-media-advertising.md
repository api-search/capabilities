---
categories:
- customer-engagement
consumed_apis: []
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
- analytics
- manages advertising campaigns and budgets on behalf of consumer brands advertising in the albertsons network.
- grocery
- food
- list all advertising campaigns with status and budget details.
- campaign creation, management, and performance optimization for brands.
- audience targeting segments.
- retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
- retail
- performance analytics
- Media Planner
- digital advertising within retail environments, leveraging shopper purchase data for targeting.
- generate a custom performance report.
- list audiences
- pharmacy
- list audience targeting segments available on albertsons media collective based on shopper purchase behavior.
- albertsons
- get detailed information about a specific advertising campaign by its identifier.
- retrieve near-real-time performance metrics.
- list audience segments for campaign targeting.
- list performance metrics
- generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
- retail media
- get campaign
- list campaigns
- consumer goods
- custom performance report generation.
- Brand Manager
- generate report
- campaigns
- create a new advertising campaign.
- campaign detail retrieval.
- advertising campaign management.
- plans and optimizes retail media campaigns, analyzes performance metrics, and generates reports for advertising clients.
- campaign performance metrics.
- list all advertising campaigns on the albertsons media collective with status, budget, and targeting details.
- get campaign details by identifier.
- create campaign
- audience targeting
- unified retail media advertising workflow for campaign management, audience targeting, performance analytics, and reporting.
- advertising
- create a new advertising campaign with budget, audience targeting, and scheduling on albertsons media collective.
slug: retail-media-advertising
source_filename: retail-media-advertising.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Albertsons Retail Media Advertising\n  description: Unified retail media advertising workflow combining campaign management, audience targeting, performance analytics,\n    and custom reporting for advertisers on the Albertsons Media Collective platform. Designed for brand managers and media\n    planners managing grocery retail advertising campaigns.\n  tags:\n  - Albertsons\n  - Retail Media\n  - Advertising\n  - Campaigns\n  - Performance Analytics\n  - Audience Targeting\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALBERTSONS_API_TOKEN: ALBERTSONS_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: retail-media-api\n    baseUri: https://api.albertsons.com\n    description: Albertsons Media Collective API for retail media campaign management and performance analytics.\n    authentication:\n      type: bearer\n      token: '{{ALBERTSONS_API_TOKEN}}'\n    resources:\n    -\
  \ name: campaigns\n      path: /campaigns\n      description: Manage advertising campaigns on the Albertsons Media Collective.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: Retrieve a list of advertising campaigns with status and budget details.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter campaigns by status (active, paused, completed, draft).\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of campaigns to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of campaigns to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method:\
  \ POST\n        description: Create a new advertising campaign with budget and targeting parameters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            budget: '{{tools.budget}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n            targetAudienceIds: '{{tools.targetAudienceIds}}'\n    - name: campaign-by-id\n      path: /campaigns/{campaignId}\n      description: Retrieve details for a specific advertising campaign.\n      operations:\n      - name: get-campaign\n        method: GET\n        description: Retrieve details for a specific campaign by ID.\n        inputParameters:\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the campaign.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performance\n      path: /performance\n      description: Access near-real-time campaign performance metrics.\n      operations:\n      - name: list-performance-metrics\n        method: GET\n        description: Retrieve near-real-time performance metrics including impressions, clicks, conversions, and ROAS.\n        inputParameters:\n        - name: campaignId\n          in: query\n          type: string\n          required: false\n          description: Filter metrics by campaign identifier.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for metrics window (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for metrics window (ISO 8601).\n        - name: granularity\n          in: query\n          type:\
  \ string\n          required: false\n          description: Time granularity for metrics aggregation (daily, weekly, monthly).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audiences\n      path: /audiences\n      description: Manage audience targeting segments for campaigns.\n      operations:\n      - name: list-audiences\n        method: GET\n        description: Retrieve audience segments available for campaign targeting based on shopper behavior.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter audiences by product category.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of audience segments to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Generate custom performance reports for advertising campaigns.\n      operations:\n      - name: generate-report\n        method: POST\n        description: Generate a custom performance report with specified dimensions and metrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            campaignIds: '{{tools.campaignIds}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n            dimensions: '{{tools.dimensions}}'\n            metrics: '{{tools.metrics}}'\n            format: '{{tools.format}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: albertsons-advertising-api\n    description: Unified REST API for retail media advertising on the Albertsons Media Collective.\n    resources:\n    - path: /v1/campaigns\n\
  \      name: campaigns\n      description: Advertising campaign management.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List all advertising campaigns with status and budget details.\n        call: retail-media-api.list-campaigns\n        with:\n          status: rest.status\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a new advertising campaign.\n        call: retail-media-api.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{campaignId}\n      name: campaign-detail\n      description: Campaign detail retrieval.\n      operations:\n      - method: GET\n        name: get-campaign\n        description: Get campaign details by identifier.\n        call: retail-media-api.get-campaign\n        with:\n      \
  \    campaignId: rest.campaignId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/performance\n      name: performance\n      description: Campaign performance metrics.\n      operations:\n      - method: GET\n        name: list-performance-metrics\n        description: Retrieve near-real-time performance metrics.\n        call: retail-media-api.list-performance-metrics\n        with:\n          campaignId: rest.campaignId\n          startDate: rest.startDate\n          endDate: rest.endDate\n          granularity: rest.granularity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n      name: audiences\n      description: Audience targeting segments.\n      operations:\n      - method: GET\n        name: list-audiences\n        description: List audience segments for campaign targeting.\n        call: retail-media-api.list-audiences\n        with:\n          category: rest.category\n         \
  \ limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Custom performance report generation.\n      operations:\n      - method: POST\n        name: generate-report\n        description: Generate a custom performance report.\n        call: retail-media-api.generate-report\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: albertsons-advertising-mcp\n    transport: http\n    description: MCP server for AI-assisted retail media advertising management on the Albertsons Media Collective.\n    tools:\n    - name: list-campaigns\n      description: List all advertising campaigns on the Albertsons Media Collective with status, budget, and targeting details.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: retail-media-api.list-campaigns\n      with:\n        status: tools.status\n        limit:\
  \ tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new advertising campaign with budget, audience targeting, and scheduling on Albertsons Media Collective.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retail-media-api.create-campaign\n      with:\n        name: tools.name\n        budget: tools.budget\n        startDate: tools.startDate\n        endDate: tools.endDate\n        targetAudienceIds: tools.targetAudienceIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign\n      description: Get detailed information about a specific advertising campaign by its identifier.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: retail-media-api.get-campaign\n      with:\n        campaignId: tools.campaignId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-performance-metrics\n      description: Retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and\n        return on ad spend.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: retail-media-api.list-performance-metrics\n      with:\n        campaignId: tools.campaignId\n        startDate: tools.startDate\n        endDate: tools.endDate\n        granularity: tools.granularity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audiences\n      description: List audience targeting segments available on Albertsons Media Collective based on shopper purchase behavior.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: retail-media-api.list-audiences\n      with:\n        category: tools.category\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-report\n   \
  \   description: Generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and\n        date ranges.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retail-media-api.generate-report\n      with:\n        campaignIds: tools.campaignIds\n        startDate: tools.startDate\n        endDate: tools.endDate\n        dimensions: tools.dimensions\n        metrics: tools.metrics\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
