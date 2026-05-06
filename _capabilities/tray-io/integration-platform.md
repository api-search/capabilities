---
categories: []
consumed_apis: []
description: Workflow capability for the Tray.io integration platform covering connector discovery, invocation, authentication management, trigger subscriptions, and workspace administration. Designed for automation engineers and integration developers building on Tray.io's 700+ pre-built connectors.
layout: capability
name: Tray.io Integration Platform
operations:
- description: List all available Tray.io service connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: Get operations and schemas for a connector version
  method: GET
  name: get-connector-version
  path: /v1/connectors/{connectorName}/versions/{connectorVersion}
- description: Execute a Tray.io connector operation
  method: POST
  name: call-connector
  path: /v1/connectors/{connectorName}/versions/{connectorVersion}/call
- description: List all service authentications
  method: GET
  name: list-authentications
  path: /v1/authentications
- description: Create a new service authentication
  method: POST
  name: create-authentication
  path: /v1/authentications
- description: List all available triggers
  method: GET
  name: list-triggers
  path: /v1/triggers
- description: Create a trigger subscription
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: List all workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Tray.io
provider_slug: tray-io
search_terms:
- list all workspaces
- manage trigger subscriptions
- list connectors
- integration
- list all stored service authentications
- get operations and schemas for a specific connector version
- create a new service authentication for a connector
- create a new service authentication
- list organization users
- create subscription
- execute a tray.io connector operation against a third-party service
- list all users in the tray.io organization
- list all users
- list all available tray.io service connectors
- browse available triggers
- list triggers
- api aggregation
- get operations and schemas for a connector version
- list all available triggers for real-time service events
- list all available tray.io service connectors (700+ integrations)
- call connector
- ipaas
- workflow automation
- ai agents
- create a trigger subscription
- create authentication
- list workspaces
- browse all available tray.io connectors
- list organization workspaces
- list users
- execute a tray.io connector operation
- connectors
- list authentications
- create a trigger subscription to receive real-time events
- list all available triggers
- list all workspaces in the tray.io organization
- get connector version details and operations
- get connector version
- list all service authentications
- execute a connector operation
- manage service authentications
- automation
slug: integration-platform
source_filename: integration-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tray.io Integration Platform\n  description: Workflow capability for the Tray.io integration platform covering connector discovery, invocation, authentication\n    management, trigger subscriptions, and workspace administration. Designed for automation engineers and integration developers\n    building on Tray.io's 700+ pre-built connectors.\n  tags:\n  - Automation\n  - Connectors\n  - Integration\n  - iPaaS\n  - Workflow Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRAY_IO_BEARER_TOKEN: TRAY_IO_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tray-io-platform\n    baseUri: https://api.tray.io/core/v1\n    description: Tray.io Platform REST API for connectors, authentications, triggers, users, and workspaces.\n    authentication:\n      type: bearer\n      token: '{{TRAY_IO_BEARER_TOKEN}}'\n    resources:\n    - name: connectors\n      path: /connectors\n \
  \     description: Discover and invoke Tray.io service connectors\n      operations:\n      - name: list-connectors\n        method: GET\n        description: Returns all available connectors from Tray's library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connector-version\n        method: GET\n        description: Get details and operations of a specific connector version\n        inputParameters:\n        - name: connectorName\n          in: path\n          type: string\n          required: true\n          description: Connector name (e.g., salesforce)\n        - name: connectorVersion\n          in: path\n          type: string\n          required: true\n          description: Connector version (e.g., 10.1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: call-connector\n        method: POST\n\
  \        description: Execute a connector operation against a third-party service\n        inputParameters:\n        - name: connectorName\n          in: path\n          type: string\n          required: true\n        - name: connectorVersion\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            operation: '{{tools.operation}}'\n            authId: '{{tools.authId}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authentications\n      path: /authentications\n      description: Manage third-party service authentications\n      operations:\n      - name: list-authentications\n        method: GET\n        description: List all stored authentications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: create-authentication\n        method: POST\n        description: Create a new service authentication\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            serviceEnvironmentId: '{{tools.serviceEnvironmentId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-authentication\n        method: DELETE\n        description: Delete a service authentication\n        inputParameters:\n        - name: authenticationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /triggers\n      description: Manage trigger subscriptions\n      operations:\n      - name: list-triggers\n        method: GET\n        description: List all available triggers\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscription\n        method: POST\n        description: Create a trigger subscription for real-time events\n        body:\n          type: json\n          data:\n            triggerName: '{{tools.triggerName}}'\n            connectorName: '{{tools.connectorName}}'\n            connectorVersion: '{{tools.connectorVersion}}'\n            authId: '{{tools.authId}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage organization workspaces\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: users\n      path: /users\n      description: Manage organization users\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tray-io-integration-api\n    description: Unified REST API for Tray.io integration platform workflows.\n    resources:\n    - path: /v1/connectors\n      name: connectors\n      description: Browse all available Tray.io connectors\n      operations:\n      - method: GET\n        name: list-connectors\n        description: List all available Tray.io service connectors\n        call: tray-io-platform.list-connectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors/{connectorName}/versions/{connectorVersion}\n      name: connector-version\n\
  \      description: Get connector version details and operations\n      operations:\n      - method: GET\n        name: get-connector-version\n        description: Get operations and schemas for a connector version\n        call: tray-io-platform.get-connector-version\n        with:\n          connectorName: rest.connectorName\n          connectorVersion: rest.connectorVersion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors/{connectorName}/versions/{connectorVersion}/call\n      name: connector-call\n      description: Execute a connector operation\n      operations:\n      - method: POST\n        name: call-connector\n        description: Execute a Tray.io connector operation\n        call: tray-io-platform.call-connector\n        with:\n          connectorName: rest.connectorName\n          connectorVersion: rest.connectorVersion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authentications\n\
  \      name: authentications\n      description: Manage service authentications\n      operations:\n      - method: GET\n        name: list-authentications\n        description: List all service authentications\n        call: tray-io-platform.list-authentications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-authentication\n        description: Create a new service authentication\n        call: tray-io-platform.create-authentication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/triggers\n      name: triggers\n      description: Browse available triggers\n      operations:\n      - method: GET\n        name: list-triggers\n        description: List all available triggers\n        call: tray-io-platform.list-triggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Manage\
  \ trigger subscriptions\n      operations:\n      - method: POST\n        name: create-subscription\n        description: Create a trigger subscription\n        call: tray-io-platform.create-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: List organization workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces\n        call: tray-io-platform.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: List organization users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: tray-io-platform.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tray-io-integration-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Tray.io integration workflows.\n    tools:\n    - name: list-connectors\n      description: List all available Tray.io service connectors (700+ integrations)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tray-io-platform.list-connectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connector-version\n      description: Get operations and schemas for a specific connector version\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-io-platform.get-connector-version\n      with:\n        connectorName: tools.connectorName\n        connectorVersion: tools.connectorVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: call-connector\n      description: Execute a Tray.io connector operation against a third-party service\n      hints:\n        readOnly: false\n        openWorld: true\n      call: tray-io-platform.call-connector\n\
  \      with:\n        connectorName: tools.connectorName\n        connectorVersion: tools.connectorVersion\n        operation: tools.operation\n        authId: tools.authId\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-authentications\n      description: List all stored service authentications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-io-platform.list-authentications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-authentication\n      description: Create a new service authentication for a connector\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-io-platform.create-authentication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-triggers\n      description: List all available triggers for real-time service events\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: tray-io-platform.list-triggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a trigger subscription to receive real-time events\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-io-platform.create-subscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all workspaces in the Tray.io organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-io-platform.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the Tray.io organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-io-platform.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tray-io/refs/heads/main/capabilities/integration-platform.yaml
tags:
- Automation
- Connectors
- Integration
- iPaaS
- Workflow Automation
tools:
- description: List all available Tray.io service connectors (700+ integrations)
  hints:
    openWorld: true
    readOnly: true
  name: list-connectors
- description: Get operations and schemas for a specific connector version
  hints:
    openWorld: false
    readOnly: true
  name: get-connector-version
- description: Execute a Tray.io connector operation against a third-party service
  hints:
    openWorld: true
    readOnly: false
  name: call-connector
- description: List all stored service authentications
  hints:
    openWorld: false
    readOnly: true
  name: list-authentications
- description: Create a new service authentication for a connector
  hints:
    openWorld: false
    readOnly: false
  name: create-authentication
- description: List all available triggers for real-time service events
  hints:
    openWorld: true
    readOnly: true
  name: list-triggers
- description: Create a trigger subscription to receive real-time events
  hints:
    openWorld: false
    readOnly: false
  name: create-subscription
- description: List all workspaces in the Tray.io organization
  hints:
    openWorld: false
    readOnly: true
  name: list-workspaces
- description: List all users in the Tray.io organization
  hints:
    openWorld: false
    readOnly: true
  name: list-users
---
