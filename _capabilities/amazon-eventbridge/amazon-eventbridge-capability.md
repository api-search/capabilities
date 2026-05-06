---
categories: []
consumed_apis: []
description: Amazon EventBridge is a serverless event bus service that makes it easy to connect your applications with data from a variety of sources. EventBridge delivers a stream of real-time data from your own applications, SaaS applications, and AWS services and routes that data to targets such as AWS Lambda, Amazon SNS, Amazon SQS, and more.
layout: capability
name: Amazon EventBridge API
operations:
- description: Amazon EventBridge Put Events
  method: POST
  name: putevents
  path: /
- description: Amazon EventBridge Put Rule
  method: POST
  name: putrule
  path: /?PutRule
- description: Amazon EventBridge Describe Rule
  method: POST
  name: describerule
  path: /?DescribeRule
- description: Amazon EventBridge List Rules
  method: POST
  name: listrules
  path: /?ListRules
- description: Amazon EventBridge Delete Rule
  method: POST
  name: deleterule
  path: /?DeleteRule
- description: Amazon EventBridge Put Targets
  method: POST
  name: puttargets
  path: /?PutTargets
- description: Amazon EventBridge List Targets by Rule
  method: POST
  name: listtargetsbyrule
  path: /?ListTargetsByRule
- description: Amazon EventBridge Remove Targets
  method: POST
  name: removetargets
  path: /?RemoveTargets
- description: Amazon EventBridge Create Event Bus
  method: POST
  name: createeventbus
  path: /?CreateEventBus
- description: Amazon EventBridge Describe Event Bus
  method: POST
  name: describeeventbus
  path: /?DescribeEventBus
- description: Amazon EventBridge List Event Buses
  method: POST
  name: listeventbuses
  path: /?ListEventBuses
- description: Amazon EventBridge Delete Event Bus
  method: POST
  name: deleteeventbus
  path: /?DeleteEventBus
- description: Amazon EventBridge Create Archive
  method: POST
  name: createarchive
  path: /?CreateArchive
- description: Amazon EventBridge List Archives
  method: POST
  name: listarchives
  path: /?ListArchives
personas: []
provider_name: Amazon EventBridge
provider_slug: amazon-eventbridge
search_terms:
- unified capability for managing amazon eventbridge resources. combines amazon eventbridge apis for integration engineer workflows in event-driven architecture.
- amazon web services
- amazon eventbridge remove targets
- integration
- amazon eventbridge delete event bus
- event bus
- eventbridge
- amazon
- serverless event bus for connecting applications with real-time data
- removetargets
- listarchives
- amazon eventbridge list archives
- serverless
- amazon eventbridge list event buses
- amazon eventbridge list rules
- operations teams managing amazon eventbridge infrastructure
- developers building applications using amazon eventbridge
- amazon eventbridge describe event bus
- amazon eventbridge delete rule
- createarchive
- amazon eventbridge create archive
- describerule
- deleteeventbus
- amazon eventbridge create event bus
- puttargets
- amazon eventbridge describe rule
- api
- putevents
- amazon eventbridge put rule
- event-driven
- listrules
- deleterule
- amazon eventbridge list targets by rule
- createeventbus
- describeeventbus
- listeventbuses
- amazon eventbridge put targets
- putrule
- listtargetsbyrule
- events
- amazon eventbridge put events
slug: amazon-eventbridge-capability
source_filename: amazon-eventbridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EventBridge API\n  description: Amazon EventBridge is a serverless event bus service that makes it easy to connect your applications with data\n    from a variety of sources. EventBridge delivers a stream of real-time data from your own applications, SaaS applications,\n    and AWS services and routes that data to targets such as AWS Lambda, Amazon SNS, Amazon SQS, and more.\n  tags:\n  - Amazon\n  - Eventbridge\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-eventbridge\n    baseUri: https://events.us-east-1.amazonaws.com\n    description: Amazon EventBridge API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_EVENTBRIDGE_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: putevents\n        method: POST\n        description: Amazon EventBridge\
  \ Put Events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: putrule\n      path: /?PutRule\n      operations:\n      - name: putrule\n        method: POST\n        description: Amazon EventBridge Put Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describerule\n      path: /?DescribeRule\n      operations:\n      - name: describerule\n        method: POST\n        description: Amazon EventBridge Describe Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listrules\n      path: /?ListRules\n      operations:\n      - name: listrules\n        method: POST\n        description: Amazon EventBridge List Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: deleterule\n      path: /?DeleteRule\n      operations:\n      - name: deleterule\n        method: POST\n        description: Amazon EventBridge Delete Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: puttargets\n      path: /?PutTargets\n      operations:\n      - name: puttargets\n        method: POST\n        description: Amazon EventBridge Put Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listtargetsbyrule\n      path: /?ListTargetsByRule\n      operations:\n      - name: listtargetsbyrule\n        method: POST\n        description: Amazon EventBridge List Targets by Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: removetargets\n      path: /?RemoveTargets\n\
  \      operations:\n      - name: removetargets\n        method: POST\n        description: Amazon EventBridge Remove Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: createeventbus\n      path: /?CreateEventBus\n      operations:\n      - name: createeventbus\n        method: POST\n        description: Amazon EventBridge Create Event Bus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describeeventbus\n      path: /?DescribeEventBus\n      operations:\n      - name: describeeventbus\n        method: POST\n        description: Amazon EventBridge Describe Event Bus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listeventbuses\n      path: /?ListEventBuses\n      operations:\n      - name: listeventbuses\n  \
  \      method: POST\n        description: Amazon EventBridge List Event Buses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deleteeventbus\n      path: /?DeleteEventBus\n      operations:\n      - name: deleteeventbus\n        method: POST\n        description: Amazon EventBridge Delete Event Bus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: createarchive\n      path: /?CreateArchive\n      operations:\n      - name: createarchive\n        method: POST\n        description: Amazon EventBridge Create Archive\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listarchives\n      path: /?ListArchives\n      operations:\n      - name: listarchives\n        method: POST\n        description: Amazon EventBridge List Archives\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-eventbridge-rest\n    description: REST adapter for Amazon EventBridge API.\n    resources:\n    - path: /\n      name: putevents\n      operations:\n      - method: POST\n        name: putevents\n        description: Amazon EventBridge Put Events\n        call: amazon-eventbridge.putevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?PutRule\n      name: putrule\n      operations:\n      - method: POST\n        name: putrule\n        description: Amazon EventBridge Put Rule\n        call: amazon-eventbridge.putrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?DescribeRule\n      name: describerule\n      operations:\n      - method: POST\n        name: describerule\n        description: Amazon EventBridge Describe\
  \ Rule\n        call: amazon-eventbridge.describerule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?ListRules\n      name: listrules\n      operations:\n      - method: POST\n        name: listrules\n        description: Amazon EventBridge List Rules\n        call: amazon-eventbridge.listrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?DeleteRule\n      name: deleterule\n      operations:\n      - method: POST\n        name: deleterule\n        description: Amazon EventBridge Delete Rule\n        call: amazon-eventbridge.deleterule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?PutTargets\n      name: puttargets\n      operations:\n      - method: POST\n        name: puttargets\n        description: Amazon EventBridge Put Targets\n        call: amazon-eventbridge.puttargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /?ListTargetsByRule\n      name: listtargetsbyrule\n      operations:\n      - method: POST\n        name: listtargetsbyrule\n        description: Amazon EventBridge List Targets by Rule\n        call: amazon-eventbridge.listtargetsbyrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?RemoveTargets\n      name: removetargets\n      operations:\n      - method: POST\n        name: removetargets\n        description: Amazon EventBridge Remove Targets\n        call: amazon-eventbridge.removetargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?CreateEventBus\n      name: createeventbus\n      operations:\n      - method: POST\n        name: createeventbus\n        description: Amazon EventBridge Create Event Bus\n        call: amazon-eventbridge.createeventbus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?DescribeEventBus\n      name: describeeventbus\n      operations:\n\
  \      - method: POST\n        name: describeeventbus\n        description: Amazon EventBridge Describe Event Bus\n        call: amazon-eventbridge.describeeventbus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?ListEventBuses\n      name: listeventbuses\n      operations:\n      - method: POST\n        name: listeventbuses\n        description: Amazon EventBridge List Event Buses\n        call: amazon-eventbridge.listeventbuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?DeleteEventBus\n      name: deleteeventbus\n      operations:\n      - method: POST\n        name: deleteeventbus\n        description: Amazon EventBridge Delete Event Bus\n        call: amazon-eventbridge.deleteeventbus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?CreateArchive\n      name: createarchive\n      operations:\n      - method: POST\n        name: createarchive\n        description:\
  \ Amazon EventBridge Create Archive\n        call: amazon-eventbridge.createarchive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?ListArchives\n      name: listarchives\n      operations:\n      - method: POST\n        name: listarchives\n        description: Amazon EventBridge List Archives\n        call: amazon-eventbridge.listarchives\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-eventbridge-mcp\n    transport: http\n    description: MCP adapter for Amazon EventBridge API for AI agent use.\n    tools:\n    - name: putevents\n      description: Amazon EventBridge Put Events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.putevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putrule\n      description: Amazon EventBridge Put Rule\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.putrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describerule\n      description: Amazon EventBridge Describe Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.describerule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrules\n      description: Amazon EventBridge List Rules\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.listrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterule\n      description: Amazon EventBridge Delete Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.deleterule\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: puttargets\n      description: Amazon EventBridge Put Targets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.puttargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtargetsbyrule\n      description: Amazon EventBridge List Targets by Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.listtargetsbyrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removetargets\n      description: Amazon EventBridge Remove Targets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.removetargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createeventbus\n      description: Amazon EventBridge Create Event Bus\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.createeventbus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeeventbus\n      description: Amazon EventBridge Describe Event Bus\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.describeeventbus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventbuses\n      description: Amazon EventBridge List Event Buses\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.listeventbuses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteeventbus\n      description: Amazon EventBridge Delete Event Bus\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.deleteeventbus\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createarchive\n      description: Amazon EventBridge Create Archive\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.createarchive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listarchives\n      description: Amazon EventBridge List Archives\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge.listarchives\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_EVENTBRIDGE_TOKEN: AMAZON_EVENTBRIDGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge/refs/heads/main/capabilities/amazon-eventbridge-capability.yaml
tags:
- Amazon
- Eventbridge
- API
tools:
- description: Amazon EventBridge Put Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putevents
- description: Amazon EventBridge Put Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putrule
- description: Amazon EventBridge Describe Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describerule
- description: Amazon EventBridge List Rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listrules
- description: Amazon EventBridge Delete Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleterule
- description: Amazon EventBridge Put Targets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: puttargets
- description: Amazon EventBridge List Targets by Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtargetsbyrule
- description: Amazon EventBridge Remove Targets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removetargets
- description: Amazon EventBridge Create Event Bus
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventbus
- description: Amazon EventBridge Describe Event Bus
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeeventbus
- description: Amazon EventBridge List Event Buses
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listeventbuses
- description: Amazon EventBridge Delete Event Bus
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteeventbus
- description: Amazon EventBridge Create Archive
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createarchive
- description: Amazon EventBridge List Archives
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listarchives
---
