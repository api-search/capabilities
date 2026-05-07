---
categories: []
consumed_apis: []
description: Workflow capability for managing no-code automation and embedded iPaaS functionality in Albato. Combines automation workflow management and embedded team management to support operations teams and SaaS developers.
layout: capability
name: Albato iPaaS Automation
operations:
- description: List all automation workflows
  method: GET
  name: list-automations
  path: /v1/automations
- description: List embedded teams
  method: GET
  name: list-teams
  path: /v1/teams
- description: List available connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
personas: []
provider_name: Albato
provider_slug: albato
search_terms:
- get execution history for an albato automation including success/error rates and step completion details.
- integrations
- creates no-code automation workflows in albato connecting apps without writing code, configuring triggers, actions, conditions, and delays.
- list albato executions
- workflow automation
- Automation Builder
- list available connectors
- albato
- automation workflows
- get details and configuration for a specific albato automation.
- Operations Manager
- list all automation workflows
- manage embedded ipaas customer accounts
- saas
- embedded integration
- list albato templates
- list teams
- list all albato automation workflows with their status, trigger counts, and success/error rates.
- list automations
- list albato embedded teams
- monitors automation health, reviews execution rates and errors, and ensures business processes run reliably across integrated apps.
- webhooks
- workflow
- list connectors
- ipaas
- list embedded teams
- SaaS Developer
- app integration
- embedded teams
- integrates albato embedded ipaas into saas products to offer white-label automation capabilities to customers. manages teams and connectors.
- app connectors
- no-code automation
- list albato automations
- white-label
- embedded ipaas
- create and monitor automation workflows
- list albato connectors
- list automation templates available for albato embedded use.
- list all embedded teams (customer accounts) in albato embedded ipaas with active automation and transaction counts.
- get albato automation
- browse 1,000+ available app connectors for albato embedded. search by name or filter to find specific integrations.
- manage no-code automations and embedded ipaas customer teams
slug: ipaas-automation
source_filename: ipaas-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Albato iPaaS Automation\n  description: Workflow capability for managing no-code automation and embedded iPaaS functionality in Albato. Combines automation\n    workflow management and embedded team management to support operations teams and SaaS developers.\n  tags:\n  - Albato\n  - iPaaS\n  - No-Code Automation\n  - Workflow\n  - Embedded Integration\n  - SaaS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALBATO_API_KEY: ALBATO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: albato-automations\n    baseUri: https://albato.com/api/v1\n    auth:\n      type: apiKey\n      header: Authorization\n      value: '{{env.ALBATO_API_KEY}}'\n    resources:\n    - name: automations\n      path: /automations\n      operations:\n      - name: list-automations\n        method: GET\n        description: List all automation workflows\n        outputParameters:\n        - name: automations\n\
  \          type: object\n          value: $.\n      - name: get-automation\n        method: GET\n        description: Get an automation by ID\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: create-automation\n        method: POST\n        description: Create a new automation\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: enable-automation\n        method: POST\n        description: Enable an automation\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: disable-automation\n        method: POST\n        description: Disable an\
  \ automation\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: automation\n          type: object\n          value: $.\n      - name: list-executions\n        method: GET\n        description: List execution history\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: executions\n          type: object\n          value: $.\n  - type: http\n    namespace: albato-embedded\n    baseUri: https://albato.com/api/v1/embedded\n    auth:\n      type: apiKey\n      header: Authorization\n      value: '{{env.ALBATO_API_KEY}}'\n    resources:\n    - name: teams\n      path: /teams\n      description: Embedded team management\n      operations:\n      - name: list-teams\n        method: GET\n        description: List all embedded teams\n        outputParameters:\n        - name: teams\n          type: object\n          value: $.\n     \
  \ - name: create-team\n        method: POST\n        description: Create a new embedded team\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: team\n          type: object\n          value: $.\n      - name: get-team\n        method: GET\n        description: Get an embedded team by ID\n        inputParameters:\n        - name: id\n          type: string\n          in: path\n        outputParameters:\n        - name: team\n          type: object\n          value: $.\n    - name: connectors\n      path: /connectors\n      description: Available app connectors\n      operations:\n      - name: list-connectors\n        method: GET\n        description: List available app connectors\n        inputParameters:\n        - name: search\n          type: string\n          in: query\n        outputParameters:\n        - name: connectors\n          type: object\n          value: $.\n    - name: templates\n      path:\
  \ /templates\n      description: Automation templates\n      operations:\n      - name: list-templates\n        method: GET\n        description: List automation templates\n        outputParameters:\n        - name: templates\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: albato-ipaas-api\n    description: Unified REST API for Albato iPaaS automation management.\n    resources:\n    - path: /v1/automations\n      name: automations\n      description: Automation workflows\n      operations:\n      - method: GET\n        name: list-automations\n        description: List all automation workflows\n        call: albato-automations.list-automations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Embedded teams\n      operations:\n      - method: GET\n        name: list-teams\n        description: List embedded teams\n        call: albato-embedded.list-teams\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors\n      name: connectors\n      description: App connectors\n      operations:\n      - method: GET\n        name: list-connectors\n        description: List available connectors\n        call: albato-embedded.list-connectors\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: albato-ipaas-mcp\n    transport: http\n    description: MCP server for AI-assisted Albato automation and embedded iPaaS management.\n    tools:\n    - name: list-albato-automations\n      description: List all Albato automation workflows with their status, trigger counts, and success/error rates.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.list-automations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-albato-automation\n      description: Get details and configuration\
  \ for a specific Albato automation.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.get-automation\n      inputParameters:\n      - name: id\n        type: string\n        description: Automation ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-executions\n      description: Get execution history for an Albato automation including success/error rates and step completion details.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-automations.list-executions\n      inputParameters:\n      - name: id\n        type: string\n        description: Automation ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-embedded-teams\n      description: List all embedded teams (customer accounts) in Albato Embedded iPaaS with active automation and transaction\n        counts.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: albato-embedded.list-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-connectors\n      description: Browse 1,000+ available app connectors for Albato Embedded. Search by name or filter to find specific integrations.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-embedded.list-connectors\n      inputParameters:\n      - name: search\n        type: string\n        description: Search term to filter connectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albato-templates\n      description: List automation templates available for Albato Embedded use.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: albato-embedded.list-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/albato/refs/heads/main/capabilities/ipaas-automation.yaml
tags:
- Albato
- iPaaS
- No-Code Automation
- Workflow
- Embedded Integration
- SaaS
tools:
- description: List all Albato automation workflows with their status, trigger counts, and success/error rates.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-automations
- description: Get details and configuration for a specific Albato automation.
  hints:
    openWorld: false
    readOnly: true
  name: get-albato-automation
- description: Get execution history for an Albato automation including success/error rates and step completion details.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-executions
- description: List all embedded teams (customer accounts) in Albato Embedded iPaaS with active automation and transaction counts.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-embedded-teams
- description: Browse 1,000+ available app connectors for Albato Embedded. Search by name or filter to find specific integrations.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-connectors
- description: List automation templates available for Albato Embedded use.
  hints:
    openWorld: false
    readOnly: true
  name: list-albato-templates
---
