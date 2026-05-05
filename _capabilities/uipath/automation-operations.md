---
categories: []
consumed_apis:
- orchestrator
- data-service
description: Unified workflow for automation operators managing robots, jobs, queues, and assets in the UiPath Orchestrator. Used by RPA developers and operations teams to deploy, monitor, and manage running automations at scale.
layout: capability
name: UiPath Automation Operations
operations:
- description: List automation jobs with filtering
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Start automation jobs
  method: POST
  name: start-jobs
  path: /v1/jobs
- description: List all registered robots
  method: GET
  name: list-robots
  path: /v1/robots
- description: List all queue definitions
  method: GET
  name: list-queues
  path: /v1/queues
- description: List queue transaction items
  method: GET
  name: list-queue-items
  path: /v1/queue-items
- description: Add item to queue
  method: POST
  name: add-queue-item
  path: /v1/queue-items
- description: List shared assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: Create a new shared asset
  method: POST
  name: create-asset
  path: /v1/assets
- description: List automation alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: List data entity records
  method: GET
  name: list-entity-records
  path: /v1/data/{entityName}/records
personas: []
provider_name: UiPath
provider_slug: uipath
search_terms:
- list automation alerts
- create asset
- oversees the automation program pipeline, prioritization, and roi tracking
- robotic process automation
- list jobs
- monitors and manages running automations, robots, queues, and alerts
- robots
- list all transaction queue definitions
- orchestrator
- uipath
- list queue items
- shared asset management
- automation operations
- automation robot management
- list assets
- list shared assets
- list data entity records
- manage automation pipeline, users, licenses, and quality
- Platform Administrator
- automation job management
- queue transaction item management
- QA Engineer
- list queue transaction items
- document processing
- stop job
- creates and manages test projects, test cases, and execution reports
- list automation jobs with filtering
- manage robots, jobs, queues, and assets in orchestrator
- enterprise automation
- artificial intelligence
- core rpa automation lifecycle from development to execution
- list all registered robots
- oversight of the automation program including pipeline, compliance, and quality
- list all registered automation robots and their status
- platform configuration including users, groups, and licenses
- RPA Developer
- orchestration
- list entity records
- list automation jobs with optional filtering and pagination
- list system and automation alerts for monitoring
- start jobs
- list robots
- list alerts
- start one or more uipath automation jobs
- system and automation alerts
- list records from a data service entity
- create a new record in a data service entity
- jobs
- list all queue definitions
- create data record
- list queues
- create a new shared asset
- develops and deploys automation workflows using uipath studio and python sdk
- configures and manages document understanding models and extraction pipelines
- testing
- list data records
- list shared automation assets like credentials and variables
- day-to-day monitoring and management of running automations
- rpa
- add a new transaction item to an automation queue
- CoE Manager
- start automation jobs
- manages users, groups, licenses, and organizational settings
- test management and automated quality verification
- add item to queue
- Automation Operator
- intelligent processing of structured and unstructured documents
- transaction queue management
- automation
- add queue item
- ocr, classify, and extract data from documents
- automation data storage records
- stop a running automation job
- Document Processing Specialist
slug: automation-operations
source_filename: automation-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UiPath Automation Operations\"\n  description: \"Unified workflow for automation operators managing robots, jobs, queues, and assets in the UiPath Orchestrator. Used by RPA developers and operations teams to deploy, monitor, and manage running automations at scale.\"\n  tags:\n    - UiPath\n    - Orchestrator\n    - Automation Operations\n    - RPA\n    - Robots\n    - Jobs\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: orchestrator\n      location: ./shared/orchestrator.yaml\n    - import: data-service\n      location: ./shared/data-service.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: automation-operations-api\n      description: \"Unified REST API for managing UiPath automation operations including jobs, queues, robots, and assets.\"\n      resources:\n       \
  \ - path: /v1/jobs\n          name: jobs\n          description: \"Automation job management\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List automation jobs with filtering\"\n              call: \"orchestrator.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: start-jobs\n              description: \"Start automation jobs\"\n              call: \"orchestrator.start-jobs\"\n              with:\n                startInfo: \"rest.startInfo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/robots\n          name: robots\n          description: \"Automation robot management\"\n          operations:\n            - method: GET\n              name: list-robots\n              description: \"List all registered robots\"\n              call: \"orchestrator.list-robots\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queues\n          name: queues\n          description: \"Transaction queue management\"\n          operations:\n            - method: GET\n              name: list-queues\n              description: \"List all queue definitions\"\n              call: \"orchestrator.list-queues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queue-items\n          name: queue-items\n          description: \"Queue transaction item management\"\n          operations:\n            - method: GET\n              name: list-queue-items\n              description: \"List queue transaction items\"\n              call: \"orchestrator.list-queue-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-queue-item\n    \
  \          description: \"Add item to queue\"\n              call: \"orchestrator.add-queue-item\"\n              with:\n                itemData: \"rest.itemData\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Shared asset management\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List shared assets\"\n              call: \"orchestrator.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-asset\n              description: \"Create a new shared asset\"\n              call: \"orchestrator.create-asset\"\n              with:\n                assetName: \"rest.assetName\"\n                valueType: \"rest.valueType\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"System and automation alerts\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List automation alerts\"\n              call: \"orchestrator.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data/{entityName}/records\n          name: data-records\n          description: \"Automation data storage records\"\n          operations:\n            - method: GET\n              name: list-entity-records\n              description: \"List data entity records\"\n              call: \"data-service.list-entity-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: automation-operations-mcp\n      transport: http\n      description: \"\
  MCP server for AI-assisted automation operations management across UiPath Orchestrator and Data Service.\"\n      tools:\n        - name: list-jobs\n          description: \"List automation jobs with optional filtering and pagination\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-jobs\n          description: \"Start one or more UiPath automation jobs\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"orchestrator.start-jobs\"\n          with:\n            startInfo: \"tools.startInfo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-job\n          description: \"Stop a running automation job\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n          call: \"orchestrator.stop-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-robots\n          description: \"List all registered automation robots and their status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-robots\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-queues\n          description: \"List all transaction queue definitions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-queues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-queue-item\n          description: \"Add a new transaction item to an automation queue\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: false\n          call: \"orchestrator.add-queue-item\"\n          with:\n            itemData: \"tools.itemData\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List shared automation assets like credentials and variables\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alerts\n          description: \"List system and automation alerts for monitoring\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-records\n          description: \"List records from a Data Service entity\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"data-service.list-entity-records\"\n          with:\n            entityName: \"tools.entityName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-record\n          description: \"Create a new record in a Data Service entity\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"data-service.create-entity-record\"\n          with:\n            entityName: \"tools.entityName\"\n            recordData: \"tools.recordData\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uipath/refs/heads/main/capabilities/automation-operations.yaml
tags:
- UiPath
- Orchestrator
- Automation Operations
- RPA
- Robots
- Jobs
tools:
- description: List automation jobs with optional filtering and pagination
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Start one or more UiPath automation jobs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-jobs
- description: Stop a running automation job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stop-job
- description: List all registered automation robots and their status
  hints:
    openWorld: true
    readOnly: true
  name: list-robots
- description: List all transaction queue definitions
  hints:
    openWorld: true
    readOnly: true
  name: list-queues
- description: Add a new transaction item to an automation queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-queue-item
- description: List shared automation assets like credentials and variables
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: List system and automation alerts for monitoring
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: List records from a Data Service entity
  hints:
    openWorld: true
    readOnly: true
  name: list-data-records
- description: Create a new record in a Data Service entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-data-record
---
