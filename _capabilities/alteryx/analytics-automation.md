---
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
- list all schedules
- schedule management
- create user
- data science
- get workflow details
- list all users on the server
- get analytic app questions for a workflow
- delete a workflow schedule
- list all collections
- get workflow
- get user
- list all workflows on the alteryx server
- list credentials
- create a new collection
- get details of a specific workflow
- delete a user
- deactivate a user account
- list workflows
- analytics
- upload workflow
- upload a new workflow
- download a workflow package
- data preparation
- create a new user
- create a new credential
- list all workflows
- get workflow jobs
- predictive analytics
- delete schedule
- alteryx
- create a new workflow schedule
- automation
- workflow management
- create job
- etl
- delete a collection
- upload a new workflow package
- download workflow
- create a new schedule
- list all workflow schedules
- create collection
- deactivate user
- list collections
- delete a workflow
- machine learning
- get user details
- data engineering
- create and execute a workflow job
- list all users
- list schedules
- collection management
- individual workflow operations
- create credential
- list all stored credentials
- get workflow questions
- create schedule
- update workflow metadata
- delete workflow
- get execution jobs for a workflow
- update workflow
- delete user
- delete collection
- list users
- user management
slug: analytics-automation
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
