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
- configurelogs
- createoriginendpoint
- create origin endpoint
- aws media processing and delivery
- list origin endpoints
- media processing
- listharvestjobs
- listchannels
- broadcasting
- list jobs
- workflow
- listoriginendpoints
- engineer managing broadcast media workflows
- list harvest jobs
- amazon mediapackage media processing workflow
- configure logs
- create harvest job
- create channel
- describechannel
- list channels
- Broadcast Engineer
- media
- aws
- Media Developer
- createchannel
- developer building media processing applications
- describe channel
- createharvestjob
- manage media processing jobs
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
