---
categories: []
consumed_apis: []
description: Unified workflow capability for managing analytics content across SAP Analytics Cloud, including story lifecycle management, content network publishing, and file repository governance. Used by BI administrators and content authors.
layout: capability
name: SAP BI Tools Analytics Content Management
operations:
- description: List all analytics stories on the tenant.
  method: GET
  name: list-stories
  path: /v1/stories
- description: Get a story by ID.
  method: GET
  name: get-story
  path: /v1/stories/{storyId}
- description: List repository resources (stories, models, folders).
  method: GET
  name: list-resources
  path: /v1/resources
- description: List Content Network items.
  method: GET
  name: list-content-items
  path: /v1/content-items
- description: Get a content item by ID.
  method: GET
  name: get-content-item
  path: /v1/content-items/{itemId}
- description: List calendar events and planning tasks.
  method: GET
  name: list-calendars
  path: /v1/calendars
personas: []
provider_name: SAP BI Tools
provider_slug: sap-bi-tools
search_terms:
- single analytics story.
- list content network items.
- import content item
- get content item
- reporting
- list all analytics stories on the sap analytics cloud tenant.
- analytics
- list repository resources (stories, models, folders).
- get story
- single content network item.
- list file repository resources (stories, models, folders).
- planning calendars.
- publish content item
- list content items in the sap analytics cloud content network.
- list planning calendar events and collaborative tasks.
- content management
- publish a local analytics artifact to the content network for sharing.
- data visualization
- list resources
- analytics story management.
- get details of a specific analytics story by id.
- list stories
- import a content package from the content network into the local tenant.
- file repository resources.
- sap
- list calendars
- get a content item by id.
- content network items.
- business intelligence
- list calendar events and planning tasks.
- list content items
- get a story by id.
- list all analytics stories on the tenant.
slug: analytics-content-management
source_filename: analytics-content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP BI Tools Analytics Content Management\n  description: Unified workflow capability for managing analytics content across SAP Analytics Cloud, including story lifecycle\n    management, content network publishing, and file repository governance. Used by BI administrators and content authors.\n  tags:\n  - Analytics\n  - Business Intelligence\n  - Content Management\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_AC_OAUTH_TOKEN: SAP_AC_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: analytics-cloud\n    baseUri: https://{tenant}.{datacenter}.sapanalytics.cloud\n    description: SAP Analytics Cloud REST API for managing stories, resources, users, and teams.\n    authentication:\n      type: bearer\n      token: '{{SAP_AC_OAUTH_TOKEN}}'\n    resources:\n    - name: stories\n      path: /api/v1/stories\n      description: Manage analytic stories including dashboards\
  \ and reports.\n      operations:\n      - name: list-stories\n        method: GET\n        description: List all stories available on the SAP Analytics Cloud tenant.\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Comma-separated related resources to include (e.g., models)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-story\n        method: GET\n        description: Get a story by its unique ID.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the story\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Comma-separated related resources to include\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /api/v1/Resources\n      description: Browse and manage resources in the SAP Analytics Cloud file repository.\n      operations:\n      - name: list-resources\n        method: GET\n        description: List resources including stories, models, and folders.\n        inputParameters:\n        - name: resourceType\n          in: query\n          type: string\n          required: false\n          description: Filter by resource type (STORY, MODEL, FOLDER)\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value:\
  \ $.\n    - name: users\n      path: /api/v1/scim2/Users\n      description: SCIM 2.0 endpoints for managing user accounts.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users using SCIM 2.0 protocol.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM 2.0 filter expression\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user using SCIM 2.0 protocol.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n          \
  \  userName: '{{tools.userName}}'\n            displayName: '{{tools.displayName}}'\n      - name: get-user\n        method: GET\n        description: Get a user by ID using SCIM 2.0.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user record using SCIM 2.0.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n\
  \      - name: delete-user\n        method: DELETE\n        description: Delete a user from SAP Analytics Cloud.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /api/v1/scim2/Groups\n      description: SCIM 2.0 endpoints for managing teams and group memberships.\n      operations:\n      - name: list-teams\n        method: GET\n        description: List teams using SCIM 2.0 protocol.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM 2.0 filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n\
  \        method: POST\n        description: Create a new team using SCIM 2.0 protocol.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n    - name: calendars\n      path: /api/v1/calendars\n      description: Manage calendar events and tasks for planning workflows.\n      operations:\n      - name: list-calendars\n        method: GET\n        description: List calendar events and planning tasks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: analytics-cloud-content-network\n    baseUri: https://{tenant}.{datacenter}.sapanalytics.cloud\n    description: SAP Analytics Cloud Content Network REST API for sharing and importing content packages.\n    authentication:\n      type: bearer\n      token: '{{SAP_AC_OAUTH_TOKEN}}'\n\
  \    resources:\n    - name: content-items\n      path: /api/v1/contentnetwork/items\n      description: Content items in the Content Network.\n      operations:\n      - name: list-content-items\n        method: GET\n        description: List content items available in the Content Network.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by content item type\n        - name: visibility\n          in: query\n          type: string\n          required: false\n          description: Filter by visibility (PRIVATE or PUBLIC)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: publish-content-item\n        method: POST\n        description: Publish a content item to the Content Network.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            resourceId: '{{tools.resourceId}}'\n            visibility: '{{tools.visibility}}'\n      - name: get-content-item\n        method: GET\n        description: Get a content item by its unique ID.\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the content item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-content-item\n        method: DELETE\n        description: Delete a content item from the Content Network.\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the content item\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: import-content-item\n        method: POST\n        description: Import a content item from the Content Network into the local tenant.\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the content item to import\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetFolderId: '{{tools.targetFolderId}}'\n            overwrite: '{{tools.overwrite}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: analytics-content-management-api\n    description: Unified REST API for SAP Analytics Cloud content lifecycle management.\n    resources:\n    - path: /v1/stories\n      name: stories\n      description: Analytics story management.\n      operations:\n\
  \      - method: GET\n        name: list-stories\n        description: List all analytics stories on the tenant.\n        call: analytics-cloud.list-stories\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/stories/{storyId}\n      name: story\n      description: Single analytics story.\n      operations:\n      - method: GET\n        name: get-story\n        description: Get a story by ID.\n        call: analytics-cloud.get-story\n        with:\n          storyId: rest.storyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resources\n      name: resources\n      description: File repository resources.\n      operations:\n      - method: GET\n        name: list-resources\n        description: List repository resources (stories, models, folders).\n        call: analytics-cloud.list-resources\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/content-items\n      name:\
  \ content-items\n      description: Content Network items.\n      operations:\n      - method: GET\n        name: list-content-items\n        description: List Content Network items.\n        call: analytics-cloud-content-network.list-content-items\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/content-items/{itemId}\n      name: content-item\n      description: Single Content Network item.\n      operations:\n      - method: GET\n        name: get-content-item\n        description: Get a content item by ID.\n        call: analytics-cloud-content-network.get-content-item\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calendars\n      name: calendars\n      description: Planning calendars.\n      operations:\n      - method: GET\n        name: list-calendars\n        description: List calendar events and planning tasks.\n        call: analytics-cloud.list-calendars\n\
  \        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: analytics-content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP Analytics Cloud content management.\n    tools:\n    - name: list-stories\n      description: List all analytics stories on the SAP Analytics Cloud tenant.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-cloud.list-stories\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-story\n      description: Get details of a specific analytics story by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: analytics-cloud.get-story\n      with:\n        storyId: tools.storyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-resources\n      description: List file repository resources (stories, models, folders).\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: analytics-cloud.list-resources\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-content-items\n      description: List content items in the SAP Analytics Cloud Content Network.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-cloud-content-network.list-content-items\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: publish-content-item\n      description: Publish a local analytics artifact to the Content Network for sharing.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: analytics-cloud-content-network.publish-content-item\n      with:\n        name: tools.name\n        resourceId: tools.resourceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-content-item\n      description: Import a content package from the Content Network into the local tenant.\n      hints:\n        readOnly:\
  \ false\n        openWorld: false\n      call: analytics-cloud-content-network.import-content-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-calendars\n      description: List planning calendar events and collaborative tasks.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-cloud.list-calendars\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi-tools/refs/heads/main/capabilities/analytics-content-management.yaml
tags:
- Analytics
- Business Intelligence
- Content Management
- SAP
tools:
- description: List all analytics stories on the SAP Analytics Cloud tenant.
  hints:
    openWorld: true
    readOnly: true
  name: list-stories
- description: Get details of a specific analytics story by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-story
- description: List file repository resources (stories, models, folders).
  hints:
    openWorld: true
    readOnly: true
  name: list-resources
- description: List content items in the SAP Analytics Cloud Content Network.
  hints:
    openWorld: true
    readOnly: true
  name: list-content-items
- description: Publish a local analytics artifact to the Content Network for sharing.
  hints:
    openWorld: false
    readOnly: false
  name: publish-content-item
- description: Import a content package from the Content Network into the local tenant.
  hints:
    openWorld: false
    readOnly: false
  name: import-content-item
- description: List planning calendar events and collaborative tasks.
  hints:
    openWorld: true
    readOnly: true
  name: list-calendars
---
