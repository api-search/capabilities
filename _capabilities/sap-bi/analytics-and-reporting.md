---
categories: []
consumed_apis: []
description: Workflow capability for creating, managing, and distributing analytics content across SAP Analytics Cloud and SAP BusinessObjects BI Platform. Supports story authoring, report scheduling, and content governance. Used by BI developers, analysts, and report consumers.
layout: capability
name: SAP Business Intelligence Analytics and Reporting
operations:
- description: List analytics stories.
  method: GET
  name: list-stories
  path: /v1/stories
- description: Get a story by ID.
  method: GET
  name: get-story
  path: /v1/stories/{storyId}
- description: List analytics models.
  method: GET
  name: list-models
  path: /v1/models
- description: List BusinessObjects reports.
  method: GET
  name: list-reports
  path: /v1/reports
- description: List InfoStore content objects.
  method: GET
  name: list-content-objects
  path: /v1/content-objects
personas: []
provider_name: SAP Business Intelligence
provider_slug: sap-bi
search_terms:
- analytics
- list analytics stories.
- get a story by id.
- list analytics data models in sap analytics cloud.
- analytics stories and dashboards.
- list reports
- businessobjects reports.
- list analytics models.
- create story
- create a new analytics story in sap analytics cloud.
- sap
- business intelligence
- list content objects
- list infostore content objects.
- list businessobjects reports.
- analytics data models.
- single analytics story.
- browse content library
- bi platform infostore objects.
- list analytics stories in sap analytics cloud.
- browse content objects in the sap businessobjects infostore repository.
- list models
- get details of a specific analytics story.
- list stories
- get story
- list reports available in the sap businessobjects bi platform.
- reporting
- data visualization
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Business Intelligence Analytics and Reporting\n  description: Workflow capability for creating, managing, and distributing analytics content across SAP Analytics Cloud and\n    SAP BusinessObjects BI Platform. Supports story authoring, report scheduling, and content governance. Used by BI developers,\n    analysts, and report consumers.\n  tags:\n  - Analytics\n  - Business Intelligence\n  - Reporting\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_BI_OAUTH_TOKEN: SAP_BI_OAUTH_TOKEN\n    SAP_BOBJ_LOGON_TOKEN: SAP_BOBJ_LOGON_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-bi-analytics-cloud\n    baseUri: https://{tenant}.sapanalytics.cloud/api/v1\n    description: SAP Analytics Cloud REST API for managing stories, models, users, and folders.\n    authentication:\n      type: bearer\n      token: '{{SAP_BI_OAUTH_TOKEN}}'\n    resources:\n    - name: stories\n\
  \      path: /stories\n      description: Manage analytics stories and dashboards.\n      operations:\n      - name: list-stories\n        method: GET\n        description: List all analytics stories accessible to the user.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search stories by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-story\n        method: POST\n        description: Create a new analytics story.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-story\n        method: GET\n        description: Get details of a specific analytics story.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: The story identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      description: Manage data models and dimensions.\n      operations:\n      - name: list-models\n        method: GET\n        description: List all analytics models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model\n        method: GET\n        description: Get details of\
  \ a specific model.\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The model identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage users and teams.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the Analytics Cloud tenant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-bi-businessobjects\n    baseUri: https://{server}:{port}/biprws\n    description: SAP BusinessObjects BI Platform RESTful Web Services.\n    authentication:\n      type: apikey\n      key: X-SAP-LogonToken\n      value: '{{SAP_BOBJ_LOGON_TOKEN}}'\n      placement: header\n    resources:\n    - name: authentication\n\
  \      path: /logon/long\n      description: Authentication for session management.\n      operations:\n      - name: logon\n        method: POST\n        description: Authenticate and obtain a logon token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n            password: '{{tools.password}}'\n    - name: info-objects\n      path: /v1/infostore\n      description: Manage BI platform content objects.\n      operations:\n      - name: list-info-objects\n        method: GET\n        description: List content objects from the InfoStore.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-info-object\n        method: GET\n        description: Get a specific InfoStore object by ID.\n        inputParameters:\n        - name:\
  \ objectId\n          in: path\n          type: string\n          required: true\n          description: The CMS object identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v1/reports\n      description: Manage and schedule reports.\n      operations:\n      - name: list-reports\n        method: GET\n        description: List available reports in the BI Platform.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sap-bi-analytics-reporting-api\n    description: Unified REST API for SAP Business Intelligence analytics and reporting workflows.\n    resources:\n    - path: /v1/stories\n      name: stories\n      description: Analytics stories and dashboards.\n      operations:\n      - method: GET\n        name: list-stories\n        description:\
  \ List analytics stories.\n        call: sap-bi-analytics-cloud.list-stories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stories/{storyId}\n      name: story\n      description: Single analytics story.\n      operations:\n      - method: GET\n        name: get-story\n        description: Get a story by ID.\n        call: sap-bi-analytics-cloud.get-story\n        with:\n          storyId: rest.storyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Analytics data models.\n      operations:\n      - method: GET\n        name: list-models\n        description: List analytics models.\n        call: sap-bi-analytics-cloud.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: BusinessObjects reports.\n      operations:\n      - method: GET\n        name: list-reports\n\
  \        description: List BusinessObjects reports.\n        call: sap-bi-businessobjects.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content-objects\n      name: content-objects\n      description: BI Platform InfoStore objects.\n      operations:\n      - method: GET\n        name: list-content-objects\n        description: List InfoStore content objects.\n        call: sap-bi-businessobjects.list-info-objects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sap-bi-analytics-reporting-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP BI analytics and reporting.\n    tools:\n    - name: list-stories\n      description: List analytics stories in SAP Analytics Cloud.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-analytics-cloud.list-stories\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-story\n      description: Get details of a specific analytics story.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-bi-analytics-cloud.get-story\n      with:\n        storyId: tools.storyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-story\n      description: Create a new analytics story in SAP Analytics Cloud.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: sap-bi-analytics-cloud.create-story\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List analytics data models in SAP Analytics Cloud.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-analytics-cloud.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List reports available in the SAP BusinessObjects\
  \ BI Platform.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-businessobjects.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-content-library\n      description: Browse content objects in the SAP BusinessObjects InfoStore repository.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-businessobjects.list-info-objects\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- Analytics
- Business Intelligence
- Reporting
- SAP
tools:
- description: List analytics stories in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-stories
- description: Get details of a specific analytics story.
  hints:
    openWorld: false
    readOnly: true
  name: get-story
- description: Create a new analytics story in SAP Analytics Cloud.
  hints:
    openWorld: false
    readOnly: false
  name: create-story
- description: List analytics data models in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: List reports available in the SAP BusinessObjects BI Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Browse content objects in the SAP BusinessObjects InfoStore repository.
  hints:
    openWorld: true
    readOnly: true
  name: browse-content-library
---
