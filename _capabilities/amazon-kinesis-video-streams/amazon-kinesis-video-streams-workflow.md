---
categories: []
consumed_apis:
- kinesis-video-streams
description: Unified workflow capability for Amazon Kinesis Video Streams combining resource management and operations.
layout: capability
name: Amazon Kinesis Video Streams Workflow
operations: []
personas: []
provider_name: Amazon Kinesis Video Streams
provider_slug: amazon-kinesis-video-streams
search_terms:
- returns an array of streaminfo objects.
- media
- iot
- workflow
- video streaming
- streams create stream
- returns an array of channelinfo objects.
- streams describe stream
- integrates api into applications
- unified workflow for amazon kinesis video streams resource management
- channels create signaling channel
- creates a signaling channel.
- returns the most current information about the specified stream.
- streams list streams
- manages resources and configurations
- machine learning
- amazon kinesis video streams
- channels list signaling channels
- returns the most current information about the signaling channel.
- creates a new kinesis video stream.
- channels describe signaling channel
- aws
- Developer
- Administrator
slug: amazon-kinesis-video-streams-workflow
source_filename: amazon-kinesis-video-streams-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Kinesis Video Streams Workflow\n  description: Unified workflow capability for Amazon Kinesis Video Streams combining resource management and operations.\n  tags:\n  - Amazon Kinesis Video Streams\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: kinesis-video-streams\n    location: ./shared/kinesis-video-streams.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kinesis-video-streams-api\n    description: REST API for Amazon Kinesis Video Streams workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kinesis-video-streams-mcp\n    transport: http\n    description: MCP server for Amazon Kinesis Video Streams.\n    tools:\n    - name: streams-create-stream\n      description: Creates a new Kinesis video stream.\n\
  \      hints:\n        readOnly: false\n        idempotent: false\n      call: kinesis-video-streams.createstream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-list-streams\n      description: Returns an array of StreamInfo objects.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.liststreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-describe-stream\n      description: Returns the most current information about the specified stream.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.describestream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: channels-create-signaling-channel\n      description: Creates a signaling channel.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kinesis-video-streams.createsignalingchannel\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: channels-list-signaling-channels\n      description: Returns an array of ChannelInfo objects.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.listsignalingchannels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: channels-describe-signaling-channel\n      description: Returns the most current information about the signaling channel.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-video-streams.describesignalingchannel\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
