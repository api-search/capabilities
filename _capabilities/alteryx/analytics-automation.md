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
- list all workflows
- delete workflow
- delete schedule
- create a new workflow schedule
- machine learning
- create credential
- download a workflow package
- get workflow
- list all workflow schedules
- analytics
- delete a user
- delete a collection
- delete collection
- list all collections
- create user
- get execution jobs for a workflow
- user management
- list collections
- upload workflow
- get workflow details
- upload a new workflow package
- list schedules
- deactivate user
- data preparation
- predictive analytics
- list all workflows on the alteryx server
- get workflow questions
- create collection
- get details of a specific workflow
- list users
- delete a workflow
- data science
- delete user
- individual workflow operations
- alteryx
- schedule management
- update workflow metadata
- upload a new workflow
- data engineering
- delete a workflow schedule
- create a new user
- list all users on the server
- download workflow
- list credentials
- list all stored credentials
- create a new schedule
- list all users
- create and execute a workflow job
- create job
- get analytic app questions for a workflow
- etl
- get user details
- list all schedules
- create schedule
- collection management
- create a new collection
- update workflow
- create a new credential
- get user
- workflow management
- list workflows
- deactivate a user account
- get workflow jobs
- automation
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
