---
categories: []
consumed_apis: []
description: Unified media advertising capability for TEGNA, combining AudienceOne first-party digital targeting and Premion OTT/CTV streaming advertising. Enables advertisers, media buyers, and agency partners to plan, execute, and measure multi-screen campaigns across TEGNA's 64 local TV brands and Premion's premium streaming inventory in 51 U.S. markets.
layout: capability
name: TEGNA Media Advertising
operations:
- description: List available audience segments for campaign targeting.
  method: GET
  name: list-audiences
  path: /v1/audiences
- description: List digital advertising campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a digital advertising campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get digital campaign performance metrics.
  method: GET
  name: get-campaign-performance
  path: /v1/campaigns/{campaignId}/performance
- description: List OTT/CTV advertising campaigns.
  method: GET
  name: list-ott-campaigns
  path: /v1/ott-campaigns
- description: Create an OTT/CTV advertising campaign.
  method: POST
  name: create-ott-campaign
  path: /v1/ott-campaigns
- description: Get OTT/CTV campaign streaming performance.
  method: GET
  name: get-ott-campaign-performance
  path: /v1/ott-campaigns/{campaignId}/performance
- description: Browse available OTT inventory.
  method: GET
  name: list-ott-inventory
  path: /v1/inventory
- description: List TEGNA broadcast markets.
  method: GET
  name: list-markets
  path: /v1/markets
personas: []
provider_name: TEGNA
provider_slug: tegna
search_terms:
- get streaming video performance metrics (impressions, completion rate, cpcv) for a premion ott campaign.
- premion ott/ctv advertising campaigns.
- list tegna broadcast markets.
- get performance metrics for a tegna digital advertising campaign.
- tegna digital advertising campaigns.
- list ott/ctv advertising campaigns.
- tegna
- list available audience segments for campaign targeting.
- get digital campaign performance
- list audiences
- ott campaign streaming performance.
- tegna local broadcast markets.
- get ott/ctv campaign streaming performance.
- browse available ott/ctv ad inventory across roku, hulu, fire tv, and other streaming platforms.
- digital advertising
- list tegna audienceone first-party audience segments for campaign targeting.
- media advertising
- list campaigns
- create an ott/ctv advertising campaign.
- list premion ott/ctv streaming advertising campaigns.
- list ott inventory
- get campaign performance
- list markets
- browse available ott inventory.
- available ott/ctv advertising inventory.
- list ott campaigns
- ctv
- television
- list digital advertising campaigns.
- list tegna audienceone digital advertising campaigns.
- create ott campaign
- list digital campaigns
- list audience segments
- media
- campaign performance metrics.
- ott
- get ott campaign performance
- create campaign
- list broadcast markets
- list tegna local tv broadcast markets available for campaign targeting.
- create a new ott/ctv streaming video advertising campaign on premion.
- audience targeting
- broadcasting
- create a digital advertising campaign.
- fortune 500
- tegna first-party audience segments for targeting.
- get digital campaign performance metrics.
slug: media-advertising
source_filename: media-advertising.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TEGNA Media Advertising\n  description: Unified media advertising capability for TEGNA, combining AudienceOne first-party digital targeting and Premion\n    OTT/CTV streaming advertising. Enables advertisers, media buyers, and agency partners to plan, execute, and measure multi-screen\n    campaigns across TEGNA's 64 local TV brands and Premion's premium streaming inventory in 51 U.S. markets.\n  tags:\n  - TEGNA\n  - Media Advertising\n  - Digital Advertising\n  - OTT\n  - CTV\n  - Audience Targeting\n  - Broadcasting\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEGNA_API_TOKEN: TEGNA_API_TOKEN\n    PREMION_API_KEY: PREMION_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tegna-audience-one\n    baseUri: https://api.tegna.com/v1\n    description: TEGNA AudienceOne digital advertising API.\n    authentication:\n      type: bearer\n      token: '{{TEGNA_API_TOKEN}}'\n    resources:\n\
  \    - name: audiences\n      path: /audiences\n      description: TEGNA first-party audience segments.\n      operations:\n      - name: list-audiences\n        method: GET\n        description: List available audience segments for targeting.\n        inputParameters:\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: Filter by TEGNA market.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Audience type filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-audience\n        method: GET\n        description: Get details for a specific audience segment.\n        inputParameters:\n        - name: audienceId\n          in: path\n          type: string\n          required: true\n          description: Audience segment ID.\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /campaigns\n      description: TEGNA advertising campaigns.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List advertising campaigns.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by campaign status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new digital advertising campaign.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            startDate: '{{tools.startDate}}'\n            budget: '{{tools.budget}}'\n            targetAudiences: '{{tools.targetAudiences}}'\n            targetMarkets: '{{tools.targetMarkets}}'\n\
  \            adFormats: '{{tools.adFormats}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-campaign\n        method: GET\n        description: Get details for a specific campaign.\n        inputParameters:\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-campaign-performance\n        method: GET\n        description: Get performance metrics for a campaign.\n        inputParameters:\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for performance\
  \ data.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for performance data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /markets\n      description: TEGNA broadcast markets.\n      operations:\n      - name: list-markets\n        method: GET\n        description: List available TEGNA broadcast markets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: tegna-premion\n    baseUri: https://api.premion.com/v1\n    description: Premion OTT/CTV advertising platform API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{PREMION_API_KEY}}'\n      placement: header\n    resources:\n    - name: ott-campaigns\n      path: /campaigns\n      description: OTT/CTV advertising\
  \ campaigns.\n      operations:\n      - name: list-ott-campaigns\n        method: GET\n        description: List OTT/CTV campaigns.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-ott-campaign\n        method: POST\n        description: Create a new OTT/CTV campaign.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            startDate: '{{tools.startDate}}'\n            budget: '{{tools.budget}}'\n            targetPlatforms: '{{tools.targetPlatforms}}'\n            impressionGoal: '{{tools.impressionGoal}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ott-campaign\n        method: GET\n\
  \        description: Get OTT campaign details.\n        inputParameters:\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ott-campaign-performance\n        method: GET\n        description: Get OTT campaign streaming performance.\n        inputParameters:\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for performance data.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for performance data.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      description: Available OTT/CTV advertising inventory.\n      operations:\n      - name: list-ott-inventory\n        method: GET\n        description: List available OTT inventory across streaming platforms.\n        inputParameters:\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: Filter by streaming platform.\n        - name: genre\n          in: query\n          type: string\n          required: false\n          description: Filter by content genre.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: creatives\n      path: /creatives\n      description: Video creative assets for OTT advertising.\n      operations:\n      - name: list-creatives\n        method: GET\n        description: List video creative assets.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tegna-media-api\n    description: Unified REST API for TEGNA multi-screen media advertising.\n    resources:\n    - path: /v1/audiences\n      name: audiences\n      description: TEGNA first-party audience segments for targeting.\n      operations:\n      - method: GET\n        name: list-audiences\n        description: List available audience segments for campaign targeting.\n        call: tegna-audience-one.list-audiences\n        with:\n          market: rest.market\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name: campaigns\n      description: TEGNA digital advertising campaigns.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List digital advertising campaigns.\n  \
  \      call: tegna-audience-one.list-campaigns\n        with:\n          status: rest.status\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a digital advertising campaign.\n        call: tegna-audience-one.create-campaign\n        with:\n          name: rest.name\n          startDate: rest.startDate\n          budget: rest.budget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{campaignId}/performance\n      name: campaign-performance\n      description: Campaign performance metrics.\n      operations:\n      - method: GET\n        name: get-campaign-performance\n        description: Get digital campaign performance metrics.\n        call: tegna-audience-one.get-campaign-performance\n        with:\n          campaignId: rest.campaignId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/ott-campaigns\n      name: ott-campaigns\n      description: Premion OTT/CTV advertising campaigns.\n      operations:\n      - method: GET\n        name: list-ott-campaigns\n        description: List OTT/CTV advertising campaigns.\n        call: tegna-premion.list-ott-campaigns\n        with:\n          status: rest.status\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-ott-campaign\n        description: Create an OTT/CTV advertising campaign.\n        call: tegna-premion.create-ott-campaign\n        with:\n          name: rest.name\n          startDate: rest.startDate\n          budget: rest.budget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ott-campaigns/{campaignId}/performance\n      name: ott-performance\n      description: OTT campaign streaming performance.\n      operations:\n      - method: GET\n  \
  \      name: get-ott-campaign-performance\n        description: Get OTT/CTV campaign streaming performance.\n        call: tegna-premion.get-ott-campaign-performance\n        with:\n          campaignId: rest.campaignId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Available OTT/CTV advertising inventory.\n      operations:\n      - method: GET\n        name: list-ott-inventory\n        description: Browse available OTT inventory.\n        call: tegna-premion.list-ott-inventory\n        with:\n          platform: rest.platform\n          genre: rest.genre\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/markets\n      name: markets\n      description: TEGNA local broadcast markets.\n      operations:\n      - method: GET\n        name: list-markets\n        description: List TEGNA\
  \ broadcast markets.\n        call: tegna-audience-one.list-markets\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tegna-media-mcp\n    transport: http\n    description: MCP server for AI-assisted TEGNA multi-screen media advertising.\n    tools:\n    - name: list-audience-segments\n      description: List TEGNA AudienceOne first-party audience segments for campaign targeting.\n      hints:\n        readOnly: true\n      call: tegna-audience-one.list-audiences\n      with:\n        market: tools.market\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-digital-campaigns\n      description: List TEGNA AudienceOne digital advertising campaigns.\n      hints:\n        readOnly: true\n      call: tegna-audience-one.list-campaigns\n      with:\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-digital-campaign-performance\n\
  \      description: Get performance metrics for a TEGNA digital advertising campaign.\n      hints:\n        readOnly: true\n      call: tegna-audience-one.get-campaign-performance\n      with:\n        campaignId: tools.campaignId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-broadcast-markets\n      description: List TEGNA local TV broadcast markets available for campaign targeting.\n      hints:\n        readOnly: true\n      call: tegna-audience-one.list-markets\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-ott-campaigns\n      description: List Premion OTT/CTV streaming advertising campaigns.\n      hints:\n        readOnly: true\n      call: tegna-premion.list-ott-campaigns\n      with:\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-ott-campaign-performance\n      description:\
  \ Get streaming video performance metrics (impressions, completion rate, CPCV) for a Premion OTT campaign.\n      hints:\n        readOnly: true\n      call: tegna-premion.get-ott-campaign-performance\n      with:\n        campaignId: tools.campaignId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ott-inventory\n      description: Browse available OTT/CTV ad inventory across Roku, Hulu, Fire TV, and other streaming platforms.\n      hints:\n        readOnly: true\n      call: tegna-premion.list-ott-inventory\n      with:\n        platform: tools.platform\n        genre: tools.genre\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-ott-campaign\n      description: Create a new OTT/CTV streaming video advertising campaign on Premion.\n      hints:\n        readOnly: false\n        destructive: false\n      call: tegna-premion.create-ott-campaign\n\
  \      with:\n        name: tools.name\n        startDate: tools.startDate\n        budget: tools.budget\n        targetPlatforms: tools.targetPlatforms\n        impressionGoal: tools.impressionGoal\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tegna/refs/heads/main/capabilities/media-advertising.yaml
tags:
- TEGNA
- Media Advertising
- Digital Advertising
- OTT
- CTV
- Audience Targeting
- Broadcasting
tools:
- description: List TEGNA AudienceOne first-party audience segments for campaign targeting.
  hints:
    readOnly: true
  name: list-audience-segments
- description: List TEGNA AudienceOne digital advertising campaigns.
  hints:
    readOnly: true
  name: list-digital-campaigns
- description: Get performance metrics for a TEGNA digital advertising campaign.
  hints:
    readOnly: true
  name: get-digital-campaign-performance
- description: List TEGNA local TV broadcast markets available for campaign targeting.
  hints:
    readOnly: true
  name: list-broadcast-markets
- description: List Premion OTT/CTV streaming advertising campaigns.
  hints:
    readOnly: true
  name: list-ott-campaigns
- description: Get streaming video performance metrics (impressions, completion rate, CPCV) for a Premion OTT campaign.
  hints:
    readOnly: true
  name: get-ott-campaign-performance
- description: Browse available OTT/CTV ad inventory across Roku, Hulu, Fire TV, and other streaming platforms.
  hints:
    readOnly: true
  name: list-ott-inventory
- description: Create a new OTT/CTV streaming video advertising campaign on Premion.
  hints:
    destructive: false
    readOnly: false
  name: create-ott-campaign
---
