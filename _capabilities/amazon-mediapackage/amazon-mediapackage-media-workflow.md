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
- developer building media processing applications
- createoriginendpoint
- list jobs
- listchannels
- create origin endpoint
- describe channel
- manage media processing jobs
- engineer managing broadcast media workflows
- listharvestjobs
- aws
- list channels
- create harvest job
- configure logs
- configurelogs
- listoriginendpoints
- list harvest jobs
- createchannel
- createharvestjob
- Broadcast Engineer
- workflow
- Media Developer
- aws media processing and delivery
- media
- create channel
- broadcasting
- media processing
- describechannel
- amazon mediapackage media processing workflow
- list origin endpoints
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
