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
- media
- manage media processing jobs
- create harvest job
- list harvest jobs
- describe channel
- list origin endpoints
- listharvestjobs
- describechannel
- create channel
- configure logs
- createchannel
- aws
- list jobs
- createoriginendpoint
- create origin endpoint
- developer building media processing applications
- media processing
- workflow
- amazon mediapackage media processing workflow
- Media Developer
- engineer managing broadcast media workflows
- broadcasting
- listoriginendpoints
- createharvestjob
- aws media processing and delivery
- list channels
- configurelogs
- listchannels
- Broadcast Engineer
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
