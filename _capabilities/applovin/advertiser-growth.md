---
categories: []
consumed_apis: []
description: Workflow capability for mobile and web advertisers running AppDiscovery (Axon) campaigns. Combines campaign management, creative management, conversion-event ingestion (CAPI), and growth + asset reporting so a single user-acquisition role can launch, optimize, and measure performance.
layout: capability
name: AppLovin Advertiser Growth
operations:
- description: List campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a new campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Update an existing campaign.
  method: PUT
  name: update-campaign
  path: /v1/campaigns
- description: List creative sets.
  method: GET
  name: list-creative-sets
  path: /v1/creative-sets
- description: Create a creative set.
  method: POST
  name: create-creative-set
  path: /v1/creative-sets
- description: Clone an existing creative set.
  method: POST
  name: clone-creative-set
  path: /v1/creative-sets
- description: List uploaded creative assets.
  method: GET
  name: list-assets
  path: /v1/assets
- description: Post a batch of conversion events to CAPI.
  method: POST
  name: post-conversion-events
  path: /v1/conversion-events
- description: Get Growth (advertiser or publisher) report rows.
  method: GET
  name: get-growth-report
  path: /v1/growth-report
- description: Get asset performance for a symbolic time range.
  method: GET
  name: get-asset-report
  path: /v1/asset-report
- description: Get asset performance for a custom date range.
  method: GET
  name: get-asset-analytics-report
  path: /v1/asset-report
personas: []
provider_name: AppLovin
provider_slug: applovin
search_terms:
- app monetization
- create creative set
- get asset performance for a symbolic time range.
- list creative sets.
- update an existing campaign.
- user acquisition
- conversion tracking
- marketing technology
- list creative assets.
- get growth (advertiser or publisher) report rows.
- mobile
- create a creative set.
- create a new appdiscovery campaign.
- appdiscovery / axon campaigns.
- applovin
- get appdiscovery growth report.
- axon
- get growth report
- adtech
- list campaigns
- list campaigns.
- post server-to-server conversion events to capi.
- appdiscovery creative sets.
- list uploaded creative assets.
- get creative-level asset report by custom date range.
- update campaign
- clone a creative set.
- appdiscovery
- clone creative set
- get asset report
- create a new campaign.
- clone an existing creative set.
- post a batch of conversion events to capi.
- create campaign
- get creative-level asset report by symbolic range.
- get asset analytics report
- list creative sets
- post conversion events
- server-to-server conversion events.
- get asset performance for a custom date range.
- advertising
- mediation
- list appdiscovery campaigns.
- update an appdiscovery campaign.
- list assets
- creative-level performance report.
- growth campaign report.
- creative assets.
slug: advertiser-growth
source_filename: advertiser-growth.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AppLovin Advertiser Growth\n  description: Workflow capability for mobile and web advertisers running AppDiscovery (Axon) campaigns. Combines campaign\n    management, creative management, conversion-event ingestion (CAPI), and growth + asset reporting so a single user-acquisition\n    role can launch, optimize, and measure performance.\n  tags:\n  - AppLovin\n  - Axon\n  - AppDiscovery\n  - User Acquisition\n  - Advertising\n  - Conversion Tracking\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPLOVIN_CAMPAIGN_MGMT_KEY: APPLOVIN_CAMPAIGN_MGMT_KEY\n    APPLOVIN_CAPI_KEY: APPLOVIN_CAPI_KEY\n    APPLOVIN_REPORT_KEY: APPLOVIN_REPORT_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: applovin-axon-campaign-management\n    baseUri: https://api.ads.axon.ai/manage/v1\n    description: Axon campaign management API.\n    authentication:\n      type: bearer\n      token: '{{APPLOVIN_CAMPAIGN_MGMT_KEY}}'\n\
  \    resources:\n    - name: campaigns\n      path: /campaign\n      description: Campaign endpoints.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List campaigns.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated campaign IDs.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description:\
  \ Create a new campaign.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.body}}'\n      - name: update-campaign\n        method: POST\n        description: Update an existing campaign.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.body}}'\n    - name: creative-sets\n      path: /creative_set\n      description: Creative set endpoints.\n      operations:\n      - name: list-creative-sets\n\
  \        method: GET\n        description: List creative sets.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-creative-set\n        method: POST\n        description: Create a creative set.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.body}}'\n      - name: clone-creative-set\n        method: POST\n        description: Clone a creative set.\n        inputParameters:\n        - name: account_id\n          in: query\n\
  \          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            campaign_id: '{{tools.campaign_id}}'\n            creative_set_id: '{{tools.creative_set_id}}'\n            status: '{{tools.status}}'\n    - name: assets\n      path: /asset\n      description: Creative asset endpoints.\n      operations:\n      - name: list-assets\n        method: GET\n        description: List uploaded assets.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        - name: resource_type\n          in: query\n          type: string\n          required: false\n          description: image, html, or video.\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: applovin-conversion-api-lead-gen\n    baseUri: https://b.applovin.com\n    description: AppLovin server-to-server conversion ingestion.\n    authentication:\n      type: bearer\n      token: '{{APPLOVIN_CAPI_KEY}}'\n    resources:\n    - name: events\n      path: /v1/event\n      description: Conversion event ingestion.\n      operations:\n      - name: post-conversion-events\n        method: POST\n        description: Post a batch of conversion events (up to 100).\n        inputParameters:\n        - name: pixel_id\n          in: query\n          type: string\n          required: true\n          description: Axon Event Key for the destination pixel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n  - type: http\n  \
  \  namespace: applovin-growth-reporting\n    baseUri: https://r.applovin.com\n    description: AppDiscovery / Axon reporting endpoint.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{APPLOVIN_REPORT_KEY}}'\n      placement: query\n    resources:\n    - name: report\n      path: /report\n      description: Aggregated campaign report rows.\n      operations:\n      - name: get-growth-report\n        method: GET\n        description: Get Growth (publisher or advertiser) report rows.\n        inputParameters:\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start date or epoch.\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End date, epoch, or 'now'.\n        - name: format\n          in: query\n          type: string\n          required: true\n          description: 'Response format: json or csv.'\n        - name: columns\n\
  \          in: query\n          type: string\n          required: true\n          description: Comma-separated list of columns.\n        - name: report_type\n          in: query\n          type: string\n          required: false\n          description: publisher or advertiser.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: applovin-growth-asset-reporting\n    baseUri: https://r.applovin.com\n    description: AppDiscovery / Axon creative-level reporting.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{APPLOVIN_REPORT_KEY}}'\n      placement: query\n    resources:\n    - name: asset-report\n      path: /assetReport\n      description: Creative report by symbolic time range.\n      operations:\n      - name: get-asset-report\n        method: GET\n        description: Get asset report for a symbolic range.\n        inputParameters:\n        - name: range\n\
  \          in: query\n          type: string\n          required: true\n          description: yesterday, last_7d, or last_month.\n        - name: columns\n          in: query\n          type: string\n          required: true\n          description: Comma-separated columns.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asset-analytics-report\n      path: /assetAnalyticsReport\n      description: Creative report by date range.\n      operations:\n      - name: get-asset-analytics-report\n        method: GET\n        description: Get asset report for a custom date range.\n        inputParameters:\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start date YYYY-MM-DD.\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End date YYYY-MM-DD.\n        - name: columns\n\
  \          in: query\n          type: string\n          required: true\n          description: Comma-separated columns.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: advertiser-growth-api\n    description: Unified REST API for AppLovin advertiser growth workflows.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description: AppDiscovery / Axon campaigns.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List campaigns.\n        call: applovin-axon-campaign-management.list-campaigns\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a new campaign.\n        call: applovin-axon-campaign-management.create-campaign\n        with:\n\
  \          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-campaign\n        description: Update an existing campaign.\n        call: applovin-axon-campaign-management.update-campaign\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/creative-sets\n      name: creative-sets\n      description: AppDiscovery creative sets.\n      operations:\n      - method: GET\n        name: list-creative-sets\n        description: List creative sets.\n        call: applovin-axon-campaign-management.list-creative-sets\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-creative-set\n        description: Create a creative set.\n        call: applovin-axon-campaign-management.create-creative-set\n\
  \        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: clone-creative-set\n        description: Clone an existing creative set.\n        call: applovin-axon-campaign-management.clone-creative-set\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Creative assets.\n      operations:\n      - method: GET\n        name: list-assets\n        description: List uploaded creative assets.\n        call: applovin-axon-campaign-management.list-assets\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversion-events\n      name: conversion-events\n      description: Server-to-server conversion events.\n      operations:\n      - method: POST\n        name:\
  \ post-conversion-events\n        description: Post a batch of conversion events to CAPI.\n        call: applovin-conversion-api-lead-gen.post-conversion-events\n        with:\n          pixel_id: rest.pixel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/growth-report\n      name: growth-report\n      description: Growth campaign report.\n      operations:\n      - method: GET\n        name: get-growth-report\n        description: Get Growth (advertiser or publisher) report rows.\n        call: applovin-growth-reporting.get-growth-report\n        with:\n          start: rest.start\n          end: rest.end\n          format: rest.format\n          columns: rest.columns\n          report_type: rest.report_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/asset-report\n      name: asset-report\n      description: Creative-level performance report.\n      operations:\n      - method: GET\n        name:\
  \ get-asset-report\n        description: Get asset performance for a symbolic time range.\n        call: applovin-growth-asset-reporting.get-asset-report\n        with:\n          range: rest.range\n          columns: rest.columns\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-asset-analytics-report\n        description: Get asset performance for a custom date range.\n        call: applovin-growth-asset-reporting.get-asset-analytics-report\n        with:\n          start: rest.start\n          end: rest.end\n          columns: rest.columns\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: advertiser-growth-mcp\n    transport: http\n    description: MCP server for AI-assisted AppDiscovery campaign management and analytics.\n    tools:\n    - name: list-campaigns\n      description: List AppDiscovery campaigns.\n      hints:\n        readOnly: true\n \
  \       openWorld: true\n      call: applovin-axon-campaign-management.list-campaigns\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new AppDiscovery campaign.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-axon-campaign-management.create-campaign\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-campaign\n      description: Update an AppDiscovery campaign.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: applovin-axon-campaign-management.update-campaign\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-creative-sets\n      description: List creative sets.\n   \
  \   hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-axon-campaign-management.list-creative-sets\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-creative-set\n      description: Create a creative set.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-axon-campaign-management.create-creative-set\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clone-creative-set\n      description: Clone a creative set.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-axon-campaign-management.clone-creative-set\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List\
  \ creative assets.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-axon-campaign-management.list-assets\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-conversion-events\n      description: Post server-to-server conversion events to CAPI.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-conversion-api-lead-gen.post-conversion-events\n      with:\n        pixel_id: tools.pixel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-growth-report\n      description: Get AppDiscovery growth report.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-growth-reporting.get-growth-report\n      with:\n        start: tools.start\n        end: tools.end\n        format: tools.format\n        columns: tools.columns\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-asset-report\n      description: Get creative-level asset report by symbolic range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-growth-asset-reporting.get-asset-report\n      with:\n        range: tools.range\n        columns: tools.columns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset-analytics-report\n      description: Get creative-level asset report by custom date range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-growth-asset-reporting.get-asset-analytics-report\n      with:\n        start: tools.start\n        end: tools.end\n        columns: tools.columns\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/applovin/refs/heads/main/capabilities/advertiser-growth.yaml
tags:
- AppLovin
- Axon
- AppDiscovery
- User Acquisition
- Advertising
- Conversion Tracking
tools:
- description: List AppDiscovery campaigns.
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Create a new AppDiscovery campaign.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-campaign
- description: Update an AppDiscovery campaign.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-campaign
- description: List creative sets.
  hints:
    openWorld: true
    readOnly: true
  name: list-creative-sets
- description: Create a creative set.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-creative-set
- description: Clone a creative set.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clone-creative-set
- description: List creative assets.
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: Post server-to-server conversion events to CAPI.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-conversion-events
- description: Get AppDiscovery growth report.
  hints:
    openWorld: true
    readOnly: true
  name: get-growth-report
- description: Get creative-level asset report by symbolic range.
  hints:
    openWorld: true
    readOnly: true
  name: get-asset-report
- description: Get creative-level asset report by custom date range.
  hints:
    openWorld: true
    readOnly: true
  name: get-asset-analytics-report
---
