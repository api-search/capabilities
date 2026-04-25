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
- audience targeting segments.
- create a new advertising campaign.
- retail media
- consumer goods
- audience targeting
- generate a custom performance report.
- campaigns
- get campaign
- get detailed information about a specific advertising campaign by its identifier.
- albertsons
- unified retail media advertising workflow for campaign management, audience targeting, performance analytics, and reporting.
- get campaign details by identifier.
- Brand Manager
- campaign creation, management, and performance optimization for brands.
- performance analytics
- list performance metrics
- list audiences
- list all advertising campaigns on the albertsons media collective with status, budget, and targeting details.
- retail
- generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
- list all advertising campaigns with status and budget details.
- plans and optimizes retail media campaigns, analyzes performance metrics, and generates reports for advertising clients.
- campaign detail retrieval.
- generate report
- Media Planner
- campaign performance metrics.
- create a new advertising campaign with budget, audience targeting, and scheduling on albertsons media collective.
- advertising
- food
- custom performance report generation.
- advertising campaign management.
- pharmacy
- analytics
- digital advertising within retail environments, leveraging shopper purchase data for targeting.
- retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
- grocery
- list audience targeting segments available on albertsons media collective based on shopper purchase behavior.
- list campaigns
- create campaign
- retrieve near-real-time performance metrics.
- list audience segments for campaign targeting.
- manages advertising campaigns and budgets on behalf of consumer brands advertising in the albertsons network.
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
