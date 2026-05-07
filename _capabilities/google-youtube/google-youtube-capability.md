---
categories: []
consumed_apis: []
description: The YouTube Data API v3 lets you incorporate YouTube functionality into your own application. You can use the API to fetch search results, retrieve and manage video resources, manage channels and playlists, and access subscription and activity data.
layout: capability
name: YouTube Data API
operations:
- description: List videos
  method: GET
  name: listvideos
  path: /videos
- description: List channels
  method: GET
  name: listchannels
  path: /channels
- description: List playlists
  method: GET
  name: listplaylists
  path: /playlists
- description: Create a playlist
  method: POST
  name: insertplaylist
  path: /playlists
- description: List playlist items
  method: GET
  name: listplaylistitems
  path: /playlistItems
- description: Search for content
  method: GET
  name: search
  path: /search
- description: List subscriptions
  method: GET
  name: listsubscriptions
  path: /subscriptions
- description: List comment threads
  method: GET
  name: listcommentthreads
  path: /commentThreads
- description: List activities
  method: GET
  name: listactivities
  path: /activities
personas: []
provider_name: YouTube Data
provider_slug: google-youtube
search_terms:
- streaming
- video
- insertplaylist
- list channels
- api
- create a playlist
- channels
- youtube
- listsubscriptions
- list playlist items
- google
- list playlists
- listplaylists
- listactivities
- list comment threads
- list subscriptions
- listvideos
- listplaylistitems
- search for content
- list activities
- media
- playlists
- list videos
- search
- listchannels
- listcommentthreads
slug: google-youtube-capability
source_filename: google-youtube-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: YouTube Data API\n  description: The YouTube Data API v3 lets you incorporate YouTube functionality into your own application. You can use the\n    API to fetch search results, retrieve and manage video resources, manage channels and playlists, and access subscription\n    and activity data.\n  tags:\n  - Google\n  - Youtube\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-youtube\n    baseUri: https://youtube.googleapis.com/youtube/v3\n    description: YouTube Data API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_YOUTUBE_TOKEN}}'\n    resources:\n    - name: videos\n      path: /videos\n      operations:\n      - name: listvideos\n        method: GET\n        description: List videos\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: The part\
  \ parameter specifies a comma-separated list of one or more video resource properties.\n        - name: id\n          in: query\n          type: string\n          description: The id parameter specifies a comma-separated list of YouTube video IDs.\n        - name: maxResults\n          in: query\n          type: integer\n          description: The maximum number of items to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Identifies a specific page in the result set.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      operations:\n      - name: listchannels\n        method: GET\n        description: List channels\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: query\n          type: string\n        - name:\
  \ mine\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlists\n      path: /playlists\n      operations:\n      - name: listplaylists\n        method: GET\n        description: List playlists\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: channelId\n          in: query\n          type: string\n        - name: mine\n          in: query\n          type: boolean\n        - name: maxResults\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertplaylist\n        method: POST\n        description: Create a playlist\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlistitems\n      path: /playlistItems\n      operations:\n      - name: listplaylistitems\n        method: GET\n        description: List playlist items\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: playlistId\n          in: query\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: search\n        method: GET\n        description: Search for content\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: q\n\
  \          in: query\n          type: string\n          description: The search query term.\n        - name: type\n          in: query\n          type: string\n          description: Restricts a search to a particular type of resource.\n        - name: maxResults\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: List subscriptions\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: mine\n          in: query\n          type: boolean\n        - name: channelId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ commentthreads\n      path: /commentThreads\n      operations:\n      - name: listcommentthreads\n        method: GET\n        description: List comment threads\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: videoId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities\n      path: /activities\n      operations:\n      - name: listactivities\n        method: GET\n        description: List activities\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n        - name: channelId\n          in: query\n          type: string\n        - name: mine\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-youtube-rest\n    description: REST adapter for YouTube Data API.\n    resources:\n    - path: /videos\n      name: listvideos\n      operations:\n      - method: GET\n        name: listvideos\n        description: List videos\n        call: google-youtube.listvideos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /channels\n      name: listchannels\n      operations:\n      - method: GET\n        name: listchannels\n        description: List channels\n        call: google-youtube.listchannels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /playlists\n      name: listplaylists\n      operations:\n      - method: GET\n        name: listplaylists\n        description: List playlists\n        call: google-youtube.listplaylists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /playlists\n\
  \      name: insertplaylist\n      operations:\n      - method: POST\n        name: insertplaylist\n        description: Create a playlist\n        call: google-youtube.insertplaylist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /playlistItems\n      name: listplaylistitems\n      operations:\n      - method: GET\n        name: listplaylistitems\n        description: List playlist items\n        call: google-youtube.listplaylistitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: search\n      operations:\n      - method: GET\n        name: search\n        description: Search for content\n        call: google-youtube.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions\n      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: List subscriptions\n        call: google-youtube.listsubscriptions\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /commentThreads\n      name: listcommentthreads\n      operations:\n      - method: GET\n        name: listcommentthreads\n        description: List comment threads\n        call: google-youtube.listcommentthreads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities\n      name: listactivities\n      operations:\n      - method: GET\n        name: listactivities\n        description: List activities\n        call: google-youtube.listactivities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-youtube-mcp\n    transport: http\n    description: MCP adapter for YouTube Data API for AI agent use.\n    tools:\n    - name: listvideos\n      description: List videos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listvideos\n\
  \      with:\n        part: tools.part\n        id: tools.id\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: part\n        type: string\n        description: The part parameter specifies a comma-separated list of one or more video resource properties.\n        required: true\n      - name: id\n        type: string\n        description: The id parameter specifies a comma-separated list of YouTube video IDs.\n      - name: maxResults\n        type: integer\n        description: The maximum number of items to return.\n      - name: pageToken\n        type: string\n        description: Identifies a specific page in the result set.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchannels\n      description: List channels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listchannels\n      with:\n        part: tools.part\n\
  \        id: tools.id\n        mine: tools.mine\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name: id\n        type: string\n        description: id\n      - name: mine\n        type: boolean\n        description: mine\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listplaylists\n      description: List playlists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listplaylists\n      with:\n        part: tools.part\n        channelId: tools.channelId\n        mine: tools.mine\n        maxResults: tools.maxResults\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name: channelId\n        type: string\n        description: channelId\n      - name: mine\n        type: boolean\n        description: mine\n      - name: maxResults\n   \
  \     type: integer\n        description: maxResults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertplaylist\n      description: Create a playlist\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-youtube.insertplaylist\n      with:\n        part: tools.part\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listplaylistitems\n      description: List playlist items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listplaylistitems\n      with:\n        part: tools.part\n        playlistId: tools.playlistId\n        maxResults: tools.maxResults\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name:\
  \ playlistId\n        type: string\n        description: playlistId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Search for content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.search\n      with:\n        part: tools.part\n        q: tools.q\n        type: tools.type\n        maxResults: tools.maxResults\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name: q\n        type: string\n        description: The search query term.\n      - name: type\n        type: string\n        description: Restricts a search to a particular type of resource.\n      - name: maxResults\n        type: integer\n        description: maxResults\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listsubscriptions\n      description: List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listsubscriptions\n      with:\n        part: tools.part\n        mine: tools.mine\n        channelId: tools.channelId\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name: mine\n        type: boolean\n        description: mine\n      - name: channelId\n        type: string\n        description: channelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcommentthreads\n      description: List comment threads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listcommentthreads\n      with:\n        part: tools.part\n        videoId: tools.videoId\n      inputParameters:\n      - name: part\n       \
  \ type: string\n        description: part\n        required: true\n      - name: videoId\n        type: string\n        description: videoId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listactivities\n      description: List activities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-youtube.listactivities\n      with:\n        part: tools.part\n        channelId: tools.channelId\n        mine: tools.mine\n      inputParameters:\n      - name: part\n        type: string\n        description: part\n        required: true\n      - name: channelId\n        type: string\n        description: channelId\n      - name: mine\n        type: boolean\n        description: mine\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_YOUTUBE_TOKEN: GOOGLE_YOUTUBE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-youtube/refs/heads/main/capabilities/google-youtube-capability.yaml
tags:
- Google
- Youtube
- API
tools:
- description: List videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvideos
- description: List channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: List playlists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listplaylists
- description: Create a playlist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertplaylist
- description: List playlist items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listplaylistitems
- description: Search for content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search
- description: List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: List comment threads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcommentthreads
- description: List activities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivities
---
