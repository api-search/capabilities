---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Kinesis Video Streams combining resource management and operations.
layout: capability
name: Amazon Kinesis Video Streams Workflow
operations: []
personas: []
provider_name: Amazon Kinesis Video Streams
provider_slug: amazon-kinesis-video-streams
search_terms:
- Administrator
- aws
- streams describe stream
- amazon kinesis video streams
- workflow
- returns the most current information about the signaling channel.
- Developer
- integrates api into applications
- iot
- channels list signaling channels
- returns the most current information about the specified stream.
- creates a new kinesis video stream.
- channels describe signaling channel
- manages resources and configurations
- machine learning
- streams list streams
- returns an array of channelinfo objects.
- media
- unified workflow for amazon kinesis video streams resource management
- channels create signaling channel
- returns an array of streaminfo objects.
- streams create stream
- creates a signaling channel.
- video streaming
slug: amazon-kinesis-video-streams-workflow
source_filename: amazon-kinesis-video-streams-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Kinesis Video Streams Workflow\n  description: Unified workflow capability for Amazon Kinesis Video Streams combining resource management and operations.\n  tags:\n  - Amazon Kinesis Video Streams\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: kinesis-video-streams\n    baseUri: https://kinesisvideo.us-east-1.amazonaws.com\n    description: Amazon Kinesis Video Streams service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: streams\n      path: /streams\n      description: Video stream management\n      operations:\n      - name: createstream\n        method: POST\n        description: Creates a new Kinesis video\
  \ stream.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: liststreams\n        method: GET\n        description: Returns an array of StreamInfo objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describestream\n        method: GET\n        description: Returns the most current information about the specified stream.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      description: WebRTC signaling channel management\n      operations:\n      - name: createsignalingchannel\n        method: POST\n        description: Creates a signaling channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: listsignalingchannels\n        method: GET\n        description: Returns an array of ChannelInfo objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describesignalingchannel\n        method: GET\n        description: Returns the most current information about the signaling channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kinesis-video-streams-api\n    description: REST API for Amazon Kinesis Video Streams workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kinesis-video-streams-mcp\n    transport: http\n    description: MCP server for Amazon Kinesis Video Streams.\n    tools:\n    - name: streams-create-stream\n      description: Creates a new Kinesis video stream.\n      hints:\n        readOnly: false\n \
  \       idempotent: false\n      call: kinesis-video-streams.createstream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-list-streams\n      description: Returns an array of StreamInfo objects.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.liststreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-describe-stream\n      description: Returns the most current information about the specified stream.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.describestream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: channels-create-signaling-channel\n      description: Creates a signaling channel.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kinesis-video-streams.createsignalingchannel\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: channels-list-signaling-channels\n      description: Returns an array of ChannelInfo objects.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.listsignalingchannels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: channels-describe-signaling-channel\n      description: Returns the most current information about the signaling channel.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.describesignalingchannel\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-kinesis-video-streams/refs/heads/main/capabilities/amazon-kinesis-video-streams-workflow.yaml
tags:
- Amazon Kinesis Video Streams
- Workflow
tools:
- description: Creates a new Kinesis video stream.
  hints:
    idempotent: false
    readOnly: false
  name: streams-create-stream
- description: Returns an array of StreamInfo objects.
  hints:
    idempotent: true
    readOnly: true
  name: streams-list-streams
- description: Returns the most current information about the specified stream.
  hints:
    idempotent: true
    readOnly: true
  name: streams-describe-stream
- description: Creates a signaling channel.
  hints:
    idempotent: false
    readOnly: false
  name: channels-create-signaling-channel
- description: Returns an array of ChannelInfo objects.
  hints:
    idempotent: true
    readOnly: true
  name: channels-list-signaling-channels
- description: Returns the most current information about the signaling channel.
  hints:
    idempotent: true
    readOnly: true
  name: channels-describe-signaling-channel
---
