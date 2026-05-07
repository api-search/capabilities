---
categories: []
consumed_apis: []
description: PicPurify provides image and video moderation services including weapons (gun and knife) detection, nudity, drug, gore, hate sign, age, gender, and other content moderation tasks.
layout: capability
name: PicPurify Image and Video Moderation API
operations:
- description: Analyze an image
  method: POST
  name: post-analyse-1-1
  path: /analyse/1.1
- description: Analyze a video
  method: POST
  name: post-analyse-video-1-0
  path: /analyse_video/1.0
personas: []
provider_name: PicPurify
provider_slug: picpurify
search_terms:
- weapon detection
- analyze an image
- content moderation
- computer vision
- post analyse 1 1
- analyze a video
- api
- image moderation
- post analyse video 1 0
- picpurify
slug: picpurify-capability
source_filename: picpurify-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PicPurify Image and Video Moderation API\n  description: PicPurify provides image and video moderation services including weapons (gun and knife) detection, nudity,\n    drug, gore, hate sign, age, gender, and other content moderation tasks.\n  tags:\n  - Picpurify\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: picpurify\n    baseUri: https://www.picpurify.com\n    description: PicPurify Image and Video Moderation API HTTP API.\n    resources:\n    - name: analyse-1-1\n      path: /analyse/1.1\n      operations:\n      - name: post-analyse-1-1\n        method: POST\n        description: Analyze an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analyse-video-1-0\n      path: /analyse_video/1.0\n      operations:\n      - name: post-analyse-video-1-0\n        method: POST\n\
  \        description: Analyze a video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: picpurify-rest\n    description: REST adapter for PicPurify Image and Video Moderation API.\n    resources:\n    - path: /analyse/1.1\n      name: post-analyse-1-1\n      operations:\n      - method: POST\n        name: post-analyse-1-1\n        description: Analyze an image\n        call: picpurify.post-analyse-1-1\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analyse_video/1.0\n      name: post-analyse-video-1-0\n      operations:\n      - method: POST\n        name: post-analyse-video-1-0\n        description: Analyze a video\n        call: picpurify.post-analyse-video-1-0\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: picpurify-mcp\n    transport:\
  \ http\n    description: MCP adapter for PicPurify Image and Video Moderation API for AI agent use.\n    tools:\n    - name: post-analyse-1-1\n      description: Analyze an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: picpurify.post-analyse-1-1\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-analyse-video-1-0\n      description: Analyze a video\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: picpurify.post-analyse-video-1-0\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/picpurify/refs/heads/main/capabilities/picpurify-capability.yaml
tags:
- Picpurify
- API
tools:
- description: Analyze an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-analyse-1-1
- description: Analyze a video
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-analyse-video-1-0
---
