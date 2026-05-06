---
categories: []
consumed_apis: []
description: Unified workflow capability for sales enablement workflows in Seismic — combining dynamic document generation, user management, analytics, and content delivery for sales reps, managers, and enablement teams.
layout: capability
name: Seismic Sales Enablement
operations:
- description: Generate a personalized LiveDoc.
  method: POST
  name: generate-livedoc
  path: /v1/documents/generate
- description: List LiveDoc templates.
  method: GET
  name: list-livedoc-templates
  path: /v1/documents/templates
- description: List generation jobs.
  method: GET
  name: list-generation-jobs
  path: /v1/documents/jobs
- description: List content items.
  method: GET
  name: list-content-items
  path: /v1/content
- description: Get user analytics.
  method: GET
  name: get-user-analytics
  path: /v1/analytics/users
- description: List reports.
  method: GET
  name: list-reports
  path: /v1/analytics/reports
- description: List users.
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Seismic
provider_slug: seismic
search_terms:
- list livedoc templates
- list livedoc templates.
- track document generation jobs.
- list generation jobs.
- browse available sales content in seismic.
- get sales rep adoption and usage analytics.
- get a shareable url for delivering content to prospects.
- reporting
- list available seismic analytics reports.
- list data sources
- manage users.
- analytics reports.
- generate livedoc
- get user analytics.
- generate a personalized sales document by merging data into a seismic livedoc template.
- search seismic content library.
- list reports
- get delivery analytics
- get livedoc template inputs
- browse sales content.
- get generation job
- list available document templates.
- check the status of an async livedoc generation job.
- get content url
- document generation
- get livedoc template
- search content
- generate personalized sales documents.
- list seismic platform users.
- list users.
- sales rep adoption analytics.
- list crm data sources available for livedoc generation.
- list users
- list content items
- get details of a specific livedoc template.
- seismic
- sales enablement
- get required input fields for a livedoc template.
- get analytics on content delivered to buyers.
- generate a personalized livedoc.
- list generation jobs
- list content items.
- livedocs
- list reports.
- list available livedoc templates for document generation.
- get user analytics
- user management
slug: sales-enablement
source_filename: sales-enablement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Seismic Sales Enablement\n  description: Unified workflow capability for sales enablement workflows in Seismic — combining dynamic document generation,\n    user management, analytics, and content delivery for sales reps, managers, and enablement teams.\n  tags:\n  - Seismic\n  - Sales Enablement\n  - Document Generation\n  - LiveDocs\n  - User Management\n  - Reporting\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SEISMIC_ACCESS_TOKEN: SEISMIC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: seismic-content\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic Content API for managing sales enablement content.\n    authentication:\n      type: bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: content-items\n      path: /content\n      description: Manage content items in the Seismic platform.\n      operations:\n    \
  \  - name: list-content-items\n        method: GET\n        description: Retrieve a list of content items.\n        inputParameters:\n        - name: folderId\n          in: query\n          type: string\n          required: false\n          description: Filter by folder ID.\n        - name: contentProfileId\n          in: query\n          type: string\n          required: false\n          description: Filter by content profile ID.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content-item\n\
  \        method: POST\n        description: Create a new content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            folderId: '{{tools.folderId}}'\n            description: '{{tools.description}}'\n    - name: content-item\n      path: /content/{contentId}\n      description: Manage a specific content item.\n      operations:\n      - name: get-content-item\n        method: GET\n        description: Retrieve details of a specific content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-content-item\n        method: PATCH\n\
  \        description: Update metadata of a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: delete-content-item\n        method: DELETE\n        description: Delete a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-url\n      path: /content/{contentId}/url\n      description:\
  \ Get a temporary URL for a content item.\n      operations:\n      - name: get-content-url\n        method: GET\n        description: Retrieve a temporary URL for accessing a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-versions\n      path: /content/{contentId}/versions\n      description: Manage content item versions.\n      operations:\n      - name: list-content-versions\n        method: GET\n        description: List versions of a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      description: Manage content folders.\n      operations:\n      - name: list-folders\n        method: GET\n        description: List content folders.\n        inputParameters:\n        - name: parentId\n          in: query\n          type: string\n          required: false\n          description: Filter by parent folder ID.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-folder\n        method: POST\n        description: Create a new content folder.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            parentId: '{{tools.parentId}}'\n    - name: search\n      path: /search\n      description: Search content in the Seismic platform.\n      operations:\n      - name: search-content\n        method: POST\n        description: Search for content items across the Seismic platform.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            offset: '{{tools.offset}}'\n            limit: '{{tools.limit}}'\n    - name: content-properties\n      path: /content-properties\n      description: Manage content property definitions.\n      operations:\n      - name: list-content-properties\n        method: GET\n        description: List content property definitions.\n\
  \        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-profiles\n      path: /content-profiles\n      description: Manage content profiles.\n      operations:\n      - name: list-content-profiles\n        method: GET\n        description: List content profiles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: seismic-livedocs\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic LiveDocs API for dynamic document generation.\n    authentication:\n      type:\
  \ bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: livedocs-generate\n      path: /livedocs/generate\n      description: Generate LiveDoc documents from templates.\n      operations:\n      - name: generate-livedoc\n        method: POST\n        description: Generate a LiveDoc by merging data into a template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            templateId: '{{tools.templateId}}'\n            name: '{{tools.name}}'\n            outputFormat: '{{tools.outputFormat}}'\n            inputs: '{{tools.inputs}}'\n            async: '{{tools.async}}'\n    - name: livedoc-templates\n      path: /livedocs/templates\n      description: Manage LiveDoc templates.\n      operations:\n      - name: list-livedoc-templates\n        method: GET\n        description: List available LiveDoc templates.\n        inputParameters:\n\
  \        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query to filter templates.\n        - name: outputFormat\n          in: query\n          type: string\n          required: false\n          description: Filter by supported output format.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: livedoc-template\n      path: /livedocs/templates/{templateId}\n      description: Manage a specific LiveDoc template.\n      operations:\n      - name: get-livedoc-template\n        method: GET\n        description: Retrieve details of a specific LiveDoc template.\n\
  \        inputParameters:\n        - name: templateId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: template-inputs\n      path: /livedocs/templates/{templateId}/inputs\n      description: Get input fields for a LiveDoc template.\n      operations:\n      - name: get-livedoc-template-inputs\n        method: GET\n        description: Retrieve input field definitions for a template.\n        inputParameters:\n        - name: templateId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generation-jobs\n      path: /livedocs/jobs\n      description: Manage\
  \ asynchronous LiveDoc generation jobs.\n      operations:\n      - name: list-generation-jobs\n        method: GET\n        description: List LiveDoc generation jobs and their statuses.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by job status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generation-job\n      path: /livedocs/jobs/{jobId}\n      description: Manage a specific generation job.\n      operations:\n      - name: get-generation-job\n        method: GET\n        description: Get the status and result of a generation job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the generation job.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: data-sources\n      path: /livedocs/datasources\n      description: Manage data sources for LiveDoc generation.\n      operations:\n      - name: list-data-sources\n        method: GET\n        description: List configured data sources for LiveDoc generation.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by data source type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: seismic-analytics\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic Analytics API for content and user engagement reporting.\n    authentication:\n      type: bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: content-analytics\n      path: /analytics/content\n      description: Analytics\
  \ on content usage and engagement.\n      operations:\n      - name: get-content-analytics\n        method: GET\n        description: Retrieve analytics data for content items.\n        inputParameters:\n        - name: contentId\n          in: query\n          type: string\n          required: false\n          description: Filter for a specific content item.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601).\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: 'Time granularity: daily, weekly, monthly.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-content\n      path: /analytics/content/top\n\
  \      description: Top-performing content analytics.\n      operations:\n      - name: get-top-content\n        method: GET\n        description: Retrieve ranked top-performing content.\n        inputParameters:\n        - name: metric\n          in: query\n          type: string\n          required: true\n          description: 'Metric to rank by: views, downloads, shares, engagement.'\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of top items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-analytics\n      path: /analytics/users\n     \
  \ description: Analytics on user activity and adoption.\n      operations:\n      - name: get-user-analytics\n        method: GET\n        description: Retrieve analytics data on user activity.\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          required: false\n          description: Filter for a specific user.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delivery-analytics\n      path: /analytics/deliveries\n      description: Analytics on content delivery to buyers.\n      operations:\n      - name: get-delivery-analytics\n        method: GET\n        description: Retrieve analytics\
  \ on content deliveries.\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          required: false\n          description: Filter by sender user ID.\n        - name: contentId\n          in: query\n          type: string\n          required: false\n          description: Filter by content item.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /analytics/reports\n      description: Analytical reports management.\n      operations:\n      - name: list-reports\n        method: GET\n        description: List available analytical reports.\n        inputParameters:\n      \
  \  - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by report type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report\n      path: /analytics/reports/{reportId}\n      description: Manage a specific report.\n      operations:\n      - name: get-report\n        method: GET\n        description: Retrieve a specific report with data.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the report.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for report period.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for report period.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-export\n      path: /analytics/reports/{reportId}/export\n      description: Export a report.\n      operations:\n      - name: export-report\n        method: POST\n        description: Initiate an export of a report.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            format: '{{tools.format}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n  - type: http\n    namespace: seismic-users\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic User Management API.\n    authentication:\n  \
  \    type: bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      description: Manage user accounts.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the Seismic platform.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        - name: groupId\n          in: query\n          type: string\n          required: false\n          description: Filter by group.\n        - name: roleId\n          in: query\n          type: string\n          required: false\n          description: Filter by role.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n       \
  \ - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            roleId: '{{tools.roleId}}'\n    - name: user\n      path: /users/{userId}\n      description: Manage a specific user.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get details of a specific user.\n        inputParameters:\n        - name: userId\n          in: path\n       \
  \   type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update a user's profile.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            status: '{{tools.status}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user account.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n\
  \          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage user groups.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List user groups.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new user group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: roles\n      path: /roles\n      description: Manage roles and permissions.\n      operations:\n      - name: list-roles\n        method: GET\n        description: List available roles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Manage team structures.\n      operations:\n      - name: list-teams\n        method: GET\n        description: List teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: seismic-sales-enablement-api\n    description: Unified REST API for Seismic sales enablement workflows.\n    resources:\n\
  \    - path: /v1/documents/generate\n      name: document-generation\n      description: Generate personalized sales documents.\n      operations:\n      - method: POST\n        name: generate-livedoc\n        description: Generate a personalized LiveDoc.\n        call: seismic-livedocs.generate-livedoc\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/templates\n      name: document-templates\n      description: List available document templates.\n      operations:\n      - method: GET\n        name: list-livedoc-templates\n        description: List LiveDoc templates.\n        call: seismic-livedocs.list-livedoc-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/jobs\n      name: generation-jobs\n      description: Track document generation jobs.\n      operations:\n      - method: GET\n        name: list-generation-jobs\n        description: List generation jobs.\n        call:\
  \ seismic-livedocs.list-generation-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content\n      name: content-items\n      description: Browse sales content.\n      operations:\n      - method: GET\n        name: list-content-items\n        description: List content items.\n        call: seismic-content.list-content-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/users\n      name: user-analytics\n      description: Sales rep adoption analytics.\n      operations:\n      - method: GET\n        name: get-user-analytics\n        description: Get user analytics.\n        call: seismic-analytics.get-user-analytics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/reports\n      name: reports\n      description: Analytics reports.\n      operations:\n      - method: GET\n        name: list-reports\n        description: List reports.\n\
  \        call: seismic-analytics.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Manage users.\n      operations:\n      - method: GET\n        name: list-users\n        description: List users.\n        call: seismic-users.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: seismic-sales-enablement-mcp\n    transport: http\n    description: MCP server for AI-assisted Seismic sales enablement.\n    tools:\n    - name: generate-livedoc\n      description: Generate a personalized sales document by merging data into a Seismic LiveDoc template.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: seismic-livedocs.generate-livedoc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-livedoc-templates\n      description: List available LiveDoc templates for\
  \ document generation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-livedocs.list-livedoc-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-livedoc-template\n      description: Get details of a specific LiveDoc template.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-livedocs.get-livedoc-template\n      with:\n        templateId: tools.templateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-livedoc-template-inputs\n      description: Get required input fields for a LiveDoc template.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-livedocs.get-livedoc-template-inputs\n      with:\n        templateId: tools.templateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-generation-job\n      description: Check the status of an async LiveDoc generation job.\n  \
  \    hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-livedocs.get-generation-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-content-items\n      description: Browse available sales content in Seismic.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-content.list-content-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-content\n      description: Search Seismic content library.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-content.search-content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-url\n      description: Get a shareable URL for delivering content to prospects.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-content.get-content-url\n      with:\n        contentId: tools.contentId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-analytics\n      description: Get sales rep adoption and usage analytics.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-analytics.get-user-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-delivery-analytics\n      description: Get analytics on content delivered to buyers.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-analytics.get-delivery-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available Seismic analytics reports.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-analytics.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List Seismic platform users.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: seismic-users.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-sources\n      description: List CRM data sources available for LiveDoc generation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-livedocs.list-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/seismic/refs/heads/main/capabilities/sales-enablement.yaml
tags:
- Seismic
- Sales Enablement
- Document Generation
- LiveDocs
- User Management
- Reporting
tools:
- description: Generate a personalized sales document by merging data into a Seismic LiveDoc template.
  hints:
    openWorld: false
    readOnly: false
  name: generate-livedoc
- description: List available LiveDoc templates for document generation.
  hints:
    openWorld: true
    readOnly: true
  name: list-livedoc-templates
- description: Get details of a specific LiveDoc template.
  hints:
    openWorld: false
    readOnly: true
  name: get-livedoc-template
- description: Get required input fields for a LiveDoc template.
  hints:
    openWorld: false
    readOnly: true
  name: get-livedoc-template-inputs
- description: Check the status of an async LiveDoc generation job.
  hints:
    openWorld: false
    readOnly: true
  name: get-generation-job
- description: Browse available sales content in Seismic.
  hints:
    openWorld: true
    readOnly: true
  name: list-content-items
- description: Search Seismic content library.
  hints:
    openWorld: true
    readOnly: true
  name: search-content
- description: Get a shareable URL for delivering content to prospects.
  hints:
    openWorld: false
    readOnly: true
  name: get-content-url
- description: Get sales rep adoption and usage analytics.
  hints:
    openWorld: true
    readOnly: true
  name: get-user-analytics
- description: Get analytics on content delivered to buyers.
  hints:
    openWorld: true
    readOnly: true
  name: get-delivery-analytics
- description: List available Seismic analytics reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: List Seismic platform users.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List CRM data sources available for LiveDoc generation.
  hints:
    openWorld: true
    readOnly: true
  name: list-data-sources
---
