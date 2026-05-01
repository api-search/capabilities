---
categories:
- content-management
consumed_apis:
- sp-sites-lists
- sp-files-search
description: Unified workflow for managing SharePoint content including sites, lists, items, files, and search. Used by content managers, site admins, and collaboration teams.
layout: capability
name: SharePoint Content Management
operations:
- description: ''
  method: GET
  name: get-web
  path: /v1/sites
- description: ''
  method: GET
  name: get-lists
  path: /v1/lists
- description: ''
  method: POST
  name: create-list
  path: /v1/lists
- description: ''
  method: GET
  name: get-list-items
  path: /v1/lists/{title}/items
- description: ''
  method: POST
  name: create-list-item
  path: /v1/lists/{title}/items
- description: ''
  method: GET
  name: get-files
  path: /v1/files
- description: ''
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: Microsoft SharePoint
provider_slug: sharepoint
search_terms:
- list all sharepoint lists
- get my user profile
- get web
- upload a file to sharepoint
- get lists
- delete list item
- search query
- document management
- create list
- get current user's sharepoint profile
- enterprise content management
- content management
- delete a sharepoint list item
- update list item
- get items from a sharepoint list
- create a new sharepoint list
- get files
- list files in a sharepoint folder
- get list items
- collaboration
- intranet
- download a file from sharepoint
- search
- sharepoint
- create list item
- add an item to a sharepoint list
- upload file
- download file
- search across all sharepoint content
- get files in folder
- microsoft
- update a sharepoint list item
- get sharepoint site properties
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SharePoint Content Management\"\n  description: \"Unified workflow for managing SharePoint content including sites, lists, items, files, and search. Used by content managers, site admins, and collaboration teams.\"\n  tags:\n    - SharePoint\n    - Content Management\n    - Collaboration\n    - Document Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHAREPOINT_ACCESS_TOKEN: SHAREPOINT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: sp-sites-lists\n      location: ./shared/sites-and-lists.yaml\n    - import: sp-files-search\n      location: ./shared/files-and-search.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sp-content-api\n      description: \"Unified REST API for SharePoint content management.\"\n      resources:\n        - path: /v1/sites\n          name: sites\n          operations:\n            - method: GET\n          \
  \    name: get-web\n              call: \"sp-sites-lists.get-web\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lists\n          name: lists\n          operations:\n            - method: GET\n              name: get-lists\n              call: \"sp-sites-lists.get-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-list\n              call: \"sp-sites-lists.create-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lists/{title}/items\n          name: items\n          operations:\n            - method: GET\n              name: get-list-items\n              call: \"sp-sites-lists.get-list-items\"\n              with:\n                list_title: \"rest.title\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n            - method: POST\n              name: create-list-item\n              call: \"sp-sites-lists.create-list-item\"\n              with:\n                list_title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/files\n          name: files\n          operations:\n            - method: GET\n              name: get-files\n              call: \"sp-files-search.get-files-in-folder\"\n              with:\n                folder_url: \"rest.folder_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          operations:\n            - method: GET\n              name: search\n              call: \"sp-files-search.search-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n\
  \      namespace: sp-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SharePoint content management.\"\n      tools:\n        - name: get-web\n          description: \"Get SharePoint site properties\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-sites-lists.get-web\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lists\n          description: \"List all SharePoint lists\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-sites-lists.get-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-list\n          description: \"Create a new SharePoint list\"\n          hints: {readOnly: false, idempotent: false}\n          call: \"sp-sites-lists.create-list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-list-items\n\
  \          description: \"Get items from a SharePoint list\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-sites-lists.get-list-items\"\n          with:\n            list_title: \"tools.list_title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-list-item\n          description: \"Add an item to a SharePoint list\"\n          hints: {readOnly: false, idempotent: false}\n          call: \"sp-sites-lists.create-list-item\"\n          with:\n            list_title: \"tools.list_title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-list-item\n          description: \"Update a SharePoint list item\"\n          hints: {readOnly: false, idempotent: true}\n          call: \"sp-sites-lists.update-list-item\"\n          with:\n            list_title: \"tools.list_title\"\n            item_id: \"tools.item_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: delete-list-item\n          description: \"Delete a SharePoint list item\"\n          hints: {readOnly: false, destructive: true, idempotent: true}\n          call: \"sp-sites-lists.delete-list-item\"\n          with:\n            list_title: \"tools.list_title\"\n            item_id: \"tools.item_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-files-in-folder\n          description: \"List files in a SharePoint folder\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-files-search.get-files-in-folder\"\n          with:\n            folder_url: \"tools.folder_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-file\n          description: \"Upload a file to SharePoint\"\n          hints: {readOnly: false, idempotent: false}\n          call: \"sp-files-search.upload-file\"\
  \n          with:\n            folder_url: \"tools.folder_url\"\n            file_name: \"tools.file_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-file\n          description: \"Download a file from SharePoint\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-files-search.download-file\"\n          with:\n            file_url: \"tools.file_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-query\n          description: \"Search across all SharePoint content\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"sp-files-search.search-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-my-user-profile\n          description: \"Get current user's SharePoint profile\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"\
  sp-files-search.get-my-user-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sharepoint/refs/heads/main/capabilities/content-management.yaml
tags:
- SharePoint
- Content Management
- Collaboration
- Document Management
tools:
- description: Get SharePoint site properties
  hints:
    idempotent: true
    readOnly: true
  name: get-web
- description: List all SharePoint lists
  hints:
    idempotent: true
    readOnly: true
  name: get-lists
- description: Create a new SharePoint list
  hints:
    idempotent: false
    readOnly: false
  name: create-list
- description: Get items from a SharePoint list
  hints:
    idempotent: true
    readOnly: true
  name: get-list-items
- description: Add an item to a SharePoint list
  hints:
    idempotent: false
    readOnly: false
  name: create-list-item
- description: Update a SharePoint list item
  hints:
    idempotent: true
    readOnly: false
  name: update-list-item
- description: Delete a SharePoint list item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-list-item
- description: List files in a SharePoint folder
  hints:
    idempotent: true
    readOnly: true
  name: get-files-in-folder
- description: Upload a file to SharePoint
  hints:
    idempotent: false
    readOnly: false
  name: upload-file
- description: Download a file from SharePoint
  hints:
    idempotent: true
    readOnly: true
  name: download-file
- description: Search across all SharePoint content
  hints:
    idempotent: true
    readOnly: true
  name: search-query
- description: Get current user's SharePoint profile
  hints:
    idempotent: true
    readOnly: true
  name: get-my-user-profile
---
