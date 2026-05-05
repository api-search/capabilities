---
categories: []
consumed_apis:
- todoist
description: Unified capability for managing tasks, projects, sections, labels, and comments in Todoist. Enables AI agents and workflow automation to create, update, organize, and complete tasks programmatically.
layout: capability
name: Todoist Task Management
operations:
- description: List tasks with optional project and label filters
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Create a new task
  method: POST
  name: create-task
  path: /v1/tasks
- description: Get task by ID
  method: GET
  name: get-task
  path: /v1/tasks/{id}
- description: Complete a task
  method: POST
  name: close-task
  path: /v1/tasks/{id}/close
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects
- description: List all labels
  method: GET
  name: list-labels
  path: /v1/labels
- description: List task comments
  method: GET
  name: list-comments
  path: /v1/comments
- description: Add a comment to a task
  method: POST
  name: create-comment
  path: /v1/comments
- description: List all workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
personas: []
provider_name: Todoist
provider_slug: todoist
search_terms:
- comment management
- list comments
- create comment
- task management operations
- complete a task
- label management
- workspace management
- create task
- list tasks with optional project and label filters
- create a new todoist project
- todoist
- list labels
- list task comments
- task management
- list all todoist projects
- collaboration
- add a comment to a task
- create a new project
- list all workspaces
- list projects
- list all todoist workspaces for the authenticated user
- add a comment to a todoist task
- get task by id
- tasks
- to-do
- get details of a specific todoist task by id
- list all projects
- mark a todoist task as completed
- project management
- single task operations
- list workspaces
- list all personal labels in todoist
- create a new task
- get task
- list todoist tasks, optionally filtered by project, label, or filter expression
- list comments on a todoist task
- task completion
- create a new task in todoist with content, due date, priority, and labels
- close task
- productivity
- create project
- list all labels
- list tasks
slug: task-management
source_filename: task-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Todoist Task Management\"\n  description: >-\n    Unified capability for managing tasks, projects, sections, labels, and\n    comments in Todoist. Enables AI agents and workflow automation to create,\n    update, organize, and complete tasks programmatically.\n  tags:\n    - Todoist\n    - Productivity\n    - Task Management\n    - Collaboration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TODOIST_API_TOKEN: TODOIST_API_TOKEN\n\ncapability:\n  consumes:\n    - import: todoist\n      location: ./shared/todoist-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: todoist-task-management-api\n      description: \"Unified REST API for Todoist task and project management.\"\n      resources:\n        - path: /v1/tasks\n          name: tasks\n          description: \"Task management operations\"\n          operations:\n            - method: GET\n      \
  \        name: list-tasks\n              description: \"List tasks with optional project and label filters\"\n              call: \"todoist.list-tasks\"\n              with:\n                project_id: \"rest.project_id\"\n                label: \"rest.label\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-task\n              description: \"Create a new task\"\n              call: \"todoist.create-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks/{id}\n          name: task\n          description: \"Single task operations\"\n          operations:\n            - method: GET\n              name: get-task\n              description: \"Get task by ID\"\n              call: \"todoist.get-task\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/tasks/{id}/close\n          name: task-close\n          description: \"Task completion\"\n          operations:\n            - method: POST\n              name: close-task\n              description: \"Complete a task\"\n              call: \"todoist.close-task\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"Project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects\"\n              call: \"todoist.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project\"\n             \
  \ call: \"todoist.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/labels\n          name: labels\n          description: \"Label management\"\n          operations:\n            - method: GET\n              name: list-labels\n              description: \"List all labels\"\n              call: \"todoist.list-labels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/comments\n          name: comments\n          description: \"Comment management\"\n          operations:\n            - method: GET\n              name: list-comments\n              description: \"List task comments\"\n              call: \"todoist.list-comments\"\n              with:\n                task_id: \"rest.task_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n            \
  \  name: create-comment\n              description: \"Add a comment to a task\"\n              call: \"todoist.create-comment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Workspace management\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List all workspaces\"\n              call: \"todoist.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: todoist-task-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted task management with Todoist.\"\n      tools:\n        - name: list-tasks\n          description: \"List Todoist tasks, optionally filtered by project, label, or filter expression\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"todoist.list-tasks\"\n          with:\n            project_id: \"tools.project_id\"\n            label: \"tools.label\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-task\n          description: \"Create a new task in Todoist with content, due date, priority, and labels\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"todoist.create-task\"\n          with:\n            content: \"tools.content\"\n            project_id: \"tools.project_id\"\n            priority: \"tools.priority\"\n            due_string: \"tools.due_string\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task\n          description: \"Get details of a specific Todoist task by ID\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"todoist.get-task\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-task\n          description: \"Mark a Todoist task as completed\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"todoist.close-task\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List all Todoist projects\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"todoist.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new Todoist project\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: false\n          call: \"todoist.create-project\"\n          with:\n            name: \"tools.name\"\n            color: \"tools.color\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-labels\n          description: \"List all personal labels in Todoist\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"todoist.list-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-comments\n          description: \"List comments on a Todoist task\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"todoist.list-comments\"\n          with:\n            task_id: \"tools.task_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-comment\n          description: \"\
  Add a comment to a Todoist task\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"todoist.create-comment\"\n          with:\n            task_id: \"tools.task_id\"\n            content: \"tools.content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List all Todoist workspaces for the authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"todoist.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/todoist/refs/heads/main/capabilities/task-management.yaml
tags:
- Todoist
- Productivity
- Task Management
- Collaboration
tools:
- description: List Todoist tasks, optionally filtered by project, label, or filter expression
  hints:
    openWorld: false
    readOnly: true
  name: list-tasks
- description: Create a new task in Todoist with content, due date, priority, and labels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-task
- description: Get details of a specific Todoist task by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-task
- description: Mark a Todoist task as completed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: close-task
- description: List all Todoist projects
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new Todoist project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-project
- description: List all personal labels in Todoist
  hints:
    openWorld: false
    readOnly: true
  name: list-labels
- description: List comments on a Todoist task
  hints:
    openWorld: false
    readOnly: true
  name: list-comments
- description: Add a comment to a Todoist task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-comment
- description: List all Todoist workspaces for the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: list-workspaces
---
