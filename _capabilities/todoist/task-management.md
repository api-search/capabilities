---
categories: []
consumed_apis: []
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
- task completion
- label management
- list all workspaces
- complete a task
- list todoist tasks, optionally filtered by project, label, or filter expression
- list comments on a todoist task
- create a new task in todoist with content, due date, priority, and labels
- tasks
- task management operations
- create a new project
- list task comments
- list tasks
- get details of a specific todoist task by id
- create a new todoist project
- get task
- project management
- create project
- list all projects
- productivity
- to-do
- list all personal labels in todoist
- workspace management
- single task operations
- task management
- close task
- get task by id
- list workspaces
- todoist
- mark a todoist task as completed
- list all labels
- list projects
- list labels
- list all todoist projects
- list tasks with optional project and label filters
- create a new task
- create comment
- add a comment to a task
- add a comment to a todoist task
- create task
- collaboration
- list all todoist workspaces for the authenticated user
- list comments
slug: task-management
source_filename: task-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Todoist Task Management\n  description: Unified capability for managing tasks, projects, sections, labels, and comments in Todoist. Enables AI agents\n    and workflow automation to create, update, organize, and complete tasks programmatically.\n  tags:\n  - Todoist\n  - Productivity\n  - Task Management\n  - Collaboration\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TODOIST_API_TOKEN: TODOIST_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: todoist\n    baseUri: https://api.todoist.com/api/v1\n    description: Todoist REST API for task and project management\n    authentication:\n      type: bearer\n      token: '{{TODOIST_API_TOKEN}}'\n    resources:\n    - name: tasks\n      path: /tasks\n      description: Task management operations\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks with optional filters\n        inputParameters:\n\
  \        - name: project_id\n          in: query\n          type: string\n          required: false\n          description: Filter by project ID\n        - name: section_id\n          in: query\n          type: string\n          required: false\n          description: Filter by section ID\n        - name: label\n          in: query\n          type: string\n          required: false\n          description: Filter by label name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-task\n        method: POST\n        description: Create a new task\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            content: '{{tools.content}}'\n            project_id: '{{tools.project_id}}'\n            priority: '{{tools.priority}}'\n            due_string: '{{tools.due_string}}'\n      - name: get-task\n        method: GET\n        description: Get a task by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: close-task\n        method: POST\n        description: Mark a task as completed\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Project management operations\n\
  \      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            color: '{{tools.color}}'\n      - name: get-project\n        method: GET\n        description: Get a project by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: labels\n      path: /labels\n      description: Label management operations\n      operations:\n      - name: list-labels\n        method: GET\n        description: List all personal labels\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments\n      description: Comment management operations\n      operations:\n      - name: list-comments\n        method: GET\n        description: List all comments on a task or project\n        inputParameters:\n        - name: task_id\n          in: query\n          type: string\n          required: false\n          description: Task ID to get comments for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-comment\n        method: POST\n        description: Create a new comment\n   \
  \     inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            task_id: '{{tools.task_id}}'\n            content: '{{tools.content}}'\n    - name: workspaces\n      path: /workspaces\n      description: Workspace management operations\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: todoist-task-management-api\n    description: Unified REST API for Todoist task and project management.\n    resources:\n    - path: /v1/tasks\n      name: tasks\n      description: Task management operations\n      operations:\n      - method: GET\n        name: list-tasks\n  \
  \      description: List tasks with optional project and label filters\n        call: todoist.list-tasks\n        with:\n          project_id: rest.project_id\n          label: rest.label\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-task\n        description: Create a new task\n        call: todoist.create-task\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks/{id}\n      name: task\n      description: Single task operations\n      operations:\n      - method: GET\n        name: get-task\n        description: Get task by ID\n        call: todoist.get-task\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks/{id}/close\n      name: task-close\n      description: Task completion\n      operations:\n      - method: POST\n        name: close-task\n        description: Complete a task\n     \
  \   call: todoist.close-task\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects\n        call: todoist.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new project\n        call: todoist.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels\n      name: labels\n      description: Label management\n      operations:\n      - method: GET\n        name: list-labels\n        description: List all labels\n        call: todoist.list-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/comments\n      name: comments\n\
  \      description: Comment management\n      operations:\n      - method: GET\n        name: list-comments\n        description: List task comments\n        call: todoist.list-comments\n        with:\n          task_id: rest.task_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-comment\n        description: Add a comment to a task\n        call: todoist.create-comment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Workspace management\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces\n        call: todoist.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: todoist-task-management-mcp\n    transport: http\n    description: MCP server for AI-assisted task management with Todoist.\n\
  \    tools:\n    - name: list-tasks\n      description: List Todoist tasks, optionally filtered by project, label, or filter expression\n      hints:\n        readOnly: true\n        openWorld: false\n      call: todoist.list-tasks\n      with:\n        project_id: tools.project_id\n        label: tools.label\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-task\n      description: Create a new task in Todoist with content, due date, priority, and labels\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: todoist.create-task\n      with:\n        content: tools.content\n        project_id: tools.project_id\n        priority: tools.priority\n        due_string: tools.due_string\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task\n      description: Get details of a specific Todoist task by ID\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: todoist.get-task\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-task\n      description: Mark a Todoist task as completed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: todoist.close-task\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all Todoist projects\n      hints:\n        readOnly: true\n        openWorld: false\n      call: todoist.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Todoist project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: todoist.create-project\n      with:\n        name: tools.name\n        color: tools.color\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-labels\n      description: List all personal labels in Todoist\n      hints:\n        readOnly: true\n        openWorld: false\n      call: todoist.list-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-comments\n      description: List comments on a Todoist task\n      hints:\n        readOnly: true\n        openWorld: false\n      call: todoist.list-comments\n      with:\n        task_id: tools.task_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-comment\n      description: Add a comment to a Todoist task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: todoist.create-comment\n      with:\n        task_id: tools.task_id\n        content: tools.content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all Todoist\
  \ workspaces for the authenticated user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: todoist.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
