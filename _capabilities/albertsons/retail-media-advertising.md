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
- campaign detail retrieval.
- retail
- list performance metrics
- custom performance report generation.
- generate a custom performance report.
- create a new advertising campaign with budget, audience targeting, and scheduling on albertsons media collective.
- list audience targeting segments available on albertsons media collective based on shopper purchase behavior.
- generate a custom performance report for advertising campaigns with configurable dimensions, metrics, and date ranges.
- food
- generate report
- create a new advertising campaign.
- campaign performance metrics.
- create campaign
- plans and optimizes retail media campaigns, analyzes performance metrics, and generates reports for advertising clients.
- pharmacy
- audience targeting segments.
- albertsons
- grocery
- list audiences
- get detailed information about a specific advertising campaign by its identifier.
- advertising
- get campaign details by identifier.
- list all advertising campaigns with status and budget details.
- get campaign
- list audience segments for campaign targeting.
- retrieve near-real-time advertising performance metrics including impressions, clicks, conversions, and return on ad spend.
- Media Planner
- campaign creation, management, and performance optimization for brands.
- analytics
- retail media
- advertising campaign management.
- unified retail media advertising workflow for campaign management, audience targeting, performance analytics, and reporting.
- consumer goods
- Brand Manager
- list all advertising campaigns on the albertsons media collective with status, budget, and targeting details.
- manages advertising campaigns and budgets on behalf of consumer brands advertising in the albertsons network.
- list campaigns
- retrieve near-real-time performance metrics.
- performance analytics
- campaigns
- digital advertising within retail environments, leveraging shopper purchase data for targeting.
- audience targeting
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
