---
categories: []
consumed_apis:
- eventbridge_scheduler
description: Unified capability for managing Amazon EventBridge Scheduler resources. Combines Amazon EventBridge Scheduler APIs for DevOps Engineer workflows in Task Scheduling.
layout: capability
name: Amazon EventBridge Scheduler Management
operations:
- description: Amazon EventBridge Scheduler GetSchedule
  method: GET
  name: GetSchedule
  path: /v1/GetSchedule
- description: Amazon EventBridge Scheduler CreateSchedule
  method: POST
  name: CreateSchedule
  path: /v1/CreateSchedule
- description: Amazon EventBridge Scheduler UpdateSchedule
  method: POST
  name: UpdateSchedule
  path: /v1/UpdateSchedule
- description: Amazon EventBridge Scheduler DeleteSchedule
  method: POST
  name: DeleteSchedule
  path: /v1/DeleteSchedule
- description: Amazon EventBridge Scheduler GetScheduleGroup
  method: GET
  name: GetScheduleGroup
  path: /v1/GetScheduleGroup
- description: Amazon EventBridge Scheduler CreateScheduleGroup
  method: POST
  name: CreateScheduleGroup
  path: /v1/CreateScheduleGroup
- description: Amazon EventBridge Scheduler DeleteScheduleGroup
  method: POST
  name: DeleteScheduleGroup
  path: /v1/DeleteScheduleGroup
- description: Amazon EventBridge Scheduler ListScheduleGroups
  method: GET
  name: ListScheduleGroups
  path: /v1/ListScheduleGroups
- description: Amazon EventBridge Scheduler ListSchedules
  method: GET
  name: ListSchedules
  path: /v1/ListSchedules
- description: Amazon EventBridge Scheduler ListTagsForResource
  method: GET
  name: ListTagsForResource
  path: /v1/ListTagsForResource
- description: Amazon EventBridge Scheduler TagResource
  method: POST
  name: TagResource
  path: /v1/TagResource
- description: Amazon EventBridge Scheduler UntagResource
  method: POST
  name: UntagResource
  path: /v1/UntagResource
personas: []
provider_name: Amazon EventBridge Scheduler
provider_slug: amazon-eventbridge-scheduler
search_terms:
- developers building applications using amazon eventbridge scheduler
- amazon eventbridge scheduler listschedulegroups
- cron
- amazon eventbridge scheduler listtagsforresource
- unified capability for managing amazon eventbridge scheduler resources. combines amazon eventbridge scheduler apis for devops engineer workflows in task scheduling.
- ListScheduleGroups
- event-driven
- amazon eventbridge scheduler deleteschedulegroup
- UpdateSchedule
- scheduling
- amazon eventbridge scheduler getschedule
- GetSchedule
- amazon eventbridge scheduler deleteschedule
- amazon eventbridge scheduler listschedules
- serverless
- operations teams managing amazon eventbridge scheduler infrastructure
- amazon eventbridge scheduler createschedule
- DeleteScheduleGroup
- UntagResource
- amazon eventbridge scheduler getschedulegroup
- CreateScheduleGroup
- amazon web services
- ListSchedules
- aws
- amazon eventbridge scheduler updateschedule
- GetScheduleGroup
- fully managed scheduling service for running tasks at scale
- CreateSchedule
- ListTagsForResource
- DeleteSchedule
- amazon eventbridge scheduler tagresource
- amazon eventbridge scheduler createschedulegroup
- amazon eventbridge scheduler untagresource
- TagResource
slug: amazon-eventbridge-scheduler-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon EventBridge Scheduler Management\n  description: Unified capability for managing Amazon EventBridge Scheduler resources. Combines Amazon EventBridge Scheduler APIs for DevOps Engineer workflows in Task Scheduling.\n  tags:\n  - Amazon Web Services\n  - Scheduling\n  - Serverless\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: eventbridge_scheduler\n    location: ./shared/eventbridge-scheduler.yaml\n  exposes:\n  - type: rest\n    port: 8194\n    namespace: amazon-eventbridge-scheduler-workflow-api\n    description: Unified REST API for Amazon EventBridge Scheduler management.\n    resources:\n    - path: /v1/GetSchedule\n      name: GetSchedule\n      description: Amazon EventBridge Scheduler GetSchedule\n      operations:\n      - method: GET\n        name: GetSchedule\n        description: Amazon\
  \ EventBridge Scheduler GetSchedule\n        call: api.GetSchedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateSchedule\n      name: CreateSchedule\n      description: Amazon EventBridge Scheduler CreateSchedule\n      operations:\n      - method: POST\n        name: CreateSchedule\n        description: Amazon EventBridge Scheduler CreateSchedule\n        call: api.CreateSchedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UpdateSchedule\n      name: UpdateSchedule\n      description: Amazon EventBridge Scheduler UpdateSchedule\n      operations:\n      - method: POST\n        name: UpdateSchedule\n        description: Amazon EventBridge Scheduler UpdateSchedule\n        call: api.UpdateSchedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteSchedule\n      name: DeleteSchedule\n      description: Amazon EventBridge Scheduler DeleteSchedule\n\
  \      operations:\n      - method: POST\n        name: DeleteSchedule\n        description: Amazon EventBridge Scheduler DeleteSchedule\n        call: api.DeleteSchedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/GetScheduleGroup\n      name: GetScheduleGroup\n      description: Amazon EventBridge Scheduler GetScheduleGroup\n      operations:\n      - method: GET\n        name: GetScheduleGroup\n        description: Amazon EventBridge Scheduler GetScheduleGroup\n        call: api.GetScheduleGroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateScheduleGroup\n      name: CreateScheduleGroup\n      description: Amazon EventBridge Scheduler CreateScheduleGroup\n      operations:\n      - method: POST\n        name: CreateScheduleGroup\n        description: Amazon EventBridge Scheduler CreateScheduleGroup\n        call: api.CreateScheduleGroup\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/DeleteScheduleGroup\n      name: DeleteScheduleGroup\n      description: Amazon EventBridge Scheduler DeleteScheduleGroup\n      operations:\n      - method: POST\n        name: DeleteScheduleGroup\n        description: Amazon EventBridge Scheduler DeleteScheduleGroup\n        call: api.DeleteScheduleGroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListScheduleGroups\n      name: ListScheduleGroups\n      description: Amazon EventBridge Scheduler ListScheduleGroups\n      operations:\n      - method: GET\n        name: ListScheduleGroups\n        description: Amazon EventBridge Scheduler ListScheduleGroups\n        call: api.ListScheduleGroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListSchedules\n      name: ListSchedules\n      description: Amazon EventBridge Scheduler ListSchedules\n      operations:\n      - method: GET\n        name: ListSchedules\n\
  \        description: Amazon EventBridge Scheduler ListSchedules\n        call: api.ListSchedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListTagsForResource\n      name: ListTagsForResource\n      description: Amazon EventBridge Scheduler ListTagsForResource\n      operations:\n      - method: GET\n        name: ListTagsForResource\n        description: Amazon EventBridge Scheduler ListTagsForResource\n        call: api.ListTagsForResource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/TagResource\n      name: TagResource\n      description: Amazon EventBridge Scheduler TagResource\n      operations:\n      - method: POST\n        name: TagResource\n        description: Amazon EventBridge Scheduler TagResource\n        call: api.TagResource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UntagResource\n      name: UntagResource\n      description: Amazon\
  \ EventBridge Scheduler UntagResource\n      operations:\n      - method: POST\n        name: UntagResource\n        description: Amazon EventBridge Scheduler UntagResource\n        call: api.UntagResource\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9204\n    namespace: amazon-eventbridge-scheduler-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon EventBridge Scheduler management.\n    tools:\n    - name: GetSchedule\n      description: Amazon EventBridge Scheduler GetSchedule\n      hints:\n        readOnly: true\n      call: api.GetSchedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateSchedule\n      description: Amazon EventBridge Scheduler CreateSchedule\n      hints:\n        readOnly: false\n      call: api.CreateSchedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdateSchedule\n      description: Amazon EventBridge Scheduler\
  \ UpdateSchedule\n      hints:\n        readOnly: false\n      call: api.UpdateSchedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeleteSchedule\n      description: Amazon EventBridge Scheduler DeleteSchedule\n      hints:\n        readOnly: false\n      call: api.DeleteSchedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: GetScheduleGroup\n      description: Amazon EventBridge Scheduler GetScheduleGroup\n      hints:\n        readOnly: true\n      call: api.GetScheduleGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateScheduleGroup\n      description: Amazon EventBridge Scheduler CreateScheduleGroup\n      hints:\n        readOnly: false\n      call: api.CreateScheduleGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeleteScheduleGroup\n      description: Amazon EventBridge Scheduler DeleteScheduleGroup\n      hints:\n        readOnly:\
  \ false\n      call: api.DeleteScheduleGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListScheduleGroups\n      description: Amazon EventBridge Scheduler ListScheduleGroups\n      hints:\n        readOnly: true\n      call: api.ListScheduleGroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListSchedules\n      description: Amazon EventBridge Scheduler ListSchedules\n      hints:\n        readOnly: true\n      call: api.ListSchedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListTagsForResource\n      description: Amazon EventBridge Scheduler ListTagsForResource\n      hints:\n        readOnly: true\n      call: api.ListTagsForResource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: TagResource\n      description: Amazon EventBridge Scheduler TagResource\n      hints:\n        readOnly: false\n      call: api.TagResource\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: UntagResource\n      description: Amazon EventBridge Scheduler UntagResource\n      hints:\n        readOnly: false\n      call: api.UntagResource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge-scheduler/refs/heads/main/capabilities/amazon-eventbridge-scheduler-capability.yaml
tags:
- Amazon Web Services
- Scheduling
- Serverless
tools:
- description: Amazon EventBridge Scheduler GetSchedule
  hints:
    readOnly: true
  name: GetSchedule
- description: Amazon EventBridge Scheduler CreateSchedule
  hints:
    readOnly: false
  name: CreateSchedule
- description: Amazon EventBridge Scheduler UpdateSchedule
  hints:
    readOnly: false
  name: UpdateSchedule
- description: Amazon EventBridge Scheduler DeleteSchedule
  hints:
    readOnly: false
  name: DeleteSchedule
- description: Amazon EventBridge Scheduler GetScheduleGroup
  hints:
    readOnly: true
  name: GetScheduleGroup
- description: Amazon EventBridge Scheduler CreateScheduleGroup
  hints:
    readOnly: false
  name: CreateScheduleGroup
- description: Amazon EventBridge Scheduler DeleteScheduleGroup
  hints:
    readOnly: false
  name: DeleteScheduleGroup
- description: Amazon EventBridge Scheduler ListScheduleGroups
  hints:
    readOnly: true
  name: ListScheduleGroups
- description: Amazon EventBridge Scheduler ListSchedules
  hints:
    readOnly: true
  name: ListSchedules
- description: Amazon EventBridge Scheduler ListTagsForResource
  hints:
    readOnly: true
  name: ListTagsForResource
- description: Amazon EventBridge Scheduler TagResource
  hints:
    readOnly: false
  name: TagResource
- description: Amazon EventBridge Scheduler UntagResource
  hints:
    readOnly: false
  name: UntagResource
---
