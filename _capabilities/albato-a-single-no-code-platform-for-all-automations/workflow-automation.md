---
categories:
- automation
consumed_apis: []
description: Workflow capability for building and managing no-code automation workflows in Albato. Combines automation management and app connection APIs to enable operations teams to create, monitor, and control multi-step automations across 1,000+ integrated apps.
layout: capability
name: Albato Workflow Automation
operations:
- description: List all automation workflows
  method: GET
  name: list-automations
  path: /v1/automations
- description: List all app connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: Browse available apps
  method: GET
  name: list-apps
  path: /v1/apps
personas: []
provider_name: Albato A Single No Code Platform For All Automations
provider_slug: albato-a-single-no-code-platform-for-all-automations
search_terms:
- integrations
- list all albato automation workflows including their status, trigger counts, and success/error rates.
- list all app connections
- monitors automation health, execution rates, and error rates. reviews workflow performance and ensures business processes run reliably.
- list connections
- workflow automation
- list albato executions
- list apps
- Automation Builder
- browse 1,000+ available app integrations in albato. search by name or filter by category.
- list all app connections configured in the albato account.
- albato
- available app integrations
- automation workflows
- connect apps and manage webhooks
- Operations Manager
- list all automation workflows
- app connections
- embedded integration
- list automations
- get details for a specific albato automation workflow by id.
- webhooks
- create and manage automation workflows
- ipaas
- creates and manages no-code automation workflows in albato, connecting apps and configuring triggers, actions, and conditions to automate business processes.
- app integration
- no-code automation
- list albato automations
- list albato connections
- embedded ipaas
- browse available apps
- list albato apps
- get albato automation
- list execution history for an albato automation, showing successes, errors, and step completion counts.
- build and manage no-code automation workflows across 1,000+ apps
- no-code
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Albato Workflow Automation\n  description: Workflow capability for building and managing no-code automation workflows in Albato. Combines automation management\n    and app connection APIs to enable operations teams to create, monitor, and control multi-step automations across 1,000+\n    integrated apps.\n  tags:\n  - Albato\n  - Workflow Automation\n  - No-Code\n  - iPaaS\n  - App Integration\n  - Embedded Integration\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALBATO_API_KEY: ALBATO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: albato-automations\n    baseUri: https://albato.com/api/v1\n    description: Albato Automations REST API\n    auth:\n      type: apiKey\n      header: Authorization\n      value: '{{env.ALBATO_API_KEY}}'\n    resources:\n    - name: automations\n      path: /automations\n      description: Automation workflows\n      operations:\n      - name:\
  \ list-automations\n        method: GET\n        description: List all automation workflows\n        outputParameters:\n        - name: automations\n          type: object\n          value: $.\n      - name: create-automation\n        method: POST\n        description: Create a new automation workflow\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: get-automation\n        method: GET\n        description: Get an automation by ID\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: enable-automation\n        method: POST\n        description: Enable an automation\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n \
  \       - name: automation\n          type: object\n          value: $.\n      - name: disable-automation\n        method: POST\n        description: Disable an automation\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: list-executions\n        method: GET\n        description: List execution history for an automation\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: executions\n          type: object\n          value: $.\n  - type: http\n    namespace: albato-connections\n    baseUri: https://albato.com/api/v1\n    description: Albato Connections REST API\n    auth:\n      type: apiKey\n      header: Authorization\n      value: '{{env.ALBATO_API_KEY}}'\n    resources:\n    - name: connections\n      path: /connections\n      description: App connections\n\
  \      operations:\n      - name: list-connections\n        method: GET\n        description: List all app connections\n        outputParameters:\n        - name: connections\n          type: object\n          value: $.\n      - name: get-connection\n        method: GET\n        description: Get a connection by ID\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: connection\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      description: Available app integrations\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all available app integrations\n        inputParameters:\n        - name: search\n          type: string\n          in: query\n        - name: category\n          type: string\n          in: query\n        outputParameters:\n        - name: apps\n          type: object\n          value: $.\n    - name: webhooks\n   \
  \   path: /webhooks\n      description: Inbound webhook endpoints\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all inbound webhooks\n        outputParameters:\n        - name: webhooks\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: albato-workflow-api\n    description: Unified REST API for Albato workflow automation management.\n    resources:\n    - path: /v1/automations\n      name: automations\n      description: Automation workflows\n      operations:\n      - method: GET\n        name: list-automations\n        description: List all automation workflows\n        call: albato-automations.list-automations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: App connections\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all app connections\n\
  \        call: albato-connections.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps\n      name: apps\n      description: Available app integrations\n      operations:\n      - method: GET\n        name: list-apps\n        description: Browse available apps\n        call: albato-connections.list-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: albato-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Albato workflow automation.\n    tools:\n    - name: list-albato-automations\n      description: List all Albato automation workflows including their status, trigger counts, and success/error rates.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.list-automations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-albato-automation\n      description:\
  \ Get details for a specific Albato automation workflow by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.get-automation\n      inputParameters:\n      - name: id\n        type: string\n        description: Automation ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-executions\n      description: List execution history for an Albato automation, showing successes, errors, and step completion counts.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.list-executions\n      inputParameters:\n      - name: id\n        type: string\n        description: Automation ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-connections\n      description: List all app connections configured in the Albato account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-connections.list-connections\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-apps\n      description: Browse 1,000+ available app integrations in Albato. Search by name or filter by category.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-connections.list-apps\n      inputParameters:\n      - name: search\n        type: string\n        description: Search term to filter apps\n      - name: category\n        type: string\n        description: Category to filter apps\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/albato-a-single-no-code-platform-for-all-automations/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Albato
- Workflow Automation
- No-Code
- iPaaS
- App Integration
- Embedded Integration
tools:
- description: List all Albato automation workflows including their status, trigger counts, and success/error rates.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-automations
- description: Get details for a specific Albato automation workflow by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-albato-automation
- description: List execution history for an Albato automation, showing successes, errors, and step completion counts.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-executions
- description: List all app connections configured in the Albato account.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-connections
- description: Browse 1,000+ available app integrations in Albato. Search by name or filter by category.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-apps
---
