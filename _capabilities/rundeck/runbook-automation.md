---
categories: []
consumed_apis: []
description: Unified runbook automation capability for Rundeck. Enables DevOps engineers and IT operations teams to trigger automated runbooks, monitor execution status, manage infrastructure nodes, and administer the Rundeck automation platform via a single REST API and MCP server. Covers job execution, monitoring, node management, project organization, and system administration workflows.
layout: capability
name: Rundeck Runbook Automation
operations:
- description: List all Rundeck projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{project}
- description: List all jobs in a project
  method: GET
  name: list-jobs
  path: /v1/projects/{project}/jobs
- description: Get job definition
  method: GET
  name: get-job
  path: /v1/jobs/{id}
- description: List execution history for a job
  method: GET
  name: list-job-executions
  path: /v1/jobs/{id}/executions
- description: Trigger a job execution
  method: POST
  name: run-job
  path: /v1/jobs/{id}/executions
- description: Get execution status and details
  method: GET
  name: get-execution
  path: /v1/executions/{id}
- description: Abort a running execution
  method: POST
  name: abort-execution
  path: /v1/executions/{id}/abort
- description: Get execution log output
  method: GET
  name: get-execution-output
  path: /v1/executions/{id}/output
- description: List project nodes
  method: GET
  name: list-nodes
  path: /v1/projects/{project}/nodes
- description: Get Rundeck server info
  method: GET
  name: get-system-info
  path: /v1/system/info
- description: Get current execution mode
  method: GET
  name: get-execution-mode
  path: /v1/system/executions/status
- description: List API tokens
  method: GET
  name: list-tokens
  path: /v1/tokens
personas: []
provider_name: Rundeck
provider_slug: rundeck
search_terms:
- get project details
- get job
- list jobs
- get the status and details of a rundeck job execution - use to poll for completion
- abort execution
- create a new project
- get details for a specific rundeck project
- abort a running rundeck execution
- workflow
- system information
- devops
- trigger a rundeck job execution with optional arguments and node filter
- rundeck
- node management per project
- list project nodes
- get execution mode
- job scheduling
- get system info
- list nodes
- api token management
- execution mode management
- list api tokens
- retrieve log output from a completed or running rundeck execution
- get rundeck server info
- get execution status and details
- get execution output
- list tokens
- get the definition and configuration of a specific rundeck job
- check whether rundeck is in active or passive execution mode
- list all rundeck projects
- project management
- create project
- it operations
- list all rundeck automation projects
- open source
- abort running executions
- get execution log output
- individual project management
- list job executions
- orchestration
- execution log output
- individual job management
- run job
- runbook
- list execution history for a specific job with optional status filter
- get rundeck server system information including version and uptime
- list nodes available in a rundeck project with optional node filter
- get project
- get job definition
- list projects
- trigger a job execution
- abort a running execution
- get execution
- list automation jobs in a rundeck project, optionally filtered by name or group
- get current execution mode
- job management within a project
- execution status and management
- list api tokens for the current user or all users (admin)
- list all jobs in a project
- job execution control and history
- list execution history for a job
- automation
slug: runbook-automation
source_filename: runbook-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rundeck Runbook Automation\n  description: Unified runbook automation capability for Rundeck. Enables DevOps engineers and IT operations teams to trigger\n    automated runbooks, monitor execution status, manage infrastructure nodes, and administer the Rundeck automation platform\n    via a single REST API and MCP server. Covers job execution, monitoring, node management, project organization, and system\n    administration workflows.\n  tags:\n  - Rundeck\n  - Automation\n  - DevOps\n  - Runbook\n  - IT Operations\n  - Job Scheduling\n  - Orchestration\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUNDECK_API_TOKEN: RUNDECK_API_TOKEN\n    RUNDECK_BASE_URL: RUNDECK_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: rundeck\n    baseUri: '{{env.RUNDECK_BASE_URL}}/api/58'\n    description: Rundeck REST API v58 for automation and runbook operations\n    authentication:\n      type:\
  \ apikey\n      key: X-Rundeck-Auth-Token\n      value: '{{env.RUNDECK_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: projects\n      path: /projects\n      description: Manage Rundeck projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all accessible projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project\n      path: /project/{project}\n      description: Manage a specific project\n      operations:\n      - name: get-project\n        method: GET\n        description:\
  \ Get project details\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete a project\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name\n    - name: project-jobs\n      path: /project/{project}/jobs\n      description: Manage jobs within a project\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List all jobs in a project\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name\n        - name: jobFilter\n          in: query\n        \
  \  type: string\n          required: false\n          description: Filter by job name substring\n        - name: groupPath\n          in: query\n          type: string\n          required: false\n          description: Filter by job group path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: job\n      path: /job/{id}\n      description: Manage a specific job by ID\n      operations:\n      - name: get-job\n        method: GET\n        description: Get job definition by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Job UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-job\n        method: DELETE\n        description: Delete a job by ID\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n          description: Job UUID\n    - name: job-executions\n      path: /job/{id}/executions\n      description: Run jobs and retrieve execution history\n      operations:\n      - name: list-job-executions\n        method: GET\n        description: List executions for a job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Job UUID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: running, succeeded, failed, aborted'\n        - name: max\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-job\n        method: POST\n        description: Trigger a\
  \ job execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Job UUID\n        body:\n          type: json\n          data:\n            argString: '{{tools.argString}}'\n            loglevel: '{{tools.loglevel}}'\n            filter: '{{tools.filter}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: execution\n      path: /execution/{id}\n      description: Manage individual executions\n      operations:\n      - name: get-execution\n        method: GET\n        description: Get execution status by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Execution ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-execution\n\
  \        method: DELETE\n        description: Delete an execution record\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Execution ID\n    - name: execution-abort\n      path: /execution/{id}/abort\n      description: Abort running executions\n      operations:\n      - name: abort-execution\n        method: POST\n        description: Abort a running execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Execution ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: execution-output\n      path: /execution/{id}/output\n      description: Retrieve execution log output\n      operations:\n      - name: get-execution-output\n        method: GET\n        description: Get execution log output\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: Execution ID\n        - name: lastlines\n          in: query\n          type: integer\n          required: false\n          description: Number of lines from end\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-nodes\n      path: /project/{project}/nodes\n      description: List and filter project nodes\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List nodes in a project\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Node filter expression\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: system-info\n      path: /system/info\n      description: System information\n      operations:\n      - name: get-system-info\n        method: GET\n        description: Get Rundeck server system information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-executions-status\n      path: /system/executions/status\n      description: Execution mode management\n      operations:\n      - name: get-execution-mode\n        method: GET\n        description: Get current execution mode (active/passive)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      description: Manage API tokens\n      operations:\n      - name: list-tokens\n        method: GET\n        description: List API tokens\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-token\n        method: POST\n        description: Create a new API token\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n            roles: '{{tools.roles}}'\n            duration: '{{tools.duration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: runbook-automation-api\n    description: Unified REST API for Rundeck runbook automation operations.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all Rundeck projects\n        call: rundeck.list-projects\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method:\
  \ POST\n        name: create-project\n        description: Create a new project\n        call: rundeck.create-project\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}\n      name: project\n      description: Individual project management\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details\n        call: rundeck.get-project\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/jobs\n      name: jobs\n      description: Job management within a project\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all jobs in a project\n        call: rundeck.list-jobs\n        with:\n          project: rest.project\n          jobFilter: rest.jobFilter\n       \
  \   groupPath: rest.groupPath\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/jobs/{id}\n      name: job\n      description: Individual job management\n      operations:\n      - method: GET\n        name: get-job\n        description: Get job definition\n        call: rundeck.get-job\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{id}/executions\n      name: job-executions\n      description: Job execution control and history\n      operations:\n      - method: GET\n        name: list-job-executions\n        description: List execution history for a job\n        call: rundeck.list-job-executions\n        with:\n          id: rest.id\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: run-job\n        description: Trigger a job execution\n        call: rundeck.run-job\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{id}\n      name: execution\n      description: Execution status and management\n      operations:\n      - method: GET\n        name: get-execution\n        description: Get execution status and details\n        call: rundeck.get-execution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{id}/abort\n      name: abort-execution\n      description: Abort running executions\n      operations:\n      - method: POST\n        name: abort-execution\n        description: Abort a running execution\n        call: rundeck.abort-execution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{id}/output\n      name: execution-output\n      description: Execution log output\n      operations:\n\
  \      - method: GET\n        name: get-execution-output\n        description: Get execution log output\n        call: rundeck.get-execution-output\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/nodes\n      name: nodes\n      description: Node management per project\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List project nodes\n        call: rundeck.list-nodes\n        with:\n          project: rest.project\n          filter: rest.filter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/system/info\n      name: system-info\n      description: System information\n      operations:\n      - method: GET\n        name: get-system-info\n        description: Get Rundeck server info\n        call: rundeck.get-system-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/system/executions/status\n\
  \      name: execution-mode\n      description: Execution mode management\n      operations:\n      - method: GET\n        name: get-execution-mode\n        description: Get current execution mode\n        call: rundeck.get-execution-mode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: API token management\n      operations:\n      - method: GET\n        name: list-tokens\n        description: List API tokens\n        call: rundeck.list-tokens\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: runbook-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted runbook automation and IT operations via Rundeck.\n    tools:\n    - name: list-projects\n      description: List all Rundeck automation projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.list-projects\n      outputParameters:\n\
  \      - type: array\n        mapping: $.\n    - name: get-project\n      description: Get details for a specific Rundeck project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.get-project\n      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List automation jobs in a Rundeck project, optionally filtered by name or group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.list-jobs\n      with:\n        project: tools.project\n        jobFilter: tools.jobFilter\n        groupPath: tools.groupPath\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-job\n      description: Get the definition and configuration of a specific Rundeck job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.get-job\n      with:\n        id: tools.id\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: run-job\n      description: Trigger a Rundeck job execution with optional arguments and node filter\n      hints:\n        readOnly: false\n        openWorld: false\n      call: rundeck.run-job\n      with:\n        id: tools.id\n        argString: tools.argString\n        loglevel: tools.loglevel\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution\n      description: Get the status and details of a Rundeck job execution - use to poll for completion\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.get-execution\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-executions\n      description: List execution history for a specific job with optional status filter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.list-job-executions\n\
  \      with:\n        id: tools.id\n        status: tools.status\n        max: tools.max\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: abort-execution\n      description: Abort a running Rundeck execution\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: rundeck.abort-execution\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-output\n      description: Retrieve log output from a completed or running Rundeck execution\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rundeck.get-execution-output\n      with:\n        id: tools.id\n        lastlines: tools.lastlines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List nodes available in a Rundeck project with optional node filter\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: rundeck.list-nodes\n      with:\n        project: tools.project\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system-info\n      description: Get Rundeck server system information including version and uptime\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rundeck.get-system-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-mode\n      description: Check whether Rundeck is in active or passive execution mode\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rundeck.get-execution-mode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tokens\n      description: List API tokens for the current user or all users (admin)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rundeck.list-tokens\n      outputParameters:\n      - type: array\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rundeck/refs/heads/main/capabilities/runbook-automation.yaml
tags:
- Rundeck
- Automation
- DevOps
- Runbook
- IT Operations
- Job Scheduling
- Orchestration
tools:
- description: List all Rundeck automation projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Get details for a specific Rundeck project
  hints:
    openWorld: true
    readOnly: true
  name: get-project
- description: List automation jobs in a Rundeck project, optionally filtered by name or group
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Get the definition and configuration of a specific Rundeck job
  hints:
    openWorld: true
    readOnly: true
  name: get-job
- description: Trigger a Rundeck job execution with optional arguments and node filter
  hints:
    openWorld: false
    readOnly: false
  name: run-job
- description: Get the status and details of a Rundeck job execution - use to poll for completion
  hints:
    openWorld: true
    readOnly: true
  name: get-execution
- description: List execution history for a specific job with optional status filter
  hints:
    openWorld: true
    readOnly: true
  name: list-job-executions
- description: Abort a running Rundeck execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: abort-execution
- description: Retrieve log output from a completed or running Rundeck execution
  hints:
    openWorld: true
    readOnly: true
  name: get-execution-output
- description: List nodes available in a Rundeck project with optional node filter
  hints:
    openWorld: true
    readOnly: true
  name: list-nodes
- description: Get Rundeck server system information including version and uptime
  hints:
    openWorld: false
    readOnly: true
  name: get-system-info
- description: Check whether Rundeck is in active or passive execution mode
  hints:
    openWorld: false
    readOnly: true
  name: get-execution-mode
- description: List API tokens for the current user or all users (admin)
  hints:
    openWorld: false
    readOnly: true
  name: list-tokens
---
