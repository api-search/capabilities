---
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
- campaign management
- media plan forecasting.
- search ad accounts
- retrieve an ad account by id.
- campaign group management.
- message archiving and regulatory communications governance.
- get audience insights
- retrieve a campaign by id.
- dmp segment management.
- forecast reach and impressions.
- creative management.
- search campaigns
- b2b advertising, audience targeting, and campaign analytics.
- social media
- search for ad targeting entities.
- get ad targeting facets
- archive a campaign.
- retrieve available ad targeting facets.
- delete campaign group
- get dmp segments
- get ad account by id
- search campaign groups
- create a new ad creative.
- create dmp segment
- audience insights.
- get campaign by id
- forecast impressions
- search for campaigns.
- delete a campaign group.
- stream users
- manages b2b ad campaigns and audience targeting on linkedin.
- professional networking
- advertising
- create a new dmp segment.
- authentication, sharing, and verification for consumer apps.
- integrates linkedin authentication and sharing into applications.
- ad targeting facets.
- forecast reach and impressions for media planning.
- fetch audience insights by targeting criteria.
- update an ad account.
- create creative
- stream user data to a dmp segment.
- business
- get audience count by targeting criteria.
- careers
- create ad account
- search for campaign groups.
- stream companies
- job posting, recruiting, and applicant tracking.
- retrieve dmp segments.
- ad account management.
- posts jobs and manages candidates through ats integrations.
- uses sales navigator for lead generation and crm sync.
- data portability and advertiser transparency for dma.
- search for ad accounts.
- archive campaign
- update ad account
- audience count estimation.
- search ad targeting entities
- marketing
- archives communications for regulatory compliance.
- campaign management.
- tracks employee learning activity and completions.
- sales intelligence, lead management, and crm integration.
- linkedin
- get audience count
- media planning
- employee development tracking and content access.
- create a new ad account.
- recruiting
- stream company data to a dmp segment.
- individual ad account operations.
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
