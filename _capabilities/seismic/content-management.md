---
categories: []
consumed_apis: []
description: Unified workflow capability for managing sales enablement content in Seismic — combining content management, folder organization, search, and analytics for content teams and sales managers.
layout: capability
name: Seismic Content Management
operations:
- description: List content items in Seismic.
  method: GET
  name: list-content-items
  path: /v1/content
- description: Upload and create a content item.
  method: POST
  name: create-content-item
  path: /v1/content
- description: Get a content item.
  method: GET
  name: get-content-item
  path: /v1/content/{contentId}
- description: Delete a content item.
  method: DELETE
  name: delete-content-item
  path: /v1/content/{contentId}
- description: Get a temporary shareable URL.
  method: GET
  name: get-content-url
  path: /v1/content/{contentId}/url
- description: List content folders.
  method: GET
  name: list-folders
  path: /v1/folders
- description: Create a content folder.
  method: POST
  name: create-folder
  path: /v1/folders
- description: Search content items.
  method: POST
  name: search-content
  path: /v1/search
- description: Get content analytics.
  method: GET
  name: get-content-analytics
  path: /v1/analytics/content
- description: Get top performing content.
  method: GET
  name: get-top-content
  path: /v1/analytics/top-content
personas: []
provider_name: Seismic
provider_slug: seismic
search_terms:
- get a shareable url for a content item.
- get content item
- analytics
- get a temporary shareable url.
- list folders
- delete content item
- manage a specific content item.
- get content analytics.
- get details of a specific content item by id.
- content management
- list content folders in seismic.
- delete a content item.
- get a content item.
- manage content items.
- list content items in seismic, optionally filtered by folder or search query.
- get top content
- list content folders.
- get content url
- search content items.
- list content items in seismic.
- top performing content.
- search content
- get analytics on content usage, views, downloads, and engagement.
- create a content folder.
- get a temporary shareable url for a content item.
- content usage analytics.
- search content.
- manage content folders.
- list content items
- search for content items using full-text search and filters.
- seismic
- sales enablement
- documents
- get content analytics
- get top performing content.
- get top-performing content ranked by views, downloads, shares, or engagement.
- create folder
- upload and create a content item.
- create content item
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Seismic Content Management\n  description: Unified workflow capability for managing sales enablement content in Seismic — combining content management,\n    folder organization, search, and analytics for content teams and sales managers.\n  tags:\n  - Seismic\n  - Content Management\n  - Sales Enablement\n  - Documents\n  - Analytics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SEISMIC_ACCESS_TOKEN: SEISMIC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: seismic-content\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic Content API for managing sales enablement content.\n    authentication:\n      type: bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: content-items\n      path: /content\n      description: Manage content items in the Seismic platform.\n      operations:\n      - name: list-content-items\n       \
  \ method: GET\n        description: Retrieve a list of content items.\n        inputParameters:\n        - name: folderId\n          in: query\n          type: string\n          required: false\n          description: Filter by folder ID.\n        - name: contentProfileId\n          in: query\n          type: string\n          required: false\n          description: Filter by content profile ID.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content-item\n        method: POST\n\
  \        description: Create a new content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            folderId: '{{tools.folderId}}'\n            description: '{{tools.description}}'\n    - name: content-item\n      path: /content/{contentId}\n      description: Manage a specific content item.\n      operations:\n      - name: get-content-item\n        method: GET\n        description: Retrieve details of a specific content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-content-item\n        method: PATCH\n        description:\
  \ Update metadata of a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: delete-content-item\n        method: DELETE\n        description: Delete a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-url\n      path: /content/{contentId}/url\n      description: Get a temporary\
  \ URL for a content item.\n      operations:\n      - name: get-content-url\n        method: GET\n        description: Retrieve a temporary URL for accessing a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-versions\n      path: /content/{contentId}/versions\n      description: Manage content item versions.\n      operations:\n      - name: list-content-versions\n        method: GET\n        description: List versions of a content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the content item.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      description: Manage content folders.\n      operations:\n      - name: list-folders\n        method: GET\n        description: List content folders.\n        inputParameters:\n        - name: parentId\n          in: query\n          type: string\n          required: false\n          description: Filter by parent folder ID.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-folder\n        method: POST\n        description: Create a new content folder.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            parentId: '{{tools.parentId}}'\n    - name: search\n      path: /search\n      description: Search content in the Seismic platform.\n      operations:\n      - name: search-content\n        method: POST\n        description: Search for content items across the Seismic platform.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            offset: '{{tools.offset}}'\n            limit: '{{tools.limit}}'\n    - name: content-properties\n      path: /content-properties\n      description: Manage content property definitions.\n      operations:\n      - name: list-content-properties\n        method: GET\n        description: List content property definitions.\n\
  \        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-profiles\n      path: /content-profiles\n      description: Manage content profiles.\n      operations:\n      - name: list-content-profiles\n        method: GET\n        description: List content profiles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: seismic-analytics\n    baseUri: https://api.seismic.com/integration/v2\n    description: Seismic Analytics API for content and user engagement reporting.\n    authentication:\n\
  \      type: bearer\n      token: '{{SEISMIC_ACCESS_TOKEN}}'\n    resources:\n    - name: content-analytics\n      path: /analytics/content\n      description: Analytics on content usage and engagement.\n      operations:\n      - name: get-content-analytics\n        method: GET\n        description: Retrieve analytics data for content items.\n        inputParameters:\n        - name: contentId\n          in: query\n          type: string\n          required: false\n          description: Filter for a specific content item.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601).\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: 'Time granularity: daily, weekly, monthly.'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-content\n      path: /analytics/content/top\n      description: Top-performing content analytics.\n      operations:\n      - name: get-top-content\n        method: GET\n        description: Retrieve ranked top-performing content.\n        inputParameters:\n        - name: metric\n          in: query\n          type: string\n          required: true\n          description: 'Metric to rank by: views, downloads, shares, engagement.'\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of top items to return.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-analytics\n      path: /analytics/users\n      description: Analytics on user activity and adoption.\n      operations:\n      - name: get-user-analytics\n        method: GET\n        description: Retrieve analytics data on user activity.\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          required: false\n          description: Filter for a specific user.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delivery-analytics\n      path: /analytics/deliveries\n      description:\
  \ Analytics on content delivery to buyers.\n      operations:\n      - name: get-delivery-analytics\n        method: GET\n        description: Retrieve analytics on content deliveries.\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          required: false\n          description: Filter by sender user ID.\n        - name: contentId\n          in: query\n          type: string\n          required: false\n          description: Filter by content item.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /analytics/reports\n      description: Analytical reports management.\n\
  \      operations:\n      - name: list-reports\n        method: GET\n        description: List available analytical reports.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by report type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report\n      path: /analytics/reports/{reportId}\n      description: Manage a specific report.\n      operations:\n      - name: get-report\n        method: GET\n        description: Retrieve a specific report with data.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the report.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for report period.\n        - name:\
  \ endDate\n          in: query\n          type: string\n          required: false\n          description: End date for report period.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-export\n      path: /analytics/reports/{reportId}/export\n      description: Export a report.\n      operations:\n      - name: export-report\n        method: POST\n        description: Initiate an export of a report.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            format: '{{tools.format}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: seismic-content-mgmt-api\n    description: Unified REST API for Seismic content management and analytics.\n    resources:\n    - path: /v1/content\n      name: content-items\n      description: Manage content items.\n      operations:\n      - method: GET\n        name: list-content-items\n        description: List content items in Seismic.\n        call: seismic-content.list-content-items\n        with:\n          folderId: rest.folderId\n          query: rest.query\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-content-item\n        description: Upload and create a content item.\n        call: seismic-content.create-content-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{contentId}\n      name: content-item\n      description: Manage a specific content\
  \ item.\n      operations:\n      - method: GET\n        name: get-content-item\n        description: Get a content item.\n        call: seismic-content.get-content-item\n        with:\n          contentId: rest.contentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-content-item\n        description: Delete a content item.\n        call: seismic-content.delete-content-item\n        with:\n          contentId: rest.contentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{contentId}/url\n      name: content-url\n      description: Get a shareable URL for a content item.\n      operations:\n      - method: GET\n        name: get-content-url\n        description: Get a temporary shareable URL.\n        call: seismic-content.get-content-url\n        with:\n          contentId: rest.contentId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/folders\n      name: folders\n      description: Manage content folders.\n      operations:\n      - method: GET\n        name: list-folders\n        description: List content folders.\n        call: seismic-content.list-folders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-folder\n        description: Create a content folder.\n        call: seismic-content.create-folder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Search content.\n      operations:\n      - method: POST\n        name: search-content\n        description: Search content items.\n        call: seismic-content.search-content\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/content\n      name: content-analytics\n      description: Content usage analytics.\n      operations:\n      - method: GET\n\
  \        name: get-content-analytics\n        description: Get content analytics.\n        call: seismic-analytics.get-content-analytics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/top-content\n      name: top-content\n      description: Top performing content.\n      operations:\n      - method: GET\n        name: get-top-content\n        description: Get top performing content.\n        call: seismic-analytics.get-top-content\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: seismic-content-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted Seismic content management.\n    tools:\n    - name: list-content-items\n      description: List content items in Seismic, optionally filtered by folder or search query.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-content.list-content-items\n      with:\n   \
  \     folderId: tools.folderId\n        query: tools.query\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-item\n      description: Get details of a specific content item by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-content.get-content-item\n      with:\n        contentId: tools.contentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-content\n      description: Search for content items using full-text search and filters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-content.search-content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-folders\n      description: List content folders in Seismic.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-content.list-folders\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-content-url\n      description: Get a temporary shareable URL for a content item.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seismic-content.get-content-url\n      with:\n        contentId: tools.contentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-analytics\n      description: Get analytics on content usage, views, downloads, and engagement.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-analytics.get-content-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-content\n      description: Get top-performing content ranked by views, downloads, shares, or engagement.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seismic-analytics.get-top-content\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/seismic/refs/heads/main/capabilities/content-management.yaml
tags:
- Seismic
- Content Management
- Sales Enablement
- Documents
- Analytics
tools:
- description: List content items in Seismic, optionally filtered by folder or search query.
  hints:
    openWorld: true
    readOnly: true
  name: list-content-items
- description: Get details of a specific content item by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-content-item
- description: Search for content items using full-text search and filters.
  hints:
    openWorld: true
    readOnly: true
  name: search-content
- description: List content folders in Seismic.
  hints:
    openWorld: true
    readOnly: true
  name: list-folders
- description: Get a temporary shareable URL for a content item.
  hints:
    openWorld: false
    readOnly: true
  name: get-content-url
- description: Get analytics on content usage, views, downloads, and engagement.
  hints:
    openWorld: true
    readOnly: true
  name: get-content-analytics
- description: Get top-performing content ranked by views, downloads, shares, or engagement.
  hints:
    openWorld: true
    readOnly: true
  name: get-top-content
---
