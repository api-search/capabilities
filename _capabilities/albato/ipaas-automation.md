---
categories: []
consumed_apis:
- albato-automations
- albato-embedded
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
- list albato templates
- list automations
- integrates albato embedded ipaas into saas products to offer white-label automation capabilities to customers. manages teams and connectors.
- webhooks
- list teams
- creates no-code automation workflows in albato connecting apps without writing code, configuring triggers, actions, conditions, and delays.
- no-code automation
- list connectors
- list automation templates available for albato embedded use.
- Automation Builder
- create and monitor automation workflows
- list albato executions
- Operations Manager
- app integration
- browse 1,000+ available app connectors for albato embedded. search by name or filter to find specific integrations.
- list albato connectors
- manage embedded ipaas customer accounts
- automation workflows
- list available connectors
- get albato automation
- get execution history for an albato automation including success/error rates and step completion details.
- monitors automation health, reviews execution rates and errors, and ensures business processes run reliably across integrated apps.
- manage no-code automations and embedded ipaas customer teams
- albato
- workflow
- embedded teams
- workflow automation
- embedded integration
- list all automation workflows
- get details and configuration for a specific albato automation.
- white-label
- SaaS Developer
- ipaas
- integrations
- list all embedded teams (customer accounts) in albato embedded ipaas with active automation and transaction counts.
- saas
- list all albato automation workflows with their status, trigger counts, and success/error rates.
- app connectors
- list albato automations
- list albato embedded teams
- list embedded teams
- embedded ipaas
slug: ipaas-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Albato iPaaS Automation\n  description: >-\n    Workflow capability for managing no-code automation and embedded iPaaS\n    functionality in Albato. Combines automation workflow management and\n    embedded team management to support operations teams and SaaS developers.\n  tags:\n    - Albato\n    - iPaaS\n    - No-Code Automation\n    - Workflow\n    - Embedded Integration\n    - SaaS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALBATO_API_KEY: ALBATO_API_KEY\n\ncapability:\n  consumes:\n    - import: albato-automations\n      location: ./shared/automations-api.yaml\n    - import: albato-embedded\n      location: ./shared/embedded-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: albato-ipaas-api\n      description: Unified REST API for Albato iPaaS automation management.\n      resources:\n        - path: /v1/automations\n          name: automations\n\
  \          description: Automation workflows\n          operations:\n            - method: GET\n              name: list-automations\n              description: List all automation workflows\n              call: \"albato-automations.list-automations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams\n          name: teams\n          description: Embedded teams\n          operations:\n            - method: GET\n              name: list-teams\n              description: List embedded teams\n              call: \"albato-embedded.list-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connectors\n          name: connectors\n          description: App connectors\n          operations:\n            - method: GET\n              name: list-connectors\n              description: List available connectors\n              call: \"albato-embedded.list-connectors\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: albato-ipaas-mcp\n      transport: http\n      description: MCP server for AI-assisted Albato automation and embedded iPaaS management.\n      tools:\n        - name: list-albato-automations\n          description: >-\n            List all Albato automation workflows with their status, trigger counts,\n            and success/error rates.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"albato-automations.list-automations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-albato-automation\n          description: Get details and configuration for a specific Albato automation.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"albato-automations.get-automation\"\n          inputParameters:\n\
  \            - name: id\n              type: string\n              description: Automation ID\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-albato-executions\n          description: >-\n            Get execution history for an Albato automation including success/error\n            rates and step completion details.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"albato-automations.list-executions\"\n          inputParameters:\n            - name: id\n              type: string\n              description: Automation ID\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-albato-embedded-teams\n          description: >-\n            List all embedded teams (customer accounts) in Albato Embedded iPaaS\n            with active automation and transaction counts.\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"albato-embedded.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-albato-connectors\n          description: >-\n            Browse 1,000+ available app connectors for Albato Embedded.\n            Search by name or filter to find specific integrations.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"albato-embedded.list-connectors\"\n          inputParameters:\n            - name: search\n              type: string\n              description: Search term to filter connectors\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-albato-templates\n          description: List automation templates available for Albato Embedded use.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"albato-embedded.list-templates\"\n          outputParameters:\n  \
  \          - type: object\n              mapping: \"$.\"\n"
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
