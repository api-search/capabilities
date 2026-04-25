---
consumed_apis:
- mediapackage
description: Workflow capability for Amazon MediaPackage media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaPackage Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaPackage
provider_slug: amazon-mediapackage
search_terms:
- createoriginendpoint
- list channels
- list harvest jobs
- broadcasting
- media
- configurelogs
- engineer managing broadcast media workflows
- list origin endpoints
- createchannel
- developer building media processing applications
- describechannel
- aws media processing and delivery
- list jobs
- listharvestjobs
- manage media processing jobs
- create harvest job
- create channel
- media processing
- listoriginendpoints
- workflow
- configure logs
- Media Developer
- createharvestjob
- describe channel
- listchannels
- amazon mediapackage media processing workflow
- aws
- Broadcast Engineer
- create origin endpoint
slug: amazon-mediapackage-media-workflow
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: ConfigureLogs
  hints:
    openWorld: true
    readOnly: false
  name: configure-logs
- description: ListChannels
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: CreateChannel
  hints:
    openWorld: true
    readOnly: false
  name: create-channel
- description: ListHarvestJobs
  hints:
    openWorld: true
    readOnly: true
  name: list-harvest-jobs
- description: CreateHarvestJob
  hints:
    openWorld: true
    readOnly: false
  name: create-harvest-job
- description: ListOriginEndpoints
  hints:
    openWorld: true
    readOnly: true
  name: list-origin-endpoints
- description: CreateOriginEndpoint
  hints:
    openWorld: true
    readOnly: false
  name: create-origin-endpoint
- description: DescribeChannel
  hints:
    openWorld: true
    readOnly: true
  name: describe-channel
---
