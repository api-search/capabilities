---
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
- list all resource assignments in a project
- create enterprise resource
- delete project
- program management office managing portfolios, governance workflows, and enterprise configurations.
- list all assignments in a project
- list timesheet periods
- list stages
- PMO
- list tasks
- list all enterprise custom field definitions
- list enterprise resources
- create draft task
- resource management
- plans, executes, and tracks projects with task scheduling, resource assignments, and progress reporting.
- get project details
- list assignments
- publish project
- list custom fields
- portfolio management
- assignment management for a project
- list all tasks in a project
- check out a project for editing
- single project operations
- delete a project by id
- check out project
- create a new task in a project draft
- unified project management workflow for managing projects, tasks, resources, assignments, timesheets, and workflows.
- get details of a specific project by id
- task creation, dependencies, and scheduling
- list all workflow stages
- create a new project with name and description
- timesheet management and approval
- project management
- calendar management
- get project
- microsoft
- list all enterprise calendars
- list projects
- list resources
- enterprise resource management
- list enterprise calendars
- manages enterprise resource pools, capacity planning, and assignment optimization.
- list all workflow phases
- timesheets
- scheduling
- list all timesheet periods
- list all microsoft project online projects
- list phases
- delete a project
- list calendars
- publish a project draft to make changes visible
- get task
- list all enterprise resources across projects
- microsoft project
- budgeting
- get a specific task from a project
- timesheet management
- project creation, checkout, publishing, and workflow governance
- create a new enterprise resource
- task management
- gantt charts
- custom fields, lookup tables, and event handlers
- list all projects
- project lifecycle management
- Project Manager
- enterprise resources and task assignments
- create a new project
- create project
- task management for a project
slug: project-management
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
