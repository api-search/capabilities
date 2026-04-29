---
api_specs:
- filename: instagram-graph-api.yaml
  format: yaml
  label: instagram-graph
  slug: instagram-graph
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/instagram/refs/heads/main/openapi/instagram-graph-api.yaml
categories:
- analytics
consumed_apis:
- instagram-graph
description: Unified workflow for Instagram analytics and insights including account-level metrics, media-level performance data, user profile analysis, and competitor research via business discovery. Used by marketing analysts and social media strategists to measure content performance, track audience growth, and benchmark against competitors.
layout: capability
name: Instagram Analytics And Insights
operations:
- description: Get fields and edges on an Instagram Business or Creator account.
  method: GET
  name: get-user
  path: /v1/users/{user_id}
- description: Get data about other Instagram Business or Creator accounts.
  method: GET
  name: get-business-discovery
  path: /v1/users/{user_id}/business-discovery
- description: Get social interaction metrics for the account.
  method: GET
  name: get-user-insights
  path: /v1/users/{user_id}/insights
- description: Get social interaction metrics for a media object.
  method: GET
  name: get-media-insights
  path: /v1/media/{media_id}/insights
- description: Get a collection of IG Media objects published on the account.
  method: GET
  name: get-user-media
  path: /v1/users/{user_id}/media
- description: Get fields on an Instagram media object.
  method: GET
  name: get-media
  path: /v1/media/{media_id}
personas: []
provider_name: Instagram
provider_slug: instagram
search_terms:
- publishes and manages content across instagram accounts.
- get fields on an instagram photo, video, story, reel, or album.
- get user
- get user insights
- meta
- get social interaction metrics for the account.
- get social interaction metrics for a media object.
- get fields and edges on an instagram business or creator account.
- get media
- tracks content performance and audience insights.
- reporting
- get user media
- instagram direct messaging.
- get fields on an instagram media object.
- instagram
- get data about other instagram business or creator accounts.
- get a collection of ig media objects published on the account.
- website embedding of instagram content.
- insights and performance metrics.
- content publishing and media management.
- embeds instagram content on websites and applications.
- insights
- account-level analytics.
- social media
- user media for analytics review.
- competitor and business account research.
- user profile data.
- analytics
- monitors mentions, comments, and brand sentiment on instagram.
- comments, mentions, and community interaction.
- videos
- creates and publishes photos, videos, reels, and stories.
- photos
- media-level analytics.
- get business discovery
- manages instagram direct conversations for business inquiries.
- content publishing
- individual media detail for analytics.
- get media insights
slug: analytics-and-insights
source_filename: analytics-and-insights.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Instagram Analytics And Insights\"\n  description: >-\n    Unified workflow for Instagram analytics and insights including account-level\n    metrics, media-level performance data, user profile analysis, and competitor\n    research via business discovery. Used by marketing analysts and social media\n    strategists to measure content performance, track audience growth, and\n    benchmark against competitors.\n  tags:\n    - Instagram\n    - Analytics\n    - Insights\n    - Social Media\n    - Reporting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: instagram-graph\n      location: ./shared/instagram-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: instagram-analytics-api\n      description: \"Unified REST API for Instagram analytics and insights workflows.\"\
  \n      resources:\n        - path: /v1/users/{user_id}\n          name: user-profile\n          description: \"User profile data.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get fields and edges on an Instagram Business or Creator account.\"\n              call: \"instagram-graph.get-user\"\n              with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/business-discovery\n          name: business-discovery\n          description: \"Competitor and business account research.\"\n          operations:\n            - method: GET\n              name: get-business-discovery\n              description: \"Get data about other Instagram Business or Creator accounts.\"\n              call: \"instagram-graph.get-business-discovery\"\
  \n              with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/insights\n          name: user-insights\n          description: \"Account-level analytics.\"\n          operations:\n            - method: GET\n              name: get-user-insights\n              description: \"Get social interaction metrics for the account.\"\n              call: \"instagram-graph.get-user-insights\"\n              with:\n                user_id: \"rest.user_id\"\n                metric: \"rest.metric\"\n                period: \"rest.period\"\n                since: \"rest.since\"\n                until: \"rest.until\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/media/{media_id}/insights\n          name: media-insights\n          description: \"Media-level analytics.\"\n          operations:\n            - method: GET\n              name: get-media-insights\n              description: \"Get social interaction metrics for a media object.\"\n              call: \"instagram-graph.get-media-insights\"\n              with:\n                media_id: \"rest.media_id\"\n                metric: \"rest.metric\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/media\n          name: user-media\n          description: \"User media for analytics review.\"\n          operations:\n            - method: GET\n              name: get-user-media\n              description: \"Get a collection of IG Media objects published on the account.\"\n              call: \"instagram-graph.get-user-media\"\n    \
  \          with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/media/{media_id}\n          name: media\n          description: \"Individual media detail for analytics.\"\n          operations:\n            - method: GET\n              name: get-media\n              description: \"Get fields on an Instagram media object.\"\n              call: \"instagram-graph.get-media\"\n              with:\n                media_id: \"rest.media_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: instagram-analytics-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted Instagram analytics and insights.\"\n      tools:\n        - name: get-user\n          description: \"Get fields and edges on an Instagram Business or Creator account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-user\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-business-discovery\n          description: \"Get data about other Instagram Business or Creator accounts.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-business-discovery\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-insights\n          description: \"Get social interaction metrics for the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-user-insights\"\n          with:\n            user_id: \"tools.user_id\"\n            metric: \"tools.metric\"\n            period: \"tools.period\"\n            since: \"tools.since\"\n            until: \"tools.until\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-media-insights\n          description: \"Get social interaction metrics for a media object.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-media-insights\"\n          with:\n            media_id: \"tools.media_id\"\n            metric:\
  \ \"tools.metric\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-media\n          description: \"Get a collection of IG Media objects published on the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-user-media\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-media\n          description: \"Get fields on an Instagram photo, video, story, reel, or album.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-media\"\n          with:\n            media_id: \"\
  tools.media_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/instagram/refs/heads/main/capabilities/analytics-and-insights.yaml
tags:
- Instagram
- Analytics
- Insights
- Social Media
- Reporting
tools:
- description: Get fields and edges on an Instagram Business or Creator account.
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Get data about other Instagram Business or Creator accounts.
  hints:
    idempotent: true
    readOnly: true
  name: get-business-discovery
- description: Get social interaction metrics for the account.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-insights
- description: Get social interaction metrics for a media object.
  hints:
    idempotent: true
    readOnly: true
  name: get-media-insights
- description: Get a collection of IG Media objects published on the account.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-media
- description: Get fields on an Instagram photo, video, story, reel, or album.
  hints:
    idempotent: true
    readOnly: true
  name: get-media
---
