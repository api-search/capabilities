---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Content Research
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
slug: content-research
source_filename: content-research.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.dev/v1\nkind: CapabilityWorkflow\nmetadata:\n  name: content-research\n  description: >-\n    Deep-dive a single TikTok video — pull details, top-level comments,\n    selected reply threads, and an English transcript for downstream NLP.\nspec:\n  imports:\n    - ../shared/konbiniapi.yaml\n  inputs:\n    - name: videoId\n      type: string\n      required: true\n    - name: language\n      type: string\n      default: en-US\n    - name: replyDepth\n      type: integer\n      default: 3\n  steps:\n    - id: video-details\n      capability: konbiniapi\n      operation: tiktokGetVideo\n      params:\n        videoId: '{{inputs.videoId}}'\n    - id: video-comments\n      capability: konbiniapi\n      operation: tiktokGetVideoComments\n      params:\n        videoId: '{{inputs.videoId}}'\n    - id: top-comment-replies\n      forEach: '{{steps.video-comments.response.data.items[0:replyDepth]}}'\n      capability: konbiniapi\n      operation: tiktokGetCommentReplies\n\
  \      params:\n        videoId: '{{inputs.videoId}}'\n        commentId: '{{item.id}}'\n    - id: transcript\n      capability: konbiniapi\n      operation: tiktokGetVideoTranscript\n      params:\n        videoId: '{{inputs.videoId}}'\n        language: '{{inputs.language}}'\n  outputs:\n    video: '{{steps.video-details.response.data}}'\n    comments: '{{steps.video-comments.response.data}}'\n    replies: '{{steps.top-comment-replies.response}}'\n    transcript: '{{steps.transcript.response.data}}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/konbiniapi/refs/heads/main/capabilities/content-research.yaml
tags: []
tools: []
---
