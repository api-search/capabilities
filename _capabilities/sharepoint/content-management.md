---
categories:
- content-management
consumed_apis: []
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
- add an item to a sharepoint list
- get sharepoint site properties
- search across all sharepoint content
- create a new sharepoint list
- list files in a sharepoint folder
- get list items
- get items from a sharepoint list
- content management
- upload a file to sharepoint
- download a file from sharepoint
- delete list item
- search query
- get files in folder
- get web
- intranet
- update a sharepoint list item
- microsoft
- get current user's sharepoint profile
- update list item
- upload file
- document management
- download file
- search
- sharepoint
- create list
- delete a sharepoint list item
- enterprise content management
- create list item
- get my user profile
- collaboration
- get files
- get lists
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SharePoint Content Management\n  description: Unified workflow for managing SharePoint content including sites, lists, items, files, and search. Used by\n    content managers, site admins, and collaboration teams.\n  tags:\n  - SharePoint\n  - Content Management\n  - Collaboration\n  - Document Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHAREPOINT_ACCESS_TOKEN: SHAREPOINT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sp-sites-lists\n    baseUri: https://{site_url}/_api\n    description: SharePoint REST API for sites, lists, and items.\n    authentication:\n      type: bearer\n      token: '{{SHAREPOINT_ACCESS_TOKEN}}'\n    resources:\n    - name: sites\n      path: /web\n      description: SharePoint site operations.\n      operations:\n      - name: get-web\n        method: GET\n        path: /web\n        description: Retrieve site properties.\n     \
  \   inputParameters:\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-web-title\n        method: GET\n        path: /web/title\n        description: Retrieve site title.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /web/lists\n      description: SharePoint list and library operations.\n      operations:\n      - name: get-lists\n        method: GET\n        path: /web/lists\n        description: Retrieve all lists on the site.\n        inputParameters:\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to return.\n        - name: $filter\n          in: query\n\
  \          type: string\n          required: false\n          description: OData filter expression.\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-list\n        method: POST\n        path: /web/lists\n        description: Create a new list.\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n            BaseTemplate: '{{tools.base_template}}'\n            Description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-list-by-title\n        method: GET\n        path: /web/lists/getbytitle('{list_title}')\n        description: Retrieve a list by title.\n        inputParameters:\n        - name: list_title\n\
  \          in: path\n          type: string\n          required: true\n          description: List title.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /web/lists\n      description: List item operations.\n      operations:\n      - name: get-list-items\n        method: GET\n        path: /web/lists/getbytitle('{list_title}')/items\n        description: Retrieve items from a list.\n        inputParameters:\n        - name: list_title\n          in: path\n          type: string\n          required: true\n          description: List title.\n        - name: $select\n          in: query\n          type: string\n          required: false\n        - name: $filter\n          in: query\n          type: string\n          required: false\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-list-item\n        method: POST\n        path: /web/lists/getbytitle('{list_title}')/items\n        description: Add an item to a list.\n        inputParameters:\n        - name: list_title\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-list-item-by-id\n        method: GET\n        path: /web/lists/getbytitle('{list_title}')/items({item_id})\n        description: Retrieve a list item by ID.\n        inputParameters:\n        - name: list_title\n          in: path\n          type: string\n          required: true\n        - name: item_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-list-item\n        method: POST\n        path: /web/lists/getbytitle('{list_title}')/items({item_id})\n        description: Update a list item.\n        inputParameters:\n        - name: list_title\n          in: path\n          type: string\n          required: true\n        - name: item_id\n          in: path\n          type: integer\n          required: true\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-list-item\n        method: DELETE\n        path: /web/lists/getbytitle('{list_title}')/items({item_id})\n        description: Delete a list item.\n        inputParameters:\n        - name: list_title\n          in: path\n          type: string\n          required: true\n      \
  \  - name: item_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sp-files-search\n    baseUri: https://{site_url}/_api\n    description: SharePoint REST API for files and search.\n    authentication:\n      type: bearer\n      token: '{{SHAREPOINT_ACCESS_TOKEN}}'\n    resources:\n    - name: files\n      path: /web\n      description: File and folder operations.\n      operations:\n      - name: get-files-in-folder\n        method: GET\n        path: /web/getfolderbyserverrelativeurl('{folder_url}')/files\n        description: Get files in a folder.\n        inputParameters:\n        - name: folder_url\n          in: path\n          type: string\n          required: true\n          description: Server-relative folder URL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: upload-file\n        method: POST\n        path: /web/getfolderbyserverrelativeurl('{folder_url}')/files/add(url='{file_name}',overwrite=true)\n        description: Upload a file.\n        inputParameters:\n        - name: folder_url\n          in: path\n          type: string\n          required: true\n        - name: file_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-file\n        method: GET\n        path: /web/getfilebyserverrelativeurl('{file_url}')/$value\n        description: Download file content.\n        inputParameters:\n        - name: file_url\n          in: path\n          type: string\n          required: true\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: search\n      path: /search\n      description: Search operations.\n      operations:\n      - name: search-query\n        method: GET\n        path: /search/query\n        description: Execute a search query.\n        inputParameters:\n        - name: querytext\n          in: query\n          type: string\n          required: true\n          description: Search query text.\n        - name: rowlimit\n          in: query\n          type: integer\n          required: false\n          description: Max results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-profiles\n      path: /SP.UserProfiles.PeopleManager\n      description: User profile operations.\n      operations:\n      - name: get-my-user-profile\n        method: GET\n        path: /SP.UserProfiles.PeopleManager/GetMyProperties\n        description: Get current user profile.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sp-content-api\n    description: Unified REST API for SharePoint content management.\n    resources:\n    - path: /v1/sites\n      name: sites\n      operations:\n      - method: GET\n        name: get-web\n        call: sp-sites-lists.get-web\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists\n      name: lists\n      operations:\n      - method: GET\n        name: get-lists\n        call: sp-sites-lists.get-lists\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-list\n        call: sp-sites-lists.create-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists/{title}/items\n      name: items\n      operations:\n      - method: GET\n        name: get-list-items\n        call: sp-sites-lists.get-list-items\n\
  \        with:\n          list_title: rest.title\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-list-item\n        call: sp-sites-lists.create-list-item\n        with:\n          list_title: rest.title\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files\n      name: files\n      operations:\n      - method: GET\n        name: get-files\n        call: sp-files-search.get-files-in-folder\n        with:\n          folder_url: rest.folder_url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      operations:\n      - method: GET\n        name: search\n        call: sp-files-search.search-query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sp-content-mcp\n    transport: http\n    description: MCP server for AI-assisted SharePoint content\
  \ management.\n    tools:\n    - name: get-web\n      description: Get SharePoint site properties\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-sites-lists.get-web\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lists\n      description: List all SharePoint lists\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-sites-lists.get-lists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-list\n      description: Create a new SharePoint list\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sp-sites-lists.create-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-list-items\n      description: Get items from a SharePoint list\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-sites-lists.get-list-items\n      with:\n        list_title: tools.list_title\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-list-item\n      description: Add an item to a SharePoint list\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sp-sites-lists.create-list-item\n      with:\n        list_title: tools.list_title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-list-item\n      description: Update a SharePoint list item\n      hints:\n        readOnly: false\n        idempotent: true\n      call: sp-sites-lists.update-list-item\n      with:\n        list_title: tools.list_title\n        item_id: tools.item_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-list-item\n      description: Delete a SharePoint list item\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sp-sites-lists.delete-list-item\n      with:\n        list_title: tools.list_title\n        item_id: tools.item_id\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-files-in-folder\n      description: List files in a SharePoint folder\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-files-search.get-files-in-folder\n      with:\n        folder_url: tools.folder_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-file\n      description: Upload a file to SharePoint\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sp-files-search.upload-file\n      with:\n        folder_url: tools.folder_url\n        file_name: tools.file_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-file\n      description: Download a file from SharePoint\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-files-search.download-file\n      with:\n        file_url: tools.file_url\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: search-query\n      description: Search across all SharePoint content\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-files-search.search-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-my-user-profile\n      description: Get current user's SharePoint profile\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sp-files-search.get-my-user-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
