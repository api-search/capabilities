---
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
- campaign creation, management, and performance optimization for brands.
- audience targeting segments.
- performance analytics
- campaign detail retrieval.
- audience targeting
- digital advertising within retail environments, leveraging shopper purchase data for targeting.
- create a new advertising campaign.
- list audiences
- Brand Manager
- grocery
- list all advertising campaigns on the albertsons media collective with status, budget, and targeting details.
- get campaign details by identifier.
- list audience segments for campaign targeting.
- advertising
- create a new advertising campaign with budget, audience targeting, and scheduling on albertsons media collective.
- list audience targeting segments available on albertsons media collective based on shopper purchase behavior.
- campaign performance metrics.
- retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
- Media Planner
- advertising campaign management.
- custom performance report generation.
- retrieve near-real-time performance metrics.
- retail media
- manages advertising campaigns and budgets on behalf of consumer brands advertising in the albertsons network.
- unified retail media advertising workflow for campaign management, audience targeting, performance analytics, and reporting.
- albertsons
- list campaigns
- list performance metrics
- retail
- generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
- consumer goods
- analytics
- pharmacy
- create campaign
- campaigns
- generate a custom performance report.
- get campaign
- list all advertising campaigns with status and budget details.
- food
- plans and optimizes retail media campaigns, analyzes performance metrics, and generates reports for advertising clients.
- get detailed information about a specific advertising campaign by its identifier.
- generate report
slug: retail-media-advertising
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
