---
categories: []
consumed_apis: []
description: Workflow capability for academic and institutional research on TikTok public data. Uses the Research API to query videos, analyze user profiles, examine comment threads, and map social networks. Designed for data scientists, academic researchers, and policy analysts.
layout: capability
name: TikTok Social Research
operations:
- description: Query TikTok videos with boolean filters
  method: POST
  name: query-research-videos
  path: /v1/research/videos
- description: Get public user account information
  method: GET
  name: query-research-user-info
  path: /v1/research/users/{username}
- description: Get all comments on a TikTok video
  method: GET
  name: list-video-comments
  path: /v1/research/videos/{video_id}/comments
- description: List followers of a TikTok user
  method: GET
  name: list-user-followers
  path: /v1/research/users/{username}/followers
- description: List accounts a user follows
  method: GET
  name: list-user-following
  path: /v1/research/users/{username}/following
- description: List videos liked by a user
  method: GET
  name: list-user-liked-videos
  path: /v1/research/users/{username}/liked-videos
- description: List videos pinned by a user
  method: GET
  name: list-user-pinned-videos
  path: /v1/research/users/{username}/pinned-videos
- description: List videos reposted by a user
  method: GET
  name: list-user-reposted-videos
  path: /v1/research/users/{username}/reposted-videos
personas: []
provider_name: TikTok for Developers
provider_slug: tiktok-for-developers
search_terms:
- analytics
- social media
- video
- videos liked by a user
- authentication
- list user liked videos
- research user profile data
- list user reposted videos
- list followers of a tiktok user for social network analysis
- list videos liked by a tiktok user for engagement research
- query research videos
- query research user info
- research
- query tiktok videos with boolean filters
- query and analyze tiktok video data
- content
- list accounts a tiktok user follows for network mapping
- list videos liked by a user
- get public user account information
- list accounts a user follows
- data science
- list videos pinned by a user
- get public tiktok account information by username for research
- retrieve all comments on a tiktok video for sentiment analysis
- user following social graph
- user follower social graph
- videos pinned by a user
- video comment data
- list videos reposted by a tiktok user for sharing behavior analysis
- list followers of a tiktok user
- list user pinned videos
- videos reposted by a user
- list user followers
- tiktok
- list user following
- query tiktok public videos using boolean filters for research analysis
- list videos reposted by a user
- list video comments
- get all comments on a tiktok video
- advertising
- list videos pinned by a tiktok user
slug: social-research
source_filename: social-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TikTok Social Research\n  description: Workflow capability for academic and institutional research on TikTok public data. Uses the Research API to\n    query videos, analyze user profiles, examine comment threads, and map social networks. Designed for data scientists, academic\n    researchers, and policy analysts.\n  tags:\n  - TikTok\n  - Research\n  - Analytics\n  - Social Media\n  - Data Science\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIKTOK_RESEARCH_ACCESS_TOKEN: TIKTOK_RESEARCH_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tiktok-research\n    baseUri: https://open.tiktokapis.com\n    description: TikTok Research API for academic data access\n    authentication:\n      type: bearer\n      token: '{{TIKTOK_RESEARCH_ACCESS_TOKEN}}'\n    resources:\n    - name: research-videos\n      path: /v2/research/video\n      description: Research video data\n      operations:\n\
  \      - name: query-research-videos\n        method: POST\n        description: Query TikTok videos using boolean filters\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            start_date: '{{tools.start_date}}'\n            end_date: '{{tools.end_date}}'\n            max_count: '{{tools.max_count}}'\n            cursor: '{{tools.cursor}}'\n      - name: list-video-comments\n        method: POST\n        description: Retrieve all comments on a specific video\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n        body:\n          type: json\n          data:\n            video_id: '{{tools.video_id}}'\n            max_count: '{{tools.max_count}}'\n      - name: list-user-liked-videos\n        method: POST\n        description: Retrieve videos liked by a user\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            max_count: '{{tools.max_count}}'\n      - name: list-user-pinned-videos\n        method: POST\n        description: Retrieve videos pinned by a user\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            max_count: '{{tools.max_count}}'\n      - name: list-user-reposted-videos\n        method: POST\n        description: Retrieve videos reposted by a user\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            max_count: '{{tools.max_count}}'\n    - name: research-users\n      path: /v2/research/user\n      description: Research user data\n      operations:\n      - name: query-research-user-info\n        method: POST\n        description: Retrieve public TikTok account information by handle\n        inputParameters:\n        - name: fields\n          in: query\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n      - name: list-user-followers\n        method: POST\n        description: Retrieve follower list for a user\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            max_count: '{{tools.max_count}}'\n      - name: list-user-following\n        method: POST\n        description: Retrieve following list for a user\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n         \
  \ required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            max_count: '{{tools.max_count}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: tiktok-social-research-api\n    description: Unified REST API for TikTok social research workflows.\n    resources:\n    - path: /v1/research/videos\n      name: research-videos\n      description: Query and analyze TikTok video data\n      operations:\n      - method: POST\n        name: query-research-videos\n        description: Query TikTok videos with boolean filters\n        call: tiktok-research.query-research-videos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}\n      name: research-users\n      description: Research user profile data\n      operations:\n      - method:\
  \ GET\n        name: query-research-user-info\n        description: Get public user account information\n        call: tiktok-research.query-research-user-info\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/videos/{video_id}/comments\n      name: video-comments\n      description: Video comment data\n      operations:\n      - method: GET\n        name: list-video-comments\n        description: Get all comments on a TikTok video\n        call: tiktok-research.list-video-comments\n        with:\n          video_id: rest.video_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}/followers\n      name: user-followers\n      description: User follower social graph\n      operations:\n      - method: GET\n        name: list-user-followers\n        description: List followers of a TikTok user\n        call: tiktok-research.list-user-followers\n\
  \        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}/following\n      name: user-following\n      description: User following social graph\n      operations:\n      - method: GET\n        name: list-user-following\n        description: List accounts a user follows\n        call: tiktok-research.list-user-following\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}/liked-videos\n      name: liked-videos\n      description: Videos liked by a user\n      operations:\n      - method: GET\n        name: list-user-liked-videos\n        description: List videos liked by a user\n        call: tiktok-research.list-user-liked-videos\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}/pinned-videos\n\
  \      name: pinned-videos\n      description: Videos pinned by a user\n      operations:\n      - method: GET\n        name: list-user-pinned-videos\n        description: List videos pinned by a user\n        call: tiktok-research.list-user-pinned-videos\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/users/{username}/reposted-videos\n      name: reposted-videos\n      description: Videos reposted by a user\n      operations:\n      - method: GET\n        name: list-user-reposted-videos\n        description: List videos reposted by a user\n        call: tiktok-research.list-user-reposted-videos\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: tiktok-social-research-mcp\n    transport: http\n    description: MCP server for AI-assisted TikTok social research and analysis.\n\
  \    tools:\n    - name: query-research-videos\n      description: Query TikTok public videos using boolean filters for research analysis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.query-research-videos\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-research-user-info\n      description: Get public TikTok account information by username for research\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.query-research-user-info\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-video-comments\n      description: Retrieve all comments on a TikTok video for sentiment analysis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-video-comments\n      with:\n        video_id: tools.video_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-user-followers\n      description: List followers of a TikTok user for social network analysis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-user-followers\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-following\n      description: List accounts a TikTok user follows for network mapping\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-user-following\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-liked-videos\n      description: List videos liked by a TikTok user for engagement research\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-user-liked-videos\n      with:\n        username: tools.username\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-user-pinned-videos\n      description: List videos pinned by a TikTok user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-user-pinned-videos\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-reposted-videos\n      description: List videos reposted by a TikTok user for sharing behavior analysis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-research.list-user-reposted-videos\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tiktok-for-developers/refs/heads/main/capabilities/social-research.yaml
tags:
- TikTok
- Research
- Analytics
- Social Media
- Data Science
tools:
- description: Query TikTok public videos using boolean filters for research analysis
  hints:
    idempotent: true
    readOnly: true
  name: query-research-videos
- description: Get public TikTok account information by username for research
  hints:
    idempotent: true
    readOnly: true
  name: query-research-user-info
- description: Retrieve all comments on a TikTok video for sentiment analysis
  hints:
    idempotent: true
    readOnly: true
  name: list-video-comments
- description: List followers of a TikTok user for social network analysis
  hints:
    idempotent: true
    readOnly: true
  name: list-user-followers
- description: List accounts a TikTok user follows for network mapping
  hints:
    idempotent: true
    readOnly: true
  name: list-user-following
- description: List videos liked by a TikTok user for engagement research
  hints:
    idempotent: true
    readOnly: true
  name: list-user-liked-videos
- description: List videos pinned by a TikTok user
  hints:
    idempotent: true
    readOnly: true
  name: list-user-pinned-videos
- description: List videos reposted by a TikTok user for sharing behavior analysis
  hints:
    idempotent: true
    readOnly: true
  name: list-user-reposted-videos
---
