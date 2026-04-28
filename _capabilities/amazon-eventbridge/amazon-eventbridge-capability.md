---
categories: []
consumed_apis:
- eventbridge
description: Unified capability for managing Amazon EventBridge resources. Combines Amazon EventBridge APIs for Integration Engineer workflows in Event-Driven Architecture.
layout: capability
name: Amazon EventBridge Management
operations:
- description: Amazon EventBridge Put Events
  method: POST
  name: PutEvents
  path: /v1/PutEvents
- description: Amazon EventBridge Put Rule
  method: POST
  name: PutRule
  path: /v1/PutRule
- description: Amazon EventBridge Describe Rule
  method: POST
  name: DescribeRule
  path: /v1/DescribeRule
- description: Amazon EventBridge List Rules
  method: POST
  name: ListRules
  path: /v1/ListRules
- description: Amazon EventBridge Delete Rule
  method: POST
  name: DeleteRule
  path: /v1/DeleteRule
- description: Amazon EventBridge Put Targets
  method: POST
  name: PutTargets
  path: /v1/PutTargets
- description: Amazon EventBridge List Targets by Rule
  method: POST
  name: ListTargetsByRule
  path: /v1/ListTargetsByRule
- description: Amazon EventBridge Remove Targets
  method: POST
  name: RemoveTargets
  path: /v1/RemoveTargets
- description: Amazon EventBridge Create Event Bus
  method: POST
  name: CreateEventBus
  path: /v1/CreateEventBus
- description: Amazon EventBridge Describe Event Bus
  method: POST
  name: DescribeEventBus
  path: /v1/DescribeEventBus
- description: Amazon EventBridge List Event Buses
  method: POST
  name: ListEventBuses
  path: /v1/ListEventBuses
- description: Amazon EventBridge Delete Event Bus
  method: POST
  name: DeleteEventBus
  path: /v1/DeleteEventBus
- description: Amazon EventBridge Create Archive
  method: POST
  name: CreateArchive
  path: /v1/CreateArchive
- description: Amazon EventBridge List Archives
  method: POST
  name: ListArchives
  path: /v1/ListArchives
personas: []
provider_name: Amazon EventBridge
provider_slug: amazon-eventbridge
search_terms:
- CreateArchive
- amazon eventbridge delete event bus
- events
- ListEventBuses
- unified capability for managing amazon eventbridge resources. combines amazon eventbridge apis for integration engineer workflows in event-driven architecture.
- amazon eventbridge put rule
- serverless
- serverless event bus for connecting applications with real-time data
- amazon eventbridge create archive
- amazon eventbridge list targets by rule
- PutEvents
- amazon eventbridge list event buses
- amazon eventbridge put targets
- ListRules
- RemoveTargets
- DescribeRule
- event bus
- aws
- DeleteRule
- integration
- amazon eventbridge list rules
- amazon eventbridge remove targets
- PutRule
- amazon eventbridge create event bus
- operations teams managing amazon eventbridge infrastructure
- amazon web services
- amazon eventbridge delete rule
- DescribeEventBus
- CreateEventBus
- amazon eventbridge describe rule
- ListTargetsByRule
- amazon eventbridge describe event bus
- event-driven
- ListArchives
- developers building applications using amazon eventbridge
- amazon eventbridge put events
- DeleteEventBus
- PutTargets
- amazon eventbridge list archives
slug: amazon-eventbridge-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon EventBridge Management\n  description: Unified capability for managing Amazon EventBridge resources. Combines Amazon EventBridge APIs for Integration Engineer workflows in Event-Driven Architecture.\n  tags:\n  - Amazon Web Services\n  - Event Bus\n  - Serverless\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: eventbridge\n    location: ./shared/eventbridge.yaml\n  exposes:\n  - type: rest\n    port: 8196\n    namespace: amazon-eventbridge-workflow-api\n    description: Unified REST API for Amazon EventBridge management.\n    resources:\n    - path: /v1/PutEvents\n      name: PutEvents\n      description: Amazon EventBridge Put Events\n      operations:\n      - method: POST\n        name: PutEvents\n        description: Amazon EventBridge Put Events\n        call: api.PutEvents\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/PutRule\n      name: PutRule\n      description: Amazon EventBridge Put Rule\n      operations:\n      - method: POST\n        name: PutRule\n        description: Amazon EventBridge Put Rule\n        call: api.PutRule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DescribeRule\n      name: DescribeRule\n      description: Amazon EventBridge Describe Rule\n      operations:\n      - method: POST\n        name: DescribeRule\n        description: Amazon EventBridge Describe Rule\n        call: api.DescribeRule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListRules\n      name: ListRules\n      description: Amazon EventBridge List Rules\n      operations:\n      - method: POST\n        name: ListRules\n        description: Amazon EventBridge List Rules\n        call: api.ListRules\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/DeleteRule\n      name: DeleteRule\n      description: Amazon EventBridge Delete Rule\n      operations:\n      - method: POST\n        name: DeleteRule\n        description: Amazon EventBridge Delete Rule\n        call: api.DeleteRule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/PutTargets\n      name: PutTargets\n      description: Amazon EventBridge Put Targets\n      operations:\n      - method: POST\n        name: PutTargets\n        description: Amazon EventBridge Put Targets\n        call: api.PutTargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListTargetsByRule\n      name: ListTargetsByRule\n      description: Amazon EventBridge List Targets by Rule\n      operations:\n      - method: POST\n        name: ListTargetsByRule\n        description: Amazon EventBridge List Targets by Rule\n        call: api.ListTargetsByRule\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/RemoveTargets\n      name: RemoveTargets\n      description: Amazon EventBridge Remove Targets\n      operations:\n      - method: POST\n        name: RemoveTargets\n        description: Amazon EventBridge Remove Targets\n        call: api.RemoveTargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateEventBus\n      name: CreateEventBus\n      description: Amazon EventBridge Create Event Bus\n      operations:\n      - method: POST\n        name: CreateEventBus\n        description: Amazon EventBridge Create Event Bus\n        call: api.CreateEventBus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DescribeEventBus\n      name: DescribeEventBus\n      description: Amazon EventBridge Describe Event Bus\n      operations:\n      - method: POST\n        name: DescribeEventBus\n        description: Amazon EventBridge Describe Event Bus\n\
  \        call: api.DescribeEventBus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListEventBuses\n      name: ListEventBuses\n      description: Amazon EventBridge List Event Buses\n      operations:\n      - method: POST\n        name: ListEventBuses\n        description: Amazon EventBridge List Event Buses\n        call: api.ListEventBuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteEventBus\n      name: DeleteEventBus\n      description: Amazon EventBridge Delete Event Bus\n      operations:\n      - method: POST\n        name: DeleteEventBus\n        description: Amazon EventBridge Delete Event Bus\n        call: api.DeleteEventBus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateArchive\n      name: CreateArchive\n      description: Amazon EventBridge Create Archive\n      operations:\n      - method: POST\n        name: CreateArchive\n\
  \        description: Amazon EventBridge Create Archive\n        call: api.CreateArchive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListArchives\n      name: ListArchives\n      description: Amazon EventBridge List Archives\n      operations:\n      - method: POST\n        name: ListArchives\n        description: Amazon EventBridge List Archives\n        call: api.ListArchives\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9206\n    namespace: amazon-eventbridge-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon EventBridge management.\n    tools:\n    - name: PutEvents\n      description: Amazon EventBridge Put Events\n      hints:\n        readOnly: false\n      call: api.PutEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: PutRule\n      description: Amazon EventBridge Put Rule\n      hints:\n        readOnly: false\n  \
  \    call: api.PutRule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DescribeRule\n      description: Amazon EventBridge Describe Rule\n      hints:\n        readOnly: false\n      call: api.DescribeRule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListRules\n      description: Amazon EventBridge List Rules\n      hints:\n        readOnly: false\n      call: api.ListRules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeleteRule\n      description: Amazon EventBridge Delete Rule\n      hints:\n        readOnly: false\n      call: api.DeleteRule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: PutTargets\n      description: Amazon EventBridge Put Targets\n      hints:\n        readOnly: false\n      call: api.PutTargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListTargetsByRule\n      description: Amazon EventBridge\
  \ List Targets by Rule\n      hints:\n        readOnly: false\n      call: api.ListTargetsByRule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: RemoveTargets\n      description: Amazon EventBridge Remove Targets\n      hints:\n        readOnly: false\n      call: api.RemoveTargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateEventBus\n      description: Amazon EventBridge Create Event Bus\n      hints:\n        readOnly: false\n      call: api.CreateEventBus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DescribeEventBus\n      description: Amazon EventBridge Describe Event Bus\n      hints:\n        readOnly: false\n      call: api.DescribeEventBus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListEventBuses\n      description: Amazon EventBridge List Event Buses\n      hints:\n        readOnly: false\n      call: api.ListEventBuses\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: DeleteEventBus\n      description: Amazon EventBridge Delete Event Bus\n      hints:\n        readOnly: false\n      call: api.DeleteEventBus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateArchive\n      description: Amazon EventBridge Create Archive\n      hints:\n        readOnly: false\n      call: api.CreateArchive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListArchives\n      description: Amazon EventBridge List Archives\n      hints:\n        readOnly: false\n      call: api.ListArchives\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge/refs/heads/main/capabilities/amazon-eventbridge-capability.yaml
tags:
- Amazon Web Services
- Event Bus
- Serverless
tools:
- description: Amazon EventBridge Put Events
  hints:
    readOnly: false
  name: PutEvents
- description: Amazon EventBridge Put Rule
  hints:
    readOnly: false
  name: PutRule
- description: Amazon EventBridge Describe Rule
  hints:
    readOnly: false
  name: DescribeRule
- description: Amazon EventBridge List Rules
  hints:
    readOnly: false
  name: ListRules
- description: Amazon EventBridge Delete Rule
  hints:
    readOnly: false
  name: DeleteRule
- description: Amazon EventBridge Put Targets
  hints:
    readOnly: false
  name: PutTargets
- description: Amazon EventBridge List Targets by Rule
  hints:
    readOnly: false
  name: ListTargetsByRule
- description: Amazon EventBridge Remove Targets
  hints:
    readOnly: false
  name: RemoveTargets
- description: Amazon EventBridge Create Event Bus
  hints:
    readOnly: false
  name: CreateEventBus
- description: Amazon EventBridge Describe Event Bus
  hints:
    readOnly: false
  name: DescribeEventBus
- description: Amazon EventBridge List Event Buses
  hints:
    readOnly: false
  name: ListEventBuses
- description: Amazon EventBridge Delete Event Bus
  hints:
    readOnly: false
  name: DeleteEventBus
- description: Amazon EventBridge Create Archive
  hints:
    readOnly: false
  name: CreateArchive
- description: Amazon EventBridge List Archives
  hints:
    readOnly: false
  name: ListArchives
---
