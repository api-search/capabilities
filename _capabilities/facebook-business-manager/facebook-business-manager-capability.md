---
categories: []
consumed_apis: []
description: Create and manage ad campaigns, analyze performance, and automate advertising workflows across Meta platforms. The Marketing API provides programmatic access to Facebook's advertising system, enabling businesses to create campaigns, ad sets, and ads, manage budgets and bidding strategies, define targeting audiences, and retrieve performance metrics.
layout: capability
name: Facebook Business Manager Facebook Marketing API
operations:
- description: Facebook Business Manager List campaigns
  method: GET
  name: listcampaigns
  path: /act_{ad_account_id}/campaigns
- description: Facebook Business Manager Create a campaign
  method: POST
  name: createcampaign
  path: /act_{ad_account_id}/campaigns
- description: Facebook Business Manager Get a campaign
  method: GET
  name: getcampaign
  path: /{campaign_id}
- description: Facebook Business Manager Update a campaign
  method: POST
  name: updatecampaign
  path: /{campaign_id}
- description: Facebook Business Manager Delete a campaign
  method: DELETE
  name: deletecampaign
  path: /{campaign_id}
- description: Facebook Business Manager List ad sets
  method: GET
  name: listadsets
  path: /act_{ad_account_id}/adsets
- description: Facebook Business Manager Create an ad set
  method: POST
  name: createadset
  path: /act_{ad_account_id}/adsets
- description: Facebook Business Manager Get an ad set
  method: GET
  name: getadset
  path: /{ad_set_id}
- description: Facebook Business Manager Update an ad set
  method: POST
  name: updateadset
  path: /{ad_set_id}
- description: Facebook Business Manager List ads
  method: GET
  name: listads
  path: /act_{ad_account_id}/ads
- description: Facebook Business Manager Create an ad
  method: POST
  name: createad
  path: /act_{ad_account_id}/ads
- description: Facebook Business Manager Get an ad
  method: GET
  name: getad
  path: /{ad_id}
- description: Facebook Business Manager List ad creatives
  method: GET
  name: listadcreatives
  path: /act_{ad_account_id}/adcreatives
- description: Facebook Business Manager Create an ad creative
  method: POST
  name: createadcreative
  path: /act_{ad_account_id}/adcreatives
- description: Facebook Business Manager Get ad account details
  method: GET
  name: getadaccount
  path: /act_{ad_account_id}
- description: Facebook Business Manager List custom audiences
  method: GET
  name: listcustomaudiences
  path: /act_{ad_account_id}/customaudiences
- description: Facebook Business Manager Create a custom audience
  method: POST
  name: createcustomaudience
  path: /act_{ad_account_id}/customaudiences
- description: Facebook Business Manager Get ad account insights
  method: GET
  name: getadaccountinsights
  path: /act_{ad_account_id}/insights
- description: Facebook Business Manager Get campaign insights
  method: GET
  name: getcampaigninsights
  path: /{campaign_id}/insights
- description: Facebook Business Manager Upload an ad image
  method: POST
  name: uploadadimage
  path: /act_{ad_account_id}/adimages
personas: []
provider_name: Facebook Business Manager
provider_slug: facebook-business-manager
search_terms:
- facebook business manager list campaigns
- updateadset
- facebook business manager create an ad creative
- facebook business manager create an ad set
- getadset
- facebook business manager create a custom audience
- analytics
- manager
- facebook business manager get ad account details
- marketing
- listadsets
- uploadadimage
- facebook business manager get an ad
- facebook business manager list custom audiences
- getcampaign
- getad
- business
- facebook business manager update an ad set
- business management
- createad
- listcustomaudiences
- createcampaign
- getadaccountinsights
- facebook business manager get an ad set
- facebook
- api
- listadcreatives
- facebook business manager create an ad
- advertising
- listcampaigns
- updatecampaign
- facebook business manager delete a campaign
- facebook business manager get a campaign
- listads
- facebook business manager list ad sets
- createadcreative
- facebook business manager get ad account insights
- createcustomaudience
- facebook business manager create a campaign
- facebook business manager list ads
- facebook business manager get campaign insights
- social media
- getcampaigninsights
- facebook business manager list ad creatives
- facebook business manager upload an ad image
- getadaccount
- facebook business manager update a campaign
- createadset
- deletecampaign
slug: facebook-business-manager-capability
source_filename: facebook-business-manager-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Facebook Business Manager Facebook Marketing API\n  description: Create and manage ad campaigns, analyze performance, and automate advertising workflows across Meta platforms.\n    The Marketing API provides programmatic access to Facebook's advertising system, enabling businesses to create campaigns,\n    ad sets, and ads, manage budgets and bidding strategies, define targeting audiences, and retrieve performance metrics.\n  tags:\n  - Facebook\n  - Business\n  - Manager\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: facebook-business-manager\n    baseUri: https://graph.facebook.com/v25.0\n    description: Facebook Business Manager Facebook Marketing API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FACEBOOK_BUSINESS_MANAGER_TOKEN}}'\n    resources:\n    - name: act-ad-account-id-campaigns\n      path: /act_{ad_account_id}/campaigns\n      operations:\n\
  \      - name: listcampaigns\n        method: GET\n        description: Facebook Business Manager List campaigns\n        inputParameters:\n        - name: filtering\n          in: query\n          type: string\n          description: Filters to apply to the campaign list. Accepts JSON array of filter objects with field, operator, and\n            value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcampaign\n        method: POST\n        description: Facebook Business Manager Create a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-id\n      path: /{campaign_id}\n      operations:\n      - name: getcampaign\n        method: GET\n        description: Facebook Business Manager Get a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: updatecampaign\n        method: POST\n        description: Facebook Business Manager Update a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecampaign\n        method: DELETE\n        description: Facebook Business Manager Delete a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id-adsets\n      path: /act_{ad_account_id}/adsets\n      operations:\n      - name: listadsets\n        method: GET\n        description: Facebook Business Manager List ad sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadset\n        method: POST\n        description: Facebook Business Manager Create an ad set\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-set-id\n      path: /{ad_set_id}\n      operations:\n      - name: getadset\n        method: GET\n        description: Facebook Business Manager Get an ad set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadset\n        method: POST\n        description: Facebook Business Manager Update an ad set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id-ads\n      path: /act_{ad_account_id}/ads\n      operations:\n      - name: listads\n        method: GET\n        description: Facebook Business Manager List ads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createad\n        method:\
  \ POST\n        description: Facebook Business Manager Create an ad\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-id\n      path: /{ad_id}\n      operations:\n      - name: getad\n        method: GET\n        description: Facebook Business Manager Get an ad\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id-adcreatives\n      path: /act_{ad_account_id}/adcreatives\n      operations:\n      - name: listadcreatives\n        method: GET\n        description: Facebook Business Manager List ad creatives\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadcreative\n        method: POST\n        description: Facebook Business Manager Create an ad creative\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id\n      path: /act_{ad_account_id}\n      operations:\n      - name: getadaccount\n        method: GET\n        description: Facebook Business Manager Get ad account details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id-customaudiences\n      path: /act_{ad_account_id}/customaudiences\n      operations:\n      - name: listcustomaudiences\n        method: GET\n        description: Facebook Business Manager List custom audiences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomaudience\n        method: POST\n        description: Facebook Business Manager Create a custom audience\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: act-ad-account-id-insights\n      path: /act_{ad_account_id}/insights\n      operations:\n      - name: getadaccountinsights\n        method: GET\n        description: Facebook Business Manager Get ad account insights\n        inputParameters:\n        - name: time_range\n          in: query\n          type: string\n          description: JSON object specifying the date range with since and until fields in YYYY-MM-DD format.\n        - name: breakdowns\n          in: query\n          type: string\n          description: Comma-separated list of breakdown dimensions such as age, gender, country, or placement.\n        - name: level\n          in: query\n          type: string\n          description: Level of aggregation for results. Options include account, campaign, adset, or ad.\n        - name: time_increment\n          in: query\n          type: string\n          description: Number of days for each increment in the time range, or use monthly or all_days.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-id-insights\n      path: /{campaign_id}/insights\n      operations:\n      - name: getcampaigninsights\n        method: GET\n        description: Facebook Business Manager Get campaign insights\n        inputParameters:\n        - name: time_range\n          in: query\n          type: string\n          description: JSON object specifying the date range with since and until fields in YYYY-MM-DD format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: act-ad-account-id-adimages\n      path: /act_{ad_account_id}/adimages\n      operations:\n      - name: uploadadimage\n        method: POST\n        description: Facebook Business Manager Upload an ad image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: facebook-business-manager-rest\n    description: REST adapter for Facebook Business Manager Facebook Marketing API.\n    resources:\n    - path: /act_{ad_account_id}/campaigns\n      name: listcampaigns\n      operations:\n      - method: GET\n        name: listcampaigns\n        description: Facebook Business Manager List campaigns\n        call: facebook-business-manager.listcampaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/campaigns\n      name: createcampaign\n      operations:\n      - method: POST\n        name: createcampaign\n        description: Facebook Business Manager Create a campaign\n        call: facebook-business-manager.createcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{campaign_id}\n      name: getcampaign\n      operations:\n      - method: GET\n        name:\
  \ getcampaign\n        description: Facebook Business Manager Get a campaign\n        call: facebook-business-manager.getcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{campaign_id}\n      name: updatecampaign\n      operations:\n      - method: POST\n        name: updatecampaign\n        description: Facebook Business Manager Update a campaign\n        call: facebook-business-manager.updatecampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{campaign_id}\n      name: deletecampaign\n      operations:\n      - method: DELETE\n        name: deletecampaign\n        description: Facebook Business Manager Delete a campaign\n        call: facebook-business-manager.deletecampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/adsets\n      name: listadsets\n      operations:\n      - method: GET\n        name: listadsets\n        description:\
  \ Facebook Business Manager List ad sets\n        call: facebook-business-manager.listadsets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/adsets\n      name: createadset\n      operations:\n      - method: POST\n        name: createadset\n        description: Facebook Business Manager Create an ad set\n        call: facebook-business-manager.createadset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{ad_set_id}\n      name: getadset\n      operations:\n      - method: GET\n        name: getadset\n        description: Facebook Business Manager Get an ad set\n        call: facebook-business-manager.getadset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{ad_set_id}\n      name: updateadset\n      operations:\n      - method: POST\n        name: updateadset\n        description: Facebook Business Manager Update an ad set\n        call: facebook-business-manager.updateadset\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/ads\n      name: listads\n      operations:\n      - method: GET\n        name: listads\n        description: Facebook Business Manager List ads\n        call: facebook-business-manager.listads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/ads\n      name: createad\n      operations:\n      - method: POST\n        name: createad\n        description: Facebook Business Manager Create an ad\n        call: facebook-business-manager.createad\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{ad_id}\n      name: getad\n      operations:\n      - method: GET\n        name: getad\n        description: Facebook Business Manager Get an ad\n        call: facebook-business-manager.getad\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/adcreatives\n\
  \      name: listadcreatives\n      operations:\n      - method: GET\n        name: listadcreatives\n        description: Facebook Business Manager List ad creatives\n        call: facebook-business-manager.listadcreatives\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/adcreatives\n      name: createadcreative\n      operations:\n      - method: POST\n        name: createadcreative\n        description: Facebook Business Manager Create an ad creative\n        call: facebook-business-manager.createadcreative\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}\n      name: getadaccount\n      operations:\n      - method: GET\n        name: getadaccount\n        description: Facebook Business Manager Get ad account details\n        call: facebook-business-manager.getadaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/customaudiences\n\
  \      name: listcustomaudiences\n      operations:\n      - method: GET\n        name: listcustomaudiences\n        description: Facebook Business Manager List custom audiences\n        call: facebook-business-manager.listcustomaudiences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/customaudiences\n      name: createcustomaudience\n      operations:\n      - method: POST\n        name: createcustomaudience\n        description: Facebook Business Manager Create a custom audience\n        call: facebook-business-manager.createcustomaudience\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/insights\n      name: getadaccountinsights\n      operations:\n      - method: GET\n        name: getadaccountinsights\n        description: Facebook Business Manager Get ad account insights\n        call: facebook-business-manager.getadaccountinsights\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /{campaign_id}/insights\n      name: getcampaigninsights\n      operations:\n      - method: GET\n        name: getcampaigninsights\n        description: Facebook Business Manager Get campaign insights\n        call: facebook-business-manager.getcampaigninsights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /act_{ad_account_id}/adimages\n      name: uploadadimage\n      operations:\n      - method: POST\n        name: uploadadimage\n        description: Facebook Business Manager Upload an ad image\n        call: facebook-business-manager.uploadadimage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: facebook-business-manager-mcp\n    transport: http\n    description: MCP adapter for Facebook Business Manager Facebook Marketing API for AI agent use.\n    tools:\n    - name: listcampaigns\n      description: Facebook Business\
  \ Manager List campaigns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.listcampaigns\n      with:\n        filtering: tools.filtering\n      inputParameters:\n      - name: filtering\n        type: string\n        description: Filters to apply to the campaign list. Accepts JSON array of filter objects with field, operator, and\n          value.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcampaign\n      description: Facebook Business Manager Create a campaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.createcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaign\n      description: Facebook Business Manager Get a campaign\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getcampaign\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecampaign\n      description: Facebook Business Manager Update a campaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.updatecampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecampaign\n      description: Facebook Business Manager Delete a campaign\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: facebook-business-manager.deletecampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadsets\n      description: Facebook Business Manager List ad sets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.listadsets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createadset\n\
  \      description: Facebook Business Manager Create an ad set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.createadset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadset\n      description: Facebook Business Manager Get an ad set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getadset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadset\n      description: Facebook Business Manager Update an ad set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.updateadset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listads\n      description: Facebook Business Manager List ads\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: facebook-business-manager.listads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createad\n      description: Facebook Business Manager Create an ad\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.createad\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getad\n      description: Facebook Business Manager Get an ad\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getad\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadcreatives\n      description: Facebook Business Manager List ad creatives\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.listadcreatives\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: createadcreative\n      description: Facebook Business Manager Create an ad creative\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.createadcreative\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadaccount\n      description: Facebook Business Manager Get ad account details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getadaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomaudiences\n      description: Facebook Business Manager List custom audiences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.listcustomaudiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomaudience\n\
  \      description: Facebook Business Manager Create a custom audience\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.createcustomaudience\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadaccountinsights\n      description: Facebook Business Manager Get ad account insights\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getadaccountinsights\n      with:\n        time_range: tools.time_range\n        breakdowns: tools.breakdowns\n        level: tools.level\n        time_increment: tools.time_increment\n      inputParameters:\n      - name: time_range\n        type: string\n        description: JSON object specifying the date range with since and until fields in YYYY-MM-DD format.\n      - name: breakdowns\n        type: string\n        description: Comma-separated list of breakdown dimensions\
  \ such as age, gender, country, or placement.\n      - name: level\n        type: string\n        description: Level of aggregation for results. Options include account, campaign, adset, or ad.\n      - name: time_increment\n        type: string\n        description: Number of days for each increment in the time range, or use monthly or all_days.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaigninsights\n      description: Facebook Business Manager Get campaign insights\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: facebook-business-manager.getcampaigninsights\n      with:\n        time_range: tools.time_range\n      inputParameters:\n      - name: time_range\n        type: string\n        description: JSON object specifying the date range with since and until fields in YYYY-MM-DD format.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadadimage\n \
  \     description: Facebook Business Manager Upload an ad image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: facebook-business-manager.uploadadimage\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FACEBOOK_BUSINESS_MANAGER_TOKEN: FACEBOOK_BUSINESS_MANAGER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/facebook-business-manager/refs/heads/main/capabilities/facebook-business-manager-capability.yaml
tags:
- Facebook
- Business
- Manager
- API
tools:
- description: Facebook Business Manager List campaigns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampaigns
- description: Facebook Business Manager Create a campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcampaign
- description: Facebook Business Manager Get a campaign
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaign
- description: Facebook Business Manager Update a campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecampaign
- description: Facebook Business Manager Delete a campaign
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecampaign
- description: Facebook Business Manager List ad sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadsets
- description: Facebook Business Manager Create an ad set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadset
- description: Facebook Business Manager Get an ad set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadset
- description: Facebook Business Manager Update an ad set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadset
- description: Facebook Business Manager List ads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listads
- description: Facebook Business Manager Create an ad
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createad
- description: Facebook Business Manager Get an ad
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getad
- description: Facebook Business Manager List ad creatives
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadcreatives
- description: Facebook Business Manager Create an ad creative
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadcreative
- description: Facebook Business Manager Get ad account details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadaccount
- description: Facebook Business Manager List custom audiences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomaudiences
- description: Facebook Business Manager Create a custom audience
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomaudience
- description: Facebook Business Manager Get ad account insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadaccountinsights
- description: Facebook Business Manager Get campaign insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaigninsights
- description: Facebook Business Manager Upload an ad image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadadimage
---
