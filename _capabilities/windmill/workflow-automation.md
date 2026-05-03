---
api_specs:
- filename: windmill-api-openapi.yml
  format: yaml
  label: windmill
  slug: windmill
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/windmill/refs/heads/main/openapi/windmill-api-openapi.yml
categories: []
consumed_apis:
- windmill
description: Workflow automation capability for Windmill, enabling end-to-end management of scripts, flows, schedules, resources, and job execution. Designed for platform engineers and automation teams building internal tools, ETL pipelines, and scheduled workflows on the Windmill platform.
layout: capability
name: Windmill Workflow Automation
operations:
- description: List all scripts in a workspace
  method: GET
  name: list-scripts
  path: /v1/scripts
- description: Create a new script
  method: POST
  name: create-script
  path: /v1/scripts
- description: Get a script by path
  method: GET
  name: get-script
  path: /v1/scripts/{path}
- description: Delete a script by path
  method: DELETE
  name: delete-script
  path: /v1/scripts/{path}
- description: List all flows in a workspace
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a new flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: Get a flow by path
  method: GET
  name: get-flow
  path: /v1/flows/{path}
- description: List completed jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get a completed job
  method: GET
  name: get-job
  path: /v1/jobs/{id}
- description: Run a script by path
  method: POST
  name: run-script
  path: /v1/runs
- description: List all schedules
  method: GET
  name: list-schedules
  path: /v1/schedules
- description: Create a new schedule
  method: POST
  name: create-schedule
  path: /v1/schedules
- description: List all resources
  method: GET
  name: list-resources
  path: /v1/resources
- description: Create a new resource
  method: POST
  name: create-resource
  path: /v1/resources
- description: List contextual variables
  method: GET
  name: list-variables
  path: /v1/variables
- description: Create a new variable
  method: POST
  name: create-variable
  path: /v1/variables
- description: List all workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a new workspace
  method: POST
  name: create-workspace
  path: /v1/workspaces
- description: List users in workspace
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Windmill
provider_slug: windmill
search_terms:
- procode api composition
- list completed jobs in a windmill workspace
- list all available windmill workspaces
- delete script
- jobs
- create schedule
- individual job operations
- schedules
- webhooks
- list jobs
- workflows
- cancel a queued job in a windmill workspace
- get script
- job execution
- list scripts
- create a new windmill workspace
- get a script by path
- create a new variable in a windmill workspace
- automation
- internal tools
- create a new resource
- create a new schedule
- get a flow by path
- list users in workspace
- open source
- list completed jobs
- windmill
- variable management
- list all resources
- get a completed job
- create script
- list resources
- list all schedules
- user management
- job listing and monitoring
- create a new resource in a windmill workspace
- resource management
- get a specific script by path from a windmill workspace
- create a new flow
- list all flows in a windmill workspace
- list all resources in a windmill workspace
- list workspaces
- get a specific flow by path from a windmill workspace
- workflow engine
- create flow
- list all flows in a workspace
- create a new flow in a windmill workspace
- individual script operations
- run a script by path
- create variable
- create a new script
- cancel job
- list variables
- list contextual variables
- list all scripts in a workspace
- get a specific completed job by id
- script management and execution
- list flows
- list all scripts in a windmill workspace
- list schedules
- create resource
- create workspace
- individual flow operations
- run script
- execute a script by path in a windmill workspace
- scripts
- list all schedules in a windmill workspace
- list users in a windmill workspace
- get flow
- delete a script by path
- create a new schedule in a windmill workspace
- workspace administration
- schedule management
- create a new variable
- flow management
- list users
- list all workspaces
- get job
- create a new workspace
- create a new script in a windmill workspace
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Windmill Workflow Automation\"\n  description: >-\n    Workflow automation capability for Windmill, enabling end-to-end management\n    of scripts, flows, schedules, resources, and job execution. Designed for\n    platform engineers and automation teams building internal tools, ETL pipelines,\n    and scheduled workflows on the Windmill platform.\n  tags:\n    - Windmill\n    - Automation\n    - Workflows\n    - Scripts\n    - Jobs\n    - Schedules\n    - Internal Tools\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WINDMILL_TOKEN: WINDMILL_TOKEN\n\ncapability:\n  consumes:\n    - import: windmill\n      location: ./shared/windmill-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: windmill-workflow-api\n      description: \"Unified REST API for Windmill workflow automation.\"\n      resources:\n        - path: /v1/scripts\n          name: scripts\n\
  \          description: \"Script management and execution\"\n          operations:\n            - method: GET\n              name: list-scripts\n              description: \"List all scripts in a workspace\"\n              call: \"windmill.list-scripts\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-script\n              description: \"Create a new script\"\n              call: \"windmill.create-script\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scripts/{path}\n          name: script\n          description: \"Individual script operations\"\n          operations:\n            - method: GET\n              name: get-script\n              description: \"Get a script by\
  \ path\"\n              call: \"windmill.get-script-by-path\"\n              with:\n                workspace: \"rest.workspace\"\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-script\n              description: \"Delete a script by path\"\n              call: \"windmill.delete-script-by-path\"\n              with:\n                workspace: \"rest.workspace\"\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows\n          name: flows\n          description: \"Flow management\"\n          operations:\n            - method: GET\n              name: list-flows\n              description: \"List all flows in a workspace\"\n              call: \"windmill.list-flows\"\n              with:\n                workspace: \"rest.workspace\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flow\n              description: \"Create a new flow\"\n              call: \"windmill.create-flow\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{path}\n          name: flow\n          description: \"Individual flow operations\"\n          operations:\n            - method: GET\n              name: get-flow\n              description: \"Get a flow by path\"\n              call: \"windmill.get-flow-by-path\"\n              with:\n                workspace: \"rest.workspace\"\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs\n          name: jobs\n          description:\
  \ \"Job listing and monitoring\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List completed jobs\"\n              call: \"windmill.list-completed-jobs\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{id}\n          name: job\n          description: \"Individual job operations\"\n          operations:\n            - method: GET\n              name: get-job\n              description: \"Get a completed job\"\n              call: \"windmill.get-completed-job\"\n              with:\n                workspace: \"rest.workspace\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/runs\n          name: runs\n          description: \"Job execution\"\n          operations:\n   \
  \         - method: POST\n              name: run-script\n              description: \"Run a script by path\"\n              call: \"windmill.run-script-by-path\"\n              with:\n                workspace: \"rest.workspace\"\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schedules\n          name: schedules\n          description: \"Schedule management\"\n          operations:\n            - method: GET\n              name: list-schedules\n              description: \"List all schedules\"\n              call: \"windmill.list-schedules\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-schedule\n              description: \"Create a new schedule\"\n              call: \"windmill.create-schedule\"\n\
  \              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List all resources\"\n              call: \"windmill.list-resources\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-resource\n              description: \"Create a new resource\"\n              call: \"windmill.create-resource\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/variables\n\
  \          name: variables\n          description: \"Variable management\"\n          operations:\n            - method: GET\n              name: list-variables\n              description: \"List contextual variables\"\n              call: \"windmill.list-contextual-variables\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-variable\n              description: \"Create a new variable\"\n              call: \"windmill.create-variable\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Workspace administration\"\n          operations:\n            - method: GET\n              name: list-workspaces\n            \
  \  description: \"List all workspaces\"\n              call: \"windmill.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace\n              description: \"Create a new workspace\"\n              call: \"windmill.create-workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users in workspace\"\n              call: \"windmill.list-users\"\n              with:\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: windmill-workflow-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted Windmill workflow automation.\"\n      tools:\n        - name: list-scripts\n          description: \"List all scripts in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-scripts\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-script\n          description: \"Get a specific script by path from a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windmill.get-script-by-path\"\n          with:\n            workspace: \"tools.workspace\"\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-script\n          description: \"Create a new script in a Windmill workspace\"\n   \
  \       hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-script\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-script\n          description: \"Execute a script by path in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.run-script-by-path\"\n          with:\n            workspace: \"tools.workspace\"\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-flows\n          description: \"List all flows in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-flows\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n\n        - name: get-flow\n          description: \"Get a specific flow by path from a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windmill.get-flow-by-path\"\n          with:\n            workspace: \"tools.workspace\"\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-flow\n          description: \"Create a new flow in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-flow\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: \"List completed jobs in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"windmill.list-completed-jobs\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job\n          description: \"Get a specific completed job by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windmill.get-completed-job\"\n          with:\n            workspace: \"tools.workspace\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-job\n          description: \"Cancel a queued job in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"windmill.cancel-queued-job\"\n          with:\n            workspace: \"tools.workspace\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-schedules\n          description: \"List all schedules in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-schedules\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-schedule\n          description: \"Create a new schedule in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-schedule\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resources\n          description: \"List all resources in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-resources\"\
  \n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-resource\n          description: \"Create a new resource in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-resource\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-variable\n          description: \"Create a new variable in a Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-variable\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workspaces\n          description: \"List all available Windmill\
  \ workspaces\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-workspace\n          description: \"Create a new Windmill workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windmill.create-workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List users in a Windmill workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windmill.list-users\"\n          with:\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/windmill/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Windmill
- Automation
- Workflows
- Scripts
- Jobs
- Schedules
- Internal Tools
tools:
- description: List all scripts in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-scripts
- description: Get a specific script by path from a Windmill workspace
  hints:
    openWorld: false
    readOnly: true
  name: get-script
- description: Create a new script in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-script
- description: Execute a script by path in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: run-script
- description: List all flows in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Get a specific flow by path from a Windmill workspace
  hints:
    openWorld: false
    readOnly: true
  name: get-flow
- description: Create a new flow in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-flow
- description: List completed jobs in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Get a specific completed job by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-job
- description: Cancel a queued job in a Windmill workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-job
- description: List all schedules in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-schedules
- description: Create a new schedule in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-schedule
- description: List all resources in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-resources
- description: Create a new resource in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-resource
- description: Create a new variable in a Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-variable
- description: List all available Windmill workspaces
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Create a new Windmill workspace
  hints:
    destructive: false
    readOnly: false
  name: create-workspace
- description: List users in a Windmill workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-users
---
