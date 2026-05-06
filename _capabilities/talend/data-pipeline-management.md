---
categories: []
consumed_apis: []
description: Workflow capability for data engineers and platform teams to manage, execute, and monitor data integration pipelines in Qlik Talend Cloud. Combines orchestration (task and plan management) with processing (execution and monitoring) for end-to-end pipeline lifecycle management.
layout: capability
name: Talend Data Pipeline Management
operations:
- description: List all workspaces in the account
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: List tasks, optionally filtered by workspace
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: List all plans
  method: GET
  name: list-plans
  path: /v1/plans
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Run a data integration task
  method: POST
  name: execute-task
  path: /v1/executions
- description: List task execution history
  method: GET
  name: list-task-executions
  path: /v1/executions
- description: Check execution status
  method: GET
  name: get-execution-status
  path: /v1/executions/{executionId}
- description: Run a data integration plan
  method: POST
  name: execute-plan
  path: /v1/plan-executions
- description: List available remote engines
  method: GET
  name: list-remote-engines
  path: /v1/remote-engines
- description: List all connections
  method: GET
  name: list-connections
  path: /v1/connections
personas: []
provider_name: Talend
provider_slug: talend
search_terms:
- list task execution history filtered by task id, status, or time range
- list all plans
- data integration
- list environments
- list all environments
- list all connections
- list tasks
- trigger and monitor task executions
- list available remote engines
- run a data integration plan
- pipelines
- list execution plans composed of multiple data integration tasks
- list data integration tasks, optionally filtered by workspace id
- data engineering
- etl
- manage data integration tasks
- get execution status and details
- list deployment environments (development, staging, production)
- data quality
- trigger and monitor plan executions
- manage deployment environments
- list tasks, optionally filtered by workspace
- list data source and destination connections configured in talend
- run a data integration task
- check the current status of a task or plan execution
- view remote engine status
- orchestration
- run a multi-step data integration plan from start or resume from a failed step
- list remote engines
- list workspaces
- execute task
- check execution status
- api management
- pipeline management
- get execution status
- list connections
- list task execution history
- manage talend cloud workspaces
- manage data source connections
- trigger execution of a talend data integration task in a specified environment
- list all talend cloud workspaces available in the account
- list all workspaces in the account
- manage execution plans
- execute plan
- list task executions
- list remote talend execution engines with their status and capabilities
- talend
- list plans
slug: data-pipeline-management
source_filename: data-pipeline-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Talend Data Pipeline Management\n  description: Workflow capability for data engineers and platform teams to manage, execute, and monitor data integration\n    pipelines in Qlik Talend Cloud. Combines orchestration (task and plan management) with processing (execution and monitoring)\n    for end-to-end pipeline lifecycle management.\n  tags:\n  - Data Engineering\n  - Data Integration\n  - ETL\n  - Pipeline Management\n  - Talend\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TALEND_ACCESS_TOKEN: TALEND_ACCESS_TOKEN\n    TALEND_REGION: TALEND_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: talend-orchestration\n    baseUri: https://api.{{TALEND_REGION}}.cloud.talend.com\n    description: Talend Cloud Orchestration API\n    authentication:\n      type: bearer\n      token: '{{TALEND_ACCESS_TOKEN}}'\n    resources:\n    - name: workspaces\n      path: /orchestration/workspaces\n\
  \      description: Manage Talend Cloud workspaces\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n      - name: create-workspace\n        method: POST\n        description: Create a new workspace\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /orchestration/executables/tasks\n      description: Manage data integration tasks\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks in the account\n        inputParameters:\n        - name: workspaceId\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter by workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n      - name: create-task\n        method: POST\n        description: Create a new data integration task\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            workspaceId: '{{tools.workspace_id}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plans\n      path: /orchestration/executables/plans\n      description: Manage execution plans\n      operations:\n      - name: list-plans\n        method: GET\n        description: List all plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n    - name: schedules\n\
  \      path: /orchestration/schedules\n      description: Manage execution schedules\n      operations:\n      - name: list-schedules\n        method: GET\n        description: List all schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n    - name: environments\n      path: /orchestration/environments\n      description: Manage deployment environments\n      operations:\n      - name: list-environments\n        method: GET\n        description: List all environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n    - name: connections\n      path: /orchestration/connections\n      description: Manage data source connections\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.items\n  - type: http\n    namespace: talend-processing\n    baseUri: https://api.{{TALEND_REGION}}.cloud.talend.com\n    description: Talend Cloud Processing API\n    authentication:\n      type: bearer\n      token: '{{TALEND_ACCESS_TOKEN}}'\n    resources:\n    - name: task-executions\n      path: /processing/executions\n      description: Execute and manage task runs\n      operations:\n      - name: execute-task\n        method: POST\n        description: Trigger execution of a data integration task\n        body:\n          type: json\n          data:\n            taskId: '{{tools.task_id}}'\n            environmentId: '{{tools.environment_id}}'\n            logLevel: '{{tools.log_level}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-execution-status\n      path: /processing/executions/{executionId}\n      description: Get status\
  \ of a task execution\n      operations:\n      - name: get-task-execution-status\n        method: GET\n        description: Check execution status and details\n        inputParameters:\n        - name: executionId\n          in: path\n          type: string\n          required: true\n          description: Execution identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-execution-list\n      path: /processing/executables/tasks/executions\n      description: List task execution history\n      operations:\n      - name: list-task-executions\n        method: GET\n        description: List all task executions with optional filters\n        inputParameters:\n        - name: taskId\n          in: query\n          type: string\n          required: false\n          description: Filter by task ID\n        - name: status\n          in: query\n          type: string\n          required: false\n \
  \         description: Filter by status (RUNNING, SUCCESS, FAILURE, CANCELLED)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n    - name: plan-executions\n      path: /processing/executions/plans\n      description: Execute plans\n      operations:\n      - name: execute-plan\n        method: POST\n        description: Trigger execution of a data integration plan\n        body:\n          type: json\n          data:\n            planId: '{{tools.plan_id}}'\n            environmentId: '{{tools.environment_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: remote-engines\n      path: /processing/runtimes/remote-engines\n      description: Manage remote engines\n      operations:\n      - name: list-remote-engines\n        method: GET\n        description: List all available remote engines\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.items\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: talend-pipeline-api\n    description: Unified REST API for Talend data pipeline management.\n    resources:\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage Talend Cloud workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces in the account\n        call: talend-orchestration.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Manage data integration tasks\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List tasks, optionally filtered by workspace\n        call: talend-orchestration.list-tasks\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/plans\n      name: plans\n      description: Manage execution plans\n      operations:\n      - method: GET\n        name: list-plans\n        description: List all plans\n        call: talend-orchestration.list-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n      name: environments\n      description: Manage deployment environments\n      operations:\n      - method: GET\n        name: list-environments\n        description: List all environments\n        call: talend-orchestration.list-environments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions\n      name: executions\n      description: Trigger and monitor task executions\n      operations:\n      - method: POST\n        name: execute-task\n        description: Run a data integration task\n        call: talend-processing.execute-task\n        with:\n          task_id:\
  \ rest.taskId\n          environment_id: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-task-executions\n        description: List task execution history\n        call: talend-processing.list-task-executions\n        with:\n          taskId: rest.taskId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{executionId}\n      name: execution-detail\n      description: Get execution status and details\n      operations:\n      - method: GET\n        name: get-execution-status\n        description: Check execution status\n        call: talend-processing.get-task-execution-status\n        with:\n          executionId: rest.executionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plan-executions\n      name: plan-executions\n      description: Trigger and monitor plan executions\n\
  \      operations:\n      - method: POST\n        name: execute-plan\n        description: Run a data integration plan\n        call: talend-processing.execute-plan\n        with:\n          plan_id: rest.planId\n          environment_id: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/remote-engines\n      name: remote-engines\n      description: View remote engine status\n      operations:\n      - method: GET\n        name: list-remote-engines\n        description: List available remote engines\n        call: talend-processing.list-remote-engines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Manage data source connections\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connections\n        call: talend-orchestration.list-connections\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: talend-pipeline-mcp\n    transport: http\n    description: MCP server for AI-assisted Talend data pipeline management.\n    tools:\n    - name: list-workspaces\n      description: List all Talend Cloud workspaces available in the account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-orchestration.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List data integration tasks, optionally filtered by workspace ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-orchestration.list-tasks\n      with:\n        workspaceId: tools.workspace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plans\n      description: List execution plans composed of multiple data integration tasks\n      hints:\n        readOnly: true\n   \
  \     openWorld: false\n      call: talend-orchestration.list-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List deployment environments (development, staging, production)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-orchestration.list-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List data source and destination connections configured in Talend\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-orchestration.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-task\n      description: Trigger execution of a Talend data integration task in a specified environment\n      hints:\n        readOnly: false\n        openWorld: false\n      call: talend-processing.execute-task\n      with:\n        task_id: tools.task_id\n\
  \        environment_id: tools.environment_id\n        log_level: tools.log_level\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-status\n      description: Check the current status of a task or plan execution\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-processing.get-task-execution-status\n      with:\n        executionId: tools.execution_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-executions\n      description: List task execution history filtered by task ID, status, or time range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-processing.list-task-executions\n      with:\n        taskId: tools.task_id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-plan\n      description: Run a multi-step data integration plan from start or resume from a failed\
  \ step\n      hints:\n        readOnly: false\n        openWorld: false\n      call: talend-processing.execute-plan\n      with:\n        plan_id: tools.plan_id\n        environment_id: tools.environment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-remote-engines\n      description: List remote Talend execution engines with their status and capabilities\n      hints:\n        readOnly: true\n        openWorld: false\n      call: talend-processing.list-remote-engines\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/talend/refs/heads/main/capabilities/data-pipeline-management.yaml
tags:
- Data Engineering
- Data Integration
- ETL
- Pipeline Management
- Talend
tools:
- description: List all Talend Cloud workspaces available in the account
  hints:
    openWorld: false
    readOnly: true
  name: list-workspaces
- description: List data integration tasks, optionally filtered by workspace ID
  hints:
    openWorld: false
    readOnly: true
  name: list-tasks
- description: List execution plans composed of multiple data integration tasks
  hints:
    openWorld: false
    readOnly: true
  name: list-plans
- description: List deployment environments (development, staging, production)
  hints:
    openWorld: false
    readOnly: true
  name: list-environments
- description: List data source and destination connections configured in Talend
  hints:
    openWorld: false
    readOnly: true
  name: list-connections
- description: Trigger execution of a Talend data integration task in a specified environment
  hints:
    openWorld: false
    readOnly: false
  name: execute-task
- description: Check the current status of a task or plan execution
  hints:
    openWorld: false
    readOnly: true
  name: get-execution-status
- description: List task execution history filtered by task ID, status, or time range
  hints:
    openWorld: false
    readOnly: true
  name: list-task-executions
- description: Run a multi-step data integration plan from start or resume from a failed step
  hints:
    openWorld: false
    readOnly: false
  name: execute-plan
- description: List remote Talend execution engines with their status and capabilities
  hints:
    openWorld: false
    readOnly: true
  name: list-remote-engines
---
