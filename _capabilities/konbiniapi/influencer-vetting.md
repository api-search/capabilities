---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Influencer Vetting
operations: []
personas: []
provider_name: KonbiniAPI
provider_slug: konbiniapi
search_terms:
- social listening
- social media
- influencer marketing
- instagram
- creator tools
- activitystreams 2.0
- public data
- tiktok
- data extraction
- model context protocol
- api
- mcp
- scraping
slug: influencer-vetting
source_filename: influencer-vetting.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.dev/v1\nkind: CapabilityWorkflow\nmetadata:\n  name: influencer-vetting\n  description: >-\n    Vet a creator across Instagram and TikTok by combining profile, recent posts,\n    engagement, and verification data into a single normalized ActivityStreams 2.0\n    payload for downstream scoring.\nspec:\n  imports:\n    - ../shared/konbiniapi.yaml\n  inputs:\n    - name: instagramUsername\n      type: string\n      required: false\n    - name: tiktokUsername\n      type: string\n      required: false\n    - name: postLimit\n      type: integer\n      default: 12\n  steps:\n    - id: instagram-profile\n      when: '{{inputs.instagramUsername}}'\n      capability: konbiniapi\n      operation: instagramGetUser\n      params:\n        username: '{{inputs.instagramUsername}}'\n    - id: instagram-recent-posts\n      when: '{{inputs.instagramUsername}}'\n      capability: konbiniapi\n      operation: instagramGetUserPosts\n      params:\n        username: '{{inputs.instagramUsername}}'\n\
  \        limit: '{{inputs.postLimit}}'\n    - id: tiktok-profile\n      when: '{{inputs.tiktokUsername}}'\n      capability: konbiniapi\n      operation: tiktokGetUser\n      params:\n        username: '{{inputs.tiktokUsername}}'\n    - id: tiktok-recent-videos\n      when: '{{inputs.tiktokUsername}}'\n      capability: konbiniapi\n      operation: tiktokGetUserVideos\n      params:\n        username: '{{inputs.tiktokUsername}}'\n        limit: '{{inputs.postLimit}}'\n  outputs:\n    instagram:\n      profile: '{{steps.instagram-profile.response.data}}'\n      recentPosts: '{{steps.instagram-recent-posts.response.data}}'\n    tiktok:\n      profile: '{{steps.tiktok-profile.response.data}}'\n      recentVideos: '{{steps.tiktok-recent-videos.response.data}}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/konbiniapi/refs/heads/main/capabilities/influencer-vetting.yaml
tags: []
tools: []
---
