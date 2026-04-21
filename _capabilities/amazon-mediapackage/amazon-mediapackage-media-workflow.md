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
- configure logs
- aws
- list harvest jobs
- developer building media processing applications
- media processing
- media
- aws media processing and delivery
- listchannels
- describe channel
- list channels
- workflow
- createoriginendpoint
- amazon mediapackage media processing workflow
- create harvest job
- createchannel
- describechannel
- list origin endpoints
- Broadcast Engineer
- create origin endpoint
- create channel
- engineer managing broadcast media workflows
- listoriginendpoints
- createharvestjob
- manage media processing jobs
- list jobs
- broadcasting
- configurelogs
- Media Developer
- listharvestjobs
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
