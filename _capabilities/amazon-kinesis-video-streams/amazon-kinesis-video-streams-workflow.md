---
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
- manages resources and configurations
- returns the most current information about the signaling channel.
- returns an array of streaminfo objects.
- channels list signaling channels
- workflow
- iot
- integrates api into applications
- streams create stream
- Administrator
- channels describe signaling channel
- creates a signaling channel.
- unified workflow for amazon kinesis video streams resource management
- media
- amazon kinesis video streams
- machine learning
- channels create signaling channel
- creates a new kinesis video stream.
- aws
- streams describe stream
- video streaming
- returns an array of channelinfo objects.
- returns the most current information about the specified stream.
- Developer
- streams list streams
slug: amazon-kinesis-video-streams-workflow
tags:
- Amazon Kinesis Video Streams
- AWS
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
