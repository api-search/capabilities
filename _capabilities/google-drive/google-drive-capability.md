---
categories: []
consumed_apis: []
description: The Google Drive API allows developers to integrate with Google Drive to create, read, update, and delete files and folders stored in Google Drive. The v3 REST API supports file metadata operations, content upload and download, folder hierarchies, sharing and permissions, and search across a user's Drive.
layout: capability
name: Google Drive API
operations:
- description: List files
  method: GET
  name: listfiles
  path: /files
- description: Create a file
  method: POST
  name: createfile
  path: /files
- description: Get a file
  method: GET
  name: getfile
  path: /files/{fileId}
- description: Update a file
  method: PATCH
  name: updatefile
  path: /files/{fileId}
- description: Delete a file
  method: DELETE
  name: deletefile
  path: /files/{fileId}
- description: Copy a file
  method: POST
  name: copyfile
  path: /files/{fileId}/copy
- description: List permissions
  method: GET
  name: listpermissions
  path: /files/{fileId}/permissions
- description: Create a permission
  method: POST
  name: createpermission
  path: /files/{fileId}/permissions
personas: []
provider_name: Google Drive
provider_slug: google-drive
search_terms:
- copy a file
- document management
- files
- createpermission
- api
- getfile
- drive
- cloud storage
- delete a file
- update a file
- create a permission
- google
- collaboration
- createfile
- create a file
- list files
- deletefile
- storage
- listpermissions
- list permissions
- copyfile
- listfiles
- get a file
- updatefile
slug: google-drive-capability
source_filename: google-drive-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Drive API\n  description: The Google Drive API allows developers to integrate with Google Drive to create, read, update, and delete files\n    and folders stored in Google Drive. The v3 REST API supports file metadata operations, content upload and download, folder\n    hierarchies, sharing and permissions, and search across a user's Drive.\n  tags:\n  - Google\n  - Drive\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-drive\n    baseUri: https://www.googleapis.com/drive/v3\n    description: Google Drive API HTTP API.\n    resources:\n    - name: files\n      path: /files\n      operations:\n      - name: listfiles\n        method: GET\n        description: List files\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Query string for searching files.\n        - name: pageSize\n          in:\
  \ query\n          type: integer\n          description: Maximum number of files to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for continuing a previous list request.\n        - name: fields\n          in: query\n          type: string\n          description: Selector specifying which fields to include in a response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfile\n        method: POST\n        description: Create a file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid\n      path: /files/{fileId}\n      operations:\n      - name: getfile\n        method: GET\n        description: Get a file\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n\
  \          description: The ID of the file.\n        - name: fields\n          in: query\n          type: string\n          description: Selector specifying which fields to include in a response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefile\n        method: PATCH\n        description: Update a file\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The ID of the file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefile\n        method: DELETE\n        description: Delete a file\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The ID of the file.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: files-fileid-copy\n      path: /files/{fileId}/copy\n      operations:\n      - name: copyfile\n        method: POST\n        description: Copy a file\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The ID of the file to copy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid-permissions\n      path: /files/{fileId}/permissions\n      operations:\n      - name: listpermissions\n        method: GET\n        description: List permissions\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The ID of the file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: createpermission\n        method: POST\n        description: Create a permission\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The ID of the file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-drive-rest\n    description: REST adapter for Google Drive API.\n    resources:\n    - path: /files\n      name: listfiles\n      operations:\n      - method: GET\n        name: listfiles\n        description: List files\n        call: google-drive.listfiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files\n      name: createfile\n      operations:\n      - method: POST\n        name: createfile\n        description: Create a file\n        call: google-drive.createfile\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: getfile\n      operations:\n      - method: GET\n        name: getfile\n        description: Get a file\n        call: google-drive.getfile\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: updatefile\n      operations:\n      - method: PATCH\n        name: updatefile\n        description: Update a file\n        call: google-drive.updatefile\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: deletefile\n      operations:\n      - method: DELETE\n        name: deletefile\n        description: Delete a file\n        call: google-drive.deletefile\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/copy\n\
  \      name: copyfile\n      operations:\n      - method: POST\n        name: copyfile\n        description: Copy a file\n        call: google-drive.copyfile\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/permissions\n      name: listpermissions\n      operations:\n      - method: GET\n        name: listpermissions\n        description: List permissions\n        call: google-drive.listpermissions\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/permissions\n      name: createpermission\n      operations:\n      - method: POST\n        name: createpermission\n        description: Create a permission\n        call: google-drive.createpermission\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: google-drive-mcp\n    transport: http\n    description: MCP adapter for Google Drive API for AI agent use.\n    tools:\n    - name: listfiles\n      description: List files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-drive.listfiles\n      with:\n        q: tools.q\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        fields: tools.fields\n      inputParameters:\n      - name: q\n        type: string\n        description: Query string for searching files.\n      - name: pageSize\n        type: integer\n        description: Maximum number of files to return per page.\n      - name: pageToken\n        type: string\n        description: Token for continuing a previous list request.\n      - name: fields\n        type: string\n        description: Selector specifying which fields to include in a response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ createfile\n      description: Create a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-drive.createfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfile\n      description: Get a file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-drive.getfile\n      with:\n        fileId: tools.fileId\n        fields: tools.fields\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID of the file.\n        required: true\n      - name: fields\n        type: string\n        description: Selector specifying which fields to include in a response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefile\n      description: Update a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-drive.updatefile\n\
  \      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID of the file.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefile\n      description: Delete a file\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-drive.deletefile\n      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID of the file.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copyfile\n      description: Copy a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-drive.copyfile\n      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID\
  \ of the file to copy.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermissions\n      description: List permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-drive.listpermissions\n      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID of the file.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpermission\n      description: Create a permission\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-drive.createpermission\n      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: The ID of the file.\n        required: true\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-drive/refs/heads/main/capabilities/google-drive-capability.yaml
tags:
- Google
- Drive
- API
tools:
- description: List files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfiles
- description: Create a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfile
- description: Get a file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfile
- description: Update a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefile
- description: Delete a file
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefile
- description: Copy a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copyfile
- description: List permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissions
- description: Create a permission
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpermission
---
