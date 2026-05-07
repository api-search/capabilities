---
categories: []
consumed_apis: []
description: Workflow capability for managing the full AI agent lifecycle on Toolhouse — from agent creation and tool configuration to execution monitoring, Agent Studio sessions, and scheduled runs.
layout: capability
name: Toolhouse Agent Management
operations:
- description: List all agents for the authenticated user.
  method: GET
  name: list-agents
  path: /v1/agents
- description: Create or update an AI agent.
  method: POST
  name: create-agent
  path: /v1/agents
- description: Get details of a specific agent.
  method: GET
  name: get-agent
  path: /v1/agents/{agent_id}
- description: List all agent execution runs.
  method: GET
  name: list-agent-runs
  path: /v1/agent-runs
- description: Get details and status of a specific agent run.
  method: GET
  name: get-agent-run
  path: /v1/agent-runs/{run_id}
- description: List all available tools.
  method: GET
  name: list-tools
  path: /v1/tools
- description: List all tool bundles.
  method: GET
  name: list-bundles
  path: /v1/bundles
- description: Create a new tool bundle.
  method: POST
  name: create-bundle
  path: /v1/bundles
- description: List all Agent Studio chat sessions.
  method: GET
  name: list-studio-chats
  path: /v1/studio-chats
- description: Start a new Agent Studio chat session.
  method: POST
  name: create-studio-chat
  path: /v1/studio-chats
- description: List all API keys for the authenticated user.
  method: GET
  name: list-api-keys
  path: /v1/api-keys
personas: []
provider_name: Toolhouse
provider_slug: toolhouse
search_terms:
- agent studio chat sessions.
- tool bundles for grouping tools.
- ai agents
- get a specific agent run.
- list studio chats
- list all toolhouse ai agents for the authenticated user.
- list all agent studio chat sessions for visual agent development.
- get details of a specific agent.
- agent infrastructure
- available tools in the toolhouse library.
- toolhouse
- list all agent studio chat sessions.
- mcp
- list all available tools in the toolhouse tool library.
- get agent
- agent execution history.
- list all api keys for the authenticated toolhouse user.
- list tools
- list all available tools.
- get agent run logs
- subscribe to agent
- create or update an ai agent.
- list bundles
- list all agent execution runs.
- get the details, status, and results of a specific toolhouse agent run.
- retrieve the execution logs for a specific toolhouse agent run.
- create a new agent studio chat session for interactive agent development.
- list all tool bundles.
- list agent runs
- list all api keys for the authenticated user.
- start a new agent studio chat session.
- get the full configuration and details of a specific toolhouse agent.
- get a specific agent.
- create a new tool bundle grouping specific tools together.
- manage ai agents.
- list all tool bundles configured for the authenticated user.
- list api keys
- backend as a service
- create agent
- list all agents for the authenticated user.
- list historical execution runs for toolhouse agents with pagination.
- tools
- create bundle
- get details and status of a specific agent run.
- get agent run
- list agents
- subscribe to a paid toolhouse agent to enable access.
- api key management.
- create a new tool bundle.
- create or update a toolhouse ai agent definition with tools, bundles, and system prompt.
- create studio chat
slug: agent-management
source_filename: agent-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toolhouse Agent Management\n  description: Workflow capability for managing the full AI agent lifecycle on Toolhouse — from agent creation and tool configuration\n    to execution monitoring, Agent Studio sessions, and scheduled runs.\n  tags:\n  - AI Agents\n  - Agent Infrastructure\n  - Backend As A Service\n  - MCP\n  - Tools\n  - Toolhouse\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOOLHOUSE_API_KEY: TOOLHOUSE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: toolhouse-platform\n    baseUri: https://api.toolhouse.ai\n    description: Toolhouse Platform API for managing AI agents, tools, and agent execution.\n    authentication:\n      type: bearer\n      token: '{{TOOLHOUSE_API_KEY}}'\n    resources:\n    - name: agent-runs\n      path: /me/agent-runs\n      description: Manage and retrieve AI agent run history and execution logs.\n      operations:\n      - name: list-agent-runs\n\
  \        method: GET\n        description: List all agent runs for the authenticated user with pagination.\n        inputParameters:\n        - name: next_cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor for next page.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return (default 30).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-run\n        method: GET\n        description: Get details of a specific agent run by run ID.\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the agent run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: get-agent-run-logs\n        method: GET\n        description: Retrieve execution logs for a specific agent run.\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the agent run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-agent-run-mcp-logs\n        method: GET\n        description: Retrieve MCP server logs for a specific agent run.\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the agent run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: agents\n      path: /me/agents\n      description: Create, manage, and configure AI agents.\n      operations:\n      - name: list-agents\n\
  \        method: GET\n        description: Get all agents for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: upsert-agent\n        method: POST\n        description: Create or update an AI agent.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            model: '{{tools.model}}'\n            systemPrompt: '{{tools.systemPrompt}}'\n      - name: get-agent\n        method: GET\n        description: Get details of a specific agent.\n        inputParameters:\n        - name: agent_id\n          in: path\n          type: string\n          required: true\n          description: The agent identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: subscribe-to-agent\n        method: POST\n        description: Subscribe to a paid agent.\n        inputParameters:\n        - name: agent_id\n          in: path\n          type: string\n          required: true\n          description: The agent identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unsubscribe-from-agent\n        method: POST\n        description: Unsubscribe from a paid agent.\n        inputParameters:\n        - name: agent_id\n          in: path\n          type: string\n          required: true\n          description: The agent identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-studio-chats\n      path: /me/agent-studio-chats\n      description: Manage Agent Studio chat sessions.\n\
  \      operations:\n      - name: list-studio-chats\n        method: GET\n        description: Get all Agent Studio chats for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-studio-chat\n        method: POST\n        description: Create a new Agent Studio chat session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            agentId: '{{tools.agentId}}'\n            runId: '{{tools.runId}}'\n      - name: get-studio-chat\n        method: GET\n        description: Get a specific Agent Studio chat by run ID.\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: The run/chat identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-studio-chat\n        method: DELETE\n        description: Delete an Agent Studio chat session.\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: The run/chat identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /me/api-keys\n      description: Manage API keys for the authenticated user.\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: Get all API keys for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create a new API key.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: tools\n      path: /me/tools\n      description: Browse and manage available Toolhouse tools.\n      operations:\n      - name: list-tools\n        method: GET\n        description: List all available tools in the Toolhouse tool library.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: bundles\n      path: /me/bundles\n      description: Manage tool bundles for organizing and sharing tool sets.\n      operations:\n      - name: list-bundles\n        method: GET\n        description: List all tool bundles for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-bundle\n        method: POST\n        description: Create\
  \ a new tool bundle.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            tools: '{{tools.tools}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: toolhouse-agent-management-api\n    description: Unified REST API for the full Toolhouse agent lifecycle management workflow.\n    resources:\n    - path: /v1/agents\n      name: agents\n      description: Manage AI agents.\n      operations:\n      - method: GET\n        name: list-agents\n        description: List all agents for the authenticated user.\n        call: toolhouse-platform.list-agents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-agent\n        description: Create or update an AI agent.\n        call: toolhouse-platform.upsert-agent\n        with:\n          name: rest.name\n\
  \          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agents/{agent_id}\n      name: agent\n      description: Get a specific agent.\n      operations:\n      - method: GET\n        name: get-agent\n        description: Get details of a specific agent.\n        call: toolhouse-platform.get-agent\n        with:\n          agent_id: rest.agent_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agent-runs\n      name: agent-runs\n      description: Agent execution history.\n      operations:\n      - method: GET\n        name: list-agent-runs\n        description: List all agent execution runs.\n        call: toolhouse-platform.list-agent-runs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agent-runs/{run_id}\n      name: agent-run\n      description: Get a specific agent run.\n      operations:\n      - method: GET\n        name:\
  \ get-agent-run\n        description: Get details and status of a specific agent run.\n        call: toolhouse-platform.get-agent-run\n        with:\n          run_id: rest.run_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tools\n      name: tools\n      description: Available tools in the Toolhouse library.\n      operations:\n      - method: GET\n        name: list-tools\n        description: List all available tools.\n        call: toolhouse-platform.list-tools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bundles\n      name: bundles\n      description: Tool bundles for grouping tools.\n      operations:\n      - method: GET\n        name: list-bundles\n        description: List all tool bundles.\n        call: toolhouse-platform.list-bundles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bundle\n        description: Create\
  \ a new tool bundle.\n        call: toolhouse-platform.create-bundle\n        with:\n          name: rest.name\n          tools: rest.tools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/studio-chats\n      name: studio-chats\n      description: Agent Studio chat sessions.\n      operations:\n      - method: GET\n        name: list-studio-chats\n        description: List all Agent Studio chat sessions.\n        call: toolhouse-platform.list-studio-chats\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-studio-chat\n        description: Start a new Agent Studio chat session.\n        call: toolhouse-platform.create-studio-chat\n        with:\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: api-keys\n      description: API key management.\n      operations:\n      - method: GET\n  \
  \      name: list-api-keys\n        description: List all API keys for the authenticated user.\n        call: toolhouse-platform.list-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: toolhouse-agent-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Toolhouse agent lifecycle management.\n    tools:\n    - name: list-agents\n      description: List all Toolhouse AI agents for the authenticated user.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-agents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agent\n      description: Get the full configuration and details of a specific Toolhouse agent.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.get-agent\n      with:\n        agent_id: tools.agent_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-agent\n      description: Create or update a Toolhouse AI agent definition with tools, bundles, and system prompt.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: toolhouse-platform.upsert-agent\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-agent-runs\n      description: List historical execution runs for Toolhouse agents with pagination.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-agent-runs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agent-run\n      description: Get the details, status, and results of a specific Toolhouse agent run.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.get-agent-run\n      with:\n        run_id: tools.run_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-agent-run-logs\n      description: Retrieve the execution logs for a specific Toolhouse agent run.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.get-agent-run-logs\n      with:\n        run_id: tools.run_id\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-tools\n      description: List all available tools in the Toolhouse tool library.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-tools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bundles\n      description: List all tool bundles configured for the authenticated user.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-bundles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bundle\n      description: Create a new\
  \ tool bundle grouping specific tools together.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: toolhouse-platform.create-bundle\n      with:\n        name: tools.name\n        tools: tools.tools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-studio-chats\n      description: List all Agent Studio chat sessions for visual agent development.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-studio-chats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-studio-chat\n      description: Create a new Agent Studio chat session for interactive agent development.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: toolhouse-platform.create-studio-chat\n      with:\n        agentId: tools.agentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List\
  \ all API keys for the authenticated Toolhouse user.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toolhouse-platform.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe-to-agent\n      description: Subscribe to a paid Toolhouse agent to enable access.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: toolhouse-platform.subscribe-to-agent\n      with:\n        agent_id: tools.agent_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toolhouse/refs/heads/main/capabilities/agent-management.yaml
tags:
- AI Agents
- Agent Infrastructure
- Backend As A Service
- MCP
- Tools
- Toolhouse
tools:
- description: List all Toolhouse AI agents for the authenticated user.
  hints:
    idempotent: true
    readOnly: true
  name: list-agents
- description: Get the full configuration and details of a specific Toolhouse agent.
  hints:
    idempotent: true
    readOnly: true
  name: get-agent
- description: Create or update a Toolhouse AI agent definition with tools, bundles, and system prompt.
  hints:
    idempotent: false
    readOnly: false
  name: create-agent
- description: List historical execution runs for Toolhouse agents with pagination.
  hints:
    idempotent: true
    readOnly: true
  name: list-agent-runs
- description: Get the details, status, and results of a specific Toolhouse agent run.
  hints:
    idempotent: true
    readOnly: true
  name: get-agent-run
- description: Retrieve the execution logs for a specific Toolhouse agent run.
  hints:
    idempotent: true
    readOnly: true
  name: get-agent-run-logs
- description: List all available tools in the Toolhouse tool library.
  hints:
    idempotent: true
    readOnly: true
  name: list-tools
- description: List all tool bundles configured for the authenticated user.
  hints:
    idempotent: true
    readOnly: true
  name: list-bundles
- description: Create a new tool bundle grouping specific tools together.
  hints:
    idempotent: false
    readOnly: false
  name: create-bundle
- description: List all Agent Studio chat sessions for visual agent development.
  hints:
    idempotent: true
    readOnly: true
  name: list-studio-chats
- description: Create a new Agent Studio chat session for interactive agent development.
  hints:
    idempotent: false
    readOnly: false
  name: create-studio-chat
- description: List all API keys for the authenticated Toolhouse user.
  hints:
    idempotent: true
    readOnly: true
  name: list-api-keys
- description: Subscribe to a paid Toolhouse agent to enable access.
  hints:
    idempotent: false
    readOnly: false
  name: subscribe-to-agent
---
