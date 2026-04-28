---
categories:
- monitoring
consumed_apis:
- oracle-developer-api
- oracle-process-api
description: Unified workflow for managing Oracle Integration lifecycle including integrations, connections, packages, monitoring, B2B trading partners, process automation, tasks, and decision models. Used by integration developers and platform administrators.
layout: capability
name: Oracle Integration Management
operations:
- description: List all connections.
  method: GET
  name: list-connections
  path: /v1/connections
- description: List all integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List monitoring instances.
  method: GET
  name: list-instances
  path: /v1/monitoring/instances
- description: List errored instances.
  method: GET
  name: list-errors
  path: /v1/monitoring/errors
- description: List all packages.
  method: GET
  name: list-packages
  path: /v1/packages
- description: List all trading partners.
  method: GET
  name: list-trading-partners
  path: /v1/trading-partners
- description: List process instances.
  method: GET
  name: list-process-instances
  path: /v1/processes
- description: List user tasks.
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Oracle Integration
provider_slug: oracle-integration
search_terms:
- b2b trading partners.
- list packages
- automation
- list errors
- list monitoring instances.
- b2b trading partner management and document exchange.
- monitoring
- errored integration instances.
- get process instance details.
- integration flows.
- list connections
- get details of a specific connection.
- manages the oracle integration platform including monitoring, users, and configuration.
- list trading partners
- list all integration packages.
- cloud integration
- real-time monitoring of integration instances and error handling.
- integration flow design, deployment, and lifecycle management.
- enterprise integration
- test connection
- list dmn spaces
- get process instance
- get task details.
- Integration Developer
- designs and manages business process definitions and decision models.
- b2b integration
- list integration monitoring instances.
- list all oracle integration connections.
- list integrations
- integration monitoring instances.
- list monitoring instances
- list all connections.
- integration
- get task
- test a connection for connectivity.
- list all process definitions.
- list dmn decision model spaces.
- list user tasks.
- oracle integration
- list process definitions
- list instances
- list errored instances.
- list all trading partners.
- manages b2b trading partners, agreements, and document exchange.
- list all b2b trading partners.
- list monitoring errors
- integration packages.
- list all packages.
- list analytics queries
- unified management of integrations, connections, monitoring, b2b, processes, and tasks.
- integration management
- list all integrations.
- ipaas
- get connection
- get details of a specific integration.
- list workspace spaces.
- process automation
- list process analytics queries.
- get integration
- user tasks.
- b2b
- integration connections.
- list process instances
- process instances.
- list spaces
- Platform Administrator
- list all oracle integration flows.
- builds and manages integration flows, connections, and adapters.
- list tasks
- api management
- business process management with tasks and decision models.
- list errored integration instances.
- list process instances.
slug: integration-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Oracle Integration Management\n  description: >-\n    Unified workflow for managing Oracle Integration lifecycle including\n    integrations, connections, packages, monitoring, B2B trading partners,\n    process automation, tasks, and decision models. Used by integration\n    developers and platform administrators.\n  tags:\n    - Oracle Integration\n    - Integration Management\n    - Process Automation\n    - B2B\n    - Monitoring\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORACLE_INTEGRATION_USERNAME: ORACLE_INTEGRATION_USERNAME\n      ORACLE_INTEGRATION_PASSWORD: ORACLE_INTEGRATION_PASSWORD\n\ncapability:\n  consumes:\n    - import: oracle-developer-api\n      location: ./shared/developer-api.yaml\n    - import: oracle-process-api\n      location: ./shared/process-automation-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: oracle-integration-api\n\
  \      description: Unified REST API for Oracle Integration management.\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: Integration connections.\n          operations:\n            - method: GET\n              name: list-connections\n              description: List all connections.\n              call: oracle-developer-api.list-connections\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations\n          name: integrations\n          description: Integration flows.\n          operations:\n            - method: GET\n              name: list-integrations\n              description: List all integrations.\n              call: oracle-developer-api.list-integrations\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitoring/instances\n          name: monitoring-instances\n          description:\
  \ Integration monitoring instances.\n          operations:\n            - method: GET\n              name: list-instances\n              description: List monitoring instances.\n              call: oracle-developer-api.list-instances\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitoring/errors\n          name: monitoring-errors\n          description: Errored integration instances.\n          operations:\n            - method: GET\n              name: list-errors\n              description: List errored instances.\n              call: oracle-developer-api.list-errors\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/packages\n          name: packages\n          description: Integration packages.\n          operations:\n            - method: GET\n              name: list-packages\n              description: List all packages.\n            \
  \  call: oracle-developer-api.list-packages\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trading-partners\n          name: trading-partners\n          description: B2B trading partners.\n          operations:\n            - method: GET\n              name: list-trading-partners\n              description: List all trading partners.\n              call: oracle-developer-api.list-trading-partners\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/processes\n          name: processes\n          description: Process instances.\n          operations:\n            - method: GET\n              name: list-process-instances\n              description: List process instances.\n              call: oracle-process-api.list-process-instances\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/tasks\n          name: tasks\n          description: User tasks.\n          operations:\n            - method: GET\n              name: list-tasks\n              description: List user tasks.\n              call: oracle-process-api.list-tasks\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: oracle-integration-mcp\n      transport: http\n      description: MCP server for AI-assisted Oracle Integration management.\n      tools:\n        - name: list-connections\n          description: List all Oracle Integration connections.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-developer-api.list-connections\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connection\n          description: Get details of a specific connection.\n          hints:\n            readOnly: true\n\
  \          call: oracle-developer-api.get-connection\n          with:\n            id: tools.id\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: test-connection\n          description: Test a connection for connectivity.\n          hints:\n            readOnly: true\n          call: oracle-developer-api.test-connection\n          with:\n            id: tools.id\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: List all Oracle Integration flows.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-developer-api.list-integrations\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-integration\n          description: Get details of a specific integration.\n          hints:\n            readOnly: true\n          call: oracle-developer-api.get-integration\n\
  \          with:\n            id: tools.id\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-monitoring-instances\n          description: List integration monitoring instances.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-developer-api.list-instances\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-monitoring-errors\n          description: List errored integration instances.\n          hints:\n            readOnly: true\n          call: oracle-developer-api.list-errors\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-packages\n          description: List all integration packages.\n          hints:\n            readOnly: true\n          call: oracle-developer-api.list-packages\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-trading-partners\n          description: List all B2B trading partners.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-developer-api.list-trading-partners\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-process-definitions\n          description: List all process definitions.\n          hints:\n            readOnly: true\n          call: oracle-process-api.list-process-definitions\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-process-instances\n          description: List process instances.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-process-api.list-process-instances\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-process-instance\n          description: Get process\
  \ instance details.\n          hints:\n            readOnly: true\n          call: oracle-process-api.get-process-instance\n          with:\n            processId: tools.processId\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: List user tasks.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: oracle-process-api.list-tasks\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task\n          description: Get task details.\n          hints:\n            readOnly: true\n          call: oracle-process-api.get-task\n          with:\n            id: tools.id\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dmn-spaces\n          description: List DMN decision model spaces.\n          hints:\n            readOnly: true\n          call: oracle-process-api.list-dmn-spaces\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spaces\n          description: List workspace spaces.\n          hints:\n            readOnly: true\n          call: oracle-process-api.list-spaces\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-queries\n          description: List process analytics queries.\n          hints:\n            readOnly: true\n          call: oracle-process-api.list-analytics-queries\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-integration/refs/heads/main/capabilities/integration-management.yaml
tags:
- Oracle Integration
- Integration Management
- Process Automation
- B2B
- Monitoring
tools:
- description: List all Oracle Integration connections.
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Get details of a specific connection.
  hints:
    readOnly: true
  name: get-connection
- description: Test a connection for connectivity.
  hints:
    readOnly: true
  name: test-connection
- description: List all Oracle Integration flows.
  hints:
    openWorld: true
    readOnly: true
  name: list-integrations
- description: Get details of a specific integration.
  hints:
    readOnly: true
  name: get-integration
- description: List integration monitoring instances.
  hints:
    openWorld: true
    readOnly: true
  name: list-monitoring-instances
- description: List errored integration instances.
  hints:
    readOnly: true
  name: list-monitoring-errors
- description: List all integration packages.
  hints:
    readOnly: true
  name: list-packages
- description: List all B2B trading partners.
  hints:
    openWorld: true
    readOnly: true
  name: list-trading-partners
- description: List all process definitions.
  hints:
    readOnly: true
  name: list-process-definitions
- description: List process instances.
  hints:
    openWorld: true
    readOnly: true
  name: list-process-instances
- description: Get process instance details.
  hints:
    readOnly: true
  name: get-process-instance
- description: List user tasks.
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
- description: Get task details.
  hints:
    readOnly: true
  name: get-task
- description: List DMN decision model spaces.
  hints:
    readOnly: true
  name: list-dmn-spaces
- description: List workspace spaces.
  hints:
    readOnly: true
  name: list-spaces
- description: List process analytics queries.
  hints:
    readOnly: true
  name: list-analytics-queries
---
