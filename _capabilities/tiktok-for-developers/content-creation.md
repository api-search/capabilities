---
categories: []
consumed_apis: []
description: 'Unified workflow capability for creating and publishing content on TikTok. Combines the Display API and Content Posting API to support the full content lifecycle: discovering user profile settings, initiating video uploads, and monitoring publish status. Designed for app developers, content management platforms, and media tools.'
layout: capability
name: TikTok Content Creation
operations:
- description: Get authenticated user's TikTok profile
  method: GET
  name: get-user-info
  path: /v1/users/me
- description: List user's recent TikTok videos
  method: GET
  name: list-videos
  path: /v1/videos
- description: Query TikTok video metadata by video IDs
  method: POST
  name: query-videos
  path: /v1/videos/query
- description: Get creator's content posting settings
  method: GET
  name: query-creator-info
  path: /v1/posts/creator-info
- description: Initiate a TikTok video upload or direct post
  method: POST
  name: init-video-publish
  path: /v1/posts/init
- description: Check the status of a video publish job
  method: POST
  name: get-publish-status
  path: /v1/posts/status
personas: []
provider_name: TikTok for Developers
provider_slug: tiktok-for-developers
search_terms:
- analytics
- social media
- get publish status
- video
- current user profile
- init video publish
- check the current status of a tiktok video publish job
- initiate a tiktok video upload or direct post to a user's account
- query tiktok video metadata by video ids
- initiate a tiktok video upload or direct post
- publishing
- query videos
- authentication
- get creator's content posting settings
- get authenticated user's tiktok profile
- list user's recent tiktok videos
- query tiktok video metadata by specific video ids
- get user info
- creator posting configuration
- check the status of a video publish job
- query creator info
- content
- video publish status
- initiate video post
- get tiktok creator's content posting settings and permissions
- retrieve authenticated user's tiktok profile information
- list videos
- list a user's most recent tiktok videos
- query specific videos by id
- content creation
- tiktok
- user video listings
- advertising
slug: content-creation
source_filename: content-creation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TikTok Content Creation\n  description: 'Unified workflow capability for creating and publishing content on TikTok. Combines the Display API and Content\n    Posting API to support the full content lifecycle: discovering user profile settings, initiating video uploads, and monitoring\n    publish status. Designed for app developers, content management platforms, and media tools.'\n  tags:\n  - TikTok\n  - Content Creation\n  - Publishing\n  - Social Media\n  - Video\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIKTOK_ACCESS_TOKEN: TIKTOK_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tiktok-display\n    baseUri: https://open.tiktokapis.com\n    description: TikTok Display API for accessing user profiles and video metadata\n    authentication:\n      type: bearer\n      token: '{{TIKTOK_ACCESS_TOKEN}}'\n    resources:\n    - name: user\n      path: /v2/user\n      description:\
  \ TikTok user profile operations\n      operations:\n      - name: get-user-info\n        method: GET\n        description: Retrieve a TikTok user's basic profile information\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video\n      path: /v2/video\n      description: TikTok video metadata operations\n      operations:\n      - name: list-videos\n        method: POST\n        description: Retrieve a paginated list of user's most recent public videos\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            max_count: '{{tools.max_count}}'\n            cursor: '{{tools.cursor}}'\n      - name: query-videos\n        method: POST\n        description: Retrieve metadata for specific videos by ID\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filters:\n              video_ids: '{{tools.video_ids}}'\n  - type: http\n    namespace: tiktok-posting\n    baseUri: https://open.tiktokapis.com\n    description: TikTok Content Posting API for publishing video content\n    authentication:\n      type: bearer\n      token: '{{TIKTOK_ACCESS_TOKEN}}'\n    resources:\n    - name: post\n      path: /v2/post/publish\n      description:\
  \ Video publish operations\n      operations:\n      - name: init-video-publish\n        method: POST\n        description: Initiate a video upload or direct post to TikTok\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            source_info:\n              source: '{{tools.source}}'\n              video_url: '{{tools.video_url}}'\n              chunk_size: '{{tools.chunk_size}}'\n              total_chunk_count: '{{tools.total_chunk_count}}'\n            post_info:\n              title: '{{tools.title}}'\n              privacy_level: '{{tools.privacy_level}}'\n              disable_duet: '{{tools.disable_duet}}'\n              disable_comment: '{{tools.disable_comment}}'\n              disable_stitch: '{{tools.disable_stitch}}'\n      - name: get-publish-status\n        method: POST\n        description: Poll the status of a video publish job\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            publish_id: '{{tools.publish_id}}'\n      - name: query-creator-info\n        method: POST\n        description: Retrieve creator content posting settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tiktok-content-creation-api\n    description: Unified REST API for TikTok content creation workflows.\n    resources:\n    - path: /v1/users/me\n      name: current-user\n      description: Current user profile\n      operations:\n      - method: GET\n        name: get-user-info\n        description: Get authenticated user's TikTok profile\n        call: tiktok-display.get-user-info\n        with:\n          fields: rest.fields\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/videos\n      name: videos\n      description: User video listings\n      operations:\n      - method: GET\n        name: list-videos\n        description: List user's recent TikTok videos\n        call: tiktok-display.list-videos\n        with:\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/videos/query\n      name: video-query\n      description: Query specific videos by ID\n      operations:\n      - method: POST\n        name: query-videos\n        description: Query TikTok video metadata by video IDs\n        call: tiktok-display.query-videos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts/creator-info\n      name: creator-info\n      description: Creator posting configuration\n      operations:\n      - method: GET\n        name: query-creator-info\n        description: Get creator's content posting settings\n\
  \        call: tiktok-posting.query-creator-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts/init\n      name: post-init\n      description: Initiate video post\n      operations:\n      - method: POST\n        name: init-video-publish\n        description: Initiate a TikTok video upload or direct post\n        call: tiktok-posting.init-video-publish\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts/status\n      name: post-status\n      description: Video publish status\n      operations:\n      - method: POST\n        name: get-publish-status\n        description: Check the status of a video publish job\n        call: tiktok-posting.get-publish-status\n        with:\n          publish_id: rest.publish_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tiktok-content-creation-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted TikTok content creation.\n    tools:\n    - name: get-user-info\n      description: Retrieve authenticated user's TikTok profile information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-display.get-user-info\n      with:\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-videos\n      description: List a user's most recent TikTok videos\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-display.list-videos\n      with:\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-videos\n      description: Query TikTok video metadata by specific video IDs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-display.query-videos\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-creator-info\n      description:\
  \ Get TikTok creator's content posting settings and permissions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-posting.query-creator-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: init-video-publish\n      description: Initiate a TikTok video upload or direct post to a user's account\n      hints:\n        readOnly: false\n        destructive: false\n      call: tiktok-posting.init-video-publish\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-publish-status\n      description: Check the current status of a TikTok video publish job\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-posting.get-publish-status\n      with:\n        publish_id: tools.publish_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tiktok-for-developers/refs/heads/main/capabilities/content-creation.yaml
tags:
- TikTok
- Content Creation
- Publishing
- Social Media
- Video
tools:
- description: Retrieve authenticated user's TikTok profile information
  hints:
    idempotent: true
    readOnly: true
  name: get-user-info
- description: List a user's most recent TikTok videos
  hints:
    idempotent: true
    readOnly: true
  name: list-videos
- description: Query TikTok video metadata by specific video IDs
  hints:
    idempotent: true
    readOnly: true
  name: query-videos
- description: Get TikTok creator's content posting settings and permissions
  hints:
    idempotent: true
    readOnly: true
  name: query-creator-info
- description: Initiate a TikTok video upload or direct post to a user's account
  hints:
    destructive: false
    readOnly: false
  name: init-video-publish
- description: Check the current status of a TikTok video publish job
  hints:
    idempotent: true
    readOnly: true
  name: get-publish-status
---
