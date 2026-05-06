---
categories: []
consumed_apis: []
description: Workflow for managing YouTube live events including scheduling broadcasts, linking streams, managing live chat, and moderating live interactions. Designed for live event producers, streaming teams, and broadcast operators.
layout: capability
name: YouTube Live Streaming
operations:
- description: List live broadcasts
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new live broadcast
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Update broadcast settings
  method: PUT
  name: update-broadcast
  path: /v1/broadcasts
- description: Delete a broadcast
  method: DELETE
  name: delete-broadcast
  path: /v1/broadcasts
- description: List live streams
  method: GET
  name: list-streams
  path: /v1/streams
- description: Create a new live stream
  method: POST
  name: create-stream
  path: /v1/streams
- description: Update stream settings
  method: PUT
  name: update-stream
  path: /v1/streams
- description: Delete a live stream
  method: DELETE
  name: delete-stream
  path: /v1/streams
- description: List live chat messages
  method: GET
  name: list-chat-messages
  path: /v1/chat-messages
- description: Send a live chat message
  method: POST
  name: send-chat-message
  path: /v1/chat-messages
- description: Delete a live chat message
  method: DELETE
  name: delete-chat-message
  path: /v1/chat-messages
- description: List live chat moderators
  method: GET
  name: list-moderators
  path: /v1/chat-moderators
- description: Add a live chat moderator
  method: POST
  name: add-moderator
  path: /v1/chat-moderators
- description: Remove a live chat moderator
  method: DELETE
  name: remove-moderator
  path: /v1/chat-moderators
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- add moderator
- delete a broadcast
- remove a live chat moderator
- update broadcast settings
- social
- create stream
- transition broadcast
- update stream settings
- manage live chat messages
- delete a live broadcast
- manage live broadcasts
- update broadcast
- list streams
- create a new live broadcast event
- bind broadcast
- create broadcast
- google
- videos
- list live streams
- delete chat message
- list messages in live chat
- bind a broadcast to a video stream
- send a live chat message
- list moderators
- list chat messages
- delete broadcast
- update live broadcast settings
- transition broadcast status (testing, live, complete)
- live chat
- delete a live stream
- list live video streams
- manage live chat moderators
- list youtube live broadcasts
- update stream
- video
- youtube
- add a live chat moderator
- media
- manage live video streams
- list live chat messages
- list live chat moderators
- send a message to live chat
- delete stream
- delete a live chat message
- create a new live stream
- broadcasting
- create a new live video stream
- remove moderator
- streaming
- list live broadcasts
- list broadcasts
- live streaming
- send chat message
- create a new live broadcast
slug: live-streaming
source_filename: live-streaming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: YouTube Live Streaming\n  description: Workflow for managing YouTube live events including scheduling broadcasts, linking streams, managing live chat,\n    and moderating live interactions. Designed for live event producers, streaming teams, and broadcast operators.\n  tags:\n  - YouTube\n  - Live Streaming\n  - Broadcasting\n  - Live Chat\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: youtube-live-streaming\n    baseUri: https://www.googleapis.com/youtube/v3\n    description: YouTube Live Streaming API for managing live broadcasts, streams, chat messages, and moderators.\n    authentication:\n      type: bearer\n      token: '{{YOUTUBE_OAUTH_TOKEN}}'\n    resources:\n    - name: live-broadcasts\n      path: /liveBroadcasts\n      description: Operations for managing YouTube live broadcast events\n\
  \      operations:\n      - name: list-live-broadcasts\n        method: GET\n        description: Returns a list of YouTube broadcasts that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube broadcast IDs for the resources being retrieved.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return only broadcasts owned by the authenticated user.\n        - name: broadcastStatus\n          in: query\n          type: string\n          required: false\n          description: Filters the API response to only include broadcasts with the specified status.\n       \
  \ - name: broadcastType\n          in: query\n          type: string\n          required: false\n          description: Filters results by the type of broadcast.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-live-broadcast\n\
  \        method: POST\n        description: Creates a broadcast\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-live-broadcast\n        method: PUT\n        description: Updates a broadcast's settings\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies\
  \ a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-live-broadcast\n        method: DELETE\n        description: Deletes a broadcast\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the broadcast to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: live-broadcast-bind\n      path: /liveBroadcasts/bind\n      description: Operations for binding YouTube broadcasts to streams\n      operations:\n      - name: bind-live-broadcast\n        method: POST\n        description: Binds a YouTube broadcast to a stream or removes an existing binding\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The unique ID of the broadcast that is being bound to a video stream.\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: streamId\n          in: query\n          type: string\n          required: false\n          description: The unique ID of the video stream that is being bound to a broadcast.\n        - name: key\n \
  \         in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-broadcast-transition\n      path: /liveBroadcasts/transition\n      description: Operations for transitioning YouTube broadcast states\n      operations:\n      - name: transition-live-broadcast\n        method: POST\n        description: Changes the status of a YouTube live broadcast\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The unique ID of the broadcast that is transitioning to another status.\n        - name: broadcastStatus\n          in: query\n          type: string\n          required: true\n          description: The broadcastStatus parameter identifies the state to which the broadcast is changing.\n        - name: part\n\
  \          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-streams\n      path: /liveStreams\n      description: Operations for managing YouTube live video streams\n      operations:\n      - name: list-live-streams\n        method: GET\n        description: Returns a list of video streams that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n\
  \          type: string\n          required: false\n          description: Comma-separated list of live stream IDs for the resources being retrieved.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return only streams owned by the authenticated user.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for\
  \ authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-live-stream\n        method: POST\n        description: Creates a video stream\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-live-stream\n        method: PUT\n        description:\
  \ Updates a video stream\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-live-stream\n        method: DELETE\n        description: Deletes a video stream\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the live stream to delete.\n        - name:\
  \ key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-chat-messages\n      path: /liveChatMessages\n      description: Operations for managing messages in YouTube live chat\n      operations:\n      - name: list-live-chat-messages\n        method: GET\n        description: Lists live chat messages for a specific live broadcast\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: liveChatId\n          in: query\n          type: string\n          required: true\n          description: The liveChatId parameter specifies the ID of the live chat whose messages will be returned.\n        - name:\
  \ maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-live-chat-message\n        method: POST\n        description: Adds a message to a live chat\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n\
  \          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-live-chat-message\n        method: DELETE\n        description: Deletes a chat message\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the live chat message to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key\
  \ for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-chat-moderators\n      path: /liveChatModerators\n      description: Operations for managing moderators in YouTube live chat\n      operations:\n      - name: list-live-chat-moderators\n        method: GET\n        description: Lists moderators for a live chat\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: liveChatId\n          in: query\n          type: string\n          required: true\n          description: The liveChatId parameter specifies the YouTube live chat for which the API should return moderators.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description:\
  \ The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-live-chat-moderator\n        method: POST\n        description: Adds a new moderator for a live chat\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource\
  \ properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-live-chat-moderator\n        method: DELETE\n        description: Removes a chat moderator\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the live chat moderator to remove.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: live-streaming-api\n    description: Unified REST API for YouTube live streaming workflows.\n    resources:\n    - path: /v1/broadcasts\n      name: broadcasts\n      description: Manage live broadcasts\n      operations:\n      - method: GET\n        name: list-broadcasts\n        description: List live broadcasts\n        call: youtube-live.list-live-broadcasts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-broadcast\n        description: Create a new live broadcast\n        call: youtube-live.insert-live-broadcast\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-broadcast\n        description: Update broadcast settings\n        call: youtube-live.update-live-broadcast\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: DELETE\n        name: delete-broadcast\n        description: Delete a broadcast\n        call: youtube-live.delete-live-broadcast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/streams\n      name: streams\n      description: Manage live video streams\n      operations:\n      - method: GET\n        name: list-streams\n        description: List live streams\n        call: youtube-live.list-live-streams\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-stream\n        description: Create a new live stream\n        call: youtube-live.insert-live-stream\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-stream\n        description: Update stream settings\n        call: youtube-live.update-live-stream\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n\
  \        name: delete-stream\n        description: Delete a live stream\n        call: youtube-live.delete-live-stream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat-messages\n      name: chat-messages\n      description: Manage live chat messages\n      operations:\n      - method: GET\n        name: list-chat-messages\n        description: List live chat messages\n        call: youtube-live.list-live-chat-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-chat-message\n        description: Send a live chat message\n        call: youtube-live.insert-live-chat-message\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-chat-message\n        description: Delete a live chat message\n        call: youtube-live.delete-live-chat-message\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/chat-moderators\n      name: chat-moderators\n      description: Manage live chat moderators\n      operations:\n      - method: GET\n        name: list-moderators\n        description: List live chat moderators\n        call: youtube-live.list-live-chat-moderators\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-moderator\n        description: Add a live chat moderator\n        call: youtube-live.insert-live-chat-moderator\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-moderator\n        description: Remove a live chat moderator\n        call: youtube-live.delete-live-chat-moderator\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: live-streaming-mcp\n    transport: http\n    description: MCP server for AI-assisted YouTube live streaming management.\n    tools:\n\
  \    - name: list-broadcasts\n      description: List YouTube live broadcasts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-live.list-live-broadcasts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broadcast\n      description: Create a new live broadcast event\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-live.insert-live-broadcast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-broadcast\n      description: Update live broadcast settings\n      hints:\n        readOnly: false\n        idempotent: true\n      call: youtube-live.update-live-broadcast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-broadcast\n      description: Delete a live broadcast\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-live.delete-live-broadcast\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bind-broadcast\n      description: Bind a broadcast to a video stream\n      hints:\n        readOnly: false\n        idempotent: true\n      call: youtube-live.bind-live-broadcast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transition-broadcast\n      description: Transition broadcast status (testing, live, complete)\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-live.transition-live-broadcast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-streams\n      description: List live video streams\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-live.list-live-streams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-stream\n      description: Create a new live video stream\n      hints:\n        readOnly: false\n        idempotent:\
  \ false\n      call: youtube-live.insert-live-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-chat-messages\n      description: List messages in live chat\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-live.list-live-chat-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-chat-message\n      description: Send a message to live chat\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-live.insert-live-chat-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-chat-message\n      description: Delete a live chat message\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-live.delete-live-chat-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-moderators\n      description: List live chat\
  \ moderators\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-live.list-live-chat-moderators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-moderator\n      description: Add a live chat moderator\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-live.insert-live-chat-moderator\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-moderator\n      description: Remove a live chat moderator\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-live.delete-live-chat-moderator\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/live-streaming.yaml
tags:
- YouTube
- Live Streaming
- Broadcasting
- Live Chat
tools:
- description: List YouTube live broadcasts
  hints:
    idempotent: true
    readOnly: true
  name: list-broadcasts
- description: Create a new live broadcast event
  hints:
    idempotent: false
    readOnly: false
  name: create-broadcast
- description: Update live broadcast settings
  hints:
    idempotent: true
    readOnly: false
  name: update-broadcast
- description: Delete a live broadcast
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-broadcast
- description: Bind a broadcast to a video stream
  hints:
    idempotent: true
    readOnly: false
  name: bind-broadcast
- description: Transition broadcast status (testing, live, complete)
  hints:
    idempotent: false
    readOnly: false
  name: transition-broadcast
- description: List live video streams
  hints:
    idempotent: true
    readOnly: true
  name: list-streams
- description: Create a new live video stream
  hints:
    idempotent: false
    readOnly: false
  name: create-stream
- description: List messages in live chat
  hints:
    idempotent: true
    readOnly: true
  name: list-chat-messages
- description: Send a message to live chat
  hints:
    idempotent: false
    readOnly: false
  name: send-chat-message
- description: Delete a live chat message
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-chat-message
- description: List live chat moderators
  hints:
    idempotent: true
    readOnly: true
  name: list-moderators
- description: Add a live chat moderator
  hints:
    idempotent: false
    readOnly: false
  name: add-moderator
- description: Remove a live chat moderator
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-moderator
---
