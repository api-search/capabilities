---
categories: []
consumed_apis: []
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
- ai genies
- get a specific workato recipe by id
- delete recipe
- integration
- list mcp servers
- list workato knowledge bases for ai-powered lookups
- list recipes
- workflow
- get genie
- get recipe
- stop a recipe
- list data tables
- consume events
- consume messages from a workato event stream topic
- knowledge bases
- start a workato recipe to begin processing triggers
- create mcp server
- list skills
- list workato automation recipes with optional filtering
- get recipe health
- get health status report for a workato recipe
- list automation recipes
- create a new workato automation recipe
- b2b
- automation recipes
- enterprise
- ai skills
- create a new workato ai genie
- list ai skills available for workato genies
- list workato data tables for structured data storage
- publish message to topic
- create a new workato knowledge base
- publish events
- create recipe
- publish message
- orchestration
- ipaas
- start a recipe
- list ai genies
- ai agents
- list ai skills
- create a new workato mcp server for exposing api tools
- list tools configured on a workato mcp server
- stop recipe
- embedded ipaas
- get a recipe
- get a specific workato ai genie by id
- workato
- create knowledge base
- api management
- list genies
- create genie
- list server tools
- delete a recipe
- data tables
- list knowledge bases
- agentic
- list workato mcp servers exposing api tools for ai agents
- stop a running workato recipe
- publish a message to a workato event stream topic
- publish event
- list workato ai genies for agentic automation
- mcp servers
- create a new recipe
- single recipe management
- start recipe
- automation
slug: automation-management
source_filename: automation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workato Automation Management\n  description: Unified capability for integration engineers and automation teams managing Workato recipes, data tables, event\n    streams, and AI-powered agent workflows. Combines the Developer API, Agent Studio, Event Streams, and MCP Server APIs\n    into a single automation operations workflow.\n  tags:\n  - AI Agents\n  - Automation\n  - Integration\n  - iPaaS\n  - Orchestration\n  - Workato\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKATO_API_TOKEN: WORKATO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workato-developer\n    baseUri: https://www.workato.com\n    description: Workato Developer API for recipe and data table management\n    authentication:\n      type: bearer\n      token: '{{WORKATO_API_TOKEN}}'\n    resources:\n    - name: recipes\n      path: /api/recipes\n      description: Workato automation recipes\n      operations:\n\
  \      - name: list-recipes\n        method: GET\n        description: List automation recipes\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-recipe\n        method: POST\n        description: Create a new recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: recipe-by-id\n      path: /api/recipes/{id}\n      description: Single recipe operations\n      operations:\n\
  \      - name: get-recipe\n        method: GET\n        description: Get a recipe by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-recipe\n        method: PUT\n        description: Update a recipe\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-recipe\n        method: DELETE\n        description: Delete a recipe\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n\
  \          required: true\n          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe-start\n      path: /api/recipes/{id}/start\n      description: Start a recipe\n      operations:\n      - name: start-recipe\n        method: PUT\n        description: Start running a recipe\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe-stop\n      path: /api/recipes/{id}/stop\n      description: Stop a recipe\n      operations:\n      - name: stop-recipe\n        method: PUT\n        description: Stop a running recipe\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n\
  \          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe-health\n      path: /api/recipes/{recipe_id}/health\n      description: Recipe health monitoring\n      operations:\n      - name: get-recipe-health\n        method: GET\n        description: Get recipe health report\n        inputParameters:\n        - name: recipe_id\n          in: path\n          type: integer\n          required: true\n          description: Recipe ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables\n      path: /api/data_tables\n      description: Workato data tables\n      operations:\n      - name: list-data-tables\n        method: GET\n        description: List all data tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-data-table\n        method: POST\n        description: Create a new data table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  - type: http\n    namespace: workato-agent-studio\n    baseUri: https://www.workato.com\n    description: Workato Agent Studio API for AI genie and skill management\n    authentication:\n      type: bearer\n      token: '{{WORKATO_API_TOKEN}}'\n    resources:\n    - name: genies\n      path: /api/agentic/genies\n      description: Workato AI genies\n      operations:\n      - name: list-genies\n        method: GET\n        description: List all AI genies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-genie\n        method: POST\n        description:\
  \ Create a new AI genie\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: genie-by-id\n      path: /api/agentic/genies/{id}\n      description: Single genie operations\n      operations:\n      - name: get-genie\n        method: GET\n        description: Get a genie by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Genie ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-genie\n        method: PUT\n        description: Update a genie\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ Genie ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-genie\n        method: DELETE\n        description: Delete a genie\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Genie ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: skills\n      path: /api/agentic/skills\n      description: Workato AI skills\n      operations:\n      - name: list-skills\n        method: GET\n        description: List all AI skills\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-skill\n        method: POST\n        description: Create a\
  \ new AI skill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: knowledge-bases\n      path: /api/agentic/knowledge_bases\n      description: Workato knowledge bases\n      operations:\n      - name: list-knowledge-bases\n        method: GET\n        description: List all knowledge bases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-knowledge-base\n        method: POST\n        description: Create a new knowledge base\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  - type: http\n    namespace: workato-mcp\n    baseUri: https://www.workato.com\n\
  \    description: Workato MCP Server management API\n    authentication:\n      type: bearer\n      token: '{{WORKATO_API_TOKEN}}'\n    resources:\n    - name: mcp-servers\n      path: /api/mcp/mcp_servers\n      description: MCP server management\n      operations:\n      - name: list-mcp-servers\n        method: GET\n        description: List MCP servers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-mcp-server\n        method: POST\n        description: Create a new MCP server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: mcp-server-by-handle\n      path: /api/mcp/mcp_servers/{handle}\n      description: Single MCP server operations\n      operations:\n      - name: get-mcp-server\n        method: GET\n\
  \        description: Get an MCP server by handle\n        inputParameters:\n        - name: handle\n          in: path\n          type: string\n          required: true\n          description: MCP server handle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-mcp-server\n        method: PUT\n        description: Update an MCP server\n        inputParameters:\n        - name: handle\n          in: path\n          type: string\n          required: true\n          description: MCP server handle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-mcp-server\n        method: DELETE\n        description: Delete an MCP server\n        inputParameters:\n        - name: handle\n          in: path\n          type:\
  \ string\n          required: true\n          description: MCP server handle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mcp-server-tools\n      path: /api/mcp/mcp_servers/{mcp_server_handle}/tools\n      description: MCP server tool management\n      operations:\n      - name: list-server-tools\n        method: GET\n        description: List tools for an MCP server\n        inputParameters:\n        - name: mcp_server_handle\n          in: path\n          type: string\n          required: true\n          description: MCP server handle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-groups\n      path: /api/mcp/user_groups\n      description: MCP user groups\n      operations:\n      - name: list-user-groups\n        method: GET\n        description: List user groups\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workato-events\n    baseUri: https://www.workato.com\n    description: Workato Event Streams API for pub/sub messaging\n    authentication:\n      type: bearer\n      token: '{{WORKATO_API_TOKEN}}'\n    resources:\n    - name: topic-publish\n      path: /api/v1/topics/{topic_id}/publish\n      description: Publish single message to topic\n      operations:\n      - name: publish-message\n        method: POST\n        description: Publish a message to a topic\n        inputParameters:\n        - name: topic_id\n          in: path\n          type: string\n          required: true\n          description: Topic ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n    - name: topic-batch-publish\n\
  \      path: /api/v1/batch/topics/{topic_id}/publish\n      description: Batch publish messages to topic\n      operations:\n      - name: batch-publish-messages\n        method: POST\n        description: Publish a batch of messages to a topic\n        inputParameters:\n        - name: topic_id\n          in: path\n          type: string\n          required: true\n          description: Topic ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            messages: '{{tools.messages}}'\n    - name: topic-consume\n      path: /api/v1/topics/{topic_id}/consume\n      description: Consume messages from topic\n      operations:\n      - name: consume-messages\n        method: POST\n        description: Consume messages from a topic\n        inputParameters:\n        - name: topic_id\n          in: path\n          type: string\n          required: true\n    \
  \      description: Topic ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            timeout: '{{tools.timeout}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workato-automation-api\n    description: Unified REST API for Workato automation management workflows.\n    resources:\n    - path: /v1/recipes\n      name: recipes\n      description: Automation recipes\n      operations:\n      - method: GET\n        name: list-recipes\n        description: List automation recipes\n        call: workato-developer.list-recipes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-recipe\n        description: Create a new recipe\n        call: workato-developer.create-recipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipes/{id}\n    \
  \  name: recipe-by-id\n      description: Single recipe management\n      operations:\n      - method: GET\n        name: get-recipe\n        description: Get a recipe\n        call: workato-developer.get-recipe\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-recipe\n        description: Delete a recipe\n        call: workato-developer.delete-recipe\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipes/{id}/start\n      name: recipe-start\n      operations:\n      - method: PUT\n        name: start-recipe\n        description: Start a recipe\n        call: workato-developer.start-recipe\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipes/{id}/stop\n      name: recipe-stop\n      operations:\n      - method: PUT\n\
  \        name: stop-recipe\n        description: Stop a recipe\n        call: workato-developer.stop-recipe\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-tables\n      name: data-tables\n      description: Data tables\n      operations:\n      - method: GET\n        name: list-data-tables\n        description: List data tables\n        call: workato-developer.list-data-tables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/genies\n      name: genies\n      description: AI genies\n      operations:\n      - method: GET\n        name: list-genies\n        description: List AI genies\n        call: workato-agent-studio.list-genies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skills\n      name: skills\n      description: AI skills\n      operations:\n      - method: GET\n        name: list-skills\n        description:\
  \ List AI skills\n        call: workato-agent-studio.list-skills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/knowledge-bases\n      name: knowledge-bases\n      description: Knowledge bases\n      operations:\n      - method: GET\n        name: list-knowledge-bases\n        description: List knowledge bases\n        call: workato-agent-studio.list-knowledge-bases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mcp-servers\n      name: mcp-servers\n      description: MCP servers\n      operations:\n      - method: GET\n        name: list-mcp-servers\n        description: List MCP servers\n        call: workato-mcp.list-mcp-servers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topics/{topic_id}/publish\n      name: topic-publish\n      description: Publish events\n      operations:\n      - method: POST\n        name: publish-message\n        description:\
  \ Publish message to topic\n        call: workato-events.publish-message\n        with:\n          topic_id: rest.topic_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: workato-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Workato automation management, recipe operations, and agentic workflow orchestration.\n    tools:\n    - name: list-recipes\n      description: List Workato automation recipes with optional filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workato-developer.list-recipes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recipe\n      description: Get a specific Workato recipe by ID\n      hints:\n        readOnly: true\n      call: workato-developer.get-recipe\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-recipe\n\
  \      description: Create a new Workato automation recipe\n      hints:\n        readOnly: false\n      call: workato-developer.create-recipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-recipe\n      description: Start a Workato recipe to begin processing triggers\n      hints:\n        readOnly: false\n      call: workato-developer.start-recipe\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-recipe\n      description: Stop a running Workato recipe\n      hints:\n        readOnly: false\n      call: workato-developer.stop-recipe\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recipe-health\n      description: Get health status report for a Workato recipe\n      hints:\n        readOnly: true\n      call: workato-developer.get-recipe-health\n      with:\n        recipe_id: tools.recipe_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-data-tables\n      description: List Workato data tables for structured data storage\n      hints:\n        readOnly: true\n      call: workato-developer.list-data-tables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-genies\n      description: List Workato AI genies for agentic automation\n      hints:\n        readOnly: true\n      call: workato-agent-studio.list-genies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-genie\n      description: Get a specific Workato AI genie by ID\n      hints:\n        readOnly: true\n      call: workato-agent-studio.get-genie\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-genie\n      description: Create a new Workato AI genie\n      hints:\n        readOnly: false\n      call: workato-agent-studio.create-genie\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: list-skills\n      description: List AI skills available for Workato genies\n      hints:\n        readOnly: true\n      call: workato-agent-studio.list-skills\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-knowledge-bases\n      description: List Workato knowledge bases for AI-powered lookups\n      hints:\n        readOnly: true\n      call: workato-agent-studio.list-knowledge-bases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-knowledge-base\n      description: Create a new Workato knowledge base\n      hints:\n        readOnly: false\n      call: workato-agent-studio.create-knowledge-base\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mcp-servers\n      description: List Workato MCP servers exposing API tools for AI agents\n      hints:\n        readOnly: true\n      call: workato-mcp.list-mcp-servers\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-mcp-server\n      description: Create a new Workato MCP server for exposing API tools\n      hints:\n        readOnly: false\n      call: workato-mcp.create-mcp-server\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-server-tools\n      description: List tools configured on a Workato MCP server\n      hints:\n        readOnly: true\n      call: workato-mcp.list-server-tools\n      with:\n        mcp_server_handle: tools.handle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-event\n      description: Publish a message to a Workato event stream topic\n      hints:\n        readOnly: false\n      call: workato-events.publish-message\n      with:\n        topic_id: tools.topic_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: consume-events\n      description: Consume messages from a Workato event stream topic\n     \
  \ hints:\n        readOnly: true\n        openWorld: true\n      call: workato-events.consume-messages\n      with:\n        topic_id: tools.topic_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
