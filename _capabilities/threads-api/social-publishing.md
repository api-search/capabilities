---
api_specs:
- filename: threads-api.yml
  format: yaml
  label: threads
  slug: threads
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/threads-api/refs/heads/main/openapi/threads-api.yml
categories: []
consumed_apis:
- threads
description: Unified social publishing capability for the Threads platform combining content publishing, reply management, engagement analytics, and account insights. Used by creators, brands, and social media managers to manage Threads presence at scale.
layout: capability
name: Threads Social Publishing
operations:
- description: Get Threads user profile information
  method: GET
  name: get-profile
  path: /v1/profile
- description: Get all user threads with pagination
  method: GET
  name: list-threads
  path: /v1/threads
- description: Create a new thread post with reply control
  method: POST
  name: create-thread
  path: /v1/threads
- description: Publish a created thread media container
  method: POST
  name: publish-thread
  path: /v1/publish
- description: Get account analytics and metrics
  method: GET
  name: get-account-insights
  path: /v1/insights
- description: Get all user replies
  method: GET
  name: list-replies
  path: /v1/replies
- description: Check publishing quota and rate limits
  method: GET
  name: get-publishing-limit
  path: /v1/publishing-limit
personas: []
provider_name: Threads
provider_slug: threads-api
search_terms:
- meta
- create a new thread post with reply control
- publish thread
- social
- account-level insights
- list replies
- get publishing limit
- social networks
- get all user threads with pagination
- analytics
- get all user's reply posts on threads
- create a new threads post with text, image, or video and reply controls
- get profile
- get threads user profile information including username and biography
- publish a created threads media container
- check publishing quota and rate limits
- publishing
- get all user's threads posts with pagination support
- get threads user profile information
- get account insights
- user reply posts
- list threads
- media
- create thread
- thread posts listing
- get threads account analytics including views, likes, replies, and followers
- get account analytics and metrics
- publish thread containers
- publish a created thread media container
- get all user replies
- publishing quota
- content management
- user profile information
- check publishing quota and rate limit status
slug: social-publishing
source_filename: social-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Threads Social Publishing\"\n  description: >-\n    Unified social publishing capability for the Threads platform combining\n    content publishing, reply management, engagement analytics, and account\n    insights. Used by creators, brands, and social media managers to manage\n    Threads presence at scale.\n  tags:\n    - Social Networks\n    - Publishing\n    - Analytics\n    - Media\n    - Meta\n    - Content Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      THREADS_ACCESS_TOKEN: THREADS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: threads\n      location: ./shared/threads-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: social-publishing-api\n      description: \"Unified REST API for Threads social publishing and management.\"\n      resources:\n        - path: /v1/profile\n          name: profile\n          description:\
  \ User profile information\n          operations:\n            - method: GET\n              name: get-profile\n              description: Get Threads user profile information\n              call: \"threads.get-profile\"\n              with:\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/threads\n          name: threads\n          description: Thread posts listing\n          operations:\n            - method: GET\n              name: list-threads\n              description: Get all user threads with pagination\n              call: \"threads.list-threads\"\n              with:\n                fields: \"rest.fields\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-thread\n              description: Create a new thread post with reply\
  \ control\n              call: \"threads.control-who-can-reply\"\n              with:\n                media_type: \"rest.media_type\"\n                text: \"rest.text\"\n                reply_control: \"rest.reply_control\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/publish\n          name: publish\n          description: Publish thread containers\n          operations:\n            - method: POST\n              name: publish-thread\n              description: Publish a created thread media container\n              call: \"threads.publish-thread\"\n              with:\n                creation_id: \"rest.creation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/insights\n          name: account-insights\n          description: Account-level insights\n          operations:\n            - method: GET\n              name: get-account-insights\n\
  \              description: Get account analytics and metrics\n              call: \"threads.get-account-insights\"\n              with:\n                metric: \"rest.metric\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/replies\n          name: replies\n          description: User reply posts\n          operations:\n            - method: GET\n              name: list-replies\n              description: Get all user replies\n              call: \"threads.list-replies\"\n              with:\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/publishing-limit\n          name: publishing-limit\n          description: Publishing quota\n          operations:\n            - method: GET\n              name: get-publishing-limit\n              description: Check publishing quota and rate limits\n            \
  \  call: \"threads.get-publishing-limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: social-publishing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Threads content management and analytics.\"\n      tools:\n        - name: get-profile\n          description: Get Threads user profile information including username and biography\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threads.get-profile\"\n          with:\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-threads\n          description: Get all user's Threads posts with pagination support\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threads.list-threads\"\n          with:\n            fields: \"tools.fields\"\
  \n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-thread\n          description: Create a new Threads post with text, image, or video and reply controls\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"threads.control-who-can-reply\"\n          with:\n            media_type: \"tools.media_type\"\n            text: \"tools.text\"\n            reply_control: \"tools.reply_control\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-thread\n          description: Publish a created Threads media container\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"threads.publish-thread\"\n          with:\n            creation_id: \"tools.creation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: get-account-insights\n          description: Get Threads account analytics including views, likes, replies, and followers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threads.get-account-insights\"\n          with:\n            metric: \"tools.metric\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-replies\n          description: Get all user's reply posts on Threads\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threads.list-replies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-publishing-limit\n          description: Check publishing quota and rate limit status\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threads.get-publishing-limit\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/threads-api/refs/heads/main/capabilities/social-publishing.yaml
tags:
- Social Networks
- Publishing
- Analytics
- Media
- Meta
- Content Management
tools:
- description: Get Threads user profile information including username and biography
  hints:
    openWorld: true
    readOnly: true
  name: get-profile
- description: Get all user's Threads posts with pagination support
  hints:
    openWorld: true
    readOnly: true
  name: list-threads
- description: Create a new Threads post with text, image, or video and reply controls
  hints:
    destructive: false
    readOnly: false
  name: create-thread
- description: Publish a created Threads media container
  hints:
    destructive: false
    readOnly: false
  name: publish-thread
- description: Get Threads account analytics including views, likes, replies, and followers
  hints:
    openWorld: true
    readOnly: true
  name: get-account-insights
- description: Get all user's reply posts on Threads
  hints:
    openWorld: true
    readOnly: true
  name: list-replies
- description: Check publishing quota and rate limit status
  hints:
    openWorld: true
    readOnly: true
  name: get-publishing-limit
---
