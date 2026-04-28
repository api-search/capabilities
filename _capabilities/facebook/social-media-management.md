---
categories:
- content-management
consumed_apis:
- graph-api
- instagram-api
- threads-api
description: Workflow capability for managing content across Facebook, Instagram, and Threads. Combines Graph API for Facebook posts, Instagram API for visual content, and Threads API for text-based publishing. Used by social media managers and content creators.
layout: capability
name: Facebook Social Media Management
operations:
- description: Get posts from a user's feed.
  method: GET
  name: list-posts
  path: /v1/posts
- description: Create a new Facebook post.
  method: POST
  name: create-post
  path: /v1/posts
- description: List Instagram media.
  method: GET
  name: list-instagram-media
  path: /v1/instagram-media
- description: Publish Instagram media.
  method: POST
  name: publish-instagram-media
  path: /v1/instagram-media
- description: Create a Threads post.
  method: POST
  name: create-threads-post
  path: /v1/threads
personas: []
provider_name: Facebook
provider_slug: facebook
search_terms:
- publish instagram media
- manage advertising campaigns and performance.
- get posts from a facebook user's feed.
- plans and executes advertising campaigns.
- handles customer inquiries via messaging channels.
- campaign management and audience targeting.
- list instagram media.
- manage content across facebook, instagram, and threads.
- create and publish instagram content.
- Conversational Commerce
- facebook
- facebook post management.
- get instagram insights
- Ad Operations
- customer messaging across messenger and whatsapp.
- advertising
- manages day-to-day ad campaign optimization.
- create a threads post.
- social networking
- create a new facebook post.
- get threads performance insights.
- creates and publishes visual and text content.
- publishing and managing content across platforms.
- list instagram media
- create threads post
- get instagram performance insights.
- direct messaging and customer communication.
- publish instagram media.
- publishing
- Marketing Manager
- manages content and engagement across meta platforms.
- performance tracking and insights.
- threads content management.
- create facebook post
- Customer Support
- create post
- get posts from a user's feed.
- Social Media Manager
- Content Creator
- instagram content management.
- list posts
- content publishing
- messaging
- create a new threads post.
- create instagram media
- list instagram media for an account.
- social media
- content management
- get threads insights
- get facebook feed
slug: social-media-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Facebook Social Media Management\n  description: >-\n    Workflow capability for managing content across Facebook, Instagram, and\n    Threads. Combines Graph API for Facebook posts, Instagram API for visual\n    content, and Threads API for text-based publishing. Used by social media\n    managers and content creators.\n  tags:\n    - Facebook\n    - Social Media\n    - Content Management\n    - Publishing\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACEBOOK_ACCESS_TOKEN: FACEBOOK_ACCESS_TOKEN\n      INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n      THREADS_ACCESS_TOKEN: THREADS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: graph-api\n      location: ./shared/graph-api.yaml\n    - import: instagram-api\n      location: ./shared/instagram-api.yaml\n    - import: threads-api\n      location: ./shared/threads-api.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: social-media-api\n      description: \"Unified REST API for social media management across Meta platforms.\"\n      resources:\n        - path: /v1/posts\n          name: posts\n          description: \"Facebook post management.\"\n          operations:\n            - method: GET\n              name: list-posts\n              description: \"Get posts from a user's feed.\"\n              call: \"graph-api.get-user-feed\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-post\n              description: \"Create a new Facebook post.\"\n              call: \"graph-api.create-post\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instagram-media\n          name: instagram-media\n          description: \"Instagram content management.\"\n          operations:\n            - method: GET\n   \
  \           name: list-instagram-media\n              description: \"List Instagram media.\"\n              call: \"instagram-api.list-media\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: publish-instagram-media\n              description: \"Publish Instagram media.\"\n              call: \"instagram-api.publish-media\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/threads\n          name: threads\n          description: \"Threads content management.\"\n          operations:\n            - method: POST\n              name: create-threads-post\n              description: \"Create a Threads post.\"\n              call: \"threads-api.create-media\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: social-media-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted social media management.\"\n      tools:\n        - name: get-facebook-feed\n          description: \"Get posts from a Facebook user's feed.\"\n          hints:\n            readOnly: true\n          call: \"graph-api.get-user-feed\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-facebook-post\n          description: \"Create a new Facebook post.\"\n          hints:\n            readOnly: false\n          call: \"graph-api.create-post\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-instagram-media\n          description: \"List Instagram media for an account.\"\n          hints:\n            readOnly: true\n          call: \"instagram-api.list-media\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-instagram-media\n         \
  \ description: \"Create and publish Instagram content.\"\n          hints:\n            readOnly: false\n          call: \"instagram-api.create-media\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-instagram-insights\n          description: \"Get Instagram performance insights.\"\n          hints:\n            readOnly: true\n          call: \"instagram-api.get-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-threads-post\n          description: \"Create a new Threads post.\"\n          hints:\n            readOnly: false\n          call: \"threads-api.create-media\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-threads-insights\n          description: \"Get Threads performance insights.\"\n          hints:\n            readOnly: true\n          call: \"threads-api.get-insights\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/facebook/refs/heads/main/capabilities/social-media-management.yaml
tags:
- Facebook
- Social Media
- Content Management
- Publishing
tools:
- description: Get posts from a Facebook user's feed.
  hints:
    readOnly: true
  name: get-facebook-feed
- description: Create a new Facebook post.
  hints:
    readOnly: false
  name: create-facebook-post
- description: List Instagram media for an account.
  hints:
    readOnly: true
  name: list-instagram-media
- description: Create and publish Instagram content.
  hints:
    readOnly: false
  name: create-instagram-media
- description: Get Instagram performance insights.
  hints:
    readOnly: true
  name: get-instagram-insights
- description: Create a new Threads post.
  hints:
    readOnly: false
  name: create-threads-post
- description: Get Threads performance insights.
  hints:
    readOnly: true
  name: get-threads-insights
---
