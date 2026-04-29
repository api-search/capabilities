---
categories: []
consumed_apis:
- project-rest
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
- get details of a specific project by id
- delete a project by id
- list all workflow phases
- list calendars
- delete project
- budgeting
- list resources
- PMO
- project creation, checkout, publishing, and workflow governance
- get a specific task from a project
- list all microsoft project online projects
- list all workflow stages
- list all resource assignments in a project
- resource management
- create a new enterprise resource
- timesheet management and approval
- scheduling
- task management
- gantt charts
- portfolio management
- single project operations
- project management
- check out project
- task creation, dependencies, and scheduling
- list all assignments in a project
- get task
- get project details
- assignment management for a project
- enterprise resource management
- list stages
- project lifecycle management
- task management for a project
- list assignments
- custom fields, lookup tables, and event handlers
- list all tasks in a project
- create a new task in a project draft
- list projects
- manages enterprise resource pools, capacity planning, and assignment optimization.
- unified project management workflow for managing projects, tasks, resources, assignments, timesheets, and workflows.
- get project
- list timesheet periods
- list enterprise calendars
- create a new project
- publish a project draft to make changes visible
- enterprise resources and task assignments
- list phases
- create a new project with name and description
- program management office managing portfolios, governance workflows, and enterprise configurations.
- publish project
- check out a project for editing
- list custom fields
- microsoft project
- list tasks
- create draft task
- microsoft
- calendar management
- timesheet management
- create enterprise resource
- list all enterprise calendars
- create project
- list all enterprise custom field definitions
- list all timesheet periods
- list all projects
- timesheets
- delete a project
- Project Manager
- list enterprise resources
- plans, executes, and tracks projects with task scheduling, resource assignments, and progress reporting.
- list all enterprise resources across projects
slug: project-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Project Management\"\n  description: \"Unified project management workflow combining the Microsoft Project Online REST API for managing projects, tasks, resources, assignments, timesheets, and workflows. Used by project managers, resource managers, and PMO teams.\"\n  tags:\n    - Microsoft Project\n    - Project Management\n    - Resource Management\n    - Task Management\n    - Timesheets\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHAREPOINT_ACCESS_TOKEN: SHAREPOINT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: project-rest\n      location: ./shared/project-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: project-management-api\n      description: \"Unified REST API for Microsoft Project management workflows.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Project\
  \ lifecycle management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects\"\n              call: \"project-rest.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project\"\n              call: \"project-rest.create-project\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{projectId}\n          name: project-detail\n          description: \"Single project operations\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details\"\n              call: \"project-rest.get-project\"\
  \n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a project\"\n              call: \"project-rest.delete-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{projectId}/tasks\n          name: tasks\n          description: \"Task management for a project\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List all tasks in a project\"\n              call: \"project-rest.list-tasks\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n     \
  \   - path: /v1/projects/{projectId}/assignments\n          name: assignments\n          description: \"Assignment management for a project\"\n          operations:\n            - method: GET\n              name: list-assignments\n              description: \"List all assignments in a project\"\n              call: \"project-rest.list-assignments\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resources\n          name: resources\n          description: \"Enterprise resource management\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List enterprise resources\"\n              call: \"project-rest.list-enterprise-resources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calendars\n          name: calendars\n\
  \          description: \"Calendar management\"\n          operations:\n            - method: GET\n              name: list-calendars\n              description: \"List enterprise calendars\"\n              call: \"project-rest.list-calendars\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/timesheets\n          name: timesheets\n          description: \"Timesheet management\"\n          operations:\n            - method: GET\n              name: list-timesheet-periods\n              description: \"List timesheet periods\"\n              call: \"project-rest.list-timesheet-periods\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: project-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Project management.\"\n      tools:\n        - name: list-projects\n       \
  \   description: \"List all Microsoft Project Online projects\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"project-rest.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get details of a specific project by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"project-rest.get-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new project with name and description\"\n          hints:\n            readOnly: false\n          call: \"project-rest.create-project\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: delete-project\n          description: \"Delete a project by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"project-rest.delete-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-out-project\n          description: \"Check out a project for editing\"\n          hints:\n            readOnly: false\n          call: \"project-rest.check-out-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-project\n          description: \"Publish a project draft to make changes visible\"\n          hints:\n            readOnly: false\n          call: \"project-rest.publish-project\"\n          with:\n            projectId: \"tools.projectId\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: \"List all tasks in a project\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"project-rest.list-tasks\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task\n          description: \"Get a specific task from a project\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"project-rest.get-task\"\n          with:\n            projectId: \"tools.projectId\"\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-draft-task\n          description: \"Create a new task in a project draft\"\n          hints:\n            readOnly: false\n          call:\
  \ \"project-rest.create-draft-task\"\n          with:\n            projectId: \"tools.projectId\"\n            name: \"tools.name\"\n            duration: \"tools.duration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-enterprise-resources\n          description: \"List all enterprise resources across projects\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"project-rest.list-enterprise-resources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-enterprise-resource\n          description: \"Create a new enterprise resource\"\n          hints:\n            readOnly: false\n          call: \"project-rest.create-enterprise-resource\"\n          with:\n            name: \"tools.name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: list-assignments\n          description: \"List all resource assignments in a project\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"project-rest.list-assignments\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-calendars\n          description: \"List all enterprise calendars\"\n          hints:\n            readOnly: true\n          call: \"project-rest.list-calendars\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-fields\n          description: \"List all enterprise custom field definitions\"\n          hints:\n            readOnly: true\n          call: \"project-rest.list-custom-fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-timesheet-periods\n          description:\
  \ \"List all timesheet periods\"\n          hints:\n            readOnly: true\n          call: \"project-rest.list-timesheet-periods\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-phases\n          description: \"List all workflow phases\"\n          hints:\n            readOnly: true\n          call: \"project-rest.list-phases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stages\n          description: \"List all workflow stages\"\n          hints:\n            readOnly: true\n          call: \"project-rest.list-stages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
