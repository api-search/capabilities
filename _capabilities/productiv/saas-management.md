---
categories: []
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
- manage provisioned users.
- get provisioned users
- fetch audit events.
- obtain an oauth2 access token.
- retrieve provisioned users.
- get app details
- usage analytics
- publish organizational chart data.
- publish spend data
- get execution details.
- retrieve the list of users provisioned to an application.
- oauth2 token endpoint.
- add provisioned users.
- list execution summaries.
- push usage events.
- list provisioning workflow execution summaries.
- push spend data.
- get signed upload urls.
- get app summaries
- fetch detailed information about a particular app.
- productiv
- push spend data for an application.
- push usage events for an application.
- manage provisioning workflows.
- get audit events
- publish org chart
- batch file upload.
- register a new connected application.
- fetch detailed app information.
- obtain an oauth2 access token using client credentials.
- list all provisioning workflows.
- manage org chart data.
- fetch detailed app info.
- get provisioning workflow execution
- setup application
- saas management
- provisioning
- remove provisioned users.
- get access token
- fetch audit events for platform activities.
- publish usage events
- remove provisioned users from an application.
- application portfolio
- list provisioning execution summaries
- query app portfolio.
- get batch upload urls
- delete provisioned users
- spend management
- list provisioning workflows
- get details of a specific provisioning workflow execution.
- register a new application.
- data export
- add provisioned users for an application.
- query all apps in your company portfolio.
- manage custom applications.
- query provisioning executions.
- get signed upload urls for batch file uploads.
- query audit events.
- query all apps in portfolio.
- publish provisioned users
- get specific execution details.
slug: saas-management
source_filename: saas-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Productiv SaaS Management\"\n  description: \"Unified workflow for managing SaaS applications, tracking usage and spend, provisioning users, and auditing platform activity using the Productiv Developer API.\"\n  tags:\n    - Productiv\n    - SaaS Management\n    - Usage Analytics\n    - Provisioning\n    - Data Export\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PRODUCTIV_CLIENT_ID: PRODUCTIV_CLIENT_ID\n      PRODUCTIV_CLIENT_SECRET: PRODUCTIV_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: productiv-developer\n      location: ./shared/developer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: productiv-saas-api\n      description: \"Unified REST API for Productiv SaaS management, usage analytics, and provisioning workflows.\"\n      resources:\n        - path: /v1/token\n          name: authentication\n          description: \"OAuth2\
  \ token endpoint.\"\n          operations:\n            - method: POST\n              name: get-access-token\n              description: \"Obtain an OAuth2 access token.\"\n              call: \"productiv-developer.get-access-token\"\n              with:\n                grant_type: \"rest.grant_type\"\n                client_id: \"rest.client_id\"\n                client_secret: \"rest.client_secret\"\n                scope: \"rest.scope\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications\n          name: applications\n          description: \"Manage custom applications.\"\n          operations:\n            - method: POST\n              name: setup-application\n              description: \"Register a new application.\"\n              call: \"productiv-developer.setup-application\"\n              with:\n                appName: \"rest.appName\"\n                appDescription: \"rest.appDescription\"\
  \n                appCategory: \"rest.appCategory\"\n                appUrl: \"rest.appUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/usage-events\n          name: usage-events\n          description: \"Push usage events.\"\n          operations:\n            - method: POST\n              name: publish-usage-events\n              description: \"Push usage events for an application.\"\n              call: \"productiv-developer.publish-usage-events\"\n              with:\n                appId: \"rest.appId\"\n                events: \"rest.events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/spend\n          name: spend-data\n          description: \"Push spend data.\"\n          operations:\n            - method: POST\n              name: publish-spend-data\n              description: \"\
  Push spend data for an application.\"\n              call: \"productiv-developer.publish-spend-data\"\n              with:\n                appId: \"rest.appId\"\n                spendData: \"rest.spendData\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/users\n          name: provisioned-users\n          description: \"Manage provisioned users.\"\n          operations:\n            - method: POST\n              name: publish-provisioned-users\n              description: \"Add provisioned users.\"\n              call: \"productiv-developer.publish-provisioned-users\"\n              with:\n                appId: \"rest.appId\"\n                users: \"rest.users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-provisioned-users\n              description: \"Retrieve provisioned users.\"\
  \n              call: \"productiv-developer.get-provisioned-users\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-provisioned-users\n              description: \"Remove provisioned users.\"\n              call: \"productiv-developer.delete-provisioned-users\"\n              with:\n                appId: \"rest.appId\"\n                users: \"rest.users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/org-chart\n          name: org-chart\n          description: \"Manage org chart data.\"\n          operations:\n            - method: PUT\n              name: publish-org-chart\n              description: \"Publish organizational chart data.\"\n              call: \"productiv-developer.publish-org-chart\"\n              with:\n                users:\
  \ \"rest.users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{appId}/upload\n          name: batch-upload\n          description: \"Batch file upload.\"\n          operations:\n            - method: GET\n              name: get-batch-upload-urls\n              description: \"Get signed upload URLs.\"\n              call: \"productiv-developer.get-batch-upload-urls\"\n              with:\n                appId: \"rest.appId\"\n                filenames: \"rest.filenames\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/app-summaries\n          name: app-summaries\n          description: \"Query app portfolio.\"\n          operations:\n            - method: GET\n              name: get-app-summaries\n              description: \"Query all apps in portfolio.\"\n              call: \"productiv-developer.get-app-summaries\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/app-details/{applicationId}\n          name: app-details\n          description: \"Fetch detailed app info.\"\n          operations:\n            - method: GET\n              name: get-app-details\n              description: \"Fetch detailed app information.\"\n              call: \"productiv-developer.get-app-details\"\n              with:\n                applicationId: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/provisioning-workflows\n          name: provisioning-workflows\n          description: \"Manage provisioning workflows.\"\n          operations:\n            - method: GET\n              name: list-provisioning-workflows\n              description: \"List all provisioning workflows.\"\n              call: \"productiv-developer.list-provisioning-workflows\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/provisioning-workflows/{workflowId}/executions\n          name: provisioning-executions\n          description: \"Query provisioning executions.\"\n          operations:\n            - method: GET\n              name: list-provisioning-execution-summaries\n              description: \"List execution summaries.\"\n              call: \"productiv-developer.list-provisioning-execution-summaries\"\n              with:\n                workflowId: \"rest.workflowId\"\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/provisioning-workflows/{workflowId}/executions/{executionId}\n          name: provisioning-execution-detail\n          description: \"Get execution details.\"\n          operations:\n            -\
  \ method: GET\n              name: get-provisioning-workflow-execution\n              description: \"Get specific execution details.\"\n              call: \"productiv-developer.get-provisioning-workflow-execution\"\n              with:\n                workflowId: \"rest.workflowId\"\n                executionId: \"rest.executionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audit-events\n          name: audit-events\n          description: \"Query audit events.\"\n          operations:\n            - method: GET\n              name: get-audit-events\n              description: \"Fetch audit events.\"\n              call: \"productiv-developer.get-audit-events\"\n              with:\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n                nextPageToken: \"rest.nextPageToken\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: productiv-saas-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SaaS management, usage analytics, and provisioning.\"\n      tools:\n        - name: get-access-token\n          description: \"Obtain an OAuth2 access token using client credentials.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"productiv-developer.get-access-token\"\n          with:\n            grant_type: \"tools.grant_type\"\n            client_id: \"tools.client_id\"\n            client_secret: \"tools.client_secret\"\n            scope: \"tools.scope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: setup-application\n          description: \"Register a new connected application.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"productiv-developer.setup-application\"\
  \n          with:\n            appName: \"tools.appName\"\n            appDescription: \"tools.appDescription\"\n            appCategory: \"tools.appCategory\"\n            appUrl: \"tools.appUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-usage-events\n          description: \"Push usage events for an application.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"productiv-developer.publish-usage-events\"\n          with:\n            appId: \"tools.appId\"\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-spend-data\n          description: \"Push spend data for an application.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"productiv-developer.publish-spend-data\"\n          with:\n            appId: \"tools.appId\"\
  \n            spendData: \"tools.spendData\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-provisioned-users\n          description: \"Add provisioned users for an application.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"productiv-developer.publish-provisioned-users\"\n          with:\n            appId: \"tools.appId\"\n            users: \"tools.users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-provisioned-users\n          description: \"Retrieve the list of users provisioned to an application.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.get-provisioned-users\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-provisioned-users\n\
  \          description: \"Remove provisioned users from an application.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"productiv-developer.delete-provisioned-users\"\n          with:\n            appId: \"tools.appId\"\n            users: \"tools.users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-org-chart\n          description: \"Publish organizational chart data.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"productiv-developer.publish-org-chart\"\n          with:\n            users: \"tools.users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-batch-upload-urls\n          description: \"Get signed upload URLs for batch file uploads.\"\n          hints:\n            readOnly: true\n            openWorld: true\n     \
  \     call: \"productiv-developer.get-batch-upload-urls\"\n          with:\n            appId: \"tools.appId\"\n            filenames: \"tools.filenames\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-app-summaries\n          description: \"Query all apps in your company portfolio.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.get-app-summaries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-app-details\n          description: \"Fetch detailed information about a particular app.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.get-app-details\"\n          with:\n            applicationId: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-provisioning-workflows\n\
  \          description: \"List all provisioning workflows.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.list-provisioning-workflows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-provisioning-execution-summaries\n          description: \"List provisioning workflow execution summaries.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.list-provisioning-execution-summaries\"\n          with:\n            workflowId: \"tools.workflowId\"\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-provisioning-workflow-execution\n          description: \"Get details of a specific provisioning workflow execution.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"productiv-developer.get-provisioning-workflow-execution\"\n          with:\n            workflowId: \"tools.workflowId\"\n            executionId: \"tools.executionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-audit-events\n          description: \"Fetch audit events for platform activities.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"productiv-developer.get-audit-events\"\n          with:\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n            nextPageToken: \"tools.nextPageToken\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/productiv/refs/heads/main/capabilities/saas-management.yaml
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
