---
categories:
- content-management
consumed_apis: []
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
- social media
- manages day-to-day ad campaign optimization.
- Conversational Commerce
- create a new threads post.
- Customer Support
- performance tracking and insights.
- Ad Operations
- Content Creator
- facebook post management.
- publishing
- publishing and managing content across platforms.
- create facebook post
- create a new facebook post.
- manage content across facebook, instagram, and threads.
- list instagram media for an account.
- manages content and engagement across meta platforms.
- create post
- list instagram media
- threads content management.
- create a threads post.
- get instagram performance insights.
- publish instagram media
- get threads performance insights.
- social networking
- create instagram media
- direct messaging and customer communication.
- customer messaging across messenger and whatsapp.
- facebook
- Marketing Manager
- handles customer inquiries via messaging channels.
- Social Media Manager
- list posts
- instagram content management.
- plans and executes advertising campaigns.
- create threads post
- content management
- get instagram insights
- list instagram media.
- publish instagram media.
- get threads insights
- content publishing
- campaign management and audience targeting.
- get posts from a facebook user's feed.
- create and publish instagram content.
- get posts from a user's feed.
- manage advertising campaigns and performance.
- advertising
- messaging
- get facebook feed
- creates and publishes visual and text content.
slug: social-media-management
source_filename: social-media-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Facebook Social Media Management\n  description: Workflow capability for managing content across Facebook, Instagram, and Threads. Combines Graph API for Facebook\n    posts, Instagram API for visual content, and Threads API for text-based publishing. Used by social media managers and\n    content creators.\n  tags:\n  - Facebook\n  - Social Media\n  - Content Management\n  - Publishing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACEBOOK_ACCESS_TOKEN: FACEBOOK_ACCESS_TOKEN\n    INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n    THREADS_ACCESS_TOKEN: THREADS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: graph-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Facebook Graph API v21.0.\n    authentication:\n      type: bearer\n      token: '{{FACEBOOK_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /\n      description: User profile\
  \ operations.\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Get the current authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get a user by ID.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posts\n      path: /\n      description: Post operations.\n      operations:\n      - name: get-user-feed\n        method: GET\n        description: Get posts from a user's feed.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-post\n        method: POST\n        description: Create a new post.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-post\n        method: DELETE\n        description: Delete a post.\n        inputParameters:\n        - name: post_id\n          in: path\n          type: string\n          required: true\n          description: Post ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /\n      description: Comment operations.\n      operations:\n      - name: get-post-comments\n        method: GET\n        description: Get comments on a post.\n        inputParameters:\n        - name: post_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Post ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-comment\n        method: POST\n        description: Create a comment on a post.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: instagram-api\n    baseUri: https://graph.facebook.com/v21.0\n    description: Instagram API via Graph API v21.0.\n    authentication:\n      type: bearer\n      token: '{{INSTAGRAM_ACCESS_TOKEN}}'\n    resources:\n    - name: media\n      path: /\n      description: Media management.\n      operations:\n      - name: list-media\n        method: GET\n        description: List Instagram media.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-media\n        method: POST\n\
  \        description: Create an Instagram media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-media\n        method: POST\n        description: Publish a media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /\n      description: Account insights.\n      operations:\n      - name: get-insights\n        method: GET\n        description: Get Instagram account insights.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: threads-api\n    baseUri: https://graph.threads.net/v1.0\n    description: Threads API v1.0.\n    authentication:\n      type: bearer\n      token: '{{THREADS_ACCESS_TOKEN}}'\n    resources:\n    - name: publishing\n      path: /\n\
  \      description: Content publishing.\n      operations:\n      - name: create-media\n        method: POST\n        description: Create a Threads media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-media\n        method: POST\n        description: Publish a Threads media container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: replies\n      path: /\n      description: Reply management.\n      operations:\n      - name: get-replies\n        method: GET\n        description: Get replies to a Threads post.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /\n      description: Performance insights.\n      operations:\n      - name: get-insights\n        method: GET\n   \
  \     description: Get Threads insights.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: social-media-api\n    description: Unified REST API for social media management across Meta platforms.\n    resources:\n    - path: /v1/posts\n      name: posts\n      description: Facebook post management.\n      operations:\n      - method: GET\n        name: list-posts\n        description: Get posts from a user's feed.\n        call: graph-api.get-user-feed\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-post\n        description: Create a new Facebook post.\n        call: graph-api.create-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instagram-media\n      name: instagram-media\n      description: Instagram content management.\n      operations:\n\
  \      - method: GET\n        name: list-instagram-media\n        description: List Instagram media.\n        call: instagram-api.list-media\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: publish-instagram-media\n        description: Publish Instagram media.\n        call: instagram-api.publish-media\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/threads\n      name: threads\n      description: Threads content management.\n      operations:\n      - method: POST\n        name: create-threads-post\n        description: Create a Threads post.\n        call: threads-api.create-media\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: social-media-mcp\n    transport: http\n    description: MCP server for AI-assisted social media management.\n    tools:\n    - name: get-facebook-feed\n      description: Get posts from\
  \ a Facebook user's feed.\n      hints:\n        readOnly: true\n      call: graph-api.get-user-feed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-facebook-post\n      description: Create a new Facebook post.\n      hints:\n        readOnly: false\n      call: graph-api.create-post\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instagram-media\n      description: List Instagram media for an account.\n      hints:\n        readOnly: true\n      call: instagram-api.list-media\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-instagram-media\n      description: Create and publish Instagram content.\n      hints:\n        readOnly: false\n      call: instagram-api.create-media\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instagram-insights\n      description: Get Instagram performance insights.\n      hints:\n        readOnly: true\n\
  \      call: instagram-api.get-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-threads-post\n      description: Create a new Threads post.\n      hints:\n        readOnly: false\n      call: threads-api.create-media\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-threads-insights\n      description: Get Threads performance insights.\n      hints:\n        readOnly: true\n      call: threads-api.get-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
