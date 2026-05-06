---
categories: []
consumed_apis: []
description: The Google Keep API enables enterprise administrators to manage Google Keep notes, including creating, listing, deleting, downloading attachments, and managing permissions on notes.
layout: capability
name: Google Keep API
operations:
- description: List notes
  method: GET
  name: listnotes
  path: /v1/notes
- description: Create note
  method: POST
  name: createnote
  path: /v1/notes
- description: Get attachment
  method: GET
  name: getattachment
  path: /v1/{name}
- description: Batch create permissions
  method: POST
  name: batchcreatepermissions
  path: /v1/{parent}/permissions:batchCreate
- description: Batch delete permissions
  method: POST
  name: batchdeletepermissions
  path: /v1/{parent}/permissions:batchDelete
personas: []
provider_name: Google Keep
provider_slug: google-keep
search_terms:
- listnotes
- batch create permissions
- keep
- google workspace
- organization
- list notes
- google
- api
- createnote
- batchdeletepermissions
- create note
- get attachment
- batch delete permissions
- notes
- batchcreatepermissions
- productivity
- getattachment
slug: google-keep-capability
source_filename: google-keep-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Keep API\n  description: The Google Keep API enables enterprise administrators to manage Google Keep notes, including creating, listing,\n    deleting, downloading attachments, and managing permissions on notes.\n  tags:\n  - Google\n  - Keep\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-keep\n    baseUri: https://keep.googleapis.com\n    description: Google Keep API HTTP API.\n    resources:\n    - name: v1-notes\n      path: /v1/notes\n      operations:\n      - name: listnotes\n        method: GET\n        description: List notes\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: createnote\n        method: POST\n        description: Create note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-name\n      path: /v1/{name}\n      operations:\n      - name: getattachment\n        method: GET\n        description: Get attachment\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: 'Format: notes/{note}/attachments/{attachment}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-permissions-batchcreate\n      path: /v1/{parent}/permissions:batchCreate\n      operations:\n      - name: batchcreatepermissions\n        method: POST\n        description: Batch create permissions\n        inputParameters:\n        - name: parent\n    \
  \      in: path\n          type: string\n          required: true\n          description: 'Format: notes/{note}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-permissions-batchdelete\n      path: /v1/{parent}/permissions:batchDelete\n      operations:\n      - name: batchdeletepermissions\n        method: POST\n        description: Batch delete permissions\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: 'Format: notes/{note}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-keep-rest\n    description: REST adapter for Google Keep API.\n    resources:\n    - path: /v1/notes\n      name: listnotes\n      operations:\n      - method: GET\n        name:\
  \ listnotes\n        description: List notes\n        call: google-keep.listnotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notes\n      name: createnote\n      operations:\n      - method: POST\n        name: createnote\n        description: Create note\n        call: google-keep.createnote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{name}\n      name: getattachment\n      operations:\n      - method: GET\n        name: getattachment\n        description: Get attachment\n        call: google-keep.getattachment\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/permissions:batchCreate\n      name: batchcreatepermissions\n      operations:\n      - method: POST\n        name: batchcreatepermissions\n        description: Batch create permissions\n        call: google-keep.batchcreatepermissions\n      \
  \  with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/permissions:batchDelete\n      name: batchdeletepermissions\n      operations:\n      - method: POST\n        name: batchdeletepermissions\n        description: Batch delete permissions\n        call: google-keep.batchdeletepermissions\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-keep-mcp\n    transport: http\n    description: MCP adapter for Google Keep API for AI agent use.\n    tools:\n    - name: listnotes\n      description: List notes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-keep.listnotes\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n      inputParameters:\n      - name: pageSize\n\
  \        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnote\n      description: Create note\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-keep.createnote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getattachment\n      description: Get attachment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-keep.getattachment\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: 'Format: notes/{note}/attachments/{attachment}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ batchcreatepermissions\n      description: Batch create permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-keep.batchcreatepermissions\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: 'Format: notes/{note}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchdeletepermissions\n      description: Batch delete permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-keep.batchdeletepermissions\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: 'Format: notes/{note}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-keep/refs/heads/main/capabilities/google-keep-capability.yaml
tags:
- Google
- Keep
- API
tools:
- description: List notes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotes
- description: Create note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnote
- description: Get attachment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getattachment
- description: Batch create permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchcreatepermissions
- description: Batch delete permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchdeletepermissions
---
