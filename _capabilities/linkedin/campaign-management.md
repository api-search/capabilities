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
- creative management.
- search for campaigns.
- stream company data to a dmp segment.
- forecast reach and impressions.
- marketing
- sales intelligence, lead management, and crm integration.
- uses sales navigator for lead generation and crm sync.
- audience insights.
- stream companies
- integrates linkedin authentication and sharing into applications.
- forecast impressions
- fetch audience insights by targeting criteria.
- get campaign by id
- advertising
- archive a campaign.
- get audience insights
- search ad targeting entities
- create a new ad creative.
- employee development tracking and content access.
- data portability and advertiser transparency for dma.
- audience count estimation.
- manages b2b ad campaigns and audience targeting on linkedin.
- business
- create dmp segment
- tracks employee learning activity and completions.
- message archiving and regulatory communications governance.
- search for campaign groups.
- stream user data to a dmp segment.
- forecast reach and impressions for media planning.
- campaign group management.
- professional networking
- search campaigns
- posts jobs and manages candidates through ats integrations.
- individual ad account operations.
- update ad account
- search ad accounts
- retrieve available ad targeting facets.
- b2b advertising, audience targeting, and campaign analytics.
- create a new ad account.
- recruiting
- delete a campaign group.
- archives communications for regulatory compliance.
- create creative
- get ad account by id
- linkedin
- media planning
- campaign management.
- create a new dmp segment.
- campaign management
- delete campaign group
- dmp segment management.
- retrieve dmp segments.
- stream users
- search for ad targeting entities.
- authentication, sharing, and verification for consumer apps.
- social media
- get audience count
- get ad targeting facets
- careers
- update an ad account.
- search for ad accounts.
- media plan forecasting.
- retrieve an ad account by id.
- archive campaign
- ad account management.
- search campaign groups
- create ad account
- retrieve a campaign by id.
- job posting, recruiting, and applicant tracking.
- get dmp segments
- ad targeting facets.
- get audience count by targeting criteria.
slug: campaign-management
source_filename: campaign-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Campaign Management\"\n  description: \"Unified workflow for marketing managers to plan, build, and manage LinkedIn ad campaigns -- combining campaign management, audience targeting, audience insights, and media planning APIs.\"\n  tags:\n    - LinkedIn\n    - Campaign Management\n    - Advertising\n    - Media Planning\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-campaigns\n      location: ./shared/marketing-campaigns.yaml\n    - import: marketing-audience\n      location: ./shared/marketing-audience.yaml\n    - import: marketing-audience-insights\n      location: ./shared/marketing-audience-insights.yaml\n    - import: marketing-media-planning\n      location: ./shared/marketing-media-planning.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ campaign-management-api\n      description: \"Unified REST API for LinkedIn campaign management workflows.\"\n      resources:\n        - path: /v1/ad-accounts\n          name: ad-accounts\n          description: \"Ad account management.\"\n          operations:\n            - method: GET\n              name: search-ad-accounts\n              description: \"Search for ad accounts.\"\n              call: \"marketing-campaigns.search-ad-accounts\"\n            - method: POST\n              name: create-ad-account\n              description: \"Create a new ad account.\"\n              call: \"marketing-campaigns.create-ad-account\"\n        - path: /v1/ad-accounts/{SponsoredAccountId}\n          name: ad-account-by-id\n          description: \"Individual ad account operations.\"\n          operations:\n            - method: GET\n              name: get-ad-account-by-id\n              description: \"Retrieve an ad account by ID.\"\n              call: \"marketing-campaigns.get-ad-account-by-id\"\
  \n            - method: POST\n              name: update-ad-account\n              description: \"Update an ad account.\"\n              call: \"marketing-campaigns.update-ad-account\"\n        - path: /v1/campaign-groups\n          name: campaign-groups\n          description: \"Campaign group management.\"\n          operations:\n            - method: GET\n              name: search-campaign-groups\n              description: \"Search for campaign groups.\"\n              call: \"marketing-campaigns.search-campaign-groups\"\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Campaign management.\"\n          operations:\n            - method: GET\n              name: search-campaigns\n              description: \"Search for campaigns.\"\n              call: \"marketing-campaigns.search-campaigns\"\n        - path: /v1/creatives\n          name: creatives\n          description: \"Creative management.\"\n          operations:\n            - method: POST\n\
  \              name: create-creative\n              description: \"Create a new ad creative.\"\n              call: \"marketing-campaigns.create-creative\"\n        - path: /v1/audience-counts\n          name: audience-counts\n          description: \"Audience count estimation.\"\n          operations:\n            - method: GET\n              name: get-audience-count\n              description: \"Get audience count by targeting criteria.\"\n              call: \"marketing-campaigns.get-audience-count\"\n        - path: /v1/dmp-segments\n          name: dmp-segments\n          description: \"DMP segment management.\"\n          operations:\n            - method: GET\n              name: get-dmp-segments\n              description: \"Retrieve DMP segments.\"\n              call: \"marketing-audience.get-dmp-segments\"\n            - method: POST\n              name: create-dmp-segment\n              description: \"Create a new DMP segment.\"\n              call: \"marketing-audience.create-dmp-segment\"\
  \n        - path: /v1/ad-targeting-facets\n          name: ad-targeting-facets\n          description: \"Ad targeting facets.\"\n          operations:\n            - method: GET\n              name: get-ad-targeting-facets\n              description: \"Retrieve available ad targeting facets.\"\n              call: \"marketing-audience-insights.get-ad-targeting-facets\"\n        - path: /v1/audience-insights\n          name: audience-insights\n          description: \"Audience insights.\"\n          operations:\n            - method: POST\n              name: get-audience-insights\n              description: \"Fetch audience insights by targeting criteria.\"\n              call: \"marketing-audience-insights.get-audience-insights\"\n        - path: /v1/media-plans\n          name: media-plans\n          description: \"Media plan forecasting.\"\n          operations:\n            - method: POST\n              name: forecast-impressions\n              description: \"Forecast reach and impressions.\"\
  \n              call: \"marketing-media-planning.forecast-impressions\"\n\n    - type: mcp\n      port: 9090\n      namespace: campaign-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted LinkedIn campaign management.\"\n      tools:\n        - name: search-ad-accounts\n          description: \"Search for ad accounts.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.search-ad-accounts\"\n        - name: create-ad-account\n          description: \"Create a new ad account.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-campaigns.create-ad-account\"\n        - name: get-ad-account-by-id\n          description: \"Retrieve an ad account by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.get-ad-account-by-id\"\n        - name: search-campaign-groups\n         \
  \ description: \"Search for campaign groups.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.search-campaign-groups\"\n        - name: search-campaigns\n          description: \"Search for campaigns.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.search-campaigns\"\n        - name: get-campaign-by-id\n          description: \"Retrieve a campaign by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.get-campaign-by-id\"\n        - name: archive-campaign\n          description: \"Archive a campaign.\"\n          hints: { readOnly: false, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.archive-campaign\"\n        - name: delete-campaign-group\n          description: \"Delete a campaign group.\"\n          hints: { readOnly: false, destructive: true, idempotent:\
  \ true }\n          call: \"marketing-campaigns.delete-campaign-group\"\n        - name: create-creative\n          description: \"Create a new ad creative.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-campaigns.create-creative\"\n        - name: get-audience-count\n          description: \"Get audience count by targeting criteria.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-campaigns.get-audience-count\"\n        - name: get-dmp-segments\n          description: \"Retrieve DMP segments.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-audience.get-dmp-segments\"\n        - name: create-dmp-segment\n          description: \"Create a new DMP segment.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-audience.create-dmp-segment\"\n        - name: stream-companies\n\
  \          description: \"Stream company data to a DMP segment.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-audience.stream-companies\"\n        - name: stream-users\n          description: \"Stream user data to a DMP segment.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-audience.stream-users\"\n        - name: get-ad-targeting-facets\n          description: \"Retrieve available ad targeting facets.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-audience-insights.get-ad-targeting-facets\"\n        - name: search-ad-targeting-entities\n          description: \"Search for ad targeting entities.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-audience-insights.search-ad-targeting-entities\"\n        - name: get-audience-insights\n          description:\
  \ \"Fetch audience insights by targeting criteria.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-audience-insights.get-audience-insights\"\n        - name: forecast-impressions\n          description: \"Forecast reach and impressions for media planning.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-media-planning.forecast-impressions\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/campaign-management.yaml
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
