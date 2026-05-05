---
categories: []
consumed_apis:
- wd-my-cloud-home
description: Workflow capability for managing personal cloud storage on Western Digital My Cloud Home devices. Covers file browsing, upload, download, sharing, and search for consumers and application developers integrating with WD NAS devices.
layout: capability
name: WD My Cloud Home Storage Management
operations:
- description: List files and folders in a directory.
  method: GET
  name: list-files
  path: /v1/files
- description: Upload a file or create a folder.
  method: POST
  name: create-file
  path: /v1/files
- description: Get metadata for a file or folder.
  method: GET
  name: get-file
  path: /v1/files/{fileId}
- description: Permanently delete a file or folder.
  method: DELETE
  name: delete-file
  path: /v1/files/{fileId}
- description: Download the binary content of a file.
  method: GET
  name: download-file
  path: /v1/files/{fileId}/content
- description: Search files within a specified parent folder.
  method: GET
  name: search-files-by-parent
  path: /v1/search
- description: Create a shareable link for one or more files.
  method: POST
  name: create-share
  path: /v1/shares
personas: []
provider_name: western-digital
provider_slug: western-digital
search_terms:
- browse and manage files and folders on the nas device.
- download the content of a file stored on my cloud home.
- search for files within a specified parent folder on my cloud home. useful for locating files in nested directory structures.
- get metadata (name, size, type, dates) for a specific file or folder.
- search files by parent
- upload and download file content.
- delete file
- create a shareable url for one or more files on my cloud home. optionally set an expiration date.
- search for files by parent folder.
- sharing
- download the binary content of a file.
- cloud storage
- list files
- upload a file or create a folder.
- download file
- permanently delete a file or folder.
- create share
- nas
- permanently delete a file or folder from my cloud home.
- list files and folders in a directory.
- get file
- create and manage file share links.
- create a shareable link for one or more files.
- upload a new file or create a folder on my cloud home.
- operate on a specific file or folder.
- consumer
- get metadata for a file or folder.
- file management
- create file
- list files and folders in a my cloud home directory. pass "root" as folder_id to list the root directory.
- search files within a specified parent folder.
slug: cloud-storage-management
source_filename: cloud-storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WD My Cloud Home Storage Management\"\n  description: >-\n    Workflow capability for managing personal cloud storage on Western Digital\n    My Cloud Home devices. Covers file browsing, upload, download, sharing, and\n    search for consumers and application developers integrating with WD NAS\n    devices.\n  tags:\n    - Cloud Storage\n    - File Management\n    - NAS\n    - Sharing\n    - Consumer\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WD_MY_CLOUD_ACCESS_TOKEN: WD_MY_CLOUD_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: wd-my-cloud-home\n      location: ./shared/my-cloud-home.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wd-storage-management-api\n      description: \"Unified REST API for WD My Cloud Home storage management workflows.\"\n      resources:\n        - path: /v1/files\n          name: files\n          description:\
  \ Browse and manage files and folders on the NAS device.\n          operations:\n            - method: GET\n              name: list-files\n              description: List files and folders in a directory.\n              call: \"wd-my-cloud-home.list-files\"\n              with:\n                ids: \"rest.folder_id\"\n                pageToken: \"rest.page_token\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-file\n              description: Upload a file or create a folder.\n              call: \"wd-my-cloud-home.create-file\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/{fileId}\n          name: file\n          description: Operate on a specific file or folder.\n          operations:\n            - method: GET\n              name: get-file\n           \
  \   description: Get metadata for a file or folder.\n              call: \"wd-my-cloud-home.get-file\"\n              with:\n                fileId: \"rest.fileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-file\n              description: Permanently delete a file or folder.\n              call: \"wd-my-cloud-home.delete-file\"\n              with:\n                fileId: \"rest.fileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/{fileId}/content\n          name: file-content\n          description: Upload and download file content.\n          operations:\n            - method: GET\n              name: download-file\n              description: Download the binary content of a file.\n              call: \"wd-my-cloud-home.download-file\"\n              with:\n                fileId: \"\
  rest.fileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: Search for files by parent folder.\n          operations:\n            - method: GET\n              name: search-files-by-parent\n              description: Search files within a specified parent folder.\n              call: \"wd-my-cloud-home.search-files-by-parent\"\n              with:\n                ids: \"rest.parent_ids\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/shares\n          name: shares\n          description: Create and manage file share links.\n          operations:\n            - method: POST\n              name: create-share\n              description: Create a shareable link for one or more files.\n              call: \"wd-my-cloud-home.create-share\"\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wd-storage-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WD My Cloud Home storage management.\"\n      tools:\n        - name: list-files\n          description: >-\n            List files and folders in a My Cloud Home directory. Pass \"root\"\n            as folder_id to list the root directory.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wd-my-cloud-home.list-files\"\n          with:\n            ids: \"tools.folder_id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-file\n          description: Get metadata (name, size, type, dates) for a specific file or folder.\n          hints:\n            readOnly: true\n            openWorld: true\n         \
  \ call: \"wd-my-cloud-home.get-file\"\n          with:\n            fileId: \"tools.fileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-file\n          description: Upload a new file or create a folder on My Cloud Home.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wd-my-cloud-home.create-file\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-file\n          description: Permanently delete a file or folder from My Cloud Home.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wd-my-cloud-home.delete-file\"\n          with:\n            fileId: \"tools.fileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-file\n          description:\
  \ Download the content of a file stored on My Cloud Home.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wd-my-cloud-home.download-file\"\n          with:\n            fileId: \"tools.fileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-files-by-parent\n          description: >-\n            Search for files within a specified parent folder on My Cloud Home.\n            Useful for locating files in nested directory structures.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wd-my-cloud-home.search-files-by-parent\"\n          with:\n            ids: \"tools.parent_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-share\n          description: >-\n            Create a shareable URL for one or more files on My Cloud Home.\n            Optionally set an expiration\
  \ date.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wd-my-cloud-home.create-share\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/western-digital/refs/heads/main/capabilities/cloud-storage-management.yaml
tags:
- Cloud Storage
- File Management
- NAS
- Sharing
- Consumer
tools:
- description: List files and folders in a My Cloud Home directory. Pass "root" as folder_id to list the root directory.
  hints:
    openWorld: true
    readOnly: true
  name: list-files
- description: Get metadata (name, size, type, dates) for a specific file or folder.
  hints:
    openWorld: true
    readOnly: true
  name: get-file
- description: Upload a new file or create a folder on My Cloud Home.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-file
- description: Permanently delete a file or folder from My Cloud Home.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-file
- description: Download the content of a file stored on My Cloud Home.
  hints:
    openWorld: true
    readOnly: true
  name: download-file
- description: Search for files within a specified parent folder on My Cloud Home. Useful for locating files in nested directory structures.
  hints:
    openWorld: true
    readOnly: true
  name: search-files-by-parent
- description: Create a shareable URL for one or more files on My Cloud Home. Optionally set an expiration date.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-share
---
