---
categories: []
consumed_apis: []
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
- retrieve specific reuters content items.
- retrieve the full details and renditions of a content item.
- 'list available reuters content channels. filter by category: txt (text), pix (images), vid (video), gfx (graphics).'
- retrieve the full content of a reuters item including body, byline, subjects, and available media renditions.
- search reuters editorial content.
- list items
- list the most recent editorial items from a reuters content channel.
- finance
- discover and browse reuters content channels.
- search reuters content by keyword, channel, and media type.
- search reuters editorial content by keyword. supports field-specific queries like headline:election or body:markets.
- business
- reuters
- search items
- content delivery
- wire service
- news
- list the most recent items from a reuters channel.
- journalism
- search
- media
- list channels
- browse content items from reuters channels.
- list available reuters content channels, optionally filtered by category.
- get item
slug: content-delivery
source_filename: content-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reuters Content Delivery\n  description: Unified workflow capability for accessing and searching Reuters editorial content through the Reuters Connect\n    API. Enables media publishers, news aggregators, and content platforms to discover channels, browse items, retrieve full\n    content with renditions, and search across the Reuters corpus.\n  tags:\n  - Reuters\n  - News\n  - Content Delivery\n  - Media\n  - Search\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REUTERS_TOKEN: REUTERS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: reuters\n    baseUri: https://rmb.reuters.com/rmd/rest/xml\n    description: Reuters Connect content delivery and search API.\n    authentication:\n      type: apikey\n      key: token\n      value: '{{REUTERS_TOKEN}}'\n      placement: query\n    resources:\n    - name: channels\n      path: /channels\n      description: List available content channels\
  \ by category.\n      operations:\n      - name: list-channels\n        method: GET\n        description: List all content channels within the subscription.\n        inputParameters:\n        - name: channelCategory\n          in: query\n          type: string\n          required: false\n          description: 'Filter by category: TXT, PIX, VID, GFX, CMP.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /items\n      description: List content items from a specific channel.\n      operations:\n      - name: list-items\n        method: GET\n        description: List the most recent items on a content channel.\n        inputParameters:\n        - name: channel\n          in: query\n          type: string\n          required: true\n          description: Channel alias to retrieve items from.\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Maximum number of items to return.\n        - name: mediaType\n          in: query\n          type: string\n          required: false\n          description: 'Filter by media type: TEXT, PICTURE, VIDEO, GRAPHIC, COMPOSITE.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: item\n      path: /item\n      description: Retrieve a specific content item by ID.\n      operations:\n      - name: get-item\n        method: GET\n        description: Retrieve the full details of a specific content item.\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Search for\
  \ content items using keyword queries.\n      operations:\n      - name: search-items\n        method: GET\n        description: Search for content items matching specified criteria.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query (supports field:value syntax).\n        - name: channel\n          in: query\n          type: string\n          required: false\n          description: Restrict search to a specific channel.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: 'Sort order: date or relevance.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: reuters-content-api\n    description: Unified REST API for Reuters content discovery and delivery.\n    resources:\n    - path: /v1/channels\n      name: channels\n      description: Discover and browse Reuters content channels.\n      operations:\n      - method: GET\n        name: list-channels\n        description: List available Reuters content channels, optionally filtered by category.\n        call: reuters.list-channels\n        with:\n          channelCategory: rest.channelCategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: Browse content items from Reuters channels.\n      operations:\n      - method: GET\n        name: list-items\n        description: List the most recent items from a Reuters channel.\n        call: reuters.list-items\n        with:\n          channel: rest.channel\n          limit: rest.limit\n          mediaType: rest.mediaType\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/items/{id}\n      name: item-by-id\n      description: Retrieve specific Reuters content items.\n      operations:\n      - method: GET\n        name: get-item\n        description: Retrieve the full details and renditions of a content item.\n        call: reuters.get-item\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Search Reuters editorial content.\n      operations:\n      - method: GET\n        name: search-items\n        description: Search Reuters content by keyword, channel, and media type.\n        call: reuters.search-items\n        with:\n          q: rest.q\n          channel: rest.channel\n          limit: rest.limit\n          sort: rest.sort\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: reuters-content-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Reuters content discovery and retrieval.\n    tools:\n    - name: list-channels\n      description: 'List available Reuters content channels. Filter by category: TXT (text), PIX (images), VID (video), GFX\n        (graphics).'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reuters.list-channels\n      with:\n        channelCategory: tools.channelCategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-items\n      description: List the most recent editorial items from a Reuters content channel.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reuters.list-items\n      with:\n        channel: tools.channel\n        limit: tools.limit\n        mediaType: tools.mediaType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-item\n      description: Retrieve the full content of a Reuters item including\
  \ body, byline, subjects, and available media renditions.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reuters.get-item\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-items\n      description: Search Reuters editorial content by keyword. Supports field-specific queries like headline:election or\n        body:markets.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reuters.search-items\n      with:\n        q: tools.q\n        channel: tools.channel\n        limit: tools.limit\n        sort: tools.sort\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
