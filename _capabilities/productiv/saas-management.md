---
categories: []
consumed_apis: []
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
- obtain an oauth2 access token.
- get specific execution details.
- retrieve provisioned users.
- list provisioning workflow execution summaries.
- push spend data for an application.
- get signed upload urls.
- list provisioning workflows
- query app portfolio.
- push usage events for an application.
- query provisioning executions.
- remove provisioned users from an application.
- get signed upload urls for batch file uploads.
- publish usage events
- remove provisioned users.
- list all provisioning workflows.
- get provisioning workflow execution
- fetch detailed information about a particular app.
- get provisioned users
- fetch detailed app information.
- get access token
- saas management
- register a new application.
- list provisioning execution summaries
- register a new connected application.
- application portfolio
- get audit events
- get details of a specific provisioning workflow execution.
- push usage events.
- query all apps in your company portfolio.
- manage provisioning workflows.
- fetch audit events for platform activities.
- list execution summaries.
- add provisioned users for an application.
- oauth2 token endpoint.
- batch file upload.
- spend management
- usage analytics
- query all apps in portfolio.
- fetch audit events.
- obtain an oauth2 access token using client credentials.
- publish organizational chart data.
- setup application
- productiv
- data export
- delete provisioned users
- retrieve the list of users provisioned to an application.
- query audit events.
- fetch detailed app info.
- push spend data.
- provisioning
- publish org chart
- get batch upload urls
- get app details
- manage provisioned users.
- publish provisioned users
- manage custom applications.
- add provisioned users.
- get execution details.
- publish spend data
- manage org chart data.
- get app summaries
slug: saas-management
source_filename: saas-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Productiv SaaS Management\n  description: Unified workflow for managing SaaS applications, tracking usage and spend, provisioning users, and auditing\n    platform activity using the Productiv Developer API.\n  tags:\n  - Productiv\n  - SaaS Management\n  - Usage Analytics\n  - Provisioning\n  - Data Export\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PRODUCTIV_CLIENT_ID: PRODUCTIV_CLIENT_ID\n    PRODUCTIV_CLIENT_SECRET: PRODUCTIV_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: productiv-developer\n    baseUri: https://public-api.productiv.com\n    description: Productiv Developer API for SaaS management, usage analytics, and provisioning workflows.\n    authentication:\n      type: bearer\n      token: '{{PRODUCTIV_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /oauth2\n      description: OAuth2 authentication endpoints.\n      operations:\n\
  \      - name: get-access-token\n        method: POST\n        description: Obtain an OAuth2 access token using client credentials.\n        inputParameters:\n        - name: grant_type\n          in: body\n          type: string\n          required: true\n          description: The OAuth2 grant type.\n        - name: client_id\n          in: body\n          type: string\n          required: true\n          description: Your application client ID.\n        - name: client_secret\n          in: body\n          type: string\n          required: true\n          description: Your application client secret.\n        - name: scope\n          in: body\n          type: string\n          required: false\n          description: Space-separated list of scopes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            grant_type: '{{tools.grant_type}}'\n          \
  \  client_id: '{{tools.client_id}}'\n            client_secret: '{{tools.client_secret}}'\n            scope: '{{tools.scope}}'\n    - name: applications\n      path: /services/push/v1/customer/apps\n      description: Set up and manage custom applications within Productiv.\n      operations:\n      - name: setup-application\n        method: POST\n        description: Define and publish a new connected application to Productiv.\n        inputParameters:\n        - name: appName\n          in: body\n          type: string\n          required: true\n          description: The name of the application to register.\n        - name: appDescription\n          in: body\n          type: string\n          required: false\n          description: A description of the application.\n        - name: appCategory\n          in: body\n          type: string\n          required: false\n          description: The category of the application.\n        - name: appUrl\n          in: body\n          type: string\n\
  \          required: false\n          description: The URL of the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            appName: '{{tools.appName}}'\n            appDescription: '{{tools.appDescription}}'\n            appCategory: '{{tools.appCategory}}'\n            appUrl: '{{tools.appUrl}}'\n    - name: usage-events\n      path: /services/push/v1/customer/apps/{appId}/usage-events\n      description: Push usage events for applications.\n      operations:\n      - name: publish-usage-events\n        method: POST\n        description: Push usage events for an application to Productiv.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        - name: events\n          in: body\n          type: array\n\
  \          required: true\n          description: A list of usage events to push.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n    - name: spend-data\n      path: /services/push/v1/customer/apps/{appId}/spend\n      description: Push spend data for applications.\n      operations:\n      - name: publish-spend-data\n        method: POST\n        description: Push spend data to Productiv for an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        - name: spendData\n          in: body\n          type: array\n          required: true\n          description: A list of spend data records.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spendData: '{{tools.spendData}}'\n    - name: provisioned-users\n      path: /services/push/v1/customer/apps/{appId}/users\n      description: Manage users provisioned to custom integrations.\n      operations:\n      - name: publish-provisioned-users\n        method: POST\n        description: Add provisioned users for an application in Productiv.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        - name: users\n          in: body\n          type: array\n          required: true\n          description: A list of users to provision.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            users: '{{tools.users}}'\n\
  \      - name: get-provisioned-users\n        method: GET\n        description: Retrieve the list of users provisioned to an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-provisioned-users\n        method: DELETE\n        description: Remove provisioned users from an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        - name: users\n          in: body\n          type: array\n          required: true\n          description: A list of users to remove.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n        body:\n          type: json\n          data:\n            users: '{{tools.users}}'\n    - name: org-chart\n      path: /services/push/v1/customer/org-chart\n      description: Publish organizational chart data.\n      operations:\n      - name: publish-org-chart\n        method: PUT\n        description: Publish organizational chart data to Productiv.\n        inputParameters:\n        - name: users\n          in: body\n          type: array\n          required: true\n          description: A list of users in the org chart (max 1000).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            users: '{{tools.users}}'\n    - name: batch-upload\n      path: /services/push/v1/customer/apps/{appId}/upload\n      description: Upload files in batch for applications.\n      operations:\n      - name: get-batch-upload-urls\n\
  \        method: GET\n        description: Get signed upload URLs for batch file uploads.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        - name: filenames\n          in: query\n          type: array\n          required: true\n          description: The filenames to upload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-summaries\n      path: /services/export/v1/customer/app-summaries\n      description: Query the list of apps in your company portfolio.\n      operations:\n      - name: get-app-summaries\n        method: GET\n        description: Query the entire list of apps that are part of your company's portfolio.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: app-details\n      path: /services/export/v1/customer/app-details/{applicationId}\n      description: Fetch detailed information about a particular app.\n      operations:\n      - name: get-app-details\n        method: GET\n        description: Fetch detailed information about a particular app.\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provisioning-workflows\n      path: /services/export/v1/customer/provisioning-workflows\n      description: Fetch provisioning workflows and execution details.\n      operations:\n      - name: list-provisioning-workflows\n        method: GET\n        description: Query the entire list of provisioning workflows.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: list-provisioning-execution-summaries\n        method: GET\n        description: Query provisioning workflow execution summaries within a time range.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the provisioning workflow.\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start time for the time range filter.\n        - name: endTime\n          in: query\n          type: string\n          required: false\n          description: End time for the time range filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-provisioning-workflow-execution\n        method: GET\n        description: Query the details of a specific\
  \ provisioning workflow execution.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the provisioning workflow.\n        - name: executionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the execution.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audit-events\n      path: /services/export/v1/customer/audit-events\n      description: Fetch audit events for activities on the Productiv platform.\n      operations:\n      - name: get-audit-events\n        method: GET\n        description: Fetch a stream of audit events for activities performed by users.\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start\
  \ time for the query range.\n        - name: endTime\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        - name: nextPageToken\n          in: query\n          type: string\n          required: false\n          description: Token for fetching the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: productiv-saas-api\n    description: Unified REST API for Productiv SaaS management, usage analytics, and provisioning workflows.\n    resources:\n    - path: /v1/token\n      name: authentication\n      description: OAuth2 token endpoint.\n      operations:\n      - method: POST\n        name: get-access-token\n        description: Obtain an OAuth2 access token.\n        call: productiv-developer.get-access-token\n        with:\n          grant_type: rest.grant_type\n\
  \          client_id: rest.client_id\n          client_secret: rest.client_secret\n          scope: rest.scope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Manage custom applications.\n      operations:\n      - method: POST\n        name: setup-application\n        description: Register a new application.\n        call: productiv-developer.setup-application\n        with:\n          appName: rest.appName\n          appDescription: rest.appDescription\n          appCategory: rest.appCategory\n          appUrl: rest.appUrl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/usage-events\n      name: usage-events\n      description: Push usage events.\n      operations:\n      - method: POST\n        name: publish-usage-events\n        description: Push usage events for an application.\n        call: productiv-developer.publish-usage-events\n\
  \        with:\n          appId: rest.appId\n          events: rest.events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/spend\n      name: spend-data\n      description: Push spend data.\n      operations:\n      - method: POST\n        name: publish-spend-data\n        description: Push spend data for an application.\n        call: productiv-developer.publish-spend-data\n        with:\n          appId: rest.appId\n          spendData: rest.spendData\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/users\n      name: provisioned-users\n      description: Manage provisioned users.\n      operations:\n      - method: POST\n        name: publish-provisioned-users\n        description: Add provisioned users.\n        call: productiv-developer.publish-provisioned-users\n        with:\n          appId: rest.appId\n          users: rest.users\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: GET\n        name: get-provisioned-users\n        description: Retrieve provisioned users.\n        call: productiv-developer.get-provisioned-users\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-provisioned-users\n        description: Remove provisioned users.\n        call: productiv-developer.delete-provisioned-users\n        with:\n          appId: rest.appId\n          users: rest.users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/org-chart\n      name: org-chart\n      description: Manage org chart data.\n      operations:\n      - method: PUT\n        name: publish-org-chart\n        description: Publish organizational chart data.\n        call: productiv-developer.publish-org-chart\n        with:\n          users: rest.users\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/upload\n      name: batch-upload\n      description: Batch file upload.\n      operations:\n      - method: GET\n        name: get-batch-upload-urls\n        description: Get signed upload URLs.\n        call: productiv-developer.get-batch-upload-urls\n        with:\n          appId: rest.appId\n          filenames: rest.filenames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/app-summaries\n      name: app-summaries\n      description: Query app portfolio.\n      operations:\n      - method: GET\n        name: get-app-summaries\n        description: Query all apps in portfolio.\n        call: productiv-developer.get-app-summaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/app-details/{applicationId}\n      name: app-details\n      description: Fetch detailed app info.\n      operations:\n      - method: GET\n   \
  \     name: get-app-details\n        description: Fetch detailed app information.\n        call: productiv-developer.get-app-details\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning-workflows\n      name: provisioning-workflows\n      description: Manage provisioning workflows.\n      operations:\n      - method: GET\n        name: list-provisioning-workflows\n        description: List all provisioning workflows.\n        call: productiv-developer.list-provisioning-workflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning-workflows/{workflowId}/executions\n      name: provisioning-executions\n      description: Query provisioning executions.\n      operations:\n      - method: GET\n        name: list-provisioning-execution-summaries\n        description: List execution summaries.\n        call: productiv-developer.list-provisioning-execution-summaries\n\
  \        with:\n          workflowId: rest.workflowId\n          startTime: rest.startTime\n          endTime: rest.endTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning-workflows/{workflowId}/executions/{executionId}\n      name: provisioning-execution-detail\n      description: Get execution details.\n      operations:\n      - method: GET\n        name: get-provisioning-workflow-execution\n        description: Get specific execution details.\n        call: productiv-developer.get-provisioning-workflow-execution\n        with:\n          workflowId: rest.workflowId\n          executionId: rest.executionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit-events\n      name: audit-events\n      description: Query audit events.\n      operations:\n      - method: GET\n        name: get-audit-events\n        description: Fetch audit events.\n        call: productiv-developer.get-audit-events\n\
  \        with:\n          startTime: rest.startTime\n          endTime: rest.endTime\n          nextPageToken: rest.nextPageToken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: productiv-saas-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS management, usage analytics, and provisioning.\n    tools:\n    - name: get-access-token\n      description: Obtain an OAuth2 access token using client credentials.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: productiv-developer.get-access-token\n      with:\n        grant_type: tools.grant_type\n        client_id: tools.client_id\n        client_secret: tools.client_secret\n        scope: tools.scope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setup-application\n      description: Register a new connected application.\n      hints:\n        readOnly: false\n        idempotent: false\n\
  \      call: productiv-developer.setup-application\n      with:\n        appName: tools.appName\n        appDescription: tools.appDescription\n        appCategory: tools.appCategory\n        appUrl: tools.appUrl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-usage-events\n      description: Push usage events for an application.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: productiv-developer.publish-usage-events\n      with:\n        appId: tools.appId\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-spend-data\n      description: Push spend data for an application.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: productiv-developer.publish-spend-data\n      with:\n        appId: tools.appId\n        spendData: tools.spendData\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-provisioned-users\n\
  \      description: Add provisioned users for an application.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: productiv-developer.publish-provisioned-users\n      with:\n        appId: tools.appId\n        users: tools.users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-provisioned-users\n      description: Retrieve the list of users provisioned to an application.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-provisioned-users\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-provisioned-users\n      description: Remove provisioned users from an application.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: productiv-developer.delete-provisioned-users\n      with:\n        appId: tools.appId\n        users: tools.users\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: publish-org-chart\n      description: Publish organizational chart data.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: productiv-developer.publish-org-chart\n      with:\n        users: tools.users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-batch-upload-urls\n      description: Get signed upload URLs for batch file uploads.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-batch-upload-urls\n      with:\n        appId: tools.appId\n        filenames: tools.filenames\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-summaries\n      description: Query all apps in your company portfolio.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-app-summaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: get-app-details\n      description: Fetch detailed information about a particular app.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-app-details\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-provisioning-workflows\n      description: List all provisioning workflows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.list-provisioning-workflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-provisioning-execution-summaries\n      description: List provisioning workflow execution summaries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.list-provisioning-execution-summaries\n      with:\n        workflowId: tools.workflowId\n        startTime: tools.startTime\n        endTime: tools.endTime\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-provisioning-workflow-execution\n      description: Get details of a specific provisioning workflow execution.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-provisioning-workflow-execution\n      with:\n        workflowId: tools.workflowId\n        executionId: tools.executionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-audit-events\n      description: Fetch audit events for platform activities.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: productiv-developer.get-audit-events\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        nextPageToken: tools.nextPageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
