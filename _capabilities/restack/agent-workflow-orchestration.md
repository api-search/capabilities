---
api_specs:
- filename: restack-openapi.yml
  format: yaml
  label: restack
  slug: restack
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/restack/refs/heads/main/openapi/restack-openapi.yml
categories: []
consumed_apis:
- restack
description: Unified capability for scheduling, triggering, and monitoring AI agents and long-running workflows on the Restack platform. Enables product teams and engineers to programmatically invoke agents, track execution status, and manage workflow lifecycle from any client application.
layout: capability
name: Restack Agent and Workflow Orchestration
operations:
- description: Schedule an AI agent by name with typed input parameters
  method: POST
  name: schedule-agent
  path: /v1/agents/{agentName}
- description: Get the current status and output of an agent run
  method: GET
  name: get-agent-run
  path: /v1/agents/{agentName}/{runId}
- description: Schedule a workflow by name with typed input parameters
  method: POST
  name: schedule-workflow
  path: /v1/workflows/{workflowName}
- description: Get the current status and output of a workflow run
  method: GET
  name: get-workflow-run
  path: /v1/workflows/{workflowName}/{runId}
- description: Check Restack server health
  method: GET
  name: health-check
  path: /v1/health
personas: []
provider_name: Restack
provider_slug: restack
search_terms:
- schedule workflow
- schedule an ai agent on restack for asynchronous execution. returns a runid to track progress.
- get workflow run
- check restack server health
- schedule agent
- check the health status of the restack server.
- enterprise
- track agent execution status and retrieve results
- track workflow execution status and retrieve results
- health check
- get the current status and output of an agent run
- schedule ai agents for asynchronous execution
- ai agents
- orchestration
- get the current status and output of a restack agent run by name and run id.
- python
- get the current status and output of a restack workflow run by name and run id.
- schedule long-running workflows that persist state
- schedule a long-running workflow on restack. workflows persist state across days, months, or years.
- server health monitoring
- schedule an ai agent by name with typed input parameters
- get agent run
- schedule a workflow by name with typed input parameters
- automation
- get the current status and output of a workflow run
- workflows
slug: agent-workflow-orchestration
source_filename: agent-workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Restack Agent and Workflow Orchestration\"\n  description: \"Unified capability for scheduling, triggering, and monitoring AI agents and long-running workflows on the Restack platform. Enables product teams and engineers to programmatically invoke agents, track execution status, and manage workflow lifecycle from any client application.\"\n  tags:\n    - AI Agents\n    - Workflows\n    - Orchestration\n    - Enterprise\n    - Automation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RESTACK_API_BEARER_TOKEN: RESTACK_API_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: restack\n      location: ./shared/restack.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: restack-orchestration-api\n      description: \"Unified REST API for AI agent and workflow orchestration on Restack.\"\n      resources:\n        - path: /v1/agents/{agentName}\n         \
  \ name: agents\n          description: \"Schedule AI agents for asynchronous execution\"\n          operations:\n            - method: POST\n              name: schedule-agent\n              description: \"Schedule an AI agent by name with typed input parameters\"\n              call: \"restack.schedule-agent\"\n              with:\n                agentName: \"rest.agentName\"\n                input: \"rest.body.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/agents/{agentName}/{runId}\n          name: agent-runs\n          description: \"Track agent execution status and retrieve results\"\n          operations:\n            - method: GET\n              name: get-agent-run\n              description: \"Get the current status and output of an agent run\"\n              call: \"restack.get-agent-run\"\n              with:\n                agentName: \"rest.agentName\"\n                runId: \"rest.runId\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowName}\n          name: workflows\n          description: \"Schedule long-running workflows that persist state\"\n          operations:\n            - method: POST\n              name: schedule-workflow\n              description: \"Schedule a workflow by name with typed input parameters\"\n              call: \"restack.schedule-workflow\"\n              with:\n                workflowName: \"rest.workflowName\"\n                input: \"rest.body.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowName}/{runId}\n          name: workflow-runs\n          description: \"Track workflow execution status and retrieve results\"\n          operations:\n            - method: GET\n              name: get-workflow-run\n              description: \"Get the current status\
  \ and output of a workflow run\"\n              call: \"restack.get-workflow-run\"\n              with:\n                workflowName: \"rest.workflowName\"\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"Server health monitoring\"\n          operations:\n            - method: GET\n              name: health-check\n              description: \"Check Restack server health\"\n              call: \"restack.health-check\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: restack-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted agent and workflow orchestration on the Restack platform.\"\n      tools:\n        - name: schedule-agent\n          description: \"Schedule an AI agent on\
  \ Restack for asynchronous execution. Returns a runId to track progress.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"restack.schedule-agent\"\n          with:\n            agentName: \"tools.agentName\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-agent-run\n          description: \"Get the current status and output of a Restack agent run by name and run ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restack.get-agent-run\"\n          with:\n            agentName: \"tools.agentName\"\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-workflow\n          description: \"Schedule a long-running workflow on Restack. Workflows\
  \ persist state across days, months, or years.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"restack.schedule-workflow\"\n          with:\n            workflowName: \"tools.workflowName\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow-run\n          description: \"Get the current status and output of a Restack workflow run by name and run ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restack.get-workflow-run\"\n          with:\n            workflowName: \"tools.workflowName\"\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: health-check\n          description: \"Check the health status of the Restack server.\"\n         \
  \ hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restack.health-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/restack/refs/heads/main/capabilities/agent-workflow-orchestration.yaml
tags:
- AI Agents
- Workflows
- Orchestration
- Enterprise
- Automation
tools:
- description: Schedule an AI agent on Restack for asynchronous execution. Returns a runId to track progress.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-agent
- description: Get the current status and output of a Restack agent run by name and run ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-run
- description: Schedule a long-running workflow on Restack. Workflows persist state across days, months, or years.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-workflow
- description: Get the current status and output of a Restack workflow run by name and run ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-workflow-run
- description: Check the health status of the Restack server.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: health-check
---
