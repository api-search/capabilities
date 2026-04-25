---
consumed_apis:
- productiv-developer
description: Unified workflow for managing SaaS applications, tracking usage and spend, provisioning users, and auditing platform activity using the Productiv Developer API.
layout: capability
name: Productiv SaaS Management
operations:
- description: Obtain an OAuth2 access token.
  method: POST
  name: get-access-token
  path: /v1/token
- description: Register a new application.
  method: POST
  name: setup-application
  path: /v1/applications
- description: Push usage events for an application.
  method: POST
  name: publish-usage-events
  path: /v1/applications/{appId}/usage-events
- description: Push spend data for an application.
  method: POST
  name: publish-spend-data
  path: /v1/applications/{appId}/spend
- description: Add provisioned users.
  method: POST
  name: publish-provisioned-users
  path: /v1/applications/{appId}/users
- description: Retrieve provisioned users.
  method: GET
  name: get-provisioned-users
  path: /v1/applications/{appId}/users
- description: Remove provisioned users.
  method: DELETE
  name: delete-provisioned-users
  path: /v1/applications/{appId}/users
- description: Publish organizational chart data.
  method: PUT
  name: publish-org-chart
  path: /v1/org-chart
- description: Get signed upload URLs.
  method: GET
  name: get-batch-upload-urls
  path: /v1/applications/{appId}/upload
- description: Query all apps in portfolio.
  method: GET
  name: get-app-summaries
  path: /v1/app-summaries
- description: Fetch detailed app information.
  method: GET
  name: get-app-details
  path: /v1/app-details/{applicationId}
- description: List all provisioning workflows.
  method: GET
  name: list-provisioning-workflows
  path: /v1/provisioning-workflows
- description: List execution summaries.
  method: GET
  name: list-provisioning-execution-summaries
  path: /v1/provisioning-workflows/{workflowId}/executions
- description: Get specific execution details.
  method: GET
  name: get-provisioning-workflow-execution
  path: /v1/provisioning-workflows/{workflowId}/executions/{executionId}
- description: Fetch audit events.
  method: GET
  name: get-audit-events
  path: /v1/audit-events
personas: []
provider_name: Productiv
provider_slug: productiv
search_terms:
- fetch detailed information about a particular app.
- get audit events
- delete provisioned users
- register a new connected application.
- data export
- fetch detailed app information.
- query audit events.
- obtain an oauth2 access token using client credentials.
- publish usage events
- publish org chart
- push spend data for an application.
- get signed upload urls for batch file uploads.
- push usage events for an application.
- get app details
- push spend data.
- retrieve the list of users provisioned to an application.
- list provisioning execution summaries
- get provisioned users
- manage provisioned users.
- publish organizational chart data.
- publish spend data
- application portfolio
- push usage events.
- spend management
- list execution summaries.
- productiv
- add provisioned users.
- oauth2 token endpoint.
- get provisioning workflow execution
- fetch audit events.
- manage custom applications.
- remove provisioned users.
- manage provisioning workflows.
- manage org chart data.
- query all apps in portfolio.
- remove provisioned users from an application.
- list all provisioning workflows.
- get specific execution details.
- query all apps in your company portfolio.
- fetch detailed app info.
- fetch audit events for platform activities.
- get access token
- get batch upload urls
- usage analytics
- list provisioning workflow execution summaries.
- query provisioning executions.
- saas management
- retrieve provisioned users.
- provisioning
- publish provisioned users
- setup application
- get execution details.
- list provisioning workflows
- get details of a specific provisioning workflow execution.
- obtain an oauth2 access token.
- query app portfolio.
- get app summaries
- get signed upload urls.
- batch file upload.
- add provisioned users for an application.
- register a new application.
slug: saas-management
tags:
- Productiv
- SaaS Management
- Usage Analytics
- Provisioning
- Data Export
tools:
- description: Obtain an OAuth2 access token using client credentials.
  hints:
    idempotent: false
    readOnly: false
  name: get-access-token
- description: Register a new connected application.
  hints:
    idempotent: false
    readOnly: false
  name: setup-application
- description: Push usage events for an application.
  hints:
    idempotent: false
    readOnly: false
  name: publish-usage-events
- description: Push spend data for an application.
  hints:
    idempotent: false
    readOnly: false
  name: publish-spend-data
- description: Add provisioned users for an application.
  hints:
    idempotent: false
    readOnly: false
  name: publish-provisioned-users
- description: Retrieve the list of users provisioned to an application.
  hints:
    openWorld: true
    readOnly: true
  name: get-provisioned-users
- description: Remove provisioned users from an application.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-provisioned-users
- description: Publish organizational chart data.
  hints:
    idempotent: true
    readOnly: false
  name: publish-org-chart
- description: Get signed upload URLs for batch file uploads.
  hints:
    openWorld: true
    readOnly: true
  name: get-batch-upload-urls
- description: Query all apps in your company portfolio.
  hints:
    openWorld: true
    readOnly: true
  name: get-app-summaries
- description: Fetch detailed information about a particular app.
  hints:
    openWorld: true
    readOnly: true
  name: get-app-details
- description: List all provisioning workflows.
  hints:
    openWorld: true
    readOnly: true
  name: list-provisioning-workflows
- description: List provisioning workflow execution summaries.
  hints:
    openWorld: true
    readOnly: true
  name: list-provisioning-execution-summaries
- description: Get details of a specific provisioning workflow execution.
  hints:
    openWorld: true
    readOnly: true
  name: get-provisioning-workflow-execution
- description: Fetch audit events for platform activities.
  hints:
    openWorld: true
    readOnly: true
  name: get-audit-events
---
