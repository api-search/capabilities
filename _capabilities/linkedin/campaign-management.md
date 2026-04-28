---
categories: []
consumed_apis:
- marketing-campaigns
- marketing-audience
- marketing-audience-insights
- marketing-media-planning
description: Unified workflow for marketing managers to plan, build, and manage LinkedIn ad campaigns -- combining campaign management, audience targeting, audience insights, and media planning APIs.
layout: capability
name: LinkedIn Campaign Management
operations:
- description: Search for ad accounts.
  method: GET
  name: search-ad-accounts
  path: /v1/ad-accounts
- description: Create a new ad account.
  method: POST
  name: create-ad-account
  path: /v1/ad-accounts
- description: Retrieve an ad account by ID.
  method: GET
  name: get-ad-account-by-id
  path: /v1/ad-accounts/{SponsoredAccountId}
- description: Update an ad account.
  method: POST
  name: update-ad-account
  path: /v1/ad-accounts/{SponsoredAccountId}
- description: Search for campaign groups.
  method: GET
  name: search-campaign-groups
  path: /v1/campaign-groups
- description: Search for campaigns.
  method: GET
  name: search-campaigns
  path: /v1/campaigns
- description: Create a new ad creative.
  method: POST
  name: create-creative
  path: /v1/creatives
- description: Get audience count by targeting criteria.
  method: GET
  name: get-audience-count
  path: /v1/audience-counts
- description: Retrieve DMP segments.
  method: GET
  name: get-dmp-segments
  path: /v1/dmp-segments
- description: Create a new DMP segment.
  method: POST
  name: create-dmp-segment
  path: /v1/dmp-segments
- description: Retrieve available ad targeting facets.
  method: GET
  name: get-ad-targeting-facets
  path: /v1/ad-targeting-facets
- description: Fetch audience insights by targeting criteria.
  method: POST
  name: get-audience-insights
  path: /v1/audience-insights
- description: Forecast reach and impressions.
  method: POST
  name: forecast-impressions
  path: /v1/media-plans
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- archives communications for regulatory compliance.
- audience count estimation.
- forecast impressions
- media plan forecasting.
- delete a campaign group.
- forecast reach and impressions.
- retrieve an ad account by id.
- stream users
- ad targeting facets.
- search for campaigns.
- create creative
- careers
- create a new dmp segment.
- dmp segment management.
- campaign management.
- get audience insights
- uses sales navigator for lead generation and crm sync.
- stream user data to a dmp segment.
- individual ad account operations.
- creative management.
- tracks employee learning activity and completions.
- archive campaign
- professional networking
- message archiving and regulatory communications governance.
- social media
- search campaigns
- authentication, sharing, and verification for consumer apps.
- search ad accounts
- b2b advertising, audience targeting, and campaign analytics.
- linkedin
- create a new ad creative.
- search for ad accounts.
- audience insights.
- delete campaign group
- create ad account
- get audience count by targeting criteria.
- retrieve dmp segments.
- fetch audience insights by targeting criteria.
- search for ad targeting entities.
- employee development tracking and content access.
- search ad targeting entities
- advertising
- get dmp segments
- sales intelligence, lead management, and crm integration.
- marketing
- retrieve available ad targeting facets.
- recruiting
- update an ad account.
- campaign group management.
- business
- job posting, recruiting, and applicant tracking.
- stream company data to a dmp segment.
- campaign management
- ad account management.
- get audience count
- integrates linkedin authentication and sharing into applications.
- update ad account
- posts jobs and manages candidates through ats integrations.
- get ad account by id
- search for campaign groups.
- manages b2b ad campaigns and audience targeting on linkedin.
- data portability and advertiser transparency for dma.
- retrieve a campaign by id.
- get ad targeting facets
- create a new ad account.
- forecast reach and impressions for media planning.
- media planning
- stream companies
- search campaign groups
- get campaign by id
- archive a campaign.
- create dmp segment
slug: campaign-management
tags:
- LinkedIn
- Campaign Management
- Advertising
- Media Planning
tools:
- description: Search for ad accounts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-ad-accounts
- description: Create a new ad account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ad-account
- description: Retrieve an ad account by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ad-account-by-id
- description: Search for campaign groups.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-campaign-groups
- description: Search for campaigns.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-campaigns
- description: Retrieve a campaign by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-campaign-by-id
- description: Archive a campaign.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: archive-campaign
- description: Delete a campaign group.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-campaign-group
- description: Create a new ad creative.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-creative
- description: Get audience count by targeting criteria.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-audience-count
- description: Retrieve DMP segments.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dmp-segments
- description: Create a new DMP segment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dmp-segment
- description: Stream company data to a DMP segment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stream-companies
- description: Stream user data to a DMP segment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stream-users
- description: Retrieve available ad targeting facets.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ad-targeting-facets
- description: Search for ad targeting entities.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-ad-targeting-entities
- description: Fetch audience insights by targeting criteria.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-audience-insights
- description: Forecast reach and impressions for media planning.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: forecast-impressions
---
