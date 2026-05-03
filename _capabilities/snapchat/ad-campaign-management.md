---
categories: []
consumed_apis:
- snapchat-ads
- snapchat-capi
description: 'Unified workflow capability for programmatic management of Snapchat advertising campaigns. Combines the Ads API and Conversions API to support the full ad lifecycle: creating and managing organizations, ad accounts, campaigns, ad squads, ads, creatives, audience segments, and measuring campaign performance with server-side conversion tracking. Used by performance marketers, growth engineers, and ad operations teams.'
layout: capability
name: Snapchat Ad Campaign Management
operations:
- description: List All Organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List All Ad Accounts for an Organization
  method: GET
  name: list-ad-accounts
  path: /v1/ad-accounts
- description: List All Campaigns for an Ad Account
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a Campaign
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: List All Ads for an Ad Account
  method: GET
  name: list-ads
  path: /v1/ads
- description: List All Audience Segments
  method: GET
  name: list-audience-segments
  path: /v1/audience-segments
- description: Send Web Conversion Events
  method: POST
  name: send-web-conversions
  path: /v1/conversions/web
- description: Send App Conversion Events
  method: POST
  name: send-app-conversions
  path: /v1/conversions/app
- description: Get Campaign Statistics
  method: GET
  name: get-campaign-stats
  path: /v1/stats/campaigns/{campaign_id}
personas: []
provider_name: Snapchat
provider_slug: snapchat
search_terms:
- get performance statistics for a snapchat campaign
- marketing
- manage custom audience segments
- send web conversion events to snapchat for campaign measurement via server-side capi
- send web conversion events
- send app conversion events to snapchat for campaign measurement via server-side capi
- conversions
- manage individual ad units
- send app conversions
- list all snapchat organizations accessible to the authenticated user
- advertising
- list all accessible snapchat organizations
- campaigns
- list audience segments
- get campaign stats
- list all audience segments
- list all organizations
- messaging
- list all ads for a snapchat ad account
- list all custom audience segments for targeting in a snapchat ad account
- snapchat
- list all ad accounts for an organization
- create a new snapchat advertising campaign
- campaign performance statistics
- list all advertising campaigns for a snapchat ad account
- manage ad accounts
- list organizations
- list ad accounts
- get campaign statistics
- send app conversion events
- social media
- list all ad accounts for a given snapchat organization
- create campaign
- send web conversions
- augmented reality
- list all campaigns for an ad account
- manage advertising campaigns
- list ads
- list all ads for an ad account
- ar
- list campaigns
- create a campaign
slug: ad-campaign-management
source_filename: ad-campaign-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snapchat Ad Campaign Management\"\n  description: >-\n    Unified workflow capability for programmatic management of Snapchat\n    advertising campaigns. Combines the Ads API and Conversions API to\n    support the full ad lifecycle: creating and managing organizations,\n    ad accounts, campaigns, ad squads, ads, creatives, audience segments,\n    and measuring campaign performance with server-side conversion tracking.\n    Used by performance marketers, growth engineers, and ad operations teams.\n  tags:\n    - Advertising\n    - Campaigns\n    - Conversions\n    - Marketing\n    - Snapchat\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNAPCHAT_ACCESS_TOKEN: SNAPCHAT_ACCESS_TOKEN\n      SNAPCHAT_CAPI_ACCESS_TOKEN: SNAPCHAT_CAPI_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: snapchat-ads\n      location: ./shared/ads-api.yaml\n    - import: snapchat-capi\n     \
  \ location: ./shared/conversions-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: snapchat-campaign-api\n      description: \"Unified REST API for Snapchat ad campaign management and conversion tracking.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"List all accessible Snapchat organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List All Organizations\"\n              call: \"snapchat-ads.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ad-accounts\n          name: ad-accounts\n          description: \"Manage ad accounts\"\n          operations:\n            - method: GET\n              name: list-ad-accounts\n              description: \"List All Ad Accounts for an Organization\"\n              call: \"snapchat-ads.list-ad-accounts\"\
  \n              with:\n                organization_id: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Manage advertising campaigns\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List All Campaigns for an Ad Account\"\n              call: \"snapchat-ads.list-campaigns\"\n              with:\n                ad_account_id: \"rest.ad_account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create a Campaign\"\n              call: \"snapchat-ads.create-campaign\"\n              with:\n                ad_account_id: \"rest.ad_account_id\"\n              outputParameters:\n                - type: object\n      \
  \            mapping: \"$.\"\n\n        - path: /v1/ads\n          name: ads\n          description: \"Manage individual ad units\"\n          operations:\n            - method: GET\n              name: list-ads\n              description: \"List All Ads for an Ad Account\"\n              call: \"snapchat-ads.list-ads\"\n              with:\n                ad_account_id: \"rest.ad_account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audience-segments\n          name: audience-segments\n          description: \"Manage custom audience segments\"\n          operations:\n            - method: GET\n              name: list-audience-segments\n              description: \"List All Audience Segments\"\n              call: \"snapchat-ads.list-audience-segments\"\n              with:\n                ad_account_id: \"rest.ad_account_id\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n\n        - path: /v1/conversions/web\n          name: web-conversions\n          description: \"Send web conversion events\"\n          operations:\n            - method: POST\n              name: send-web-conversions\n              description: \"Send Web Conversion Events\"\n              call: \"snapchat-capi.send-web-conversion-events\"\n              with:\n                pixel_id: \"rest.pixel_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/conversions/app\n          name: app-conversions\n          description: \"Send app conversion events\"\n          operations:\n            - method: POST\n              name: send-app-conversions\n              description: \"Send App Conversion Events\"\n              call: \"snapchat-capi.send-app-conversion-events\"\n              with:\n                snap_app_id: \"rest.snap_app_id\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stats/campaigns/{campaign_id}\n          name: campaign-stats\n          description: \"Campaign performance statistics\"\n          operations:\n            - method: GET\n              name: get-campaign-stats\n              description: \"Get Campaign Statistics\"\n              call: \"snapchat-ads.get-campaign-stats\"\n              with:\n                ad_account_id: \"rest.ad_account_id\"\n                campaign_id: \"rest.campaign_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: snapchat-campaign-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snapchat ad campaign management and conversion optimization.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Snapchat organizations accessible to the authenticated user\"\n        \
  \  hints:\n            readOnly: true\n            openWorld: false\n          call: \"snapchat-ads.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ad-accounts\n          description: \"List all ad accounts for a given Snapchat organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snapchat-ads.list-ad-accounts\"\n          with:\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-campaigns\n          description: \"List all advertising campaigns for a Snapchat ad account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snapchat-ads.list-campaigns\"\n          with:\n            ad_account_id: \"tools.ad_account_id\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n\n        - name: create-campaign\n          description: \"Create a new Snapchat advertising campaign\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snapchat-ads.create-campaign\"\n          with:\n            ad_account_id: \"tools.ad_account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ads\n          description: \"List all ads for a Snapchat ad account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snapchat-ads.list-ads\"\n          with:\n            ad_account_id: \"tools.ad_account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-audience-segments\n          description: \"List all custom audience segments for targeting in a Snapchat ad account\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"snapchat-ads.list-audience-segments\"\n          with:\n            ad_account_id: \"tools.ad_account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-campaign-stats\n          description: \"Get performance statistics for a Snapchat campaign\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snapchat-ads.get-campaign-stats\"\n          with:\n            ad_account_id: \"tools.ad_account_id\"\n            campaign_id: \"tools.campaign_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-web-conversion-events\n          description: \"Send web conversion events to Snapchat for campaign measurement via server-side CAPI\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snapchat-capi.send-web-conversion-events\"\n          with:\n            pixel_id:\
  \ \"tools.pixel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-app-conversion-events\n          description: \"Send app conversion events to Snapchat for campaign measurement via server-side CAPI\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snapchat-capi.send-app-conversion-events\"\n          with:\n            snap_app_id: \"tools.snap_app_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snapchat/refs/heads/main/capabilities/ad-campaign-management.yaml
tags:
- Advertising
- Campaigns
- Conversions
- Marketing
- Snapchat
tools:
- description: List all Snapchat organizations accessible to the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: list-organizations
- description: List all ad accounts for a given Snapchat organization
  hints:
    openWorld: false
    readOnly: true
  name: list-ad-accounts
- description: List all advertising campaigns for a Snapchat ad account
  hints:
    openWorld: false
    readOnly: true
  name: list-campaigns
- description: Create a new Snapchat advertising campaign
  hints:
    destructive: false
    readOnly: false
  name: create-campaign
- description: List all ads for a Snapchat ad account
  hints:
    openWorld: false
    readOnly: true
  name: list-ads
- description: List all custom audience segments for targeting in a Snapchat ad account
  hints:
    openWorld: false
    readOnly: true
  name: list-audience-segments
- description: Get performance statistics for a Snapchat campaign
  hints:
    openWorld: false
    readOnly: true
  name: get-campaign-stats
- description: Send web conversion events to Snapchat for campaign measurement via server-side CAPI
  hints:
    destructive: false
    readOnly: false
  name: send-web-conversion-events
- description: Send app conversion events to Snapchat for campaign measurement via server-side CAPI
  hints:
    destructive: false
    readOnly: false
  name: send-app-conversion-events
---
