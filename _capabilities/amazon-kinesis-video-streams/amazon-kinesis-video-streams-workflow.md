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
- channels list signaling channels
- creates a signaling channel.
- returns an array of channelinfo objects.
- amazon kinesis video streams
- streams describe stream
- Administrator
- creates a new kinesis video stream.
- workflow
- iot
- channels create signaling channel
- streams create stream
- returns an array of streaminfo objects.
- machine learning
- unified workflow for amazon kinesis video streams resource management
- integrates api into applications
- manages resources and configurations
- media
- aws
- returns the most current information about the specified stream.
- returns the most current information about the signaling channel.
- video streaming
- channels describe signaling channel
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
