---
categories:
- monitoring
consumed_apis: []
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
- list all packages.
- process instances.
- list process analytics queries.
- integration
- integration flows.
- list all integration packages.
- list tasks
- real-time monitoring of integration instances and error handling.
- get process instance
- list all b2b trading partners.
- integration connections.
- designs and manages business process definitions and decision models.
- b2b trading partner management and document exchange.
- get details of a specific integration.
- cloud integration
- list all oracle integration flows.
- list process definitions
- get task details.
- list all integrations.
- list process instances
- list monitoring errors
- manages the oracle integration platform including monitoring, users, and configuration.
- list all connections.
- get details of a specific connection.
- get task
- b2b
- list trading partners
- monitoring
- list dmn spaces
- business process management with tasks and decision models.
- integration management
- unified management of integrations, connections, monitoring, b2b, processes, and tasks.
- Platform Administrator
- builds and manages integration flows, connections, and adapters.
- manages b2b trading partners, agreements, and document exchange.
- automation
- enterprise integration
- list errored instances.
- list instances
- b2b trading partners.
- get process instance details.
- list monitoring instances.
- process automation
- list integrations
- list all oracle integration connections.
- integration flow design, deployment, and lifecycle management.
- list errored integration instances.
- ipaas
- list errors
- list monitoring instances
- list spaces
- list process instances.
- test connection
- list analytics queries
- list integration monitoring instances.
- test a connection for connectivity.
- api management
- list connections
- list dmn decision model spaces.
- list user tasks.
- list workspace spaces.
- Integration Developer
- b2b integration
- list all trading partners.
- integration monitoring instances.
- get connection
- errored integration instances.
- integration packages.
- get integration
- oracle integration
- list packages
- list all process definitions.
- user tasks.
slug: integration-management
source_filename: integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Integration Management\n  description: Unified workflow for managing Oracle Integration lifecycle including integrations, connections, packages, monitoring,\n    B2B trading partners, process automation, tasks, and decision models. Used by integration developers and platform administrators.\n  tags:\n  - Oracle Integration\n  - Integration Management\n  - Process Automation\n  - B2B\n  - Monitoring\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORACLE_INTEGRATION_USERNAME: ORACLE_INTEGRATION_USERNAME\n    ORACLE_INTEGRATION_PASSWORD: ORACLE_INTEGRATION_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-developer-api\n    baseUri: https://{instance}.integration.ocp.oraclecloud.com\n    description: Oracle Integration Developer REST API\n    authentication:\n      type: basic\n      username: '{{ORACLE_INTEGRATION_USERNAME}}'\n      password: '{{ORACLE_INTEGRATION_PASSWORD}}'\n\
  \    resources:\n    - name: connections\n      path: /ic/api/integration/v1/connections\n      description: Manage integration connections.\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connection\n        method: GET\n        description: Get a specific connection.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Connection identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-connection\n        method: POST\n        description: Update a connection.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Connection identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-connection\n        method: DELETE\n        description: Delete a connection.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Connection identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: test-connection\n        method: POST\n        description: Test a connection.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Connection identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /ic/api/integration/v1/integrations\n\
  \      description: Manage integrations.\n      operations:\n      - name: list-integrations\n        method: GET\n        description: List all integrations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-integration\n        method: GET\n        description: Get a specific integration.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: activate-integration\n        method: POST\n        description: Activate or deactivate an integration.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clone-integration\n        method: POST\n        description: Clone an integration.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-integration\n        method: DELETE\n        description: Delete an integration version.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /ic/api/integration/v1/monitoring\n      description: Monitor integration instances.\n\
  \      operations:\n      - name: list-instances\n        method: GET\n        description: List integration instances.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance\n        method: GET\n        description: Get a specific integration instance.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: abort-instance\n        method: POST\n        description: Abort a running integration instance.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: list-errors\n        method: GET\n        description: List errored integration instances.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resubmit-error\n        method: POST\n        description: Resubmit an errored instance.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Error instance identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages\n      path: /ic/api/integration/v1/packages\n      description: Manage integration packages.\n      operations:\n      - name: list-packages\n        method: GET\n        description: List all packages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: get-package\n        method: GET\n        description: Get a specific package.\n        inputParameters:\n        - name: packagename\n          in: path\n          type: string\n          required: true\n          description: Package name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trading-partners\n      path: /ic/api/b2b/v1/tpm/partners\n      description: Manage B2B trading partners.\n      operations:\n      - name: list-trading-partners\n        method: GET\n        description: List all trading partners.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-trading-partner\n        method: GET\n        description: Get a specific trading partner.\n        inputParameters:\n        - name: tpId\n          in: path\n          type: string\n         \
  \ required: true\n          description: Trading partner identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-trading-partner\n        method: POST\n        description: Create a new trading partner.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-trading-partner\n        method: DELETE\n        description: Delete a trading partner.\n        inputParameters:\n        - name: tpId\n          in: path\n          type: string\n          required: true\n          description: Trading partner identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: oracle-process-api\n    baseUri: https://{instance}.integration.ocp.oraclecloud.com\n    description: Oracle Integration Process\
  \ Automation REST API\n    authentication:\n      type: basic\n      username: '{{ORACLE_INTEGRATION_USERNAME}}'\n      password: '{{ORACLE_INTEGRATION_PASSWORD}}'\n    resources:\n    - name: process-definitions\n      path: /ic/api/process/v1/process-definitions\n      description: Process definitions management.\n      operations:\n      - name: list-process-definitions\n        method: GET\n        description: List all process definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances\n      path: /ic/api/process/v1/processes\n      description: Process instance management.\n      operations:\n      - name: list-process-instances\n        method: GET\n        description: List process instances.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-process-instance\n        method:\
  \ GET\n        description: Get a process instance.\n        inputParameters:\n        - name: processId\n          in: path\n          type: string\n          required: true\n          description: Process instance identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-process-instance\n        method: POST\n        description: Create a new process instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /ic/api/process/v1/tasks\n      description: Task management.\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List user tasks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task\n        method: GET\n        description: Get a specific\
  \ task.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: perform-task-action\n        method: PUT\n        description: Perform an action on a task.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decision-models\n      path: /ic/api/process/v1/dmn/spaces\n      description: Decision model management.\n      operations:\n      - name: list-dmn-spaces\n        method: GET\n        description: List DMN spaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: list-decision-models\n        method: GET\n        description: List decision models in a space.\n        inputParameters:\n        - name: spaceId\n          in: path\n          type: string\n          required: true\n          description: Space identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces\n      path: /ic/api/process/v1/spaces\n      description: Workspace space management.\n      operations:\n      - name: list-spaces\n        method: GET\n        description: List workspace spaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /ic/api/process/v1/analyticsqueries\n      description: Process analytics.\n      operations:\n      - name: list-analytics-queries\n        method: GET\n        description:\
  \ List analytics queries.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-integration-api\n    description: Unified REST API for Oracle Integration management.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Integration connections.\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connections.\n        call: oracle-developer-api.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations\n      name: integrations\n      description: Integration flows.\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List all integrations.\n        call: oracle-developer-api.list-integrations\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/monitoring/instances\n      name: monitoring-instances\n      description: Integration monitoring instances.\n      operations:\n      - method: GET\n        name: list-instances\n        description: List monitoring instances.\n        call: oracle-developer-api.list-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring/errors\n      name: monitoring-errors\n      description: Errored integration instances.\n      operations:\n      - method: GET\n        name: list-errors\n        description: List errored instances.\n        call: oracle-developer-api.list-errors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/packages\n      name: packages\n      description: Integration packages.\n      operations:\n      - method: GET\n        name: list-packages\n        description: List all packages.\n        call: oracle-developer-api.list-packages\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/trading-partners\n      name: trading-partners\n      description: B2B trading partners.\n      operations:\n      - method: GET\n        name: list-trading-partners\n        description: List all trading partners.\n        call: oracle-developer-api.list-trading-partners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/processes\n      name: processes\n      description: Process instances.\n      operations:\n      - method: GET\n        name: list-process-instances\n        description: List process instances.\n        call: oracle-process-api.list-process-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: User tasks.\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List user tasks.\n        call: oracle-process-api.list-tasks\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle Integration management.\n    tools:\n    - name: list-connections\n      description: List all Oracle Integration connections.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-developer-api.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connection\n      description: Get details of a specific connection.\n      hints:\n        readOnly: true\n      call: oracle-developer-api.get-connection\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: test-connection\n      description: Test a connection for connectivity.\n      hints:\n        readOnly: true\n      call: oracle-developer-api.test-connection\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List all Oracle Integration flows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-developer-api.list-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-integration\n      description: Get details of a specific integration.\n      hints:\n        readOnly: true\n      call: oracle-developer-api.get-integration\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-monitoring-instances\n      description: List integration monitoring instances.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-developer-api.list-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-monitoring-errors\n      description: List errored integration instances.\n      hints:\n        readOnly: true\n\
  \      call: oracle-developer-api.list-errors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-packages\n      description: List all integration packages.\n      hints:\n        readOnly: true\n      call: oracle-developer-api.list-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-trading-partners\n      description: List all B2B trading partners.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-developer-api.list-trading-partners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-process-definitions\n      description: List all process definitions.\n      hints:\n        readOnly: true\n      call: oracle-process-api.list-process-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-process-instances\n      description: List process instances.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: oracle-process-api.list-process-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-process-instance\n      description: Get process instance details.\n      hints:\n        readOnly: true\n      call: oracle-process-api.get-process-instance\n      with:\n        processId: tools.processId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List user tasks.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-process-api.list-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task\n      description: Get task details.\n      hints:\n        readOnly: true\n      call: oracle-process-api.get-task\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dmn-spaces\n      description: List DMN decision model spaces.\n      hints:\n    \
  \    readOnly: true\n      call: oracle-process-api.list-dmn-spaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spaces\n      description: List workspace spaces.\n      hints:\n        readOnly: true\n      call: oracle-process-api.list-spaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analytics-queries\n      description: List process analytics queries.\n      hints:\n        readOnly: true\n      call: oracle-process-api.list-analytics-queries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
