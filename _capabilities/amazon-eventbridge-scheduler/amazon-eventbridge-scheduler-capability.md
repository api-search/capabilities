---
categories: []
consumed_apis: []
description: Amazon EventBridge Scheduler is a serverless scheduler that allows you to create, run, and manage tasks from one central, managed service. EventBridge Scheduler delivers your tasks reliably, with built-in mechanisms that adjust your schedules based on the availability of downstream targets. The following reference lists the available API actions, and data types for EventBridge Scheduler.
layout: capability
name: Amazon EventBridge Scheduler
operations:
- description: Amazon EventBridge Scheduler CreateSchedule
  method: POST
  name: createschedule
  path: /schedules/{Name}
- description: Amazon EventBridge Scheduler DeleteSchedule
  method: DELETE
  name: deleteschedule
  path: /schedules/{Name}
- description: Amazon EventBridge Scheduler GetSchedule
  method: GET
  name: getschedule
  path: /schedules/{Name}
- description: Amazon EventBridge Scheduler UpdateSchedule
  method: PUT
  name: updateschedule
  path: /schedules/{Name}
- description: Amazon EventBridge Scheduler CreateScheduleGroup
  method: POST
  name: createschedulegroup
  path: /schedule-groups/{Name}
- description: Amazon EventBridge Scheduler DeleteScheduleGroup
  method: DELETE
  name: deleteschedulegroup
  path: /schedule-groups/{Name}
- description: Amazon EventBridge Scheduler GetScheduleGroup
  method: GET
  name: getschedulegroup
  path: /schedule-groups/{Name}
- description: Amazon EventBridge Scheduler ListScheduleGroups
  method: GET
  name: listschedulegroups
  path: /schedule-groups
- description: Amazon EventBridge Scheduler ListSchedules
  method: GET
  name: listschedules
  path: /schedules
- description: Amazon EventBridge Scheduler ListTagsForResource
  method: GET
  name: listtagsforresource
  path: /tags/{ResourceArn}
- description: Amazon EventBridge Scheduler TagResource
  method: POST
  name: tagresource
  path: /tags/{ResourceArn}
- description: Amazon EventBridge Scheduler UntagResource
  method: DELETE
  name: untagresource
  path: /tags/{ResourceArn}#TagKeys
personas: []
provider_name: Amazon EventBridge Scheduler
provider_slug: amazon-eventbridge-scheduler
search_terms:
- eventbridge
- listtagsforresource
- event-driven
- amazon eventbridge scheduler createschedulegroup
- amazon eventbridge scheduler getschedule
- unified capability for managing amazon eventbridge scheduler resources. combines amazon eventbridge scheduler apis for devops engineer workflows in task scheduling.
- amazon web services
- scheduler
- api
- listschedules
- amazon eventbridge scheduler tagresource
- fully managed scheduling service for running tasks at scale
- amazon eventbridge scheduler getschedulegroup
- amazon
- deleteschedulegroup
- amazon eventbridge scheduler untagresource
- developers building applications using amazon eventbridge scheduler
- getschedulegroup
- getschedule
- amazon eventbridge scheduler listschedules
- deleteschedule
- serverless
- createschedulegroup
- amazon eventbridge scheduler listschedulegroups
- tagresource
- listschedulegroups
- createschedule
- cron
- untagresource
- amazon eventbridge scheduler deleteschedule
- amazon eventbridge scheduler updateschedule
- amazon eventbridge scheduler createschedule
- operations teams managing amazon eventbridge scheduler infrastructure
- amazon eventbridge scheduler deleteschedulegroup
- scheduling
- amazon eventbridge scheduler listtagsforresource
- updateschedule
slug: amazon-eventbridge-scheduler-capability
source_filename: amazon-eventbridge-scheduler-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EventBridge Scheduler\n  description: Amazon EventBridge Scheduler is a serverless scheduler that allows you to create, run, and manage tasks from\n    one central, managed service. EventBridge Scheduler delivers your tasks reliably, with built-in mechanisms that adjust\n    your schedules based on the availability of downstream targets. The following reference lists the available API actions,\n    and data types for EventBridge Scheduler.\n  tags:\n  - Amazon\n  - Eventbridge\n  - Scheduler\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-eventbridge-scheduler\n    baseUri: http://scheduler.us-east-1.amazonaws.com\n    description: Amazon EventBridge Scheduler HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_EVENTBRIDGE_SCHEDULER_TOKEN}}'\n    resources:\n    - name: schedules-name\n\
  \      path: /schedules/{Name}\n      operations:\n      - name: createschedule\n        method: POST\n        description: Amazon EventBridge Scheduler CreateSchedule\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule that you are creating.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteschedule\n        method: DELETE\n        description: Amazon EventBridge Scheduler DeleteSchedule\n        inputParameters:\n        - name: clientToken\n          in: query\n          type: string\n          description: Unique, case-sensitive identifier you provide to ensure the idempotency of the request. If you do not\n            specify a client token, EventBridge Scheduler uses a rando\n        - name: groupName\n          in: query\n          type: string\n          description: The\
  \ name of the schedule group associated with this schedule. If you omit this, the default schedule\n            group is used.\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getschedule\n        method: GET\n        description: Amazon EventBridge Scheduler GetSchedule\n        inputParameters:\n        - name: groupName\n          in: query\n          type: string\n          description: The name of the schedule group associated with this schedule. If you omit this, EventBridge Scheduler\n            assumes that the schedule is associated with the default g\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule to retrieve.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateschedule\n        method: PUT\n        description: Amazon EventBridge Scheduler UpdateSchedule\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule that you are updating.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedule-groups-name\n      path: /schedule-groups/{Name}\n      operations:\n      - name: createschedulegroup\n        method: POST\n        description: Amazon EventBridge Scheduler CreateScheduleGroup\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule group that you are creating.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleteschedulegroup\n        method: DELETE\n        description: Amazon EventBridge Scheduler DeleteScheduleGroup\n        inputParameters:\n        - name: clientToken\n          in: query\n          type: string\n          description: Unique, case-sensitive identifier you provide to ensure the idempotency of the request. If you do not\n            specify a client token, EventBridge Scheduler uses a rando\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the schedule group to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getschedulegroup\n        method: GET\n        description: Amazon EventBridge Scheduler GetScheduleGroup\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n   \
  \       required: true\n          description: The name of the schedule group to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedule-groups\n      path: /schedule-groups\n      operations:\n      - name: listschedulegroups\n        method: GET\n        description: Amazon EventBridge Scheduler ListScheduleGroups\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: integer\n          description: If specified, limits the number of results returned by this operation. The operation also returns a\n            <code>NextToken</code> which you can use in a subsequent ope\n        - name: NamePrefix\n          in: query\n          type: string\n          description: The name prefix that you can use to return a filtered list of your schedule groups.\n        - name: NextToken\n          in: query\n          type: string\n          description: The\
  \ token returned by a previous call to retrieve the next set of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description: Amazon EventBridge Scheduler ListSchedules\n        inputParameters:\n        - name: ScheduleGroup\n          in: query\n          type: string\n          description: If specified, only lists the schedules whose associated schedule group matches the given filter.\n        - name: MaxResults\n          in: query\n          type: integer\n          description: If specified, limits the number of results returned by this operation. The operation also returns a\n            <code>NextToken</code> which you can use in a subsequent ope\n        - name: NamePrefix\n          in: query\n          type: string\n          description: Schedule name prefix to return\
  \ the filtered list of resources.\n        - name: NextToken\n          in: query\n          type: string\n          description: The token returned by a previous call to retrieve the next set of results.\n        - name: State\n          in: query\n          type: string\n          description: If specified, only lists the schedules whose current state matches the given filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn\n      path: /tags/{ResourceArn}\n      operations:\n      - name: listtagsforresource\n        method: GET\n        description: Amazon EventBridge Scheduler ListTagsForResource\n        inputParameters:\n        - name: ResourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the EventBridge Scheduler resource for which you want to view tags.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: tagresource\n        method: POST\n        description: Amazon EventBridge Scheduler TagResource\n        inputParameters:\n        - name: ResourceArn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the schedule group that you are adding tags to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn-tagkeys\n      path: /tags/{ResourceArn}#TagKeys\n      operations:\n      - name: untagresource\n        method: DELETE\n        description: Amazon EventBridge Scheduler UntagResource\n        inputParameters:\n        - name: ResourceArn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the schedule group from which you are removing tags.\n       \
  \ - name: TagKeys\n          in: query\n          type: array\n          required: true\n          description: The list of tag keys to remove from the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-eventbridge-scheduler-rest\n    description: REST adapter for Amazon EventBridge Scheduler.\n    resources:\n    - path: /schedules/{Name}\n      name: createschedule\n      operations:\n      - method: POST\n        name: createschedule\n        description: Amazon EventBridge Scheduler CreateSchedule\n        call: amazon-eventbridge-scheduler.createschedule\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{Name}\n      name: deleteschedule\n      operations:\n      - method: DELETE\n        name: deleteschedule\n        description: Amazon EventBridge\
  \ Scheduler DeleteSchedule\n        call: amazon-eventbridge-scheduler.deleteschedule\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{Name}\n      name: getschedule\n      operations:\n      - method: GET\n        name: getschedule\n        description: Amazon EventBridge Scheduler GetSchedule\n        call: amazon-eventbridge-scheduler.getschedule\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{Name}\n      name: updateschedule\n      operations:\n      - method: PUT\n        name: updateschedule\n        description: Amazon EventBridge Scheduler UpdateSchedule\n        call: amazon-eventbridge-scheduler.updateschedule\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule-groups/{Name}\n      name: createschedulegroup\n\
  \      operations:\n      - method: POST\n        name: createschedulegroup\n        description: Amazon EventBridge Scheduler CreateScheduleGroup\n        call: amazon-eventbridge-scheduler.createschedulegroup\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule-groups/{Name}\n      name: deleteschedulegroup\n      operations:\n      - method: DELETE\n        name: deleteschedulegroup\n        description: Amazon EventBridge Scheduler DeleteScheduleGroup\n        call: amazon-eventbridge-scheduler.deleteschedulegroup\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule-groups/{Name}\n      name: getschedulegroup\n      operations:\n      - method: GET\n        name: getschedulegroup\n        description: Amazon EventBridge Scheduler GetScheduleGroup\n        call: amazon-eventbridge-scheduler.getschedulegroup\n    \
  \    with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule-groups\n      name: listschedulegroups\n      operations:\n      - method: GET\n        name: listschedulegroups\n        description: Amazon EventBridge Scheduler ListScheduleGroups\n        call: amazon-eventbridge-scheduler.listschedulegroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: Amazon EventBridge Scheduler ListSchedules\n        call: amazon-eventbridge-scheduler.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{ResourceArn}\n      name: listtagsforresource\n      operations:\n      - method: GET\n        name: listtagsforresource\n        description: Amazon EventBridge Scheduler ListTagsForResource\n        call: amazon-eventbridge-scheduler.listtagsforresource\n\
  \        with:\n          ResourceArn: rest.ResourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{ResourceArn}\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: Amazon EventBridge Scheduler TagResource\n        call: amazon-eventbridge-scheduler.tagresource\n        with:\n          ResourceArn: rest.ResourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{ResourceArn}#TagKeys\n      name: untagresource\n      operations:\n      - method: DELETE\n        name: untagresource\n        description: Amazon EventBridge Scheduler UntagResource\n        call: amazon-eventbridge-scheduler.untagresource\n        with:\n          ResourceArn: rest.ResourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-eventbridge-scheduler-mcp\n    transport: http\n\
  \    description: MCP adapter for Amazon EventBridge Scheduler for AI agent use.\n    tools:\n    - name: createschedule\n      description: Amazon EventBridge Scheduler CreateSchedule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-scheduler.createschedule\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the schedule that you are creating.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteschedule\n      description: Amazon EventBridge Scheduler DeleteSchedule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-eventbridge-scheduler.deleteschedule\n      with:\n        Name: tools.Name\n        clientToken: tools.clientToken\n        groupName: tools.groupName\n      inputParameters:\n      - name: Name\n\
  \        type: string\n        description: The name of the schedule to delete.\n        required: true\n      - name: clientToken\n        type: string\n        description: Unique, case-sensitive identifier you provide to ensure the idempotency of the request. If you do not\n          specify a client token, EventBridge Scheduler uses a rando\n      - name: groupName\n        type: string\n        description: The name of the schedule group associated with this schedule. If you omit this, the default schedule\n          group is used.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getschedule\n      description: Amazon EventBridge Scheduler GetSchedule\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.getschedule\n      with:\n        Name: tools.Name\n        groupName: tools.groupName\n      inputParameters:\n      - name: Name\n        type: string\n        description:\
  \ The name of the schedule to retrieve.\n        required: true\n      - name: groupName\n        type: string\n        description: The name of the schedule group associated with this schedule. If you omit this, EventBridge Scheduler\n          assumes that the schedule is associated with the default g\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateschedule\n      description: Amazon EventBridge Scheduler UpdateSchedule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.updateschedule\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the schedule that you are updating.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createschedulegroup\n      description: Amazon EventBridge Scheduler CreateScheduleGroup\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-scheduler.createschedulegroup\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the schedule group that you are creating.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteschedulegroup\n      description: Amazon EventBridge Scheduler DeleteScheduleGroup\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-eventbridge-scheduler.deleteschedulegroup\n      with:\n        Name: tools.Name\n        clientToken: tools.clientToken\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the schedule group to delete.\n        required: true\n      - name: clientToken\n        type: string\n        description: Unique, case-sensitive identifier\
  \ you provide to ensure the idempotency of the request. If you do not\n          specify a client token, EventBridge Scheduler uses a rando\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getschedulegroup\n      description: Amazon EventBridge Scheduler GetScheduleGroup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.getschedulegroup\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the schedule group to retrieve.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedulegroups\n      description: Amazon EventBridge Scheduler ListScheduleGroups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.listschedulegroups\n      with:\n        MaxResults:\
  \ tools.MaxResults\n        NamePrefix: tools.NamePrefix\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n        type: integer\n        description: If specified, limits the number of results returned by this operation. The operation also returns a <code>NextToken</code>\n          which you can use in a subsequent ope\n      - name: NamePrefix\n        type: string\n        description: The name prefix that you can use to return a filtered list of your schedule groups.\n      - name: NextToken\n        type: string\n        description: The token returned by a previous call to retrieve the next set of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedules\n      description: Amazon EventBridge Scheduler ListSchedules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.listschedules\n      with:\n        ScheduleGroup:\
  \ tools.ScheduleGroup\n        MaxResults: tools.MaxResults\n        NamePrefix: tools.NamePrefix\n        NextToken: tools.NextToken\n        State: tools.State\n      inputParameters:\n      - name: ScheduleGroup\n        type: string\n        description: If specified, only lists the schedules whose associated schedule group matches the given filter.\n      - name: MaxResults\n        type: integer\n        description: If specified, limits the number of results returned by this operation. The operation also returns a <code>NextToken</code>\n          which you can use in a subsequent ope\n      - name: NamePrefix\n        type: string\n        description: Schedule name prefix to return the filtered list of resources.\n      - name: NextToken\n        type: string\n        description: The token returned by a previous call to retrieve the next set of results.\n      - name: State\n        type: string\n        description: If specified, only lists the schedules whose current state\
  \ matches the given filter.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: Amazon EventBridge Scheduler ListTagsForResource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-scheduler.listtagsforresource\n      with:\n        ResourceArn: tools.ResourceArn\n      inputParameters:\n      - name: ResourceArn\n        type: string\n        description: The ARN of the EventBridge Scheduler resource for which you want to view tags.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: Amazon EventBridge Scheduler TagResource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-scheduler.tagresource\n      with:\n        ResourceArn: tools.ResourceArn\n      inputParameters:\n      - name: ResourceArn\n\
  \        type: string\n        description: The Amazon Resource Name (ARN) of the schedule group that you are adding tags to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untagresource\n      description: Amazon EventBridge Scheduler UntagResource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-eventbridge-scheduler.untagresource\n      with:\n        ResourceArn: tools.ResourceArn\n        TagKeys: tools.TagKeys\n      inputParameters:\n      - name: ResourceArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the schedule group from which you are removing tags.\n        required: true\n      - name: TagKeys\n        type: array\n        description: The list of tag keys to remove from the resource.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_EVENTBRIDGE_SCHEDULER_TOKEN:\
  \ AMAZON_EVENTBRIDGE_SCHEDULER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge-scheduler/refs/heads/main/capabilities/amazon-eventbridge-scheduler-capability.yaml
tags:
- Amazon
- Eventbridge
- Scheduler
- API
tools:
- description: Amazon EventBridge Scheduler CreateSchedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschedule
- description: Amazon EventBridge Scheduler DeleteSchedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschedule
- description: Amazon EventBridge Scheduler GetSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschedule
- description: Amazon EventBridge Scheduler UpdateSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateschedule
- description: Amazon EventBridge Scheduler CreateScheduleGroup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschedulegroup
- description: Amazon EventBridge Scheduler DeleteScheduleGroup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschedulegroup
- description: Amazon EventBridge Scheduler GetScheduleGroup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschedulegroup
- description: Amazon EventBridge Scheduler ListScheduleGroups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedulegroups
- description: Amazon EventBridge Scheduler ListSchedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: Amazon EventBridge Scheduler ListTagsForResource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtagsforresource
- description: Amazon EventBridge Scheduler TagResource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: Amazon EventBridge Scheduler UntagResource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: untagresource
---
