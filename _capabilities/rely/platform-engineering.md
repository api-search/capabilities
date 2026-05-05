---
api_specs:
- filename: rely-openapi.yml
  format: yaml
  label: rely
  slug: rely
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/rely/refs/heads/main/openapi/rely-openapi.yml
categories: []
consumed_apis:
- rely
description: Unified workflow capability for platform engineering teams using Rely.io. Combines catalog management, scorecard evaluation, self-service action configuration, and automation management into a single integration for building and operating internal developer portals. Used by platform engineers to programmatically manage the service catalog, enforce engineering standards, and automate developer workflows.
layout: capability
name: Rely.io Platform Engineering
operations:
- description: List all blueprint schemas
  method: GET
  name: list-blueprints
  path: /v1/blueprints
- description: Create a new blueprint schema
  method: POST
  name: create-blueprint
  path: /v1/blueprints
- description: Get blueprint details
  method: GET
  name: get-blueprint
  path: /v1/blueprints/{blueprintId}
- description: List entities
  method: GET
  name: list-entities
  path: /v1/blueprints/{blueprintId}/entities
- description: Create a catalog entity
  method: POST
  name: create-entity
  path: /v1/blueprints/{blueprintId}/entities
- description: Get entity details
  method: GET
  name: get-entity
  path: /v1/blueprints/{blueprintId}/entities/{entityId}
- description: List all scorecards
  method: GET
  name: list-scorecards
  path: /v1/scorecards
- description: Create a scorecard
  method: POST
  name: create-scorecard
  path: /v1/scorecards
- description: Get scorecard details
  method: GET
  name: get-scorecard
  path: /v1/scorecards/{scorecardId}
- description: List all self-service actions
  method: GET
  name: list-actions
  path: /v1/actions
- description: Create a self-service action
  method: POST
  name: create-action
  path: /v1/actions
- description: List all automations
  method: GET
  name: list-automations
  path: /v1/automations
- description: Create an automation rule
  method: POST
  name: create-automation
  path: /v1/automations
personas: []
provider_name: Rely.io
provider_slug: rely
search_terms:
- individual scorecard
- get entity details
- list entities
- create scorecard
- software catalog
- list all automations
- get entity
- list actions
- list all automation rules configured in the portal
- create a new automation rule triggered by catalog changes
- create a scorecard
- get a specific scorecard with all its rules
- service catalog
- update entity
- create a catalog entity
- create blueprint
- create entity
- create a new catalog entity such as a service or team
- list all blueprint schemas defining catalog entity types
- get scorecard details
- create a self-service action
- list all blueprint schemas
- engineering scorecards
- platform engineering
- list all scorecards
- self-service actions
- get a specific blueprint schema and its property definitions
- catalog automation rules
- self-service developer actions
- create a new self-service action for developer workflows
- list scorecards
- list all self-service actions
- get blueprint
- create a new blueprint schema for a catalog entity type
- rely.io
- list all self-service developer actions available in the portal
- create a new blueprint schema
- update a catalog entity's properties and relations
- get blueprint details
- catalog entities of a blueprint type
- list all catalog entities of a specific blueprint type (services, teams, deployments)
- get details for a specific catalog entity
- developer experience
- internal developer portal
- create action
- get scorecard
- create automation
- list blueprints
- individual catalog entity
- create an automation rule
- software catalog blueprint schemas
- individual blueprint schema
- list all engineering scorecards tracking service standards
- create a new engineering scorecard with rules and thresholds
- list automations
slug: platform-engineering
source_filename: platform-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Rely.io Platform Engineering\n  description: >-\n    Unified workflow capability for platform engineering teams using Rely.io.\n    Combines catalog management, scorecard evaluation, self-service action\n    configuration, and automation management into a single integration for\n    building and operating internal developer portals. Used by platform\n    engineers to programmatically manage the service catalog, enforce\n    engineering standards, and automate developer workflows.\n  tags:\n    - Rely.io\n    - Platform Engineering\n    - Internal Developer Portal\n    - Software Catalog\n    - Engineering Scorecards\n    - Self-Service Actions\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RELY_API_KEY: RELY_API_KEY\n\ncapability:\n  consumes:\n    - import: rely\n      location: ./shared/rely.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rely-platform-api\n\
  \      description: \"Unified REST API for Rely.io platform engineering operations.\"\n      resources:\n        - path: /v1/blueprints\n          name: blueprints\n          description: Software catalog blueprint schemas\n          operations:\n            - method: GET\n              name: list-blueprints\n              description: List all blueprint schemas\n              call: \"rely.list-blueprints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-blueprint\n              description: Create a new blueprint schema\n              call: \"rely.create-blueprint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blueprints/{blueprintId}\n          name: blueprint\n          description: Individual blueprint schema\n          operations:\n            - method: GET\n              name: get-blueprint\n      \
  \        description: Get blueprint details\n              call: \"rely.get-blueprint\"\n              with:\n                blueprintId: \"rest.blueprintId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blueprints/{blueprintId}/entities\n          name: entities\n          description: Catalog entities of a blueprint type\n          operations:\n            - method: GET\n              name: list-entities\n              description: List entities\n              call: \"rely.list-entities\"\n              with:\n                blueprintId: \"rest.blueprintId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-entity\n              description: Create a catalog entity\n              call: \"rely.create-entity\"\n              with:\n                blueprintId: \"rest.blueprintId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blueprints/{blueprintId}/entities/{entityId}\n          name: entity\n          description: Individual catalog entity\n          operations:\n            - method: GET\n              name: get-entity\n              description: Get entity details\n              call: \"rely.get-entity\"\n              with:\n                blueprintId: \"rest.blueprintId\"\n                entityId: \"rest.entityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scorecards\n          name: scorecards\n          description: Engineering scorecards\n          operations:\n            - method: GET\n              name: list-scorecards\n              description: List all scorecards\n              call: \"rely.list-scorecards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ POST\n              name: create-scorecard\n              description: Create a scorecard\n              call: \"rely.create-scorecard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scorecards/{scorecardId}\n          name: scorecard\n          description: Individual scorecard\n          operations:\n            - method: GET\n              name: get-scorecard\n              description: Get scorecard details\n              call: \"rely.get-scorecard\"\n              with:\n                scorecardId: \"rest.scorecardId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/actions\n          name: actions\n          description: Self-service developer actions\n          operations:\n            - method: GET\n              name: list-actions\n              description: List all self-service actions\n              call: \"rely.list-actions\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-action\n              description: Create a self-service action\n              call: \"rely.create-action\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/automations\n          name: automations\n          description: Catalog automation rules\n          operations:\n            - method: GET\n              name: list-automations\n              description: List all automations\n              call: \"rely.list-automations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-automation\n              description: Create an automation rule\n              call: \"rely.create-automation\"\n              outputParameters:\n                - type: object\n    \
  \              mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: rely-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted internal developer portal management.\"\n      tools:\n        - name: list-blueprints\n          description: List all blueprint schemas defining catalog entity types\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rely.list-blueprints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blueprint\n          description: Create a new blueprint schema for a catalog entity type\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rely.create-blueprint\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            properties: \"tools.properties\"\n            relations: \"tools.relations\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blueprint\n          description: Get a specific blueprint schema and its property definitions\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rely.get-blueprint\"\n          with:\n            blueprintId: \"tools.blueprintId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-entities\n          description: List all catalog entities of a specific blueprint type (services, teams, deployments)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rely.list-entities\"\n          with:\n            blueprintId: \"tools.blueprintId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-entity\n          description: Create a new catalog entity such as a service or team\n      \
  \    hints:\n            readOnly: false\n            destructive: false\n          call: \"rely.create-entity\"\n          with:\n            blueprintId: \"tools.blueprintId\"\n            id: \"tools.id\"\n            name: \"tools.name\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity\n          description: Get details for a specific catalog entity\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rely.get-entity\"\n          with:\n            blueprintId: \"tools.blueprintId\"\n            entityId: \"tools.entityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-entity\n          description: Update a catalog entity's properties and relations\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n     \
  \     call: \"rely.update-entity\"\n          with:\n            blueprintId: \"tools.blueprintId\"\n            entityId: \"tools.entityId\"\n            name: \"tools.name\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-scorecards\n          description: List all engineering scorecards tracking service standards\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rely.list-scorecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-scorecard\n          description: Create a new engineering scorecard with rules and thresholds\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rely.create-scorecard\"\n          with:\n            name: \"tools.name\"\n            blueprintId: \"tools.blueprintId\"\n            rules: \"tools.rules\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-scorecard\n          description: Get a specific scorecard with all its rules\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rely.get-scorecard\"\n          with:\n            scorecardId: \"tools.scorecardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-actions\n          description: List all self-service developer actions available in the portal\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rely.list-actions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-action\n          description: Create a new self-service action for developer workflows\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rely.create-action\"\
  \n          with:\n            name: \"tools.name\"\n            blueprintId: \"tools.blueprintId\"\n            trigger: \"tools.trigger\"\n            invocationMethod: \"tools.invocationMethod\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-automations\n          description: List all automation rules configured in the portal\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rely.list-automations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-automation\n          description: Create a new automation rule triggered by catalog changes\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rely.create-automation\"\n          with:\n            name: \"tools.name\"\n            trigger: \"tools.trigger\"\n            action: \"tools.action\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rely/refs/heads/main/capabilities/platform-engineering.yaml
tags:
- Rely.io
- Platform Engineering
- Internal Developer Portal
- Software Catalog
- Engineering Scorecards
- Self-Service Actions
tools:
- description: List all blueprint schemas defining catalog entity types
  hints:
    openWorld: true
    readOnly: true
  name: list-blueprints
- description: Create a new blueprint schema for a catalog entity type
  hints:
    destructive: false
    readOnly: false
  name: create-blueprint
- description: Get a specific blueprint schema and its property definitions
  hints:
    openWorld: false
    readOnly: true
  name: get-blueprint
- description: List all catalog entities of a specific blueprint type (services, teams, deployments)
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Create a new catalog entity such as a service or team
  hints:
    destructive: false
    readOnly: false
  name: create-entity
- description: Get details for a specific catalog entity
  hints:
    openWorld: false
    readOnly: true
  name: get-entity
- description: Update a catalog entity's properties and relations
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-entity
- description: List all engineering scorecards tracking service standards
  hints:
    openWorld: true
    readOnly: true
  name: list-scorecards
- description: Create a new engineering scorecard with rules and thresholds
  hints:
    destructive: false
    readOnly: false
  name: create-scorecard
- description: Get a specific scorecard with all its rules
  hints:
    openWorld: false
    readOnly: true
  name: get-scorecard
- description: List all self-service developer actions available in the portal
  hints:
    openWorld: true
    readOnly: true
  name: list-actions
- description: Create a new self-service action for developer workflows
  hints:
    destructive: false
    readOnly: false
  name: create-action
- description: List all automation rules configured in the portal
  hints:
    openWorld: true
    readOnly: true
  name: list-automations
- description: Create a new automation rule triggered by catalog changes
  hints:
    destructive: false
    readOnly: false
  name: create-automation
---
