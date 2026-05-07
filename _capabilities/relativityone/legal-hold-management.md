---
categories: []
consumed_apis: []
description: Unified legal hold management capability for RelativityOne. Combines legal hold project management, custodian tracking, data preservation workflows, HR entity integration, and communication management into a single workflow-oriented API. Used by legal operations teams, compliance officers, and eDiscovery professionals to manage litigation holds across Microsoft 365 and Google Workspace data sources.
layout: capability
name: RelativityOne Legal Hold Management
operations:
- description: List all legal hold projects in a workspace.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new legal hold project.
  method: POST
  name: create-project
  path: /v1/projects
- description: Get a specific legal hold project by ID.
  method: GET
  name: get-project
  path: /v1/projects/{projectId}
- description: List all custodians in a legal hold project.
  method: GET
  name: list-custodians
  path: /v1/projects/{projectId}/custodians
- description: Add a custodian to a legal hold project.
  method: POST
  name: add-custodian
  path: /v1/projects/{projectId}/custodians
- description: Get all custodians currently on hold.
  method: GET
  name: get-active-custodians
  path: /v1/active-custodians
- description: Create an HR entity for legal hold workflows.
  method: POST
  name: create-entity
  path: /v1/entities
- description: Update the employment status of an entity.
  method: PUT
  name: update-entity-status
  path: /v1/entities/{entityId}
- description: Preserve custodian data in M365 and Google Workspace.
  method: POST
  name: preserve-data
  path: /v1/projects/{projectId}/preserve
- description: Release custodians from a legal hold project.
  method: POST
  name: release-custodians
  path: /v1/projects/{projectId}/release
- description: Create a legal hold communication.
  method: POST
  name: create-communication
  path: /v1/projects/{projectId}/communications
- description: Create a new legal hold task.
  method: POST
  name: create-task
  path: /v1/tasks
personas: []
provider_name: RelativityOne
provider_slug: relativityone
search_terms:
- update the employment status of an entity.
- list all legal hold projects in a workspace.
- litigation
- create a legal hold communication.
- create a task for tracking legal hold actions and assignments.
- create legal hold task
- create legal hold project
- preserve data
- get active custodians
- document management
- data preservation workflows.
- add an employee as a custodian to a legal hold project.
- release custodians from a legal hold and remove their data preservation.
- relativity
- preserve custodian data in m365 and google workspace.
- individual entity operations.
- get legal hold project
- list custodians
- release custodians from a legal hold project.
- create an hr entity to integrate employee records with legal hold workflows.
- create hr entity
- individual legal hold project operations.
- get a specific legal hold project by id.
- update entity status
- compliance
- release custodians from hold
- create a new legal hold project.
- ediscovery
- list all custodians in a legal hold project.
- create communication
- legal hold project management.
- legal hold task management.
- add custodian to project
- get a summary of all custodians currently on legal hold across all projects.
- add a custodian to a legal hold project.
- create project
- custodian management for legal hold projects.
- list projects
- create task
- create a new legal hold task.
- list project custodians
- legal hold communications and notifications.
- custodian release from legal hold.
- get active custodian summary
- add custodian
- list all custodians assigned to a legal hold project.
- update employee status
- release custodians
- get project
- get all custodians currently on hold.
- legal operations
- create an hr entity for legal hold workflows.
- get details of a specific legal hold project.
- create a new legal hold project for litigation matter management.
- update the employment status of an entity in the legal hold system.
- preserve custodian data
- create hold communication
- hr entity management for legal hold integration.
- create entity
- legal
- list legal hold projects
- active custodian summary across all projects.
- legal hold
- initiate data preservation for custodians across m365 and google workspace.
- create a legal hold communication notice with escalation and reminder schedules.
slug: legal-hold-management
source_filename: legal-hold-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RelativityOne Legal Hold Management\n  description: Unified legal hold management capability for RelativityOne. Combines legal hold project management, custodian\n    tracking, data preservation workflows, HR entity integration, and communication management into a single workflow-oriented\n    API. Used by legal operations teams, compliance officers, and eDiscovery professionals to manage litigation holds across\n    Microsoft 365 and Google Workspace data sources.\n  tags:\n  - Legal Hold\n  - eDiscovery\n  - Compliance\n  - Litigation\n  - Relativity\n  - Legal Operations\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RELATIVITY_BEARER_TOKEN: RELATIVITY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: relativity-legal-hold\n    baseUri: https://relativity.rest/api/relativity-environment/v1\n    description: RelativityOne Legal Hold REST API for eDiscovery matter management.\n\
  \    authentication:\n      type: bearer\n      token: '{{RELATIVITY_BEARER_TOKEN}}'\n    resources:\n    - name: legal-hold-projects\n      path: /workspaces/{workspaceId}/legal-hold/projects\n      description: Legal hold project management endpoints.\n      operations:\n      - name: list-legal-hold-projects\n        method: GET\n        description: Retrieves a list of legal hold projects in a workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: create-legal-hold-project\n        method: POST\n        description: Creates a new legal hold project.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ownerEmailAddress: '{{tools.ownerEmailAddress}}'\n            description: '{{tools.description}}'\n            status: '{{tools.status}}'\n    - name: legal-hold-project-by-id\n      path: /workspaces/{workspaceId}/legal-hold/projects/{projectId}\n      description: Individual legal hold project operations.\n      operations:\n      - name: get-legal-hold-project\n        method: GET\n        description: Retrieves a specific legal hold project by ID.\n    \
  \    inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Project artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custodians\n      path: /workspaces/{workspaceId}/legal-hold/projects/{projectId}/custodians\n      description: Custodian management for legal hold projects.\n      operations:\n      - name: list-project-custodians\n        method: GET\n        description: Retrieves all custodians assigned to a legal hold project.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: projectId\n          in: path\n       \
  \   type: integer\n          required: true\n          description: Project artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-custodian-to-project\n        method: POST\n        description: Adds a custodian to a legal hold project.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Project artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            emailAddress: '{{tools.emailAddress}}'\n            employeeId: '{{tools.employeeId}}'\n    - name: active-custodians\n      path: /workspaces/{workspaceId}/legal-hold/active-custodians\n\
  \      description: Active custodian summary across all legal hold projects.\n      operations:\n      - name: get-active-custodian-summary\n        method: GET\n        description: Retrieves all custodians who are actively on hold.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return (max 1000).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities\n      path: /workspaces/{workspaceId}/legal-hold/entities\n      description: HR entity management for legal hold integration.\n  \
  \    operations:\n      - name: create-entity\n        method: POST\n        description: Creates an HR entity with name and email.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            emailAddress: '{{tools.emailAddress}}'\n            employeeId: '{{tools.employeeId}}'\n    - name: entity-by-id\n      path: /workspaces/{workspaceId}/legal-hold/entities/{entityId}\n      description: Individual entity management operations.\n      operations:\n      - name: update-entity-status\n        method: PUT\n        description: Updates the employee status of an entity.\n        inputParameters:\n\
  \        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: entityId\n          in: path\n          type: integer\n          required: true\n          description: Entity artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            employeeStatus: '{{tools.employeeStatus}}'\n    - name: preservation\n      path: /workspaces/{workspaceId}/legal-hold/projects/{projectId}/preserve\n      description: Data preservation operations for legal hold.\n      operations:\n      - name: preserve-custodian-data\n        method: POST\n        description: Initiates data preservation for custodians across M365 and Google Workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n\
  \          description: Workspace artifact ID.\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Project artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            custodianIds: '{{tools.custodianIds}}'\n            dataSources: '{{tools.dataSources}}'\n    - name: release\n      path: /workspaces/{workspaceId}/legal-hold/projects/{projectId}/release\n      description: Release custodians from legal hold.\n      operations:\n      - name: release-custodian-from-project\n        method: POST\n        description: Releases custodians from a legal hold project.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: projectId\n          in:\
  \ path\n          type: integer\n          required: true\n          description: Project artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            custodianIds: '{{tools.custodianIds}}'\n    - name: communications\n      path: /workspaces/{workspaceId}/legal-hold/projects/{projectId}/communications\n      description: Legal hold communication management.\n      operations:\n      - name: create-legal-hold-communication\n        method: POST\n        description: Creates a legal hold communication with escalation and reminder settings.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Project artifact\
  \ ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            escalationEnabled: '{{tools.escalationEnabled}}'\n            reminderIntervalDays: '{{tools.reminderIntervalDays}}'\n    - name: tasks\n      path: /workspaces/{workspaceId}/legal-hold/tasks\n      description: Legal hold task management.\n      operations:\n      - name: create-legal-hold-task\n        method: POST\n        description: Creates a new task for a legal hold project.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: integer\n          required: true\n          description: Workspace artifact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n   \
  \       data:\n            name: '{{tools.name}}'\n            projectId: '{{tools.projectId}}'\n            dueDate: '{{tools.dueDate}}'\n            assignedTo: '{{tools.assignedTo}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: legal-hold-management-api\n    description: Unified REST API for RelativityOne legal hold management workflows.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Legal hold project management.\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all legal hold projects in a workspace.\n        call: relativity-legal-hold.list-legal-hold-projects\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new legal hold project.\n        call: relativity-legal-hold.create-legal-hold-project\n        with:\n          workspaceId:\
  \ rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project\n      description: Individual legal hold project operations.\n      operations:\n      - method: GET\n        name: get-project\n        description: Get a specific legal hold project by ID.\n        call: relativity-legal-hold.get-legal-hold-project\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/custodians\n      name: custodians\n      description: Custodian management for legal hold projects.\n      operations:\n      - method: GET\n        name: list-custodians\n        description: List all custodians in a legal hold project.\n        call: relativity-legal-hold.list-project-custodians\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-custodian\n        description: Add a custodian to a legal hold project.\n        call: relativity-legal-hold.add-custodian-to-project\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/active-custodians\n      name: active-custodians\n      description: Active custodian summary across all projects.\n      operations:\n      - method: GET\n        name: get-active-custodians\n        description: Get all custodians currently on hold.\n        call: relativity-legal-hold.get-active-custodian-summary\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities\n      name: entities\n      description: HR entity management for legal hold integration.\n\
  \      operations:\n      - method: POST\n        name: create-entity\n        description: Create an HR entity for legal hold workflows.\n        call: relativity-legal-hold.create-entity\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{entityId}\n      name: entity\n      description: Individual entity operations.\n      operations:\n      - method: PUT\n        name: update-entity-status\n        description: Update the employment status of an entity.\n        call: relativity-legal-hold.update-entity-status\n        with:\n          workspaceId: rest.workspaceId\n          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/preserve\n      name: preservation\n      description: Data preservation workflows.\n      operations:\n      - method: POST\n        name: preserve-data\n        description:\
  \ Preserve custodian data in M365 and Google Workspace.\n        call: relativity-legal-hold.preserve-custodian-data\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/release\n      name: release\n      description: Custodian release from legal hold.\n      operations:\n      - method: POST\n        name: release-custodians\n        description: Release custodians from a legal hold project.\n        call: relativity-legal-hold.release-custodian-from-project\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/communications\n      name: communications\n      description: Legal hold communications and notifications.\n      operations:\n      - method: POST\n        name: create-communication\n\
  \        description: Create a legal hold communication.\n        call: relativity-legal-hold.create-legal-hold-communication\n        with:\n          workspaceId: rest.workspaceId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Legal hold task management.\n      operations:\n      - method: POST\n        name: create-task\n        description: Create a new legal hold task.\n        call: relativity-legal-hold.create-legal-hold-task\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: legal-hold-management-mcp\n    transport: http\n    description: MCP server for AI-assisted legal hold management in RelativityOne.\n    tools:\n    - name: list-legal-hold-projects\n      description: List all legal hold projects in a workspace.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: relativity-legal-hold.list-legal-hold-projects\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-legal-hold-project\n      description: Create a new legal hold project for litigation matter management.\n      hints:\n        readOnly: false\n      call: relativity-legal-hold.create-legal-hold-project\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-legal-hold-project\n      description: Get details of a specific legal hold project.\n      hints:\n        readOnly: true\n      call: relativity-legal-hold.get-legal-hold-project\n      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-project-custodians\n      description: List all custodians\
  \ assigned to a legal hold project.\n      hints:\n        readOnly: true\n      call: relativity-legal-hold.list-project-custodians\n      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-custodian-to-project\n      description: Add an employee as a custodian to a legal hold project.\n      hints:\n        readOnly: false\n      call: relativity-legal-hold.add-custodian-to-project\n      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-custodian-summary\n      description: Get a summary of all custodians currently on legal hold across all projects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: relativity-legal-hold.get-active-custodian-summary\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-hr-entity\n      description: Create an HR entity to integrate employee records with legal hold workflows.\n      hints:\n        readOnly: false\n      call: relativity-legal-hold.create-entity\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-employee-status\n      description: Update the employment status of an entity in the legal hold system.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: relativity-legal-hold.update-entity-status\n      with:\n        workspaceId: tools.workspaceId\n        entityId: tools.entityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: preserve-custodian-data\n      description: Initiate data preservation for custodians across M365 and Google Workspace.\n      hints:\n        readOnly: false\n        destructive: false\n      call: relativity-legal-hold.preserve-custodian-data\n\
  \      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: release-custodians-from-hold\n      description: Release custodians from a legal hold and remove their data preservation.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: relativity-legal-hold.release-custodian-from-project\n      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-hold-communication\n      description: Create a legal hold communication notice with escalation and reminder schedules.\n      hints:\n        readOnly: false\n      call: relativity-legal-hold.create-legal-hold-communication\n      with:\n        workspaceId: tools.workspaceId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-legal-hold-task\n      description: Create a task for tracking legal hold actions and assignments.\n      hints:\n        readOnly: false\n      call: relativity-legal-hold.create-legal-hold-task\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/relativityone/refs/heads/main/capabilities/legal-hold-management.yaml
tags:
- Legal Hold
- eDiscovery
- Compliance
- Litigation
- Relativity
- Legal Operations
tools:
- description: List all legal hold projects in a workspace.
  hints:
    openWorld: true
    readOnly: true
  name: list-legal-hold-projects
- description: Create a new legal hold project for litigation matter management.
  hints:
    readOnly: false
  name: create-legal-hold-project
- description: Get details of a specific legal hold project.
  hints:
    readOnly: true
  name: get-legal-hold-project
- description: List all custodians assigned to a legal hold project.
  hints:
    readOnly: true
  name: list-project-custodians
- description: Add an employee as a custodian to a legal hold project.
  hints:
    readOnly: false
  name: add-custodian-to-project
- description: Get a summary of all custodians currently on legal hold across all projects.
  hints:
    openWorld: true
    readOnly: true
  name: get-active-custodian-summary
- description: Create an HR entity to integrate employee records with legal hold workflows.
  hints:
    readOnly: false
  name: create-hr-entity
- description: Update the employment status of an entity in the legal hold system.
  hints:
    idempotent: true
    readOnly: false
  name: update-employee-status
- description: Initiate data preservation for custodians across M365 and Google Workspace.
  hints:
    destructive: false
    readOnly: false
  name: preserve-custodian-data
- description: Release custodians from a legal hold and remove their data preservation.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: release-custodians-from-hold
- description: Create a legal hold communication notice with escalation and reminder schedules.
  hints:
    readOnly: false
  name: create-hold-communication
- description: Create a task for tracking legal hold actions and assignments.
  hints:
    readOnly: false
  name: create-legal-hold-task
---
