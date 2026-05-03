---
categories: []
consumed_apis:
- reuters
description: Unified workflow capability for accessing and searching Reuters editorial content through the Reuters Connect API. Enables media publishers, news aggregators, and content platforms to discover channels, browse items, retrieve full content with renditions, and search across the Reuters corpus.
layout: capability
name: Reuters Content Delivery
operations:
- description: List available Reuters content channels, optionally filtered by category.
  method: GET
  name: list-channels
  path: /v1/channels
- description: List the most recent items from a Reuters channel.
  method: GET
  name: list-items
  path: /v1/items
- description: Retrieve the full details and renditions of a content item.
  method: GET
  name: get-item
  path: /v1/items/{id}
- description: Search Reuters content by keyword, channel, and media type.
  method: GET
  name: search-items
  path: /v1/search
personas: []
provider_name: Reuters
provider_slug: reuters
search_terms:
- retrieve the full content of a reuters item including body, byline, subjects, and available media renditions.
- list the most recent editorial items from a reuters content channel.
- business
- journalism
- list channels
- discover and browse reuters content channels.
- search
- media
- retrieve specific reuters content items.
- retrieve the full details and renditions of a content item.
- 'list available reuters content channels. filter by category: txt (text), pix (images), vid (video), gfx (graphics).'
- search reuters content by keyword, channel, and media type.
- finance
- wire service
- news
- list items
- list available reuters content channels, optionally filtered by category.
- search reuters editorial content.
- content delivery
- search reuters editorial content by keyword. supports field-specific queries like headline:election or body:markets.
- get item
- browse content items from reuters channels.
- reuters
- list the most recent items from a reuters channel.
- search items
slug: content-delivery
source_filename: content-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Reuters Content Delivery\"\n  description: >-\n    Unified workflow capability for accessing and searching Reuters editorial\n    content through the Reuters Connect API. Enables media publishers, news\n    aggregators, and content platforms to discover channels, browse items,\n    retrieve full content with renditions, and search across the Reuters corpus.\n  tags:\n    - Reuters\n    - News\n    - Content Delivery\n    - Media\n    - Search\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REUTERS_TOKEN: REUTERS_TOKEN\n\ncapability:\n  consumes:\n    - import: reuters\n      location: ./shared/reuters-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: reuters-content-api\n      description: \"Unified REST API for Reuters content discovery and delivery.\"\n      resources:\n        - path: /v1/channels\n          name: channels\n          description:\
  \ \"Discover and browse Reuters content channels.\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List available Reuters content channels, optionally filtered by category.\"\n              call: \"reuters.list-channels\"\n              with:\n                channelCategory: \"rest.channelCategory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items\n          name: items\n          description: \"Browse content items from Reuters channels.\"\n          operations:\n            - method: GET\n              name: list-items\n              description: \"List the most recent items from a Reuters channel.\"\n              call: \"reuters.list-items\"\n              with:\n                channel: \"rest.channel\"\n                limit: \"rest.limit\"\n                mediaType: \"rest.mediaType\"\n              outputParameters:\n              \
  \  - type: object\n                  mapping: \"$.\"\n        - path: /v1/items/{id}\n          name: item-by-id\n          description: \"Retrieve specific Reuters content items.\"\n          operations:\n            - method: GET\n              name: get-item\n              description: \"Retrieve the full details and renditions of a content item.\"\n              call: \"reuters.get-item\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Search Reuters editorial content.\"\n          operations:\n            - method: GET\n              name: search-items\n              description: \"Search Reuters content by keyword, channel, and media type.\"\n              call: \"reuters.search-items\"\n              with:\n                q: \"rest.q\"\n                channel: \"rest.channel\"\n                limit:\
  \ \"rest.limit\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: reuters-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Reuters content discovery and retrieval.\"\n      tools:\n        - name: list-channels\n          description: \"List available Reuters content channels. Filter by category: TXT (text), PIX (images), VID (video), GFX (graphics).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reuters.list-channels\"\n          with:\n            channelCategory: \"tools.channelCategory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-items\n          description: \"List the most recent editorial items from a Reuters content channel.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"reuters.list-items\"\n          with:\n            channel: \"tools.channel\"\n            limit: \"tools.limit\"\n            mediaType: \"tools.mediaType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-item\n          description: \"Retrieve the full content of a Reuters item including body, byline, subjects, and available media renditions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reuters.get-item\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-items\n          description: \"Search Reuters editorial content by keyword. Supports field-specific queries like headline:election or body:markets.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reuters.search-items\"\n          with:\n     \
  \       q: \"tools.q\"\n            channel: \"tools.channel\"\n            limit: \"tools.limit\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reuters/refs/heads/main/capabilities/content-delivery.yaml
tags:
- Reuters
- News
- Content Delivery
- Media
- Search
tools:
- description: 'List available Reuters content channels. Filter by category: TXT (text), PIX (images), VID (video), GFX (graphics).'
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: List the most recent editorial items from a Reuters content channel.
  hints:
    openWorld: true
    readOnly: true
  name: list-items
- description: Retrieve the full content of a Reuters item including body, byline, subjects, and available media renditions.
  hints:
    openWorld: true
    readOnly: true
  name: get-item
- description: Search Reuters editorial content by keyword. Supports field-specific queries like headline:election or body:markets.
  hints:
    openWorld: true
    readOnly: true
  name: search-items
---
