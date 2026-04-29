---
categories: []
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
- delete channel
- amazon mediatailor media processing workflow
- createchannel
- media
- update channel
- manage media processing jobs
- list jobs
- configurelogsforchannel
- describechannel
- workflow
- describe live source
- developer building media processing applications
- deletechannel
- Media Developer
- create live source
- aws
- aws media processing and delivery
- broadcasting
- describe channel
- configurelogsforplaybackconfiguration
- engineer managing broadcast media workflows
- createlivesource
- create channel
- configure logs for channel
- updatechannel
- configure logs for playback configuration
- describelivesource
- media processing
slug: amazon-mediatailor-media-workflow
source_filename: amazon-mediatailor-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaTailor Workflow\n  description: Workflow capability for Amazon MediaTailor media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mediatailor\n    location: ./shared/mediatailor.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediatailor-workflow-api\n    description: Unified REST API for Amazon MediaTailor workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediatailor.list-jobs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediatailor-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaTailor workflow management.\n    tools:\n    - name: configure-logs-for-channel\n      description: ConfigureLogsForChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.configure-logs-for-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: configure-logs-for-playback-configuration\n      description: ConfigureLogsForPlaybackConfiguration\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.configure-logs-for-playback-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-channel\n      description: DescribeChannel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediatailor.describe-channel\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-channel\n      description: CreateChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.create-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-channel\n      description: UpdateChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.update-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-channel\n      description: DeleteChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.delete-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-live-source\n      description: DescribeLiveSource\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediatailor.describe-live-source\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: create-live-source\n      description: CreateLiveSource\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediatailor.create-live-source\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediatailor/refs/heads/main/capabilities/amazon-mediatailor-media-workflow.yaml
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
