---
categories: []
consumed_apis:
- workato-developer
- workato-agent-studio
- workato-mcp
- workato-events
description: Unified capability for integration engineers and automation teams managing Workato recipes, data tables, event streams, and AI-powered agent workflows. Combines the Developer API, Agent Studio, Event Streams, and MCP Server APIs into a single automation operations workflow.
layout: capability
name: Workato Automation Management
operations:
- description: List automation recipes
  method: GET
  name: list-recipes
  path: /v1/recipes
- description: Create a new recipe
  method: POST
  name: create-recipe
  path: /v1/recipes
- description: Get a recipe
  method: GET
  name: get-recipe
  path: /v1/recipes/{id}
- description: Delete a recipe
  method: DELETE
  name: delete-recipe
  path: /v1/recipes/{id}
- description: Start a recipe
  method: PUT
  name: start-recipe
  path: /v1/recipes/{id}/start
- description: Stop a recipe
  method: PUT
  name: stop-recipe
  path: /v1/recipes/{id}/stop
- description: List data tables
  method: GET
  name: list-data-tables
  path: /v1/data-tables
- description: List AI genies
  method: GET
  name: list-genies
  path: /v1/genies
- description: List AI skills
  method: GET
  name: list-skills
  path: /v1/skills
- description: List knowledge bases
  method: GET
  name: list-knowledge-bases
  path: /v1/knowledge-bases
- description: List MCP servers
  method: GET
  name: list-mcp-servers
  path: /v1/mcp-servers
- description: Publish message to topic
  method: POST
  name: publish-message
  path: /v1/topics/{topic_id}/publish
personas: []
provider_name: Workato
provider_slug: workato
search_terms:
- automation
- start recipe
- start a workato recipe to begin processing triggers
- get a recipe
- list recipes
- ai agents
- list skills
- list ai skills
- create recipe
- get health status report for a workato recipe
- list workato automation recipes with optional filtering
- data tables
- list tools configured on a workato mcp server
- get recipe
- api management
- stop a recipe
- list mcp servers
- ai genies
- mcp servers
- create a new workato knowledge base
- list knowledge bases
- integration
- automation recipes
- list data tables
- create a new workato ai genie
- create genie
- start a recipe
- list server tools
- create a new workato automation recipe
- stop recipe
- b2b
- workato
- list ai genies
- consume messages from a workato event stream topic
- embedded ipaas
- list workato mcp servers exposing api tools for ai agents
- consume events
- get a specific workato ai genie by id
- publish a message to a workato event stream topic
- enterprise
- publish events
- delete a recipe
- stop a running workato recipe
- list ai skills available for workato genies
- publish message to topic
- delete recipe
- publish event
- list workato knowledge bases for ai-powered lookups
- create a new recipe
- list genies
- ai skills
- get genie
- ipaas
- list workato data tables for structured data storage
- agentic
- create mcp server
- knowledge bases
- orchestration
- single recipe management
- get recipe health
- get a specific workato recipe by id
- create a new workato mcp server for exposing api tools
- workflow
- list workato ai genies for agentic automation
- create knowledge base
- list automation recipes
- publish message
slug: automation-management
source_filename: automation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workato Automation Management\"\n  description: \"Unified capability for integration engineers and automation teams managing Workato recipes, data tables, event streams, and AI-powered agent workflows. Combines the Developer API, Agent Studio, Event Streams, and MCP Server APIs into a single automation operations workflow.\"\n  tags:\n    - AI Agents\n    - Automation\n    - Integration\n    - iPaaS\n    - Orchestration\n    - Workato\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKATO_API_TOKEN: WORKATO_API_TOKEN\n\ncapability:\n  consumes:\n    - import: workato-developer\n      location: ./shared/developer-api.yaml\n    - import: workato-agent-studio\n      location: ./shared/agent-studio.yaml\n    - import: workato-mcp\n      location: ./shared/mcp-server.yaml\n    - import: workato-events\n      location: ./shared/event-streams.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: workato-automation-api\n      description: \"Unified REST API for Workato automation management workflows.\"\n      resources:\n        - path: /v1/recipes\n          name: recipes\n          description: \"Automation recipes\"\n          operations:\n            - method: GET\n              name: list-recipes\n              description: \"List automation recipes\"\n              call: \"workato-developer.list-recipes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-recipe\n              description: \"Create a new recipe\"\n              call: \"workato-developer.create-recipe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recipes/{id}\n          name: recipe-by-id\n          description: \"Single recipe management\"\n          operations:\n            - method: GET\n\
  \              name: get-recipe\n              description: \"Get a recipe\"\n              call: \"workato-developer.get-recipe\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-recipe\n              description: \"Delete a recipe\"\n              call: \"workato-developer.delete-recipe\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recipes/{id}/start\n          name: recipe-start\n          operations:\n            - method: PUT\n              name: start-recipe\n              description: \"Start a recipe\"\n              call: \"workato-developer.start-recipe\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n        - path: /v1/recipes/{id}/stop\n          name: recipe-stop\n          operations:\n            - method: PUT\n              name: stop-recipe\n              description: \"Stop a recipe\"\n              call: \"workato-developer.stop-recipe\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-tables\n          name: data-tables\n          description: \"Data tables\"\n          operations:\n            - method: GET\n              name: list-data-tables\n              description: \"List data tables\"\n              call: \"workato-developer.list-data-tables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/genies\n          name: genies\n          description: \"AI genies\"\n          operations:\n            - method: GET\n              name: list-genies\n\
  \              description: \"List AI genies\"\n              call: \"workato-agent-studio.list-genies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/skills\n          name: skills\n          description: \"AI skills\"\n          operations:\n            - method: GET\n              name: list-skills\n              description: \"List AI skills\"\n              call: \"workato-agent-studio.list-skills\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/knowledge-bases\n          name: knowledge-bases\n          description: \"Knowledge bases\"\n          operations:\n            - method: GET\n              name: list-knowledge-bases\n              description: \"List knowledge bases\"\n              call: \"workato-agent-studio.list-knowledge-bases\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/mcp-servers\n          name: mcp-servers\n          description: \"MCP servers\"\n          operations:\n            - method: GET\n              name: list-mcp-servers\n              description: \"List MCP servers\"\n              call: \"workato-mcp.list-mcp-servers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/topics/{topic_id}/publish\n          name: topic-publish\n          description: \"Publish events\"\n          operations:\n            - method: POST\n              name: publish-message\n              description: \"Publish message to topic\"\n              call: \"workato-events.publish-message\"\n              with:\n                topic_id: \"rest.topic_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: workato-automation-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Workato automation management, recipe operations, and agentic workflow orchestration.\"\n      tools:\n        - name: list-recipes\n          description: \"List Workato automation recipes with optional filtering\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workato-developer.list-recipes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recipe\n          description: \"Get a specific Workato recipe by ID\"\n          hints:\n            readOnly: true\n          call: \"workato-developer.get-recipe\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-recipe\n          description: \"Create a new Workato automation recipe\"\n          hints:\n            readOnly: false\n          call: \"workato-developer.create-recipe\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: start-recipe\n          description: \"Start a Workato recipe to begin processing triggers\"\n          hints:\n            readOnly: false\n          call: \"workato-developer.start-recipe\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-recipe\n          description: \"Stop a running Workato recipe\"\n          hints:\n            readOnly: false\n          call: \"workato-developer.stop-recipe\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recipe-health\n          description: \"Get health status report for a Workato recipe\"\n          hints:\n            readOnly: true\n          call: \"workato-developer.get-recipe-health\"\n          with:\n            recipe_id: \"tools.recipe_id\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-tables\n          description: \"List Workato data tables for structured data storage\"\n          hints:\n            readOnly: true\n          call: \"workato-developer.list-data-tables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-genies\n          description: \"List Workato AI genies for agentic automation\"\n          hints:\n            readOnly: true\n          call: \"workato-agent-studio.list-genies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-genie\n          description: \"Get a specific Workato AI genie by ID\"\n          hints:\n            readOnly: true\n          call: \"workato-agent-studio.get-genie\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-genie\n          description: \"Create a new Workato AI genie\"\n          hints:\n            readOnly: false\n          call: \"workato-agent-studio.create-genie\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-skills\n          description: \"List AI skills available for Workato genies\"\n          hints:\n            readOnly: true\n          call: \"workato-agent-studio.list-skills\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-knowledge-bases\n          description: \"List Workato knowledge bases for AI-powered lookups\"\n          hints:\n            readOnly: true\n          call: \"workato-agent-studio.list-knowledge-bases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-knowledge-base\n          description: \"Create a new Workato knowledge base\"\n    \
  \      hints:\n            readOnly: false\n          call: \"workato-agent-studio.create-knowledge-base\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mcp-servers\n          description: \"List Workato MCP servers exposing API tools for AI agents\"\n          hints:\n            readOnly: true\n          call: \"workato-mcp.list-mcp-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mcp-server\n          description: \"Create a new Workato MCP server for exposing API tools\"\n          hints:\n            readOnly: false\n          call: \"workato-mcp.create-mcp-server\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-server-tools\n          description: \"List tools configured on a Workato MCP server\"\n          hints:\n            readOnly: true\n          call: \"workato-mcp.list-server-tools\"\
  \n          with:\n            mcp_server_handle: \"tools.handle\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-event\n          description: \"Publish a message to a Workato event stream topic\"\n          hints:\n            readOnly: false\n          call: \"workato-events.publish-message\"\n          with:\n            topic_id: \"tools.topic_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: consume-events\n          description: \"Consume messages from a Workato event stream topic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workato-events.consume-messages\"\n          with:\n            topic_id: \"tools.topic_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workato/refs/heads/main/capabilities/automation-management.yaml
tags:
- AI Agents
- Automation
- Integration
- iPaaS
- Orchestration
- Workato
tools:
- description: List Workato automation recipes with optional filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-recipes
- description: Get a specific Workato recipe by ID
  hints:
    readOnly: true
  name: get-recipe
- description: Create a new Workato automation recipe
  hints:
    readOnly: false
  name: create-recipe
- description: Start a Workato recipe to begin processing triggers
  hints:
    readOnly: false
  name: start-recipe
- description: Stop a running Workato recipe
  hints:
    readOnly: false
  name: stop-recipe
- description: Get health status report for a Workato recipe
  hints:
    readOnly: true
  name: get-recipe-health
- description: List Workato data tables for structured data storage
  hints:
    readOnly: true
  name: list-data-tables
- description: List Workato AI genies for agentic automation
  hints:
    readOnly: true
  name: list-genies
- description: Get a specific Workato AI genie by ID
  hints:
    readOnly: true
  name: get-genie
- description: Create a new Workato AI genie
  hints:
    readOnly: false
  name: create-genie
- description: List AI skills available for Workato genies
  hints:
    readOnly: true
  name: list-skills
- description: List Workato knowledge bases for AI-powered lookups
  hints:
    readOnly: true
  name: list-knowledge-bases
- description: Create a new Workato knowledge base
  hints:
    readOnly: false
  name: create-knowledge-base
- description: List Workato MCP servers exposing API tools for AI agents
  hints:
    readOnly: true
  name: list-mcp-servers
- description: Create a new Workato MCP server for exposing API tools
  hints:
    readOnly: false
  name: create-mcp-server
- description: List tools configured on a Workato MCP server
  hints:
    readOnly: true
  name: list-server-tools
- description: Publish a message to a Workato event stream topic
  hints:
    readOnly: false
  name: publish-event
- description: Consume messages from a Workato event stream topic
  hints:
    openWorld: true
    readOnly: true
  name: consume-events
---
