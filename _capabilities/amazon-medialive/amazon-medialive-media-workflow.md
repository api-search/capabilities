---
categories: []
consumed_apis:
- medialive
description: Workflow capability for Amazon MediaLive media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaLive Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaLive
provider_slug: amazon-medialive
search_terms:
- Broadcast Engineer
- broadcasting
- media
- media processing
- batchupdateschedule
- workflow
- cancelinputdevicetransfer
- amazon medialive media processing workflow
- batch update schedule
- aws media processing and delivery
- acceptinputdevicetransfer
- batch delete
- describeschedule
- cancel input device transfer
- deleteschedule
- describe schedule
- accept input device transfer
- delete schedule
- list jobs
- Media Developer
- engineer managing broadcast media workflows
- developer building media processing applications
- batchstop
- batchdelete
- batch start
- manage media processing jobs
- batchstart
- aws
- batch stop
slug: amazon-medialive-media-workflow
source_filename: amazon-medialive-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaLive Workflow\n  description: Workflow capability for Amazon MediaLive media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: medialive\n    location: ./shared/medialive.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: medialive-workflow-api\n    description: Unified REST API for Amazon MediaLive workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: medialive.list-jobs\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: medialive-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaLive workflow management.\n    tools:\n    - name: accept-input-device-transfer\n      description: AcceptInputDeviceTransfer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.accept-input-device-transfer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-delete\n      description: BatchDelete\n      hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.batch-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-start\n      description: BatchStart\n      hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.batch-start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-stop\n      description: BatchStop\n     \
  \ hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.batch-stop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-schedule\n      description: DescribeSchedule\n      hints:\n        readOnly: true\n        openWorld: true\n      call: medialive.describe-schedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-update-schedule\n      description: BatchUpdateSchedule\n      hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.batch-update-schedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-schedule\n      description: DeleteSchedule\n      hints:\n        readOnly: false\n        openWorld: true\n      call: medialive.delete-schedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-input-device-transfer\n      description: CancelInputDeviceTransfer\n      hints:\n        readOnly:\
  \ false\n        openWorld: true\n      call: medialive.cancel-input-device-transfer\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-medialive/refs/heads/main/capabilities/amazon-medialive-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: AcceptInputDeviceTransfer
  hints:
    openWorld: true
    readOnly: false
  name: accept-input-device-transfer
- description: BatchDelete
  hints:
    openWorld: true
    readOnly: false
  name: batch-delete
- description: BatchStart
  hints:
    openWorld: true
    readOnly: false
  name: batch-start
- description: BatchStop
  hints:
    openWorld: true
    readOnly: false
  name: batch-stop
- description: DescribeSchedule
  hints:
    openWorld: true
    readOnly: true
  name: describe-schedule
- description: BatchUpdateSchedule
  hints:
    openWorld: true
    readOnly: false
  name: batch-update-schedule
- description: DeleteSchedule
  hints:
    openWorld: true
    readOnly: false
  name: delete-schedule
- description: CancelInputDeviceTransfer
  hints:
    openWorld: true
    readOnly: false
  name: cancel-input-device-transfer
---
