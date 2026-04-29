---
categories: []
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
- createoriginendpoint
- Broadcast Engineer
- engineer managing broadcast media workflows
- developer building media processing applications
- list jobs
- createchannel
- configurelogs
- workflow
- broadcasting
- configure logs
- create origin endpoint
- manage media processing jobs
- create channel
- Media Developer
- list channels
- describechannel
- listharvestjobs
- createharvestjob
- describe channel
- list harvest jobs
- amazon mediapackage media processing workflow
- listoriginendpoints
- media processing
- aws media processing and delivery
- aws
- listchannels
- create harvest job
- list origin endpoints
slug: amazon-mediapackage-media-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaPackage Workflow\n  description: Workflow capability for Amazon MediaPackage media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mediapackage\n    location: ./shared/mediapackage.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediapackage-workflow-api\n    description: Unified REST API for Amazon MediaPackage workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediapackage.list-jobs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediapackage-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaPackage workflow management.\n    tools:\n    - name: configure-logs\n      description: ConfigureLogs\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.configure-logs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-channels\n      description: ListChannels\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-channel\n      description: CreateChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-harvest-jobs\n      description: ListHarvestJobs\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-harvest-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-harvest-job\n      description: CreateHarvestJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-harvest-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-origin-endpoints\n      description: ListOriginEndpoints\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-origin-endpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-origin-endpoint\n      description: CreateOriginEndpoint\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-origin-endpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-channel\n      description: DescribeChannel\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.describe-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediapackage/refs/heads/main/capabilities/amazon-mediapackage-media-workflow.yaml
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
