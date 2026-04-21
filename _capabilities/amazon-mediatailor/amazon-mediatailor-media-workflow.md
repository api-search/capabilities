---
consumed_apis:
- mediatailor
description: Workflow capability for Amazon MediaTailor media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaTailor Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaTailor
provider_slug: amazon-mediatailor
search_terms:
- Broadcast Engineer
- createlivesource
- create channel
- delete channel
- configure logs for playback configuration
- engineer managing broadcast media workflows
- broadcasting
- Media Developer
- manage media processing jobs
- describe channel
- describe live source
- developer building media processing applications
- updatechannel
- configurelogsforplaybackconfiguration
- update channel
- createchannel
- configure logs for channel
- deletechannel
- create live source
- workflow
- media processing
- list jobs
- amazon mediatailor media processing workflow
- describelivesource
- aws
- aws media processing and delivery
- describechannel
- media
- configurelogsforchannel
slug: amazon-mediatailor-media-workflow
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: ConfigureLogsForChannel
  hints:
    openWorld: true
    readOnly: false
  name: configure-logs-for-channel
- description: ConfigureLogsForPlaybackConfiguration
  hints:
    openWorld: true
    readOnly: false
  name: configure-logs-for-playback-configuration
- description: DescribeChannel
  hints:
    openWorld: true
    readOnly: true
  name: describe-channel
- description: CreateChannel
  hints:
    openWorld: true
    readOnly: false
  name: create-channel
- description: UpdateChannel
  hints:
    openWorld: true
    readOnly: false
  name: update-channel
- description: DeleteChannel
  hints:
    openWorld: true
    readOnly: false
  name: delete-channel
- description: DescribeLiveSource
  hints:
    openWorld: true
    readOnly: true
  name: describe-live-source
- description: CreateLiveSource
  hints:
    openWorld: true
    readOnly: false
  name: create-live-source
---
