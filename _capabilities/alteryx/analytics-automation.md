---
categories:
- automation
consumed_apis:
- alteryx-server
description: Analytics automation workflow combining Alteryx Server V3 API for workflow management, job execution, scheduling, user administration, credential management, and collection organization. Used by data analysts and server administrators to automate analytics pipelines.
layout: capability
name: Alteryx Analytics Automation
operations:
- description: List all workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Upload a new workflow
  method: POST
  name: upload-workflow
  path: /v1/workflows
- description: Get workflow details
  method: GET
  name: get-workflow
  path: /v1/workflows/{workflowId}
- description: List all schedules
  method: GET
  name: list-schedules
  path: /v1/schedules
- description: Create a new schedule
  method: POST
  name: create-schedule
  path: /v1/schedules
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: List all collections
  method: GET
  name: list-collections
  path: /v1/collections
personas: []
provider_name: Alteryx
provider_slug: alteryx
search_terms:
- list all workflows on the alteryx server
- create job
- list collections
- get details of a specific workflow
- create a new credential
- create a new workflow schedule
- deactivate user
- create collection
- analytics
- get analytic app questions for a workflow
- deactivate a user account
- list all stored credentials
- machine learning
- list all schedules
- upload workflow
- list all users
- delete a workflow
- create and execute a workflow job
- predictive analytics
- get workflow questions
- create a new collection
- update workflow
- list schedules
- download a workflow package
- get user details
- delete user
- get execution jobs for a workflow
- list workflows
- upload a new workflow package
- workflow management
- list users
- delete a workflow schedule
- data preparation
- list all users on the server
- create user
- data science
- list all workflow schedules
- user management
- delete workflow
- automation
- individual workflow operations
- get user
- alteryx
- schedule management
- get workflow jobs
- etl
- create schedule
- collection management
- list credentials
- create credential
- list all workflows
- delete collection
- create a new user
- delete schedule
- create a new schedule
- upload a new workflow
- data engineering
- get workflow
- update workflow metadata
- delete a user
- download workflow
- get workflow details
- delete a collection
- list all collections
slug: analytics-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Alteryx Analytics Automation\"\n  description: \"Analytics automation workflow combining Alteryx Server V3 API for workflow management, job execution, scheduling, user administration, credential management, and collection organization. Used by data analysts and server administrators to automate analytics pipelines.\"\n  tags:\n    - Alteryx\n    - Analytics\n    - Automation\n    - Data Engineering\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALTERYX_SERVER_URL: ALTERYX_SERVER_URL\n      ALTERYX_CLIENT_ID: ALTERYX_CLIENT_ID\n      ALTERYX_CLIENT_SECRET: ALTERYX_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: alteryx-server\n      location: ./shared/server-v3.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: alteryx-automation-api\n      description: \"Unified REST API for Alteryx analytics automation.\"\n      resources:\n        - path: /v1/workflows\n\
  \          name: workflows\n          description: \"Workflow management\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List all workflows\"\n              call: \"alteryx-server.get-workflows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-workflow\n              description: \"Upload a new workflow\"\n              call: \"alteryx-server.upload-workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowId}\n          name: workflow-detail\n          description: \"Individual workflow operations\"\n          operations:\n            - method: GET\n              name: get-workflow\n              description: \"Get workflow details\"\n              call: \"alteryx-server.get-workflow\"\n              with:\n          \
  \      workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/schedules\n          name: schedules\n          description: \"Schedule management\"\n          operations:\n            - method: GET\n              name: list-schedules\n              description: \"List all schedules\"\n              call: \"alteryx-server.get-schedules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-schedule\n              description: \"Create a new schedule\"\n              call: \"alteryx-server.create-schedule\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n           \
  \   description: \"List all users\"\n              call: \"alteryx-server.get-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: \"Collection management\"\n          operations:\n            - method: GET\n              name: list-collections\n              description: \"List all collections\"\n              call: \"alteryx-server.get-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: alteryx-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Alteryx analytics automation.\"\n      tools:\n        - name: list-workflows\n          description: \"List all workflows on the Alteryx Server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"alteryx-server.get-workflows\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow\n          description: \"Get details of a specific workflow\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-workflow\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-workflow\n          description: \"Upload a new workflow package\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.upload-workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-workflow\n          description: \"Update workflow metadata\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"alteryx-server.update-workflow\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: delete-workflow\n          description: \"Delete a workflow\"\n          hints:\n            destructive: true\n          call: \"alteryx-server.delete-workflow\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-workflow\n          description: \"Download a workflow package\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.download-workflow-package\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow-questions\n          description: \"Get analytic app questions for a workflow\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-workflow-questions\"\n          with:\n            workflowId: \"\
  tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow-jobs\n          description: \"Get execution jobs for a workflow\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-workflow-jobs\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job\n          description: \"Create and execute a workflow job\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.create-job\"\n          with:\n            workflowId: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schedules\n          description: \"List all workflow schedules\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-schedules\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-schedule\n          description: \"Create a new workflow schedule\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.create-schedule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-schedule\n          description: \"Delete a workflow schedule\"\n          hints:\n            destructive: true\n          call: \"alteryx-server.delete-schedule\"\n          with:\n            scheduleId: \"tools.schedule_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all users on the server\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"\
  Create a new user\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get user details\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-user\"\n          with:\n            userId: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a user\"\n          hints:\n            destructive: true\n          call: \"alteryx-server.delete-user\"\n          with:\n            userId: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deactivate-user\n          description: \"Deactivate a user account\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.deactivate-user\"\
  \n          with:\n            userId: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-credentials\n          description: \"List all stored credentials\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-credentials\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-credential\n          description: \"Create a new credential\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.create-credential\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collections\n          description: \"List all collections\"\n          hints:\n            readOnly: true\n          call: \"alteryx-server.get-collections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-collection\n\
  \          description: \"Create a new collection\"\n          hints:\n            readOnly: false\n          call: \"alteryx-server.create-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-collection\n          description: \"Delete a collection\"\n          hints:\n            destructive: true\n          call: \"alteryx-server.delete-collection\"\n          with:\n            collectionId: \"tools.collection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alteryx/refs/heads/main/capabilities/analytics-automation.yaml
tags:
- Alteryx
- Analytics
- Automation
- Data Engineering
tools:
- description: List all workflows on the Alteryx Server
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: Get details of a specific workflow
  hints:
    readOnly: true
  name: get-workflow
- description: Upload a new workflow package
  hints:
    readOnly: false
  name: upload-workflow
- description: Update workflow metadata
  hints:
    idempotent: true
    readOnly: false
  name: update-workflow
- description: Delete a workflow
  hints:
    destructive: true
  name: delete-workflow
- description: Download a workflow package
  hints:
    readOnly: true
  name: download-workflow
- description: Get analytic app questions for a workflow
  hints:
    readOnly: true
  name: get-workflow-questions
- description: Get execution jobs for a workflow
  hints:
    readOnly: true
  name: get-workflow-jobs
- description: Create and execute a workflow job
  hints:
    readOnly: false
  name: create-job
- description: List all workflow schedules
  hints:
    readOnly: true
  name: list-schedules
- description: Create a new workflow schedule
  hints:
    readOnly: false
  name: create-schedule
- description: Delete a workflow schedule
  hints:
    destructive: true
  name: delete-schedule
- description: List all users on the server
  hints:
    readOnly: true
  name: list-users
- description: Create a new user
  hints:
    readOnly: false
  name: create-user
- description: Get user details
  hints:
    readOnly: true
  name: get-user
- description: Delete a user
  hints:
    destructive: true
  name: delete-user
- description: Deactivate a user account
  hints:
    readOnly: false
  name: deactivate-user
- description: List all stored credentials
  hints:
    readOnly: true
  name: list-credentials
- description: Create a new credential
  hints:
    readOnly: false
  name: create-credential
- description: List all collections
  hints:
    readOnly: true
  name: list-collections
- description: Create a new collection
  hints:
    readOnly: false
  name: create-collection
- description: Delete a collection
  hints:
    destructive: true
  name: delete-collection
---
