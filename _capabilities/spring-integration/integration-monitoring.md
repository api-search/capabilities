---
api_specs:
- filename: spring-integration-management-openapi.yml
  format: yaml
  label: spring-integration-mgmt
  slug: spring-integration-mgmt
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spring-integration/refs/heads/main/openapi/spring-integration-management-openapi.yml
categories: []
consumed_apis:
- spring-integration-mgmt
description: Workflow capability for monitoring and managing Spring Integration message flows at runtime. Provides channel statistics, handler metrics, adapter lifecycle control, and integration flow graph visualization. Used by integration engineers, platform operations teams, and system administrators.
layout: capability
name: Spring Integration - Integration Monitoring
operations:
- description: List all message channels with send counts and performance stats
  method: GET
  name: list-channels
  path: /v1/channels
- description: Get detailed statistics for a specific channel
  method: GET
  name: get-channel
  path: /v1/channels/{name}
- description: List all message handlers with handle counts and durations
  method: GET
  name: list-handlers
  path: /v1/handlers
- description: List all inbound channel adapters and their running state
  method: GET
  name: list-adapters
  path: /v1/adapters
- description: Get the complete integration flow graph
  method: GET
  name: get-flow-graph
  path: /v1/graph
personas: []
provider_name: Spring Integration
provider_slug: spring-integration
search_terms:
- list all message channels with send counts and performance stats
- message channel statistics and monitoring
- list all message handlers with handle counts and durations
- java
- integration
- list adapters
- stop a running spring integration inbound channel adapter to pause message ingestion
- get channel statistics
- list all inbound channel adapters and their running state
- start inbound adapter
- individual channel statistics
- amqp
- event-driven
- list channels
- message handler performance metrics
- inbound adapter lifecycle management
- get detailed runtime statistics for a specific spring integration message channel by name
- enterprise integration
- integration patterns
- get detailed statistics for a specific channel
- list all spring integration message handlers with handle counts and mean processing duration
- start a stopped spring integration inbound channel adapter to resume message ingestion
- list message channels
- get the complete integration flow graph
- list handlers
- monitoring
- get channel
- list all spring integration message channels with send counts, error counts, and performance statistics
- stop inbound adapter
- get flow graph
- get handler metrics
- spring
- retrieve the complete spring integration message flow graph showing channels, handlers, and connections
- integration flow visualization
- get performance metrics for a specific spring integration message handler
- management
- messaging
- list message handlers
slug: integration-monitoring
source_filename: integration-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spring Integration - Integration Monitoring\"\n  description: >-\n    Workflow capability for monitoring and managing Spring Integration message\n    flows at runtime. Provides channel statistics, handler metrics, adapter\n    lifecycle control, and integration flow graph visualization. Used by integration\n    engineers, platform operations teams, and system administrators.\n  tags:\n    - Enterprise Integration\n    - Integration\n    - Management\n    - Messaging\n    - Monitoring\n    - Spring\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPRING_INTEGRATION_BASE_URL: SPRING_INTEGRATION_BASE_URL\n\ncapability:\n  consumes:\n    - import: spring-integration-mgmt\n      location: ./shared/spring-integration-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: integration-monitoring-api\n      description: \"Unified REST API for Spring Integration\
  \ monitoring and management.\"\n      resources:\n        - path: /v1/channels\n          name: channels\n          description: \"Message channel statistics and monitoring\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List all message channels with send counts and performance stats\"\n              call: \"spring-integration-mgmt.list-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/channels/{name}\n          name: channel-detail\n          description: \"Individual channel statistics\"\n          operations:\n            - method: GET\n              name: get-channel\n              description: \"Get detailed statistics for a specific channel\"\n              call: \"spring-integration-mgmt.get-channel\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n   \
  \               mapping: \"$.\"\n\n        - path: /v1/handlers\n          name: handlers\n          description: \"Message handler performance metrics\"\n          operations:\n            - method: GET\n              name: list-handlers\n              description: \"List all message handlers with handle counts and durations\"\n              call: \"spring-integration-mgmt.list-handlers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/adapters\n          name: adapters\n          description: \"Inbound adapter lifecycle management\"\n          operations:\n            - method: GET\n              name: list-adapters\n              description: \"List all inbound channel adapters and their running state\"\n              call: \"spring-integration-mgmt.list-adapters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/graph\n          name:\
  \ flow-graph\n          description: \"Integration flow visualization\"\n          operations:\n            - method: GET\n              name: get-flow-graph\n              description: \"Get the complete integration flow graph\"\n              call: \"spring-integration-mgmt.get-graph\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: integration-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spring Integration monitoring and operations.\"\n      tools:\n        - name: list-message-channels\n          description: \"List all Spring Integration message channels with send counts, error counts, and performance statistics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-integration-mgmt.list-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: get-channel-statistics\n          description: \"Get detailed runtime statistics for a specific Spring Integration message channel by name\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spring-integration-mgmt.get-channel\"\n          with:\n            name: \"tools.channelName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-message-handlers\n          description: \"List all Spring Integration message handlers with handle counts and mean processing duration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-integration-mgmt.list-handlers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-handler-metrics\n          description: \"Get performance metrics for a specific Spring Integration message handler\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"spring-integration-mgmt.get-handler\"\n          with:\n            name: \"tools.handlerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flow-graph\n          description: \"Retrieve the complete Spring Integration message flow graph showing channels, handlers, and connections\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-integration-mgmt.get-graph\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-inbound-adapter\n          description: \"Start a stopped Spring Integration inbound channel adapter to resume message ingestion\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"spring-integration-mgmt.control-adapter\"\n          with:\n            name: \"tools.adapterName\"\
  \n            action: \"start\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-inbound-adapter\n          description: \"Stop a running Spring Integration inbound channel adapter to pause message ingestion\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"spring-integration-mgmt.control-adapter\"\n          with:\n            name: \"tools.adapterName\"\n            action: \"stop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-integration/refs/heads/main/capabilities/integration-monitoring.yaml
tags:
- Enterprise Integration
- Integration
- Management
- Messaging
- Monitoring
- Spring
tools:
- description: List all Spring Integration message channels with send counts, error counts, and performance statistics
  hints:
    openWorld: true
    readOnly: true
  name: list-message-channels
- description: Get detailed runtime statistics for a specific Spring Integration message channel by name
  hints:
    openWorld: false
    readOnly: true
  name: get-channel-statistics
- description: List all Spring Integration message handlers with handle counts and mean processing duration
  hints:
    openWorld: true
    readOnly: true
  name: list-message-handlers
- description: Get performance metrics for a specific Spring Integration message handler
  hints:
    openWorld: false
    readOnly: true
  name: get-handler-metrics
- description: Retrieve the complete Spring Integration message flow graph showing channels, handlers, and connections
  hints:
    openWorld: true
    readOnly: true
  name: get-flow-graph
- description: Start a stopped Spring Integration inbound channel adapter to resume message ingestion
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-inbound-adapter
- description: Stop a running Spring Integration inbound channel adapter to pause message ingestion
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-inbound-adapter
---
