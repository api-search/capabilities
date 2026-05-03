---
categories: []
consumed_apis:
- seismic-content
- seismic-analytics
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
- list folders
- create a content folder.
- list content items in seismic.
- manage content items.
- analytics
- get content analytics
- content management
- search content items.
- list content items in seismic, optionally filtered by folder or search query.
- documents
- delete a content item.
- create content item
- content usage analytics.
- manage content folders.
- get analytics on content usage, views, downloads, and engagement.
- get top-performing content ranked by views, downloads, shares, or engagement.
- top performing content.
- get a content item.
- get a temporary shareable url.
- get top performing content.
- get a shareable url for a content item.
- get content analytics.
- list content folders.
- upload and create a content item.
- get top content
- list content folders in seismic.
- create folder
- list content items
- search for content items using full-text search and filters.
- get content url
- sales enablement
- search content
- get details of a specific content item by id.
- get a temporary shareable url for a content item.
- get content item
- seismic
- manage a specific content item.
- search content.
- delete content item
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Seismic Content Management\"\n  description: \"Unified workflow capability for managing sales enablement content in Seismic — combining content management, folder organization, search, and analytics for content teams and sales managers.\"\n  tags:\n    - Seismic\n    - Content Management\n    - Sales Enablement\n    - Documents\n    - Analytics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEISMIC_ACCESS_TOKEN: SEISMIC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: seismic-content\n      location: ./shared/content-api.yaml\n    - import: seismic-analytics\n      location: ./shared/analytics-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: seismic-content-mgmt-api\n      description: \"Unified REST API for Seismic content management and analytics.\"\n      resources:\n        - path: /v1/content\n          name: content-items\n        \
  \  description: \"Manage content items.\"\n          operations:\n            - method: GET\n              name: list-content-items\n              description: \"List content items in Seismic.\"\n              call: \"seismic-content.list-content-items\"\n              with:\n                folderId: \"rest.folderId\"\n                query: \"rest.query\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-content-item\n              description: \"Upload and create a content item.\"\n              call: \"seismic-content.create-content-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/{contentId}\n          name: content-item\n          description: \"Manage a specific content item.\"\n          operations:\n        \
  \    - method: GET\n              name: get-content-item\n              description: \"Get a content item.\"\n              call: \"seismic-content.get-content-item\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-content-item\n              description: \"Delete a content item.\"\n              call: \"seismic-content.delete-content-item\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/{contentId}/url\n          name: content-url\n          description: \"Get a shareable URL for a content item.\"\n          operations:\n            - method: GET\n              name: get-content-url\n              description: \"Get a temporary shareable URL.\"\n              call:\
  \ \"seismic-content.get-content-url\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/folders\n          name: folders\n          description: \"Manage content folders.\"\n          operations:\n            - method: GET\n              name: list-folders\n              description: \"List content folders.\"\n              call: \"seismic-content.list-folders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-folder\n              description: \"Create a content folder.\"\n              call: \"seismic-content.create-folder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Search content.\"\n          operations:\n\
  \            - method: POST\n              name: search-content\n              description: \"Search content items.\"\n              call: \"seismic-content.search-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics/content\n          name: content-analytics\n          description: \"Content usage analytics.\"\n          operations:\n            - method: GET\n              name: get-content-analytics\n              description: \"Get content analytics.\"\n              call: \"seismic-analytics.get-content-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics/top-content\n          name: top-content\n          description: \"Top performing content.\"\n          operations:\n            - method: GET\n              name: get-top-content\n              description: \"Get top performing content.\"\n             \
  \ call: \"seismic-analytics.get-top-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: seismic-content-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Seismic content management.\"\n      tools:\n        - name: list-content-items\n          description: \"List content items in Seismic, optionally filtered by folder or search query.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-content.list-content-items\"\n          with:\n            folderId: \"tools.folderId\"\n            query: \"tools.query\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-content-item\n          description: \"Get details of a specific content item by ID.\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"seismic-content.get-content-item\"\n          with:\n            contentId: \"tools.contentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-content\n          description: \"Search for content items using full-text search and filters.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-content.search-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-folders\n          description: \"List content folders in Seismic.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-content.list-folders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-content-url\n          description: \"Get a temporary shareable URL for a content\
  \ item.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seismic-content.get-content-url\"\n          with:\n            contentId: \"tools.contentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-content-analytics\n          description: \"Get analytics on content usage, views, downloads, and engagement.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-analytics.get-content-analytics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-content\n          description: \"Get top-performing content ranked by views, downloads, shares, or engagement.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-analytics.get-top-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n"
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
