---
categories: []
consumed_apis: []
description: Unified workflow for automation governance combining Automation Hub for pipeline management, Platform Management for user and license administration, and Test Manager for quality assurance. Used by Center of Excellence managers and platform administrators overseeing the enterprise automation program.
layout: capability
name: UiPath Automation Governance
operations:
- description: List automation ideas in the pipeline
  method: GET
  name: list-automations
  path: /v1/automation-ideas
- description: Submit a new automation idea
  method: POST
  name: create-automation-idea
  path: /v1/automation-ideas
- description: Get automation pipeline status
  method: GET
  name: get-pipeline
  path: /v1/pipeline
- description: Create a platform user
  method: POST
  name: create-user
  path: /v1/users
- description: List organization groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Query audit log events
  method: GET
  name: query-audit-events
  path: /v1/audit-events
- description: List test projects
  method: GET
  name: list-test-projects
  path: /v1/test-projects
- description: List test executions
  method: GET
  name: list-test-executions
  path: /v1/test-executions
personas: []
provider_name: UiPath
provider_slug: uipath
search_terms:
- query audit events
- get automation pipeline status
- create a platform user
- submit a new automation idea to the automation hub pipeline
- get the overall automation pipeline status and metrics
- licensing
- ocr, classify, and extract data from documents
- platform user management
- enterprise automation
- document processing
- query organization audit log for compliance and governance
- list test projects for qa governance
- test management and automated quality verification
- create automation idea
- create user
- list automation ideas in the pipeline
- query audit log events
- list automation ideas
- list test executions
- RPA Developer
- Platform Administrator
- list organization groups and memberships
- monitors and manages running automations, robots, queues, and alerts
- list test projects
- get automation pipeline
- CoE Manager
- get details of an organization user
- manages users, groups, licenses, and organizational settings
- automation
- robotic process automation
- day-to-day monitoring and management of running automations
- center of excellence
- list automations
- create a new test case in a test project
- get license allocation
- artificial intelligence
- create a new user in the uipath organization
- orchestration
- uipath
- Document Processing Specialist
- oversees the automation program pipeline, prioritization, and roi tracking
- list test execution history for quality reporting
- automation idea pipeline management
- platform administration
- list organization groups
- organization audit log
- automation governance
- creates and manages test projects, test cases, and execution reports
- rpa
- manage automation pipeline, users, licenses, and quality
- configures and manages document understanding models and extraction pipelines
- create test case
- manage robots, jobs, queues, and assets in orchestrator
- Automation Operator
- get user
- automation pipeline overview
- core rpa automation lifecycle from development to execution
- testing
- submit a new automation idea
- test project management
- get pipeline
- list groups
- list automation ideas in the automation hub pipeline
- platform configuration including users, groups, and licenses
- intelligent processing of structured and unstructured documents
- platform group management
- oversight of the automation program including pipeline, compliance, and quality
- test execution results
- QA Engineer
- get license allocation for an organization group
- quality assurance
- develops and deploys automation workflows using uipath studio and python sdk
slug: automation-governance
source_filename: automation-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UiPath Automation Governance\n  description: Unified workflow for automation governance combining Automation Hub for pipeline management, Platform Management\n    for user and license administration, and Test Manager for quality assurance. Used by Center of Excellence managers and\n    platform administrators overseeing the enterprise automation program.\n  tags:\n  - UiPath\n  - Automation Governance\n  - Center of Excellence\n  - Platform Administration\n  - Licensing\n  - Quality Assurance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UIPATH_AUTOMATION_HUB_API_KEY: UIPATH_AUTOMATION_HUB_API_KEY\n    UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: automation-hub\n    baseUri: https://cloud.uipath.com/{orgName}/{tenantName}/automationhub_/api/v1\n    description: UiPath Automation Hub API for managing automation ideas and pipeline.\n    authentication:\n\
  \      type: apikey\n      key: X-Authorization\n      value: '{{UIPATH_AUTOMATION_HUB_API_KEY}}'\n      placement: header\n    resources:\n    - name: automations\n      path: /automations\n      description: Manage automation ideas and projects\n      operations:\n      - name: list-automations\n        method: GET\n        description: List automation ideas in the pipeline\n        inputParameters:\n        - name: phase\n          in: query\n          type: string\n          required: false\n          description: Filter by pipeline phase\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-automation-idea\n        method: POST\n        description: Submit a new automation idea\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-automation\n        method: GET\n        description: Get details of a specific automation\n        inputParameters:\n        - name: automationId\n          in: path\n          type: string\n          required: true\n          description: Automation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-automation\n        method: PATCH\n        description: Update automation details\n        inputParameters:\n        - name:\
  \ automationId\n          in: path\n          type: string\n          required: true\n          description: Automation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n      - name: delete-automation\n        method: DELETE\n        description: Delete an automation idea\n        inputParameters:\n        - name: automationId\n          in: path\n          type: string\n          required: true\n          description: Automation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipeline\n      path: /automationpipeline\n      description: View the overall automation pipeline\n      operations:\n      - name: get-automation-pipeline\n        method: GET\n        description: Get the automation pipeline overview\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage Automation Hub users\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in Automation Hub\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: platform-management\n    baseUri: https://cloud.uipath.com\n    description: UiPath Platform Management API for organization and user administration.\n    authentication:\n      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n    resources:\n    - name: users\n      path: /{organizationName}/identity_/api/User\n      description: Manage organization users\n      operations:\n      - name: get-user\n        method: GET\n        description: Get user details by ID\n        inputParameters:\n     \
  \   - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in the organization\n        inputParameters:\n        - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n      - name: delete-user\n        method: DELETE\n        description:\
  \ Delete a user from the organization\n        inputParameters:\n        - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /{organizationName}/identity_/api/Group\n      description: Manage organization groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all groups in the organization\n        inputParameters:\n        - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: partitionGlobalId\n          in: path\n          type: string\n          required: true\n     \
  \     description: Partition global identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group\n        inputParameters:\n        - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.groupName}}'\n    - name: audit\n      path: /{organizationName}/orgaudit_/api/query/events\n      description: Query organization audit events\n      operations:\n      - name: query-audit-events\n        method: GET\n        description: Query organization-level audit events\n        inputParameters:\n        - name: organizationName\n          in: path\n\
  \          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses\n      path: /{organizationName}/la/api/account/{accountId}/user-license/group/{groupId}\n      description: Manage license allocations\n      operations:\n      - name: get-group-license-allocation\n        method: GET\n        description: Get license allocation for a group\n        inputParameters:\n        - name: organizationName\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group identifier\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: test-manager\n    baseUri: https://cloud.uipath.com/{organizationName}/{tenantName}/testmanager_\n    description: UiPath Test Manager API for managing test projects, cases, sets, and executions.\n    authentication:\n      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n    resources:\n    - name: projects\n      path: /api/v2/projects\n      description: Manage test projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all test projects\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new test project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.projectName}}'\n      - name: get-project\n        method: GET\n        description: Get test project details\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: test-cases\n      path: /api/v2/projects/{projectId}/testcases\n      description: Manage test cases within a project\n      operations:\n      - name: list-test-cases\n        method: GET\n        description: List test cases in\
  \ a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-test-case\n        method: POST\n        description: Create a new test case\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.testCaseName}}'\n    - name: test-sets\n      path: /api/v2/projects/{projectId}/testsets\n\
  \      description: Manage test sets for grouping test cases\n      operations:\n      - name: list-test-sets\n        method: GET\n        description: List test sets in a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-test-set\n        method: POST\n        description: Create a new test set\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.testSetName}}'\n    - name: test-executions\n      path:\
  \ /api/v2/projects/{projectId}/testexecutions\n      description: Track test execution results\n      operations:\n      - name: list-test-executions\n        method: GET\n        description: List test execution results\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: automation-governance-api\n    description: Unified REST API for automation governance across Automation Hub, Platform Management, and Test Manager.\n    resources:\n    - path: /v1/automation-ideas\n      name: automation-ideas\n      description: Automation idea pipeline management\n      operations:\n      - method: GET\n        name: list-automations\n        description: List automation ideas in the pipeline\n       \
  \ call: automation-hub.list-automations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-automation-idea\n        description: Submit a new automation idea\n        call: automation-hub.create-automation-idea\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipeline\n      name: pipeline\n      description: Automation pipeline overview\n      operations:\n      - method: GET\n        name: get-pipeline\n        description: Get automation pipeline status\n        call: automation-hub.get-automation-pipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Platform user management\n      operations:\n      - method: POST\n        name: create-user\n        description: Create a platform user\n        call: platform-management.create-user\n\
  \        with:\n          email: rest.email\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Platform group management\n      operations:\n      - method: GET\n        name: list-groups\n        description: List organization groups\n        call: platform-management.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit-events\n      name: audit-events\n      description: Organization audit log\n      operations:\n      - method: GET\n        name: query-audit-events\n        description: Query audit log events\n        call: platform-management.query-audit-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-projects\n      name: test-projects\n      description: Test project management\n      operations:\n      - method: GET\n        name: list-test-projects\n      \
  \  description: List test projects\n        call: test-manager.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-executions\n      name: test-executions\n      description: Test execution results\n      operations:\n      - method: GET\n        name: list-test-executions\n        description: List test executions\n        call: test-manager.list-test-executions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: automation-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted automation governance across Automation Hub, Platform Management, and Test Manager.\n    tools:\n    - name: list-automation-ideas\n      description: List automation ideas in the Automation Hub pipeline\n      hints:\n        readOnly: true\n        openWorld: true\n      call: automation-hub.list-automations\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: create-automation-idea\n      description: Submit a new automation idea to the Automation Hub pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: automation-hub.create-automation-idea\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-automation-pipeline\n      description: Get the overall automation pipeline status and metrics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: automation-hub.get-automation-pipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details of an organization user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: platform-management.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: create-user\n      description: Create a new user in the UiPath organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platform-management.create-user\n      with:\n        email: tools.email\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List organization groups and memberships\n      hints:\n        readOnly: true\n        openWorld: true\n      call: platform-management.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-audit-events\n      description: Query organization audit log for compliance and governance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: platform-management.query-audit-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-license-allocation\n      description: Get license\
  \ allocation for an organization group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: platform-management.get-group-license-allocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-test-projects\n      description: List test projects for QA governance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: test-manager.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-test-executions\n      description: List test execution history for quality reporting\n      hints:\n        readOnly: true\n        openWorld: true\n      call: test-manager.list-test-executions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-test-case\n      description: Create a new test case in a test project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: test-manager.create-test-case\n\
  \      with:\n        projectId: tools.projectId\n        testCaseName: tools.testCaseName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uipath/refs/heads/main/capabilities/automation-governance.yaml
tags:
- UiPath
- Automation Governance
- Center of Excellence
- Platform Administration
- Licensing
- Quality Assurance
tools:
- description: List automation ideas in the Automation Hub pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-automation-ideas
- description: Submit a new automation idea to the Automation Hub pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-automation-idea
- description: Get the overall automation pipeline status and metrics
  hints:
    openWorld: true
    readOnly: true
  name: get-automation-pipeline
- description: Get details of an organization user
  hints:
    openWorld: true
    readOnly: true
  name: get-user
- description: Create a new user in the UiPath organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: List organization groups and memberships
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Query organization audit log for compliance and governance
  hints:
    openWorld: true
    readOnly: true
  name: query-audit-events
- description: Get license allocation for an organization group
  hints:
    openWorld: true
    readOnly: true
  name: get-license-allocation
- description: List test projects for QA governance
  hints:
    openWorld: true
    readOnly: true
  name: list-test-projects
- description: List test execution history for quality reporting
  hints:
    openWorld: true
    readOnly: true
  name: list-test-executions
- description: Create a new test case in a test project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-test-case
---
