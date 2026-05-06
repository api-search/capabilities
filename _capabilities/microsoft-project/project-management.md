---
categories: []
consumed_apis: []
description: Unified project management workflow combining the Microsoft Project Online REST API for managing projects, tasks, resources, assignments, timesheets, and workflows. Used by project managers, resource managers, and PMO teams.
layout: capability
name: Microsoft Project Management
operations:
- description: List all projects
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
  path: /v1/projects/{projectId}
- description: Delete a project
  method: DELETE
  name: delete-project
  path: /v1/projects/{projectId}
- description: List all tasks in a project
  method: GET
  name: list-tasks
  path: /v1/projects/{projectId}/tasks
- description: List all assignments in a project
  method: GET
  name: list-assignments
  path: /v1/projects/{projectId}/assignments
- description: List enterprise resources
  method: GET
  name: list-resources
  path: /v1/resources
- description: List enterprise calendars
  method: GET
  name: list-calendars
  path: /v1/calendars
- description: List timesheet periods
  method: GET
  name: list-timesheet-periods
  path: /v1/timesheets
personas: []
provider_name: Microsoft Project
provider_slug: microsoft-project
search_terms:
- timesheet management and approval
- get project details
- publish a project draft to make changes visible
- list all resource assignments in a project
- list all microsoft project online projects
- scheduling
- create a new project
- calendar management
- check out project
- get a specific task from a project
- create enterprise resource
- list all enterprise custom field definitions
- list custom fields
- list tasks
- timesheets
- list assignments
- list stages
- publish project
- create a new task in a project draft
- list phases
- portfolio management
- microsoft project
- list timesheet periods
- plans, executes, and tracks projects with task scheduling, resource assignments, and progress reporting.
- manages enterprise resource pools, capacity planning, and assignment optimization.
- get task
- task management for a project
- Project Manager
- project management
- create project
- list all enterprise resources across projects
- assignment management for a project
- list all projects
- project lifecycle management
- enterprise resource management
- timesheet management
- task creation, dependencies, and scheduling
- list resources
- program management office managing portfolios, governance workflows, and enterprise configurations.
- check out a project for editing
- list all enterprise calendars
- list all workflow phases
- list all workflow stages
- task management
- custom fields, lookup tables, and event handlers
- list enterprise resources
- create a new project with name and description
- create draft task
- PMO
- delete a project
- delete project
- list calendars
- unified project management workflow for managing projects, tasks, resources, assignments, timesheets, and workflows.
- get project
- list projects
- project creation, checkout, publishing, and workflow governance
- list all assignments in a project
- create a new enterprise resource
- list all timesheet periods
- budgeting
- delete a project by id
- get details of a specific project by id
- resource management
- microsoft
- list all tasks in a project
- gantt charts
- list enterprise calendars
- enterprise resources and task assignments
- single project operations
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Project Management\n  description: Unified project management workflow combining the Microsoft Project Online REST API for managing projects,\n    tasks, resources, assignments, timesheets, and workflows. Used by project managers, resource managers, and PMO teams.\n  tags:\n  - Microsoft Project\n  - Project Management\n  - Resource Management\n  - Task Management\n  - Timesheets\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHAREPOINT_ACCESS_TOKEN: SHAREPOINT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: project-rest\n    baseUri: https://{tenant}.sharepoint.com/sites/pwa/_api/ProjectServer\n    description: Microsoft Project Online REST API via SharePoint\n    authentication:\n      type: bearer\n      token: '{{SHAREPOINT_ACCESS_TOKEN}}'\n    resources:\n    - name: projects\n      path: /Projects\n      description: Manage projects\n      operations:\n\
  \      - name: list-projects\n        method: GET\n        description: Retrieve all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Description: '{{tools.description}}'\n      - name: get-project\n        method: GET\n        description: Get a specific project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n     \
  \   method: DELETE\n        description: Delete a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-out-project\n        method: POST\n        description: Check out a project for editing\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-project\n        method: POST\n        description: Publish a project draft\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /Projects('{projectId}')/Tasks\n      description: Manage project tasks\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks in a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task\n        method: GET\n        description: Get a specific task\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task\
  \ GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-draft-task\n        method: POST\n        description: Create a task in the project draft\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Duration: '{{tools.duration}}'\n    - name: resources\n      path: /EnterpriseResources\n      description: Manage enterprise resources\n      operations:\n      - name: list-enterprise-resources\n        method: GET\n        description: List all enterprise resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-enterprise-resource\n        method: POST\n        description: Create an enterprise resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Email: '{{tools.email}}'\n    - name: assignments\n      path: /Projects('{projectId}')/Assignments\n      description: Manage resource assignments\n      operations:\n      - name: list-assignments\n        method: GET\n        description: List all assignments in a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendars\n      path: /Calendars\n      description:\
  \ Manage enterprise calendars\n      operations:\n      - name: list-calendars\n        method: GET\n        description: List all calendars\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-calendar\n        method: POST\n        description: Create a calendar\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n    - name: custom-fields\n      path: /CustomFields\n      description: Manage custom field definitions\n      operations:\n      - name: list-custom-fields\n        method: GET\n        description: List all custom fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timesheets\n      path: /TimeSheetPeriods\n      description:\
  \ Manage timesheets\n      operations:\n      - name: list-timesheet-periods\n        method: GET\n        description: List all timesheet periods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phases\n      path: /Phases\n      description: Manage workflow phases\n      operations:\n      - name: list-phases\n        method: GET\n        description: List all workflow phases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stages\n      path: /Stages\n      description: Manage workflow stages\n      operations:\n      - name: list-stages\n        method: GET\n        description: List all workflow stages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: project-management-api\n\
  \    description: Unified REST API for Microsoft Project management workflows.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Project lifecycle management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects\n        call: project-rest.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new project\n        call: project-rest.create-project\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project-detail\n      description: Single project operations\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details\n        call: project-rest.get-project\n        with:\n          projectId:\
  \ rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete a project\n        call: project-rest.delete-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/tasks\n      name: tasks\n      description: Task management for a project\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List all tasks in a project\n        call: project-rest.list-tasks\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/assignments\n      name: assignments\n      description: Assignment management for a project\n      operations:\n      - method: GET\n        name: list-assignments\n        description: List all assignments in a project\n\
  \        call: project-rest.list-assignments\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resources\n      name: resources\n      description: Enterprise resource management\n      operations:\n      - method: GET\n        name: list-resources\n        description: List enterprise resources\n        call: project-rest.list-enterprise-resources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calendars\n      name: calendars\n      description: Calendar management\n      operations:\n      - method: GET\n        name: list-calendars\n        description: List enterprise calendars\n        call: project-rest.list-calendars\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timesheets\n      name: timesheets\n      description: Timesheet management\n      operations:\n      - method: GET\n        name: list-timesheet-periods\n\
  \        description: List timesheet periods\n        call: project-rest.list-timesheet-periods\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: project-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft Project management.\n    tools:\n    - name: list-projects\n      description: List all Microsoft Project Online projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: project-rest.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details of a specific project by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: project-rest.get-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new project with name and description\n\
  \      hints:\n        readOnly: false\n      call: project-rest.create-project\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete a project by ID\n      hints:\n        readOnly: false\n        destructive: true\n      call: project-rest.delete-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-out-project\n      description: Check out a project for editing\n      hints:\n        readOnly: false\n      call: project-rest.check-out-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-project\n      description: Publish a project draft to make changes visible\n      hints:\n        readOnly: false\n      call: project-rest.publish-project\n      with:\n  \
  \      projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List all tasks in a project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: project-rest.list-tasks\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task\n      description: Get a specific task from a project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: project-rest.get-task\n      with:\n        projectId: tools.projectId\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-draft-task\n      description: Create a new task in a project draft\n      hints:\n        readOnly: false\n      call: project-rest.create-draft-task\n      with:\n        projectId: tools.projectId\n        name: tools.name\n        duration: tools.duration\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-enterprise-resources\n      description: List all enterprise resources across projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: project-rest.list-enterprise-resources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-enterprise-resource\n      description: Create a new enterprise resource\n      hints:\n        readOnly: false\n      call: project-rest.create-enterprise-resource\n      with:\n        name: tools.name\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assignments\n      description: List all resource assignments in a project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: project-rest.list-assignments\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-calendars\n      description: List all enterprise calendars\n      hints:\n        readOnly: true\n      call: project-rest.list-calendars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-fields\n      description: List all enterprise custom field definitions\n      hints:\n        readOnly: true\n      call: project-rest.list-custom-fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-timesheet-periods\n      description: List all timesheet periods\n      hints:\n        readOnly: true\n      call: project-rest.list-timesheet-periods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-phases\n      description: List all workflow phases\n      hints:\n        readOnly: true\n      call: project-rest.list-phases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stages\n      description: List all workflow stages\n      hints:\n\
  \        readOnly: true\n      call: project-rest.list-stages\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-project/refs/heads/main/capabilities/project-management.yaml
tags:
- Microsoft Project
- Project Management
- Resource Management
- Task Management
- Timesheets
tools:
- description: List all Microsoft Project Online projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Get details of a specific project by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Create a new project with name and description
  hints:
    readOnly: false
  name: create-project
- description: Delete a project by ID
  hints:
    destructive: true
    readOnly: false
  name: delete-project
- description: Check out a project for editing
  hints:
    readOnly: false
  name: check-out-project
- description: Publish a project draft to make changes visible
  hints:
    readOnly: false
  name: publish-project
- description: List all tasks in a project
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Get a specific task from a project
  hints:
    idempotent: true
    readOnly: true
  name: get-task
- description: Create a new task in a project draft
  hints:
    readOnly: false
  name: create-draft-task
- description: List all enterprise resources across projects
  hints:
    openWorld: true
    readOnly: true
  name: list-enterprise-resources
- description: Create a new enterprise resource
  hints:
    readOnly: false
  name: create-enterprise-resource
- description: List all resource assignments in a project
  hints:
    idempotent: true
    readOnly: true
  name: list-assignments
- description: List all enterprise calendars
  hints:
    readOnly: true
  name: list-calendars
- description: List all enterprise custom field definitions
  hints:
    readOnly: true
  name: list-custom-fields
- description: List all timesheet periods
  hints:
    readOnly: true
  name: list-timesheet-periods
- description: List all workflow phases
  hints:
    readOnly: true
  name: list-phases
- description: List all workflow stages
  hints:
    readOnly: true
  name: list-stages
---
