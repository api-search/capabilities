---
api_specs:
- filename: basecamp-api-openapi.yml
  format: yaml
  label: basecamp-api
  slug: basecamp-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/basecamp/refs/heads/main/openapi/basecamp-api-openapi.yml
categories: []
consumed_apis:
- basecamp-api
description: Basecamp project management workflow for teams, covering project creation, to-do management, messaging, scheduling, and team member management.
layout: capability
name: Basecamp Project Management
operations: []
personas: []
provider_name: Basecamp
provider_slug: basecamp
search_terms:
- saas
- post a new message to a basecamp message board
- create basecamp project
- post message
- Project Manager
- project management
- developer integrating basecamp into custom workflows and tools
- full basecamp project lifecycle including todos, messages, scheduling, and team management
- Developer
- create a new basecamp project
- basecamp
- list todos
- manager overseeing project progress, tasks, and team communication
- list messages
- create a new to-do item in a basecamp project
- project creation and lifecycle management
- list basecamp projects
- list all people in the basecamp account
- list messages on a basecamp message board
- collaboration
- create todo
- list to-dos in a basecamp todolist
- rest
- list all active basecamp projects for the account
- list team members
- Team Member
- team communication
- individual contributor managing tasks and collaborating on projects
- to-dos, messages, and team member management
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Basecamp Project Management\"\n  description: >-\n    Basecamp project management workflow for teams, covering project creation,\n    to-do management, messaging, scheduling, and team member management.\n  tags:\n    - Basecamp\n    - Project Management\n    - Collaboration\n    - Team Communication\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BASECAMP_ACCESS_TOKEN: BASECAMP_ACCESS_TOKEN\n      BASECAMP_ACCOUNT_ID: BASECAMP_ACCOUNT_ID\n\ncapability:\n  consumes:\n    - import: basecamp-api\n      location: ./shared/basecamp-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9080\n      namespace: basecamp-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Basecamp project management.\"\n      tools:\n        - name: list-basecamp-projects\n          description: List all active Basecamp projects for the account\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"basecamp-api.listProjects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-basecamp-project\n          description: Create a new Basecamp project\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"basecamp-api.createProject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-todos\n          description: List to-dos in a Basecamp todolist\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"basecamp-api.listTodos\"\n          with:\n            projectId: \"tools.projectId\"\n            todolistId: \"tools.todolistId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-todo\n          description: Create a new to-do item in a Basecamp project\n          hints:\n\
  \            readOnly: false\n            openWorld: false\n          call: \"basecamp-api.createTodo\"\n          with:\n            projectId: \"tools.projectId\"\n            todolistId: \"tools.todolistId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-messages\n          description: List messages on a Basecamp message board\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"basecamp-api.listMessages\"\n          with:\n            projectId: \"tools.projectId\"\n            messageBoardId: \"tools.messageBoardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-message\n          description: Post a new message to a Basecamp message board\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"basecamp-api.createMessage\"\n          with:\n            projectId: \"tools.projectId\"\
  \n            messageBoardId: \"tools.messageBoardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-team-members\n          description: List all people in the Basecamp account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"basecamp-api.listPeople\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/basecamp/refs/heads/main/capabilities/project-management.yaml
tags:
- Basecamp
- Project Management
- Collaboration
- Team Communication
tools:
- description: List all active Basecamp projects for the account
  hints:
    openWorld: false
    readOnly: true
  name: list-basecamp-projects
- description: Create a new Basecamp project
  hints:
    openWorld: false
    readOnly: false
  name: create-basecamp-project
- description: List to-dos in a Basecamp todolist
  hints:
    openWorld: false
    readOnly: true
  name: list-todos
- description: Create a new to-do item in a Basecamp project
  hints:
    openWorld: false
    readOnly: false
  name: create-todo
- description: List messages on a Basecamp message board
  hints:
    openWorld: false
    readOnly: true
  name: list-messages
- description: Post a new message to a Basecamp message board
  hints:
    openWorld: false
    readOnly: false
  name: post-message
- description: List all people in the Basecamp account
  hints:
    openWorld: false
    readOnly: true
  name: list-team-members
---
