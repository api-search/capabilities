---
categories: []
consumed_apis:
- restream
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
- channel stream metadata
- get channel stream metadata
- get stream key
- retrieve the rtmp stream key and srt url for broadcasting
- list all currently active live streaming events
- get channel meta
- get stream key for a specific event
- live streaming
- get a specific channel
- list all scheduled upcoming live stream events
- list in progress events
- update channel stream title and description
- individual event management
- update channel
- streaming platform directory
- get a specific event
- get stream metadata (title, description) for a channel
- get details for a specific live streaming event
- get event
- restream
- broadcast
- update channel settings
- update the stream title and description for a channel
- get details for a specific streaming channel
- event-specific stream key
- list all streaming platforms supported by restream for multistreaming destinations
- list historical completed live streaming events
- list all supported streaming destination platforms
- update channel meta
- list channels
- chat
- get event stream key
- enable or disable a channel, or update its display name
- list event history
- scheduled upcoming events
- currently streaming events
- list upcoming events
- list historical events
- get the stream key for a specific event
- get user profile
- channels
- connected streaming channels
- list platforms
- get channel
- events
- video streaming
- list all connected streaming destination channels
- completed event history
- list upcoming live events
- rtmp stream key and srt url
- content delivery
- list all connected streaming channels
- individual channel management
- list currently active live events
- get the authenticated user's restream account profile
- get stream key for broadcasting
- multistreaming
slug: multistream-management
source_filename: multistream-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Restream Multistream Management\"\n  description: >-\n    Unified workflow capability for managing live multistreaming operations.\n    Combines Restream REST API capabilities for channel configuration, event\n    lifecycle management, stream key retrieval, and platform management.\n    Used by content creators and developers integrating multistreaming into\n    their applications.\n  tags:\n    - Broadcast\n    - Channels\n    - Events\n    - Live Streaming\n    - Multistreaming\n    - Restream\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RESTREAM_ACCESS_TOKEN: RESTREAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: restream\n      location: ./shared/restream-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: multistream-management-api\n      description: \"Unified REST API for Restream multistreaming management.\"\n      resources:\n\
  \        - path: /v1/platforms\n          name: platforms\n          description: \"Streaming platform directory\"\n          operations:\n            - method: GET\n              name: list-platforms\n              description: \"List all supported streaming destination platforms\"\n              call: \"restream.list-platforms\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/channels\n          name: channels\n          description: \"Connected streaming channels\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List all connected streaming channels\"\n              call: \"restream.list-channels\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/channels/{id}\n          name: channel\n          description: \"Individual channel management\"\n          operations:\n      \
  \      - method: GET\n              name: get-channel\n              description: \"Get a specific channel\"\n              call: \"restream.get-channel\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-channel\n              description: \"Update channel settings\"\n              call: \"restream.update-channel\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/channels/{id}/meta\n          name: channel-meta\n          description: \"Channel stream metadata\"\n          operations:\n            - method: GET\n              name: get-channel-meta\n              description: \"Get channel stream metadata\"\n              call: \"restream.get-channel-meta\"\n              with:\n                id: \"\
  rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-channel-meta\n              description: \"Update channel stream title and description\"\n              call: \"restream.update-channel-meta\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stream-key\n          name: stream-key\n          description: \"RTMP stream key and SRT URL\"\n          operations:\n            - method: GET\n              name: get-stream-key\n              description: \"Get stream key for broadcasting\"\n              call: \"restream.get-stream-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/upcoming\n          name: upcoming-events\n          description: \"Scheduled upcoming events\"\
  \n          operations:\n            - method: GET\n              name: list-upcoming-events\n              description: \"List upcoming live events\"\n              call: \"restream.list-upcoming-events\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/events/in-progress\n          name: live-events\n          description: \"Currently streaming events\"\n          operations:\n            - method: GET\n              name: list-in-progress-events\n              description: \"List currently active live events\"\n              call: \"restream.list-in-progress-events\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/events/history\n          name: event-history\n          description: \"Completed event history\"\n          operations:\n            - method: GET\n              name: list-event-history\n              description: \"List historical\
  \ events\"\n              call: \"restream.list-event-history\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/events/{id}\n          name: event\n          description: \"Individual event management\"\n          operations:\n            - method: GET\n              name: get-event\n              description: \"Get a specific event\"\n              call: \"restream.get-event\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/{id}/stream-key\n          name: event-stream-key\n          description: \"Event-specific stream key\"\n          operations:\n            - method: GET\n              name: get-event-stream-key\n              description: \"Get stream key for a specific event\"\n              call: \"restream.get-event-stream-key\"\n              with:\n                id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: multistream-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted multistreaming management and live event operations.\"\n      tools:\n        - name: list-platforms\n          description: \"List all streaming platforms supported by Restream for multistreaming destinations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.list-platforms\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-user-profile\n          description: \"Get the authenticated user's Restream account profile\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-user-profile\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n\n        - name: get-stream-key\n          description: \"Retrieve the RTMP stream key and SRT URL for broadcasting\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-stream-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-channels\n          description: \"List all connected streaming destination channels\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.list-channels\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-channel\n          description: \"Get details for a specific streaming channel\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-channel\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n\n        - name: update-channel\n          description: \"Enable or disable a channel, or update its display name\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"restream.update-channel\"\n          with:\n            id: \"tools.id\"\n            active: \"tools.active\"\n            displayName: \"tools.displayName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-channel-meta\n          description: \"Get stream metadata (title, description) for a channel\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-channel-meta\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-channel-meta\n          description: \"Update the stream title and description for a channel\"\n          hints:\n\
  \            readOnly: false\n            idempotent: true\n          call: \"restream.update-channel-meta\"\n          with:\n            id: \"tools.id\"\n            title: \"tools.title\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-upcoming-events\n          description: \"List all scheduled upcoming live stream events\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.list-upcoming-events\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-in-progress-events\n          description: \"List all currently active live streaming events\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.list-in-progress-events\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n   \
  \     - name: list-event-history\n          description: \"List historical completed live streaming events\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.list-event-history\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-event\n          description: \"Get details for a specific live streaming event\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-event\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-stream-key\n          description: \"Get the stream key for a specific event\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"restream.get-event-stream-key\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
