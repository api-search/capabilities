---
categories: []
consumed_apis: []
description: Unified capability for managing StreamYard live streaming and recording operations. Designed for content creators, media teams, and broadcast automation platforms. Covers the full broadcast lifecycle from creation through multi-platform destination setup, live monitoring, and post-broadcast recording access.
layout: capability
name: StreamYard Live Streaming
operations:
- description: List all broadcasts
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new broadcast
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Get broadcast details and status
  method: GET
  name: get-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: Update broadcast metadata
  method: PATCH
  name: update-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: Delete a broadcast
  method: DELETE
  name: delete-broadcast
  path: /v1/broadcasts/{broadcastId}
- description: List destinations for a broadcast
  method: GET
  name: list-broadcast-destinations
  path: /v1/broadcasts/{broadcastId}/destinations
- description: Add a streaming destination
  method: POST
  name: add-broadcast-destination
  path: /v1/broadcasts/{broadcastId}/destinations
- description: List connected platform accounts
  method: GET
  name: list-destinations
  path: /v1/destinations
- description: List all recordings
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: Get recording details and download URL
  method: GET
  name: get-recording
  path: /v1/recordings/{recordingId}
personas: []
provider_name: StreamYard
provider_slug: streamyard
search_terms:
- list the streaming platforms added to a specific broadcast
- video
- list broadcasts
- get details and current status of a broadcast
- list destinations
- get broadcast details and status
- connected streaming platform accounts
- list broadcast destinations
- create a new live stream or recording session
- list all broadcasts
- update broadcast
- create a new broadcast
- add broadcast destination
- get a recording with its time-limited download url
- list all recordings from completed broadcasts
- update a broadcast title, description, or scheduled time
- single recording access
- delete a broadcast permanently
- create broadcast
- get recording download
- list recordings
- list all broadcasts in the streamyard account including live and completed
- broadcast lifecycle management
- list all connected streaming platform accounts available for broadcasting
- delete broadcast
- list destinations for a broadcast
- list all recordings
- add a streaming platform (youtube, facebook, linkedin, twitch) to a broadcast
- delete a broadcast
- add a streaming destination
- single broadcast management
- list connected destinations
- live streaming
- broadcasting
- recordings
- list connected platform accounts
- multi-streaming
- multi-platform streaming destinations
- post-broadcast recordings
- get recording details and download url
- get broadcast
- update broadcast metadata
- get recording
slug: live-streaming
source_filename: live-streaming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StreamYard Live Streaming\n  description: Unified capability for managing StreamYard live streaming and recording operations. Designed for content creators,\n    media teams, and broadcast automation platforms. Covers the full broadcast lifecycle from creation through multi-platform\n    destination setup, live monitoring, and post-broadcast recording access.\n  tags:\n  - Broadcasting\n  - Live Streaming\n  - Multi-Streaming\n  - Recordings\n  - Video\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STREAMYARD_ACCESS_TOKEN: STREAMYARD_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: streamyard\n    baseUri: https://api.streamyard.com\n    description: StreamYard API\n    authentication:\n      type: bearer\n      token: '{{STREAMYARD_ACCESS_TOKEN}}'\n    resources:\n    - name: broadcasts\n      path: /broadcasts\n      description: Broadcast management\n      operations:\n\
  \      - name: list-broadcasts\n        method: GET\n        description: List all broadcasts in the account\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: perPage\n          in: query\n          type: integer\n          required: false\n          description: Broadcasts per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-broadcast\n        method: POST\n        description: Create a new broadcast\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n            scheduledAt: '{{tools.scheduledAt}}'\n\
  \    - name: broadcast\n      path: /broadcasts/{broadcastId}\n      description: Single broadcast operations\n      operations:\n      - name: get-broadcast\n        method: GET\n        description: Get details of a specific broadcast\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-broadcast\n        method: PATCH\n        description: Update broadcast title or scheduled time\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n    \
  \      data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            scheduledAt: '{{tools.scheduledAt}}'\n      - name: delete-broadcast\n        method: DELETE\n        description: Delete a broadcast\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: broadcast-destinations\n      path: /broadcasts/{broadcastId}/destinations\n      description: Broadcast destination management\n      operations:\n      - name: list-broadcast-destinations\n        method: GET\n        description: List destinations for a broadcast\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-broadcast-destination\n        method: POST\n        description: Add a streaming destination to a broadcast\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            destinationId: '{{tools.destinationId}}'\n            title: '{{tools.title}}'\n            privacy: '{{tools.privacy}}'\n    - name: destinations\n      path: /destinations\n      description: Connected streaming destinations\n      operations:\n      - name: list-destinations\n        method: GET\n        description: List all connected streaming destinations\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recordings\n      path: /recordings\n      description: Recorded broadcasts\n      operations:\n      - name: list-recordings\n        method: GET\n        description: List all recordings\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: perPage\n          in: query\n          type: integer\n          required: false\n          description: Recordings per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recording\n      path: /recordings/{recordingId}\n      description: Single recording access\n      operations:\n      - name: get-recording\n        method: GET\n        description: Get details and download URL for a recording\n\
  \        inputParameters:\n        - name: recordingId\n          in: path\n          type: string\n          required: true\n          description: The recording identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: streamyard-live-streaming-api\n    description: Unified REST API for StreamYard live streaming and recording management.\n    resources:\n    - path: /v1/broadcasts\n      name: broadcasts\n      description: Broadcast lifecycle management\n      operations:\n      - method: GET\n        name: list-broadcasts\n        description: List all broadcasts\n        call: streamyard.list-broadcasts\n        with:\n          page: rest.page\n          perPage: rest.perPage\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-broadcast\n        description: Create a new broadcast\n\
  \        call: streamyard.create-broadcast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/{broadcastId}\n      name: broadcast\n      description: Single broadcast management\n      operations:\n      - method: GET\n        name: get-broadcast\n        description: Get broadcast details and status\n        call: streamyard.get-broadcast\n        with:\n          broadcastId: rest.broadcastId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-broadcast\n        description: Update broadcast metadata\n        call: streamyard.update-broadcast\n        with:\n          broadcastId: rest.broadcastId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-broadcast\n        description: Delete a broadcast\n        call: streamyard.delete-broadcast\n        with:\n          broadcastId: rest.broadcastId\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/{broadcastId}/destinations\n      name: broadcast-destinations\n      description: Multi-platform streaming destinations\n      operations:\n      - method: GET\n        name: list-broadcast-destinations\n        description: List destinations for a broadcast\n        call: streamyard.list-broadcast-destinations\n        with:\n          broadcastId: rest.broadcastId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-broadcast-destination\n        description: Add a streaming destination\n        call: streamyard.add-broadcast-destination\n        with:\n          broadcastId: rest.broadcastId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/destinations\n      name: destinations\n      description: Connected streaming platform accounts\n      operations:\n      - method: GET\n     \
  \   name: list-destinations\n        description: List connected platform accounts\n        call: streamyard.list-destinations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings\n      name: recordings\n      description: Post-broadcast recordings\n      operations:\n      - method: GET\n        name: list-recordings\n        description: List all recordings\n        call: streamyard.list-recordings\n        with:\n          page: rest.page\n          perPage: rest.perPage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings/{recordingId}\n      name: recording\n      description: Single recording access\n      operations:\n      - method: GET\n        name: get-recording\n        description: Get recording details and download URL\n        call: streamyard.get-recording\n        with:\n          recordingId: rest.recordingId\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: streamyard-live-streaming-mcp\n    transport: http\n    description: MCP server for AI-assisted StreamYard broadcast management.\n    tools:\n    - name: list-broadcasts\n      description: List all broadcasts in the StreamYard account including live and completed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamyard.list-broadcasts\n      with:\n        page: tools.page\n        perPage: tools.perPage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broadcast\n      description: Create a new live stream or recording session\n      hints:\n        readOnly: false\n      call: streamyard.create-broadcast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-broadcast\n      description: Get details and current status of a broadcast\n      hints:\n        readOnly: true\n      call: streamyard.get-broadcast\n      with:\n    \
  \    broadcastId: tools.broadcastId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-broadcast\n      description: Update a broadcast title, description, or scheduled time\n      hints:\n        readOnly: false\n        idempotent: true\n      call: streamyard.update-broadcast\n      with:\n        broadcastId: tools.broadcastId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-broadcast\n      description: Delete a broadcast permanently\n      hints:\n        readOnly: false\n        destructive: true\n      call: streamyard.delete-broadcast\n      with:\n        broadcastId: tools.broadcastId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-broadcast-destinations\n      description: List the streaming platforms added to a specific broadcast\n      hints:\n        readOnly: true\n      call: streamyard.list-broadcast-destinations\n      with:\n        broadcastId: tools.broadcastId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-broadcast-destination\n      description: Add a streaming platform (YouTube, Facebook, LinkedIn, Twitch) to a broadcast\n      hints:\n        readOnly: false\n      call: streamyard.add-broadcast-destination\n      with:\n        broadcastId: tools.broadcastId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connected-destinations\n      description: List all connected streaming platform accounts available for broadcasting\n      hints:\n        readOnly: true\n      call: streamyard.list-destinations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recordings\n      description: List all recordings from completed broadcasts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamyard.list-recordings\n      with:\n        page: tools.page\n        perPage: tools.perPage\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-recording-download\n      description: Get a recording with its time-limited download URL\n      hints:\n        readOnly: true\n      call: streamyard.get-recording\n      with:\n        recordingId: tools.recordingId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/streamyard/refs/heads/main/capabilities/live-streaming.yaml
tags:
- Broadcasting
- Live Streaming
- Multi-Streaming
- Recordings
- Video
tools:
- description: List all broadcasts in the StreamYard account including live and completed
  hints:
    openWorld: true
    readOnly: true
  name: list-broadcasts
- description: Create a new live stream or recording session
  hints:
    readOnly: false
  name: create-broadcast
- description: Get details and current status of a broadcast
  hints:
    readOnly: true
  name: get-broadcast
- description: Update a broadcast title, description, or scheduled time
  hints:
    idempotent: true
    readOnly: false
  name: update-broadcast
- description: Delete a broadcast permanently
  hints:
    destructive: true
    readOnly: false
  name: delete-broadcast
- description: List the streaming platforms added to a specific broadcast
  hints:
    readOnly: true
  name: list-broadcast-destinations
- description: Add a streaming platform (YouTube, Facebook, LinkedIn, Twitch) to a broadcast
  hints:
    readOnly: false
  name: add-broadcast-destination
- description: List all connected streaming platform accounts available for broadcasting
  hints:
    readOnly: true
  name: list-connected-destinations
- description: List all recordings from completed broadcasts
  hints:
    openWorld: true
    readOnly: true
  name: list-recordings
- description: Get a recording with its time-limited download URL
  hints:
    readOnly: true
  name: get-recording-download
---
