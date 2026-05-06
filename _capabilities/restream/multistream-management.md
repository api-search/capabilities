---
categories: []
consumed_apis: []
description: Unified workflow capability for managing live multistreaming operations. Combines Restream REST API capabilities for channel configuration, event lifecycle management, stream key retrieval, and platform management. Used by content creators and developers integrating multistreaming into their applications.
layout: capability
name: Restream Multistream Management
operations:
- description: List all supported streaming destination platforms
  method: GET
  name: list-platforms
  path: /v1/platforms
- description: List all connected streaming channels
  method: GET
  name: list-channels
  path: /v1/channels
- description: Get a specific channel
  method: GET
  name: get-channel
  path: /v1/channels/{id}
- description: Update channel settings
  method: PATCH
  name: update-channel
  path: /v1/channels/{id}
- description: Get channel stream metadata
  method: GET
  name: get-channel-meta
  path: /v1/channels/{id}/meta
- description: Update channel stream title and description
  method: PATCH
  name: update-channel-meta
  path: /v1/channels/{id}/meta
- description: Get stream key for broadcasting
  method: GET
  name: get-stream-key
  path: /v1/stream-key
- description: List upcoming live events
  method: GET
  name: list-upcoming-events
  path: /v1/events/upcoming
- description: List currently active live events
  method: GET
  name: list-in-progress-events
  path: /v1/events/in-progress
- description: List historical events
  method: GET
  name: list-event-history
  path: /v1/events/history
- description: Get a specific event
  method: GET
  name: get-event
  path: /v1/events/{id}
- description: Get stream key for a specific event
  method: GET
  name: get-event-stream-key
  path: /v1/events/{id}/stream-key
personas: []
provider_name: Restream
provider_slug: restream
search_terms:
- broadcast
- individual channel management
- get a specific channel
- retrieve the rtmp stream key and srt url for broadcasting
- get stream key for broadcasting
- connected streaming channels
- list all connected streaming destination channels
- update channel stream title and description
- scheduled upcoming events
- list event history
- get event
- get channel
- video streaming
- update channel meta
- event-specific stream key
- get channel meta
- get the authenticated user's restream account profile
- get stream key
- get event stream key
- update channel
- channel stream metadata
- individual event management
- list all supported streaming destination platforms
- completed event history
- content delivery
- enable or disable a channel, or update its display name
- get user profile
- get the stream key for a specific event
- get a specific event
- list historical events
- restream
- list all scheduled upcoming live stream events
- list all currently active live streaming events
- list upcoming events
- rtmp stream key and srt url
- list channels
- list in progress events
- chat
- get details for a specific streaming channel
- list all connected streaming channels
- update channel settings
- get channel stream metadata
- list all streaming platforms supported by restream for multistreaming destinations
- get stream key for a specific event
- get stream metadata (title, description) for a channel
- list platforms
- list historical completed live streaming events
- multistreaming
- streaming platform directory
- list upcoming live events
- live streaming
- currently streaming events
- update the stream title and description for a channel
- list currently active live events
- events
- get details for a specific live streaming event
- channels
slug: multistream-management
source_filename: multistream-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Restream Multistream Management\n  description: Unified workflow capability for managing live multistreaming operations. Combines Restream REST API capabilities\n    for channel configuration, event lifecycle management, stream key retrieval, and platform management. Used by content\n    creators and developers integrating multistreaming into their applications.\n  tags:\n  - Broadcast\n  - Channels\n  - Events\n  - Live Streaming\n  - Multistreaming\n  - Restream\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RESTREAM_ACCESS_TOKEN: RESTREAM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: restream\n    baseUri: https://api.restream.io/v2\n    description: Restream REST API v2 for multistreaming management\n    authentication:\n      type: bearer\n      token: '{{RESTREAM_ACCESS_TOKEN}}'\n    resources:\n    - name: platforms\n      path: /platform/all\n      description:\
  \ Public streaming platform listings\n      operations:\n      - name: list-platforms\n        method: GET\n        description: List all supported streaming platforms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: user-profile\n      path: /user/profile\n      description: Authenticated user profile\n      operations:\n      - name: get-user-profile\n        method: GET\n        description: Retrieve the authenticated user profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-key\n      path: /user/streamKey\n      description: User RTMP stream key and SRT URL\n      operations:\n      - name: get-stream-key\n        method: GET\n        description: Retrieve stream key and SRT URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: channels\n      path: /user/channel/all\n      description: All user channels\n      operations:\n      - name: list-channels\n        method: GET\n        description: List all channels for the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: channel\n      path: /user/channel/{id}\n      description: Individual channel management\n      operations:\n      - name: get-channel\n        method: GET\n        description: Retrieve a specific channel by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Channel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-channel\n        method: PATCH\n        description: Update channel settings\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Channel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            active: '{{tools.active}}'\n            displayName: '{{tools.displayName}}'\n    - name: channel-meta\n      path: /user/channel/{id}/meta\n      description: Channel metadata (title, description, tags)\n      operations:\n      - name: get-channel-meta\n        method: GET\n        description: Retrieve channel metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Channel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-channel-meta\n        method: PATCH\n \
  \       description: Update channel metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Channel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n    - name: events-upcoming\n      path: /user/event/upcoming\n      description: Upcoming live events\n      operations:\n      - name: list-upcoming-events\n        method: GET\n        description: List all upcoming events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: events-in-progress\n      path: /user/event/in-progress\n      description: Currently active live events\n      operations:\n      - name: list-in-progress-events\n\
  \        method: GET\n        description: List all in-progress events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: events-history\n      path: /user/event/history\n      description: Historical live events\n      operations:\n      - name: list-event-history\n        method: GET\n        description: List historical events\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: event\n      path: /user/event/{id}\n      description: Individual event management\n      operations:\n      - name: get-event\n\
  \        method: GET\n        description: Retrieve a specific event by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-stream-key\n      path: /user/event/{id}/streamKey\n      description: Event stream keys\n      operations:\n      - name: get-event-stream-key\n        method: GET\n        description: Retrieve stream key for a specific event\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: multistream-management-api\n    description: Unified\
  \ REST API for Restream multistreaming management.\n    resources:\n    - path: /v1/platforms\n      name: platforms\n      description: Streaming platform directory\n      operations:\n      - method: GET\n        name: list-platforms\n        description: List all supported streaming destination platforms\n        call: restream.list-platforms\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Connected streaming channels\n      operations:\n      - method: GET\n        name: list-channels\n        description: List all connected streaming channels\n        call: restream.list-channels\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/channels/{id}\n      name: channel\n      description: Individual channel management\n      operations:\n      - method: GET\n        name: get-channel\n        description: Get a specific channel\n        call: restream.get-channel\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-channel\n        description: Update channel settings\n        call: restream.update-channel\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels/{id}/meta\n      name: channel-meta\n      description: Channel stream metadata\n      operations:\n      - method: GET\n        name: get-channel-meta\n        description: Get channel stream metadata\n        call: restream.get-channel-meta\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-channel-meta\n        description: Update channel stream title and description\n        call: restream.update-channel-meta\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/stream-key\n      name: stream-key\n      description: RTMP stream key and SRT URL\n      operations:\n      - method: GET\n        name: get-stream-key\n        description: Get stream key for broadcasting\n        call: restream.get-stream-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/upcoming\n      name: upcoming-events\n      description: Scheduled upcoming events\n      operations:\n      - method: GET\n        name: list-upcoming-events\n        description: List upcoming live events\n        call: restream.list-upcoming-events\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/events/in-progress\n      name: live-events\n      description: Currently streaming events\n      operations:\n      - method: GET\n        name: list-in-progress-events\n        description: List currently active live events\n        call: restream.list-in-progress-events\n\
  \        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/events/history\n      name: event-history\n      description: Completed event history\n      operations:\n      - method: GET\n        name: list-event-history\n        description: List historical events\n        call: restream.list-event-history\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/events/{id}\n      name: event\n      description: Individual event management\n      operations:\n      - method: GET\n        name: get-event\n        description: Get a specific event\n        call: restream.get-event\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{id}/stream-key\n      name: event-stream-key\n      description: Event-specific stream key\n      operations:\n      - method: GET\n        name: get-event-stream-key\n        description: Get stream key for a specific\
  \ event\n        call: restream.get-event-stream-key\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: multistream-management-mcp\n    transport: http\n    description: MCP server for AI-assisted multistreaming management and live event operations.\n    tools:\n    - name: list-platforms\n      description: List all streaming platforms supported by Restream for multistreaming destinations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.list-platforms\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-user-profile\n      description: Get the authenticated user's Restream account profile\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-user-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stream-key\n      description: Retrieve\
  \ the RTMP stream key and SRT URL for broadcasting\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-stream-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-channels\n      description: List all connected streaming destination channels\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.list-channels\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-channel\n      description: Get details for a specific streaming channel\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-channel\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-channel\n      description: Enable or disable a channel, or update its display name\n      hints:\n        readOnly: false\n        idempotent: true\n      call: restream.update-channel\n      with:\n    \
  \    id: tools.id\n        active: tools.active\n        displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-channel-meta\n      description: Get stream metadata (title, description) for a channel\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-channel-meta\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-channel-meta\n      description: Update the stream title and description for a channel\n      hints:\n        readOnly: false\n        idempotent: true\n      call: restream.update-channel-meta\n      with:\n        id: tools.id\n        title: tools.title\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-upcoming-events\n      description: List all scheduled upcoming live stream events\n      hints:\n        readOnly: true\n       \
  \ idempotent: true\n      call: restream.list-upcoming-events\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-in-progress-events\n      description: List all currently active live streaming events\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.list-in-progress-events\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-event-history\n      description: List historical completed live streaming events\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.list-event-history\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-event\n      description: Get details for a specific live streaming event\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-event\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-event-stream-key\n      description: Get the stream key for a specific event\n      hints:\n        readOnly: true\n        idempotent: true\n      call: restream.get-event-stream-key\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/restream/refs/heads/main/capabilities/multistream-management.yaml
tags:
- Broadcast
- Channels
- Events
- Live Streaming
- Multistreaming
- Restream
tools:
- description: List all streaming platforms supported by Restream for multistreaming destinations
  hints:
    idempotent: true
    readOnly: true
  name: list-platforms
- description: Get the authenticated user's Restream account profile
  hints:
    idempotent: true
    readOnly: true
  name: get-user-profile
- description: Retrieve the RTMP stream key and SRT URL for broadcasting
  hints:
    idempotent: true
    readOnly: true
  name: get-stream-key
- description: List all connected streaming destination channels
  hints:
    idempotent: true
    readOnly: true
  name: list-channels
- description: Get details for a specific streaming channel
  hints:
    idempotent: true
    readOnly: true
  name: get-channel
- description: Enable or disable a channel, or update its display name
  hints:
    idempotent: true
    readOnly: false
  name: update-channel
- description: Get stream metadata (title, description) for a channel
  hints:
    idempotent: true
    readOnly: true
  name: get-channel-meta
- description: Update the stream title and description for a channel
  hints:
    idempotent: true
    readOnly: false
  name: update-channel-meta
- description: List all scheduled upcoming live stream events
  hints:
    idempotent: true
    readOnly: true
  name: list-upcoming-events
- description: List all currently active live streaming events
  hints:
    idempotent: true
    readOnly: true
  name: list-in-progress-events
- description: List historical completed live streaming events
  hints:
    idempotent: true
    readOnly: true
  name: list-event-history
- description: Get details for a specific live streaming event
  hints:
    idempotent: true
    readOnly: true
  name: get-event
- description: Get the stream key for a specific event
  hints:
    idempotent: true
    readOnly: true
  name: get-event-stream-key
---
