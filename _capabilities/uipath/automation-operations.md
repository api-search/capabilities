---
categories: []
consumed_apis: []
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
- queue transaction item management
- Automation Operator
- oversight of the automation program including pipeline, compliance, and quality
- list all registered robots
- list queue items
- list system and automation alerts for monitoring
- list queue transaction items
- testing
- list records from a data service entity
- automation
- list data entity records
- robotic process automation
- list queues
- stop job
- start jobs
- create asset
- automation operations
- day-to-day monitoring and management of running automations
- shared asset management
- develops and deploys automation workflows using uipath studio and python sdk
- system and automation alerts
- automation job management
- uipath
- list robots
- robots
- automation robot management
- list shared assets
- artificial intelligence
- start automation jobs
- create data record
- manage automation pipeline, users, licenses, and quality
- list automation jobs with optional filtering and pagination
- configures and manages document understanding models and extraction pipelines
- orchestration
- list shared automation assets like credentials and variables
- intelligent processing of structured and unstructured documents
- orchestrator
- creates and manages test projects, test cases, and execution reports
- QA Engineer
- transaction queue management
- automation data storage records
- list data records
- RPA Developer
- list all registered automation robots and their status
- list alerts
- list automation alerts
- CoE Manager
- test management and automated quality verification
- add queue item
- rpa
- list jobs
- Platform Administrator
- platform configuration including users, groups, and licenses
- enterprise automation
- manage robots, jobs, queues, and assets in orchestrator
- create a new shared asset
- manages users, groups, licenses, and organizational settings
- jobs
- monitors and manages running automations, robots, queues, and alerts
- stop a running automation job
- start one or more uipath automation jobs
- list all queue definitions
- add item to queue
- create a new record in a data service entity
- Document Processing Specialist
- list entity records
- document processing
- list automation jobs with filtering
- core rpa automation lifecycle from development to execution
- list all transaction queue definitions
- list assets
- add a new transaction item to an automation queue
- ocr, classify, and extract data from documents
- oversees the automation program pipeline, prioritization, and roi tracking
slug: automation-operations
source_filename: automation-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UiPath Automation Operations\n  description: Unified workflow for automation operators managing robots, jobs, queues, and assets in the UiPath Orchestrator.\n    Used by RPA developers and operations teams to deploy, monitor, and manage running automations at scale.\n  tags:\n  - UiPath\n  - Orchestrator\n  - Automation Operations\n  - RPA\n  - Robots\n  - Jobs\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: orchestrator\n    baseUri: https://cloud.uipath.com/{organizationName}/{tenantName}/orchestrator_\n    description: UiPath Orchestrator API for managing automation robots, jobs, queues, and assets.\n    authentication:\n      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /odata/Jobs\n      description: Manage automation job execution\n   \
  \   operations:\n      - name: list-jobs\n        method: GET\n        description: List automation jobs with filtering\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get a specific job by key\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Job identifier\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-jobs\n        method: POST\n        description: Start one or more automation jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            startInfo: '{{tools.startInfo}}'\n      - name: stop-job\n        method: POST\n        description: Stop a running automation job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n    - name: processes\n      path: /odata/Processes\n      description: Manage automation processes\n      operations:\n      - name: list-processes\n        method: GET\n        description: List deployed automation processes\n        inputParameters:\n\
  \        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /odata/QueueDefinitions\n      description: Manage transaction queues\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all queue definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new queue definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.queueName}}'\n    - name: queue-items\n      path: /odata/QueueItems\n\
  \      description: Manage queue transaction items\n      operations:\n      - name: list-queue-items\n        method: GET\n        description: List queue transaction items\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-queue-item\n        method: POST\n        description: Add a new item to a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            itemData: '{{tools.itemData}}'\n    - name: assets\n      path: /odata/Assets\n      description: Manage shared assets like credentials and values\n      operations:\n      - name: list-assets\n        method: GET\n        description:\
  \ List all shared assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-asset\n        method: POST\n        description: Create a new shared asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.assetName}}'\n            ValueType: '{{tools.valueType}}'\n      - name: get-asset\n        method: GET\n        description: Get a specific asset by key\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-asset\n        method: PUT\n        description: Update an existing asset\n  \
  \      inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Value: '{{tools.value}}'\n      - name: delete-asset\n        method: DELETE\n        description: Delete an asset\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: robots\n      path: /odata/Robots\n      description: Manage automation robots\n      operations:\n      - name: list-robots\n        method: GET\n        description: List all registered robots\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /odata/Alerts\n      description: Retrieve system and automation alerts\n      operations:\n      - name: list-alerts\n        method: GET\n        description: List system alerts and notifications\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /odata/Webhooks\n      description: Manage webhook subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n \
  \       method: POST\n        description: Create a new webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Url: '{{tools.webhookUrl}}'\n            EventTypes: '{{tools.eventTypes}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Delete a webhook subscription\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Webhook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: data-service\n    baseUri: https://cloud.uipath.com/{organizationName}/{tenantName}/dataservice_/api/EntityService\n    description: UiPath Data Service API for managing custom data entities and records.\n    authentication:\n\
  \      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n    resources:\n    - name: entities\n      path: /{entityName}\n      description: Manage records for a custom entity\n      operations:\n      - name: list-entity-records\n        method: GET\n        description: List records for a specific entity\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Records to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-entity-record\n        method: POST\n        description: Create a new record for an entity\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.recordData}}'\n      - name: get-entity-record\n        method: GET\n        description: Get a specific entity record by ID\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: Record identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: update-entity-record\n        method: PUT\n        description: Update an existing entity record\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: Record identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.recordData}}'\n      - name: delete-entity-record\n        method: DELETE\n        description: Delete an entity record\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        - name: recordId\n          in: path\n\
  \          type: string\n          required: true\n          description: Record identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-entity-records\n        method: POST\n        description: Query entity records with complex filters\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n          description: Entity name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filter: '{{tools.filter}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: automation-operations-api\n    description: Unified REST API for managing UiPath automation operations including jobs, queues, robots, and assets.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description:\
  \ Automation job management\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List automation jobs with filtering\n        call: orchestrator.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-jobs\n        description: Start automation jobs\n        call: orchestrator.start-jobs\n        with:\n          startInfo: rest.startInfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/robots\n      name: robots\n      description: Automation robot management\n      operations:\n      - method: GET\n        name: list-robots\n        description: List all registered robots\n        call: orchestrator.list-robots\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Transaction queue management\n      operations:\n      - method: GET\n        name: list-queues\n\
  \        description: List all queue definitions\n        call: orchestrator.list-queues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queue-items\n      name: queue-items\n      description: Queue transaction item management\n      operations:\n      - method: GET\n        name: list-queue-items\n        description: List queue transaction items\n        call: orchestrator.list-queue-items\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-queue-item\n        description: Add item to queue\n        call: orchestrator.add-queue-item\n        with:\n          itemData: rest.itemData\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Shared asset management\n      operations:\n      - method: GET\n        name: list-assets\n        description: List shared assets\n        call: orchestrator.list-assets\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-asset\n        description: Create a new shared asset\n        call: orchestrator.create-asset\n        with:\n          assetName: rest.assetName\n          valueType: rest.valueType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: System and automation alerts\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List automation alerts\n        call: orchestrator.list-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data/{entityName}/records\n      name: data-records\n      description: Automation data storage records\n      operations:\n      - method: GET\n        name: list-entity-records\n        description: List data entity records\n        call: data-service.list-entity-records\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: automation-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted automation operations management across UiPath Orchestrator and Data Service.\n    tools:\n    - name: list-jobs\n      description: List automation jobs with optional filtering and pagination\n      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-jobs\n      description: Start one or more UiPath automation jobs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orchestrator.start-jobs\n      with:\n        startInfo: tools.startInfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-job\n      description: Stop a running automation job\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: orchestrator.stop-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-robots\n      description: List all registered automation robots and their status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-robots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List all transaction queue definitions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-queues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-queue-item\n      description: Add a new transaction item to an automation queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orchestrator.add-queue-item\n      with:\n        itemData: tools.itemData\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List shared automation assets like credentials and variables\n      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: List system and automation alerts for monitoring\n      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-records\n      description: List records from a Data Service entity\n      hints:\n        readOnly: true\n        openWorld: true\n      call: data-service.list-entity-records\n      with:\n        entityName: tools.entityName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-record\n      description: Create a new record in a Data Service entity\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: data-service.create-entity-record\n      with:\n        entityName: tools.entityName\n        recordData: tools.recordData\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
