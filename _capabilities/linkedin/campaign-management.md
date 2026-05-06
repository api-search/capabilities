---
categories: []
consumed_apis: []
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
- create a new ad creative.
- audience count estimation.
- delete a campaign group.
- search for campaign groups.
- stream company data to a dmp segment.
- search campaign groups
- create dmp segment
- creative management.
- stream users
- tracks employee learning activity and completions.
- recruiting
- stream user data to a dmp segment.
- get ad account by id
- search campaigns
- search ad accounts
- campaign group management.
- get audience count by targeting criteria.
- archive campaign
- forecast reach and impressions for media planning.
- authentication, sharing, and verification for consumer apps.
- careers
- linkedin
- get audience count
- stream companies
- marketing
- delete campaign group
- search for ad accounts.
- create a new ad account.
- media planning
- create ad account
- professional networking
- data portability and advertiser transparency for dma.
- forecast impressions
- campaign management.
- business
- fetch audience insights by targeting criteria.
- employee development tracking and content access.
- create creative
- get ad targeting facets
- search for ad targeting entities.
- update ad account
- audience insights.
- individual ad account operations.
- sales intelligence, lead management, and crm integration.
- message archiving and regulatory communications governance.
- get audience insights
- advertising
- update an ad account.
- archive a campaign.
- retrieve available ad targeting facets.
- b2b advertising, audience targeting, and campaign analytics.
- manages b2b ad campaigns and audience targeting on linkedin.
- ad targeting facets.
- posts jobs and manages candidates through ats integrations.
- search ad targeting entities
- retrieve an ad account by id.
- ad account management.
- forecast reach and impressions.
- get campaign by id
- media plan forecasting.
- job posting, recruiting, and applicant tracking.
- retrieve a campaign by id.
- social media
- search for campaigns.
- uses sales navigator for lead generation and crm sync.
- retrieve dmp segments.
- integrates linkedin authentication and sharing into applications.
- archives communications for regulatory compliance.
- campaign management
- create a new dmp segment.
- dmp segment management.
- get dmp segments
slug: campaign-management
source_filename: campaign-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Campaign Management\n  description: Unified workflow for marketing managers to plan, build, and manage LinkedIn ad campaigns -- combining campaign\n    management, audience targeting, audience insights, and media planning APIs.\n  tags:\n  - LinkedIn\n  - Campaign Management\n  - Advertising\n  - Media Planning\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-campaigns\n    baseUri: https://api.linkedin.com/rest\n    description: LinkedIn Marketing Campaign Management API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ad-account-users\n      path: /adAccountUsers\n      description: Ad account user access management.\n      operations:\n      - name: get-authenticated-user-ad-accounts\n        method: GET\n     \
  \   description: Retrieve all ad accounts the authenticated user has access to.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-acls\n      path: /organizationAcls\n      description: Organization access control lists.\n      operations:\n      - name: get-organization-acls\n        method: GET\n        description: Retrieve organization roles for the authenticated user.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-accounts\n      path: /adAccounts\n      description: Ad account management.\n\
  \      operations:\n      - name: create-ad-account\n        method: POST\n        description: Create a new ad account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-ad-accounts\n        method: GET\n        description: Search for ad accounts.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-account-by-id\n      path: /adAccounts/{SponsoredAccountId}\n      description: Individual ad account operations.\n      operations:\n      - name: get-ad-account-by-id\n        method: GET\n        description: Retrieve\
  \ an ad account by ID.\n        inputParameters:\n        - name: SponsoredAccountId\n          in: path\n          type: string\n          required: true\n          description: Sponsored account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ad-account\n        method: POST\n        description: Update an ad account.\n        inputParameters:\n        - name: SponsoredAccountId\n          in: path\n          type: string\n          required: true\n          description: Sponsored account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-groups\n      path: /adAccounts/{AdAccountsId}/adCampaignGroups\n      description: Campaign group management.\n      operations:\n      - name: search-campaign-groups\n        method: GET\n        description: Search for campaign groups.\n       \
  \ inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-campaign-groups\n        method: DELETE\n        description: Delete multiple campaign groups.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Campaign group IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-group-by-id\n      path: /adAccounts/{AdAccountsId}/adCampaignGroups/{CampaignGroupId}\n\
  \      description: Individual campaign group operations.\n      operations:\n      - name: get-campaign-group-by-id\n        method: GET\n        description: Retrieve a campaign group by ID.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: CampaignGroupId\n          in: path\n          type: string\n          required: true\n          description: Campaign group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-campaign-group\n        method: POST\n        description: Update a campaign group.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: CampaignGroupId\n          in: path\n          type: string\n          required: true\n\
  \          description: Campaign group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-campaign-group\n        method: DELETE\n        description: Delete a campaign group.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: CampaignGroupId\n          in: path\n          type: string\n          required: true\n          description: Campaign group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /adAccounts/{AdAccountsId}/adCampaigns\n      description: Campaign management.\n      operations:\n      - name: search-campaigns\n        method: GET\n        description: Search for campaigns.\n        inputParameters:\n        - name: AdAccountsId\n\
  \          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-by-id\n      path: /adAccounts/{AdAccountsId}/adCampaigns/{CampaignId}\n      description: Individual campaign operations.\n      operations:\n      - name: get-campaign-by-id\n        method: GET\n        description: Retrieve a campaign by ID.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: CampaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: archive-campaign\n        method: POST\n        description: Archive a campaign.\n        inputParameters:\n        - name: AdAccountsId\n          in: path\n          type: string\n          required: true\n          description: Ad account ID\n        - name: CampaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: creatives\n      path: /creatives\n      description: Creative management.\n      operations:\n      - name: create-creative\n        method: POST\n        description: Create a new ad creative.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audience-counts\n      path: /audienceCounts\n      description: Audience count\
  \ estimation.\n      operations:\n      - name: get-audience-count\n        method: GET\n        description: Get audience count by targeting criteria.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: targetingCriteria\n          in: query\n          type: string\n          required: true\n          description: URL-encoded targeting criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-audience\n    baseUri: https://api.linkedin.com/rest\n    description: LinkedIn Marketing Audiences API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ad-accounts\n      path: /adAccounts\n      description: Ad account management.\n      operations:\n      - name: get-ad-accounts\n        method: GET\n\
  \        description: Retrieve the authenticated user's ad accounts.\n        inputParameters:\n        - name: X-Restli-Protocol-Version\n          in: header\n          type: string\n          required: true\n          description: RestLi protocol version\n        - name: LinkedIn-Version\n          in: header\n          type: string\n          required: true\n          description: LinkedIn API version\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dmp-segments\n      path: /dmpSegments\n      description: DMP segment management.\n      operations:\n      - name: get-dmp-segments\n        method: GET\n        description: Retrieve DMP\
  \ segments for an ad account.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: account\n          in: query\n          type: string\n          required: true\n          description: Sponsored account URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dmp-segment\n        method: POST\n        description: Create a new DMP segment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-streaming\n      path: /dmpSegments/{CompanySegmentId}/companies\n      description: Stream company data to DMP segments.\n      operations:\n      - name: stream-companies\n        method: POST\n        description: Add or remove companies from a DMP segment.\n        inputParameters:\n        -\
  \ name: CompanySegmentId\n          in: path\n          type: string\n          required: true\n          description: ID of the company DMP segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-streaming\n      path: /dmpSegments/{UserSegmentId}/users\n      description: Stream user data to DMP segments.\n      operations:\n      - name: stream-users\n        method: POST\n        description: Add or remove users from a DMP segment.\n        inputParameters:\n        - name: UserSegmentId\n          in: path\n          type: string\n          required: true\n          description: ID of the user DMP segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-uploads\n      path: /dmpSegments/{ListUploadSegmentId}/listUploads\n      description: Attach uploaded lists to DMP segments.\n      operations:\n\
  \      - name: attach-list\n        method: POST\n        description: Attach an uploaded CSV list to a DMP segment.\n        inputParameters:\n        - name: ListUploadSegmentId\n          in: path\n          type: string\n          required: true\n          description: ID of the list upload DMP segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-audience-insights\n    baseUri: https://api.linkedin.com/rest\n    description: LinkedIn Marketing Audience Insights API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ad-targeting-facets\n      path: /adTargetingFacets\n      description: Ad targeting facets for audience segmentation.\n      operations:\n      - name: get-ad-targeting-facets\n        method: GET\n        description: Retrieve available ad targeting facets.\n        inputParameters:\n  \
  \      - name: LinkedIn-Version\n          in: header\n          type: string\n          required: true\n          description: LinkedIn API version\n        - name: X-Restli-Protocol-Version\n          in: header\n          type: string\n          required: true\n          description: RestLi protocol version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-targeting-entities\n      path: /adTargetingEntities\n      description: Ad targeting entities for specific facets.\n      operations:\n      - name: search-ad-targeting-entities\n        method: GET\n        description: Search for ad targeting entities using typeahead.\n        inputParameters:\n        - name: LinkedIn-Version\n          in: header\n          type: string\n          required: true\n          description: LinkedIn API version\n        - name: X-Restli-Protocol-Version\n          in: header\n          type: string\n     \
  \     required: true\n          description: RestLi protocol version\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query string\n        - name: facet\n          in: query\n          type: string\n          required: true\n          description: Facet URN to search within\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Starting index\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: targeting-audience-insights\n      path: /targetingAudienceInsights\n      description: Audience insights based\
  \ on targeting criteria.\n      operations:\n      - name: get-audience-insights\n        method: POST\n        description: Fetch audience insights by targeting criteria.\n        inputParameters:\n        - name: LinkedIn-Version\n          in: header\n          type: string\n          required: true\n          description: LinkedIn API version\n        - name: X-Restli-Protocol-Version\n          in: header\n          type: string\n          required: true\n          description: RestLi protocol version\n        - name: action\n          in: query\n          type: string\n          required: true\n          description: Action to perform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-media-planning\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Media Planning API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n\
  \    resources:\n    - name: ad-targeting-facets\n      path: /adTargetingFacets\n      description: Ad targeting facets for media planning.\n      operations:\n      - name: get-targeting-facets\n        method: GET\n        description: Get available ad targeting facets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-targeting-entities\n      path: /adTargetingEntities\n      description: Ad targeting entities for media planning.\n      operations:\n      - name: search-targeting-entities\n        method: GET\n        description: Search targeting entities using typeahead.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: facet\n          in:\
  \ query\n          type: string\n          required: false\n          description: Facet URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media-planning\n      path: /mediaPlanning\n      description: Media plan forecasting.\n      operations:\n      - name: forecast-impressions\n        method: POST\n        description: Forecast average lifetime frequency and impressions.\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: false\n          description: Action type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: campaign-management-api\n    description: Unified REST API for LinkedIn campaign management workflows.\n    resources:\n    - path: /v1/ad-accounts\n      name: ad-accounts\n      description:\
  \ Ad account management.\n      operations:\n      - method: GET\n        name: search-ad-accounts\n        description: Search for ad accounts.\n        call: marketing-campaigns.search-ad-accounts\n      - method: POST\n        name: create-ad-account\n        description: Create a new ad account.\n        call: marketing-campaigns.create-ad-account\n    - path: /v1/ad-accounts/{SponsoredAccountId}\n      name: ad-account-by-id\n      description: Individual ad account operations.\n      operations:\n      - method: GET\n        name: get-ad-account-by-id\n        description: Retrieve an ad account by ID.\n        call: marketing-campaigns.get-ad-account-by-id\n      - method: POST\n        name: update-ad-account\n        description: Update an ad account.\n        call: marketing-campaigns.update-ad-account\n    - path: /v1/campaign-groups\n      name: campaign-groups\n      description: Campaign group management.\n      operations:\n      - method: GET\n        name: search-campaign-groups\n\
  \        description: Search for campaign groups.\n        call: marketing-campaigns.search-campaign-groups\n    - path: /v1/campaigns\n      name: campaigns\n      description: Campaign management.\n      operations:\n      - method: GET\n        name: search-campaigns\n        description: Search for campaigns.\n        call: marketing-campaigns.search-campaigns\n    - path: /v1/creatives\n      name: creatives\n      description: Creative management.\n      operations:\n      - method: POST\n        name: create-creative\n        description: Create a new ad creative.\n        call: marketing-campaigns.create-creative\n    - path: /v1/audience-counts\n      name: audience-counts\n      description: Audience count estimation.\n      operations:\n      - method: GET\n        name: get-audience-count\n        description: Get audience count by targeting criteria.\n        call: marketing-campaigns.get-audience-count\n    - path: /v1/dmp-segments\n      name: dmp-segments\n      description:\
  \ DMP segment management.\n      operations:\n      - method: GET\n        name: get-dmp-segments\n        description: Retrieve DMP segments.\n        call: marketing-audience.get-dmp-segments\n      - method: POST\n        name: create-dmp-segment\n        description: Create a new DMP segment.\n        call: marketing-audience.create-dmp-segment\n    - path: /v1/ad-targeting-facets\n      name: ad-targeting-facets\n      description: Ad targeting facets.\n      operations:\n      - method: GET\n        name: get-ad-targeting-facets\n        description: Retrieve available ad targeting facets.\n        call: marketing-audience-insights.get-ad-targeting-facets\n    - path: /v1/audience-insights\n      name: audience-insights\n      description: Audience insights.\n      operations:\n      - method: POST\n        name: get-audience-insights\n        description: Fetch audience insights by targeting criteria.\n        call: marketing-audience-insights.get-audience-insights\n    - path:\
  \ /v1/media-plans\n      name: media-plans\n      description: Media plan forecasting.\n      operations:\n      - method: POST\n        name: forecast-impressions\n        description: Forecast reach and impressions.\n        call: marketing-media-planning.forecast-impressions\n  - type: mcp\n    port: 9090\n    namespace: campaign-management-mcp\n    transport: http\n    description: MCP server for AI-assisted LinkedIn campaign management.\n    tools:\n    - name: search-ad-accounts\n      description: Search for ad accounts.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.search-ad-accounts\n    - name: create-ad-account\n      description: Create a new ad account.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-campaigns.create-ad-account\n    - name: get-ad-account-by-id\n      description: Retrieve an ad account by ID.\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.get-ad-account-by-id\n    - name: search-campaign-groups\n      description: Search for campaign groups.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.search-campaign-groups\n    - name: search-campaigns\n      description: Search for campaigns.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.search-campaigns\n    - name: get-campaign-by-id\n      description: Retrieve a campaign by ID.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.get-campaign-by-id\n    - name: archive-campaign\n      description: Archive a campaign.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.archive-campaign\n\
  \    - name: delete-campaign-group\n      description: Delete a campaign group.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: marketing-campaigns.delete-campaign-group\n    - name: create-creative\n      description: Create a new ad creative.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-campaigns.create-creative\n    - name: get-audience-count\n      description: Get audience count by targeting criteria.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-campaigns.get-audience-count\n    - name: get-dmp-segments\n      description: Retrieve DMP segments.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-audience.get-dmp-segments\n    - name: create-dmp-segment\n      description: Create a new DMP segment.\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: marketing-audience.create-dmp-segment\n    - name: stream-companies\n      description: Stream company data to a DMP segment.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-audience.stream-companies\n    - name: stream-users\n      description: Stream user data to a DMP segment.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-audience.stream-users\n    - name: get-ad-targeting-facets\n      description: Retrieve available ad targeting facets.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-audience-insights.get-ad-targeting-facets\n    - name: search-ad-targeting-entities\n      description: Search for ad targeting entities.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: marketing-audience-insights.search-ad-targeting-entities\n    - name: get-audience-insights\n      description: Fetch audience insights by targeting criteria.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-audience-insights.get-audience-insights\n    - name: forecast-impressions\n      description: Forecast reach and impressions for media planning.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-media-planning.forecast-impressions\n"
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
