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
- facebook post management.
- get facebook feed
- manage advertising campaigns and performance.
- manage content across facebook, instagram, and threads.
- Customer Support
- manages day-to-day ad campaign optimization.
- publish instagram media
- customer messaging across messenger and whatsapp.
- social networking
- get threads insights
- get threads performance insights.
- plans and executes advertising campaigns.
- Conversational Commerce
- publishing
- list instagram media
- campaign management and audience targeting.
- create facebook post
- list posts
- direct messaging and customer communication.
- create a threads post.
- create threads post
- get instagram performance insights.
- content management
- create a new facebook post.
- Social Media Manager
- publishing and managing content across platforms.
- instagram content management.
- Ad Operations
- list instagram media for an account.
- create a new threads post.
- messaging
- facebook
- create and publish instagram content.
- advertising
- get posts from a facebook user's feed.
- Marketing Manager
- create instagram media
- creates and publishes visual and text content.
- Content Creator
- get posts from a user's feed.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
- social media
- publish instagram media.
- manages content and engagement across meta platforms.
- create post
- threads content management.
- get instagram insights
- content publishing
- list instagram media.
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
