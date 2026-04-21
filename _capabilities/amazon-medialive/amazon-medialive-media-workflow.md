---
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
- delete schedule
- cancel input device transfer
- accept input device transfer
- engineer managing broadcast media workflows
- broadcasting
- batchstop
- batch start
- Media Developer
- manage media processing jobs
- describeschedule
- developer building media processing applications
- deleteschedule
- batchupdateschedule
- cancelinputdevicetransfer
- batchdelete
- batch stop
- workflow
- media processing
- batch update schedule
- list jobs
- amazon medialive media processing workflow
- batchstart
- describe schedule
- batch delete
- aws
- aws media processing and delivery
- acceptinputdevicetransfer
- media
slug: amazon-medialive-media-workflow
tags:
- AWS
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
