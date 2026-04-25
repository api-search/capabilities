---
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
- content publishing
- analytics
- tracks content performance and audience insights.
- social media
- meta
- get data about other instagram business or creator accounts.
- insights and performance metrics.
- publishes and manages content across instagram accounts.
- creates and publishes photos, videos, reels, and stories.
- get fields on an instagram photo, video, story, reel, or album.
- instagram
- get media
- user media for analytics review.
- reporting
- user profile data.
- get social interaction metrics for the account.
- get fields and edges on an instagram business or creator account.
- get media insights
- get fields on an instagram media object.
- get a collection of ig media objects published on the account.
- individual media detail for analytics.
- manages instagram direct conversations for business inquiries.
- get user
- comments, mentions, and community interaction.
- website embedding of instagram content.
- get business discovery
- instagram direct messaging.
- competitor and business account research.
- get social interaction metrics for a media object.
- content publishing and media management.
- photos
- insights
- embeds instagram content on websites and applications.
- get user insights
- account-level analytics.
- media-level analytics.
- videos
- monitors mentions, comments, and brand sentiment on instagram.
- get user media
slug: analytics-and-insights
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
