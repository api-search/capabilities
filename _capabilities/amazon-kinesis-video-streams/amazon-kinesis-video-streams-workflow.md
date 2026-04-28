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
- channels create signaling channel
- creates a signaling channel.
- channels describe signaling channel
- channels list signaling channels
- iot
- Developer
- Administrator
- streams describe stream
- streams create stream
- media
- returns an array of streaminfo objects.
- returns the most current information about the signaling channel.
- streams list streams
- unified workflow for amazon kinesis video streams resource management
- video streaming
- creates a new kinesis video stream.
- integrates api into applications
- returns an array of channelinfo objects.
- machine learning
- returns the most current information about the specified stream.
- aws
- workflow
- amazon kinesis video streams
- manages resources and configurations
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
