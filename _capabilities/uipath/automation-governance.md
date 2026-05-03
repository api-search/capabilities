---
categories: []
consumed_apis:
- automation-hub
- platform-management
- test-manager
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
- automation idea pipeline management
- Document Processing Specialist
- configures and manages document understanding models and extraction pipelines
- automation
- test project management
- query audit log events
- center of excellence
- create user
- query audit events
- list automation ideas
- manage automation pipeline, users, licenses, and quality
- ocr, classify, and extract data from documents
- Automation Operator
- licensing
- develops and deploys automation workflows using uipath studio and python sdk
- submit a new automation idea to the automation hub pipeline
- manages users, groups, licenses, and organizational settings
- manage robots, jobs, queues, and assets in orchestrator
- list automation ideas in the automation hub pipeline
- automation governance
- RPA Developer
- list automation ideas in the pipeline
- create automation idea
- QA Engineer
- get the overall automation pipeline status and metrics
- test management and automated quality verification
- platform administration
- create a new test case in a test project
- list automations
- get user
- list organization groups and memberships
- Platform Administrator
- list test execution history for quality reporting
- platform group management
- get pipeline
- list test projects
- list test executions
- get license allocation for an organization group
- creates and manages test projects, test cases, and execution reports
- create a platform user
- create a new user in the uipath organization
- submit a new automation idea
- organization audit log
- platform user management
- get automation pipeline
- intelligent processing of structured and unstructured documents
- artificial intelligence
- robotic process automation
- automation pipeline overview
- test execution results
- uipath
- list organization groups
- create test case
- quality assurance
- oversees the automation program pipeline, prioritization, and roi tracking
- day-to-day monitoring and management of running automations
- CoE Manager
- platform configuration including users, groups, and licenses
- query organization audit log for compliance and governance
- list groups
- monitors and manages running automations, robots, queues, and alerts
- enterprise automation
- get details of an organization user
- get automation pipeline status
- orchestration
- list test projects for qa governance
- oversight of the automation program including pipeline, compliance, and quality
- get license allocation
- core rpa automation lifecycle from development to execution
- testing
- rpa
- document processing
slug: automation-governance
source_filename: automation-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UiPath Automation Governance\"\n  description: \"Unified workflow for automation governance combining Automation Hub for pipeline management, Platform Management for user and license administration, and Test Manager for quality assurance. Used by Center of Excellence managers and platform administrators overseeing the enterprise automation program.\"\n  tags:\n    - UiPath\n    - Automation Governance\n    - Center of Excellence\n    - Platform Administration\n    - Licensing\n    - Quality Assurance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UIPATH_AUTOMATION_HUB_API_KEY: UIPATH_AUTOMATION_HUB_API_KEY\n      UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: automation-hub\n      location: ./shared/automation-hub.yaml\n    - import: platform-management\n      location: ./shared/platform-management.yaml\n    - import: test-manager\n   \
  \   location: ./shared/test-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: automation-governance-api\n      description: \"Unified REST API for automation governance across Automation Hub, Platform Management, and Test Manager.\"\n      resources:\n        - path: /v1/automation-ideas\n          name: automation-ideas\n          description: \"Automation idea pipeline management\"\n          operations:\n            - method: GET\n              name: list-automations\n              description: \"List automation ideas in the pipeline\"\n              call: \"automation-hub.list-automations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-automation-idea\n              description: \"Submit a new automation idea\"\n              call: \"automation-hub.create-automation-idea\"\n              with:\n                name: \"rest.name\"\n           \
  \     description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipeline\n          name: pipeline\n          description: \"Automation pipeline overview\"\n          operations:\n            - method: GET\n              name: get-pipeline\n              description: \"Get automation pipeline status\"\n              call: \"automation-hub.get-automation-pipeline\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"Platform user management\"\n          operations:\n            - method: POST\n              name: create-user\n              description: \"Create a platform user\"\n              call: \"platform-management.create-user\"\n              with:\n                email: \"rest.email\"\n                name: \"rest.name\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Platform group management\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List organization groups\"\n              call: \"platform-management.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audit-events\n          name: audit-events\n          description: \"Organization audit log\"\n          operations:\n            - method: GET\n              name: query-audit-events\n              description: \"Query audit log events\"\n              call: \"platform-management.query-audit-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/test-projects\n          name: test-projects\n          description: \"Test project management\"\
  \n          operations:\n            - method: GET\n              name: list-test-projects\n              description: \"List test projects\"\n              call: \"test-manager.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/test-executions\n          name: test-executions\n          description: \"Test execution results\"\n          operations:\n            - method: GET\n              name: list-test-executions\n              description: \"List test executions\"\n              call: \"test-manager.list-test-executions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: automation-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted automation governance across Automation Hub, Platform Management, and Test Manager.\"\n      tools:\n        - name: list-automation-ideas\n\
  \          description: \"List automation ideas in the Automation Hub pipeline\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"automation-hub.list-automations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-automation-idea\n          description: \"Submit a new automation idea to the Automation Hub pipeline\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"automation-hub.create-automation-idea\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-automation-pipeline\n          description: \"Get the overall automation pipeline status and metrics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  automation-hub.get-automation-pipeline\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get details of an organization user\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"platform-management.get-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user in the UiPath organization\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"platform-management.create-user\"\n          with:\n            email: \"tools.email\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List organization\
  \ groups and memberships\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"platform-management.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-audit-events\n          description: \"Query organization audit log for compliance and governance\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"platform-management.query-audit-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-license-allocation\n          description: \"Get license allocation for an organization group\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"platform-management.get-group-license-allocation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-test-projects\n          description: \"\
  List test projects for QA governance\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"test-manager.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-test-executions\n          description: \"List test execution history for quality reporting\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"test-manager.list-test-executions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-test-case\n          description: \"Create a new test case in a test project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"test-manager.create-test-case\"\n          with:\n            projectId: \"tools.projectId\"\n            testCaseName: \"tools.testCaseName\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n"
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
