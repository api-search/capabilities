---
categories: []
consumed_apis: []
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
- analytics
- check publishing quota and rate limit status
- get all user's threads posts with pagination support
- publishing
- publish thread
- publish thread containers
- publish a created thread media container
- meta
- create thread
- account-level insights
- list threads
- social networks
- create a new threads post with text, image, or video and reply controls
- publishing quota
- get all user threads with pagination
- create a new thread post with reply control
- list replies
- check publishing quota and rate limits
- publish a created threads media container
- user profile information
- get profile
- thread posts listing
- get account analytics and metrics
- media
- content management
- get account insights
- social
- get threads account analytics including views, likes, replies, and followers
- user reply posts
- get all user's reply posts on threads
- get threads user profile information
- get threads user profile information including username and biography
- get all user replies
- get publishing limit
slug: social-publishing
source_filename: social-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Threads Social Publishing\n  description: Unified social publishing capability for the Threads platform combining content publishing, reply management,\n    engagement analytics, and account insights. Used by creators, brands, and social media managers to manage Threads presence\n    at scale.\n  tags:\n  - Social Networks\n  - Publishing\n  - Analytics\n  - Media\n  - Meta\n  - Content Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THREADS_ACCESS_TOKEN: THREADS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: threads\n    baseUri: https://graph.threads.net\n    description: Meta Threads API\n    authentication:\n      type: bearer\n      token: '{{THREADS_ACCESS_TOKEN}}'\n    resources:\n    - name: authorization\n      path: /oauth\n      description: OAuth authorization endpoints\n      operations:\n      - name: exchange-code-for-token\n        method: POST\n\
  \        description: Exchange authorization code for short-lived access token\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: Threads App ID\n        - name: client_secret\n          in: query\n          type: string\n          required: true\n          description: Threads App secret\n        - name: code\n          in: query\n          type: string\n          required: true\n          description: Authorization code\n        - name: grant_type\n          in: query\n          type: string\n          required: true\n          description: Must be authorization_code\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: Redirect URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-long-lived-access-token\n        method: GET\n\
  \        description: Exchange short-lived token for long-lived access token\n        inputParameters:\n        - name: grant_type\n          in: query\n          type: string\n          required: true\n          description: Must be th_exchange_token\n        - name: client_secret\n          in: query\n          type: string\n          required: true\n          description: App secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile\n      path: /me\n      description: User profile operations\n      operations:\n      - name: get-profile\n        method: GET\n        description: Get Threads user profile information\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: threads\n      path: /me/threads\n      description: User thread posts\n      operations:\n      - name: list-threads\n        method: GET\n        description: Get paginated list of all user threads\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: control-who-can-reply\n        method: POST\n        description: Create a post with reply control settings\n        inputParameters:\n        - name: media_type\n          in: query\n          type: string\n          required: true\n          description: Media type of the post\n\
  \        - name: text\n          in: query\n          type: string\n          required: false\n          description: Post text\n        - name: reply_control\n          in: query\n          type: string\n          required: false\n          description: Who can reply (everyone, accounts_you_follow, mentioned_only)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publish\n      path: /me/threads_publish\n      description: Publish thread posts\n      operations:\n      - name: publish-thread\n        method: POST\n        description: Publish a Threads media container\n        inputParameters:\n        - name: creation_id\n          in: query\n          type: string\n          required: true\n          description: Container ID to publish\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path:\
  \ /me/threads_insights\n      description: Account-level insights\n      operations:\n      - name: get-account-insights\n        method: GET\n        description: Get account-level insights and analytics\n        inputParameters:\n        - name: metric\n          in: query\n          type: string\n          required: true\n          description: Metrics to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: replies\n      path: /me/replies\n      description: User replies\n      operations:\n      - name: list-replies\n        method: GET\n        description: Get paginated list of user's replies\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: publishing-limit\n      path: /me/threads_publishing_limit\n      description: Publishing quota\n      operations:\n      - name: get-publishing-limit\n        method: GET\n        description: Check user publishing quota limit\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: social-publishing-api\n    description: Unified REST API for Threads social publishing and management.\n    resources:\n    - path: /v1/profile\n      name: profile\n      description: User profile information\n      operations:\n      - method: GET\n        name: get-profile\n        description: Get Threads user profile information\n        call: threads.get-profile\n        with:\n          fields: rest.fields\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/threads\n      name: threads\n      description: Thread posts listing\n      operations:\n      - method: GET\n        name: list-threads\n        description: Get all user threads with pagination\n        call: threads.list-threads\n        with:\n          fields: rest.fields\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-thread\n        description: Create a new thread post with reply control\n        call: threads.control-who-can-reply\n        with:\n          media_type: rest.media_type\n          text: rest.text\n          reply_control: rest.reply_control\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/publish\n      name: publish\n      description: Publish thread containers\n      operations:\n      - method: POST\n        name: publish-thread\n\
  \        description: Publish a created thread media container\n        call: threads.publish-thread\n        with:\n          creation_id: rest.creation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights\n      name: account-insights\n      description: Account-level insights\n      operations:\n      - method: GET\n        name: get-account-insights\n        description: Get account analytics and metrics\n        call: threads.get-account-insights\n        with:\n          metric: rest.metric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/replies\n      name: replies\n      description: User reply posts\n      operations:\n      - method: GET\n        name: list-replies\n        description: Get all user replies\n        call: threads.list-replies\n        with:\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/publishing-limit\n\
  \      name: publishing-limit\n      description: Publishing quota\n      operations:\n      - method: GET\n        name: get-publishing-limit\n        description: Check publishing quota and rate limits\n        call: threads.get-publishing-limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: social-publishing-mcp\n    transport: http\n    description: MCP server for AI-assisted Threads content management and analytics.\n    tools:\n    - name: get-profile\n      description: Get Threads user profile information including username and biography\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threads.get-profile\n      with:\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-threads\n      description: Get all user's Threads posts with pagination support\n      hints:\n        readOnly: true\n        openWorld: true\n   \
  \   call: threads.list-threads\n      with:\n        fields: tools.fields\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-thread\n      description: Create a new Threads post with text, image, or video and reply controls\n      hints:\n        readOnly: false\n        destructive: false\n      call: threads.control-who-can-reply\n      with:\n        media_type: tools.media_type\n        text: tools.text\n        reply_control: tools.reply_control\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-thread\n      description: Publish a created Threads media container\n      hints:\n        readOnly: false\n        destructive: false\n      call: threads.publish-thread\n      with:\n        creation_id: tools.creation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-insights\n      description: Get Threads account analytics including views,\
  \ likes, replies, and followers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threads.get-account-insights\n      with:\n        metric: tools.metric\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-replies\n      description: Get all user's reply posts on Threads\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threads.list-replies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-publishing-limit\n      description: Check publishing quota and rate limit status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threads.get-publishing-limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
