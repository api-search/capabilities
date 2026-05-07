---
categories: []
consumed_apis: []
description: The Display & Video 360 API enables programmatic management of display, video, and audio advertising campaigns including advertisers, campaigns, insertion orders, line items, creatives, targeting, and audiences.
layout: capability
name: Google Display & Video 360 API
operations:
- description: Google Display & Video 360 List advertisers
  method: GET
  name: listadvertisers
  path: /v4/advertisers
- description: Google Display & Video 360 List campaigns
  method: GET
  name: listcampaigns
  path: /v4/advertisers/{advertiserId}/campaigns
- description: Google Display & Video 360 List insertion orders
  method: GET
  name: listinsertionorders
  path: /v4/advertisers/{advertiserId}/insertionOrders
- description: Google Display & Video 360 List line items
  method: GET
  name: listlineitems
  path: /v4/advertisers/{advertiserId}/lineItems
- description: Google Display & Video 360 List creatives
  method: GET
  name: listcreatives
  path: /v4/advertisers/{advertiserId}/creatives
personas: []
provider_name: Google Display & Video 360
provider_slug: google-display-video-360
search_terms:
- google display & video 360 list insertion orders
- google display & video 360 list creatives
- listlineitems
- video
- targeting
- api
- display ads
- '360'
- dv360
- display
- listadvertisers
- google
- listcreatives
- google display & video 360 list advertisers
- campaign management
- video ads
- listcampaigns
- google display & video 360 list line items
- programmatic advertising
- google display & video 360 list campaigns
- listinsertionorders
slug: google-display-video-360-capability
source_filename: google-display-video-360-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Display & Video 360 API\n  description: The Display & Video 360 API enables programmatic management of display, video, and audio advertising campaigns\n    including advertisers, campaigns, insertion orders, line items, creatives, targeting, and audiences.\n  tags:\n  - Google\n  - Display\n  - Video\n  - '360'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-display-video-360\n    baseUri: https://displayvideo.googleapis.com\n    description: Google Display & Video 360 API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_DISPLAY_VIDEO_360_TOKEN}}'\n    resources:\n    - name: v4-advertisers\n      path: /v4/advertisers\n      operations:\n      - name: listadvertisers\n        method: GET\n        description: Google Display & Video 360 List advertisers\n        inputParameters:\n        - name: partnerId\n          in: query\n\
  \          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-advertisers-advertiserid-campaigns\n      path: /v4/advertisers/{advertiserId}/campaigns\n      operations:\n      - name: listcampaigns\n        method: GET\n        description: Google Display & Video 360 List campaigns\n        inputParameters:\n        - name: advertiserId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-advertisers-advertiserid-insertionorders\n      path: /v4/advertisers/{advertiserId}/insertionOrders\n      operations:\n      - name: listinsertionorders\n        method:\
  \ GET\n        description: Google Display & Video 360 List insertion orders\n        inputParameters:\n        - name: advertiserId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-advertisers-advertiserid-lineitems\n      path: /v4/advertisers/{advertiserId}/lineItems\n      operations:\n      - name: listlineitems\n        method: GET\n        description: Google Display & Video 360 List line items\n        inputParameters:\n        - name: advertiserId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-advertisers-advertiserid-creatives\n      path: /v4/advertisers/{advertiserId}/creatives\n      operations:\n      - name: listcreatives\n        method: GET\n  \
  \      description: Google Display & Video 360 List creatives\n        inputParameters:\n        - name: advertiserId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-display-video-360-rest\n    description: REST adapter for Google Display & Video 360 API.\n    resources:\n    - path: /v4/advertisers\n      name: listadvertisers\n      operations:\n      - method: GET\n        name: listadvertisers\n        description: Google Display & Video 360 List advertisers\n        call: google-display-video-360.listadvertisers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/advertisers/{advertiserId}/campaigns\n      name: listcampaigns\n      operations:\n      - method: GET\n        name: listcampaigns\n        description: Google Display\
  \ & Video 360 List campaigns\n        call: google-display-video-360.listcampaigns\n        with:\n          advertiserId: rest.advertiserId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/advertisers/{advertiserId}/insertionOrders\n      name: listinsertionorders\n      operations:\n      - method: GET\n        name: listinsertionorders\n        description: Google Display & Video 360 List insertion orders\n        call: google-display-video-360.listinsertionorders\n        with:\n          advertiserId: rest.advertiserId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/advertisers/{advertiserId}/lineItems\n      name: listlineitems\n      operations:\n      - method: GET\n        name: listlineitems\n        description: Google Display & Video 360 List line items\n        call: google-display-video-360.listlineitems\n        with:\n          advertiserId: rest.advertiserId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v4/advertisers/{advertiserId}/creatives\n      name: listcreatives\n      operations:\n      - method: GET\n        name: listcreatives\n        description: Google Display & Video 360 List creatives\n        call: google-display-video-360.listcreatives\n        with:\n          advertiserId: rest.advertiserId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-display-video-360-mcp\n    transport: http\n    description: MCP adapter for Google Display & Video 360 API for AI agent use.\n    tools:\n    - name: listadvertisers\n      description: Google Display & Video 360 List advertisers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-display-video-360.listadvertisers\n      with:\n        partnerId: tools.partnerId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n \
  \     inputParameters:\n      - name: partnerId\n        type: string\n        description: partnerId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcampaigns\n      description: Google Display & Video 360 List campaigns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-display-video-360.listcampaigns\n      with:\n        advertiserId: tools.advertiserId\n      inputParameters:\n      - name: advertiserId\n        type: string\n        description: advertiserId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinsertionorders\n      description: Google Display & Video 360 List insertion orders\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-display-video-360.listinsertionorders\n      with:\n        advertiserId: tools.advertiserId\n      inputParameters:\n      - name: advertiserId\n        type: string\n        description: advertiserId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlineitems\n      description: Google Display & Video 360 List line items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-display-video-360.listlineitems\n      with:\n        advertiserId: tools.advertiserId\n      inputParameters:\n      - name: advertiserId\n        type: string\n        description: advertiserId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcreatives\n      description: Google Display & Video 360 List creatives\n      hints:\n        readOnly: true\n        destructive: false\n     \
  \   idempotent: true\n      call: google-display-video-360.listcreatives\n      with:\n        advertiserId: tools.advertiserId\n      inputParameters:\n      - name: advertiserId\n        type: string\n        description: advertiserId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_DISPLAY_VIDEO_360_TOKEN: GOOGLE_DISPLAY_VIDEO_360_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-display-video-360/refs/heads/main/capabilities/google-display-video-360-capability.yaml
tags:
- Google
- Display
- Video
- '360'
- API
tools:
- description: Google Display & Video 360 List advertisers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadvertisers
- description: Google Display & Video 360 List campaigns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampaigns
- description: Google Display & Video 360 List insertion orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinsertionorders
- description: Google Display & Video 360 List line items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlineitems
- description: Google Display & Video 360 List creatives
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcreatives
---
