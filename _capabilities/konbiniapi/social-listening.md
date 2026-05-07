---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Social Listening
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
slug: social-listening
source_filename: social-listening.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.dev/v1\nkind: CapabilityWorkflow\nmetadata:\n  name: social-listening\n  description: >-\n    Track brand or topic mentions across Instagram and TikTok by searching media,\n    expanding hashtag/audio surfaces, and pulling top-level comments for sentiment.\nspec:\n  imports:\n    - ../shared/konbiniapi.yaml\n  inputs:\n    - name: query\n      type: string\n      required: true\n    - name: tagName\n      type: string\n      required: false\n  steps:\n    - id: instagram-search\n      capability: konbiniapi\n      operation: instagramSearch\n      params:\n        query: '{{inputs.query}}'\n    - id: tiktok-search\n      capability: konbiniapi\n      operation: tiktokSearch\n      params:\n        query: '{{inputs.query}}'\n    - id: tiktok-search-videos\n      capability: konbiniapi\n      operation: tiktokSearchVideos\n      params:\n        query: '{{inputs.query}}'\n    - id: tiktok-tag\n      when: '{{inputs.tagName}}'\n      capability: konbiniapi\n\
  \      operation: tiktokGetTagVideos\n      params:\n        tagName: '{{inputs.tagName}}'\n  outputs:\n    instagramHits: '{{steps.instagram-search.response.data}}'\n    tiktokMixed: '{{steps.tiktok-search.response.data}}'\n    tiktokVideos: '{{steps.tiktok-search-videos.response.data}}'\n    taggedContent: '{{steps.tiktok-tag.response.data}}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/konbiniapi/refs/heads/main/capabilities/social-listening.yaml
tags: []
tools: []
---
