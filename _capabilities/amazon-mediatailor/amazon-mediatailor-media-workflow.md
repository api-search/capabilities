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
- createlivesource
- describe live source
- broadcasting
- create live source
- createchannel
- workflow
- list jobs
- create channel
- describelivesource
- Media Developer
- configurelogsforchannel
- describe channel
- configure logs for channel
- Broadcast Engineer
- update channel
- aws media processing and delivery
- media processing
- updatechannel
- aws
- deletechannel
- describechannel
- configurelogsforplaybackconfiguration
- manage media processing jobs
- amazon mediatailor media processing workflow
- engineer managing broadcast media workflows
- developer building media processing applications
- media
- delete channel
- configure logs for playback configuration
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
