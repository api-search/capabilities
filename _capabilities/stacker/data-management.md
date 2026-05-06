---
categories: []
consumed_apis: []
description: Unified workflow capability for managing data within Stacker no-code applications. Covers account and stack discovery, object (table) inspection, and full record lifecycle operations including search, create, update, delete, and bulk upsert. Designed for developers, data teams, and automation engineers building integrations on top of Stacker portals.
layout: capability
name: Stacker Data Management
operations:
- description: List all accounts accessible by the integration key
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List all objects for a given stack
  method: GET
  name: list-objects
  path: /v1/stacks/{stack_id}/objects
- description: Search and filter records
  method: POST
  name: search-records
  path: /v1/stacks/{stack_id}/objects/{object_sid}/records
- description: Create a new record
  method: POST
  name: create-record
  path: /v1/stacks/{stack_id}/objects/{object_sid}/records
- description: Get a record by SID
  method: GET
  name: get-record
  path: /v1/stacks/{stack_id}/objects/{object_sid}/records/{record_sid}
- description: Update record fields
  method: PATCH
  name: update-record
  path: /v1/stacks/{stack_id}/objects/{object_sid}/records/{record_sid}
- description: Delete a record
  method: DELETE
  name: delete-record
  path: /v1/stacks/{stack_id}/objects/{object_sid}/records/{record_sid}
- description: Create or update up to 1000 records
  method: POST
  name: bulk-upsert-records
  path: /v1/stacks/{stack_id}/objects/{object_sid}/bulk-records
personas: []
provider_name: Stacker
provider_slug: stacker
search_terms:
- stacker accounts
- no-code
- delete record
- low-code
- create or update up to 1000 stacker records in a single operation
- list all objects (tables) in a stacker application stack
- create a new record in a stacker object
- update record fields
- update one or more fields on an existing stacker record
- search, filter, and paginate records within a stacker object
- portals
- get record
- objects (tables) in a stacker stack
- get a single stacker record by sid
- list all accounts accessible by the integration key
- update record
- list all objects for a given stack
- get a record by sid
- records
- application development
- search records
- bulk upsert records
- search and filter records
- list objects
- create or update up to 1000 records
- records within a stacker object
- permanently delete a stacker record
- create a new record
- single record operations
- data management
- workflow automation
- list all stacker accounts accessible via the integration key
- create record
- list accounts
- delete a record
- bulk record operations
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stacker Data Management\n  description: Unified workflow capability for managing data within Stacker no-code applications. Covers account and stack\n    discovery, object (table) inspection, and full record lifecycle operations including search, create, update, delete, and\n    bulk upsert. Designed for developers, data teams, and automation engineers building integrations on top of Stacker portals.\n  tags:\n  - No-Code\n  - Records\n  - Data Management\n  - Portals\n  - Application Development\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACKER_INTEGRATION_KEY: STACKER_INTEGRATION_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stacker\n    baseUri: https://api.go.stackerhq.com\n    description: Stacker no-code platform API for managing records, objects, and accounts.\n    authentication:\n      type: apikey\n      key: X-Integration-Key\n      value: '{{STACKER_INTEGRATION_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: hello\n      path: /api/external/hello/\n      description: Health check endpoint\n      operations:\n      - name: get-hello\n        method: GET\n        description: Health check - verify API connectivity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /api/external/accounts/\n      description: Manage Stacker accounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts accessible by the integration key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /api/external/objects/\n      description: List objects (tables) in a stack\n      operations:\n      - name: list-objects\n        method: GET\n        description: List all objects for an account and stack\n\
  \        inputParameters:\n        - name: X-Account-Id\n          in: header\n          type: string\n          required: true\n          description: The Stacker account ID\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n          description: The Stacker stack ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: records\n      path: /api/external/objects/{object_sid}/search/\n      description: Search and paginate records within an object\n      operations:\n      - name: search-records\n        method: POST\n        description: Search records in an object with filtering and pagination\n        inputParameters:\n        - name: object_sid\n          in: path\n          type: string\n          required: true\n          description: The object SID\n        - name: X-Account-Id\n          in: header\n          type: string\n          required:\
  \ true\n          description: The Stacker account ID\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n          description: The Stacker stack ID\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n            count: '{{tools.count}}'\n            start: '{{tools.start}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        description: Create a new record in an object\n        inputParameters:\n        - name: object_sid\n          in: path\n          type: string\n          required: true\n          description: The object SID\n        - name: X-Account-Id\n          in: header\n          type: string\n          required: true\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n\
  \          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-record\n        method: GET\n        description: Retrieve a single record by SID\n        inputParameters:\n        - name: object_sid\n          in: path\n          type: string\n          required: true\n        - name: record_sid\n          in: path\n          type: string\n          required: true\n        - name: X-Account-Id\n          in: header\n          type: string\n          required: true\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-record\n        method: PATCH\n        description: Partially update a record\n        inputParameters:\n        - name: object_sid\n        \
  \  in: path\n          type: string\n          required: true\n        - name: record_sid\n          in: path\n          type: string\n          required: true\n        - name: X-Account-Id\n          in: header\n          type: string\n          required: true\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-record\n        method: DELETE\n        description: Delete a record by SID\n        inputParameters:\n        - name: object_sid\n          in: path\n          type: string\n          required: true\n        - name: record_sid\n          in: path\n          type: string\n          required: true\n        - name: X-Account-Id\n          in: header\n          type: string\n          required:\
  \ true\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: bulk-upsert-records\n        method: POST\n        description: Create or update up to 1000 records in a single request\n        inputParameters:\n        - name: object_sid\n          in: path\n          type: string\n          required: true\n        - name: X-Account-Id\n          in: header\n          type: string\n          required: true\n        - name: X-Stack-Id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stacker-data-api\n   \
  \ description: Unified REST API for Stacker data management.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Stacker accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accounts accessible by the integration key\n        call: stacker.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stack_id}/objects\n      name: objects\n      description: Objects (tables) in a Stacker stack\n      operations:\n      - method: GET\n        name: list-objects\n        description: List all objects for a given stack\n        call: stacker.list-objects\n        with:\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stack_id}/objects/{object_sid}/records\n      name: records\n      description: Records within a Stacker object\n      operations:\n      - method: POST\n\
  \        name: search-records\n        description: Search and filter records\n        call: stacker.search-records\n        with:\n          object_sid: rest.object_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-record\n        description: Create a new record\n        call: stacker.create-record\n        with:\n          object_sid: rest.object_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stack_id}/objects/{object_sid}/records/{record_sid}\n      name: record\n      description: Single record operations\n      operations:\n      - method: GET\n        name: get-record\n        description: Get a record by SID\n        call: stacker.get-record\n        with:\n          object_sid: rest.object_sid\n          record_sid: rest.record_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-record\n        description: Update record fields\n        call: stacker.update-record\n        with:\n          object_sid: rest.object_sid\n          record_sid: rest.record_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-record\n        description: Delete a record\n        call: stacker.delete-record\n        with:\n          object_sid: rest.object_sid\n          record_sid: rest.record_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stack_id}/objects/{object_sid}/bulk-records\n      name: bulk-records\n      description: Bulk record operations\n      operations:\n      - method: POST\n        name: bulk-upsert-records\n        description: Create or update up to 1000 records\n        call:\
  \ stacker.bulk-upsert-records\n        with:\n          object_sid: rest.object_sid\n          X-Stack-Id: rest.stack_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: stacker-data-mcp\n    transport: http\n    description: MCP server for AI-assisted Stacker data management.\n    tools:\n    - name: list-accounts\n      description: List all Stacker accounts accessible via the integration key\n      hints:\n        readOnly: true\n      call: stacker.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-objects\n      description: List all objects (tables) in a Stacker application stack\n      hints:\n        readOnly: true\n      call: stacker.list-objects\n      with:\n        X-Account-Id: tools.account_id\n        X-Stack-Id: tools.stack_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-records\n      description: Search, filter,\
  \ and paginate records within a Stacker object\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stacker.search-records\n      with:\n        object_sid: tools.object_sid\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-record\n      description: Get a single Stacker record by SID\n      hints:\n        readOnly: true\n      call: stacker.get-record\n      with:\n        object_sid: tools.object_sid\n        record_sid: tools.record_sid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-record\n      description: Create a new record in a Stacker object\n      hints:\n        readOnly: false\n      call: stacker.create-record\n      with:\n        object_sid: tools.object_sid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-record\n      description: Update one or more fields on an existing Stacker record\n      hints:\n\
  \        readOnly: false\n        idempotent: true\n      call: stacker.update-record\n      with:\n        object_sid: tools.object_sid\n        record_sid: tools.record_sid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-record\n      description: Permanently delete a Stacker record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: stacker.delete-record\n      with:\n        object_sid: tools.object_sid\n        record_sid: tools.record_sid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulk-upsert-records\n      description: Create or update up to 1000 Stacker records in a single operation\n      hints:\n        readOnly: false\n      call: stacker.bulk-upsert-records\n      with:\n        object_sid: tools.object_sid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stacker/refs/heads/main/capabilities/data-management.yaml
tags:
- No-Code
- Records
- Data Management
- Portals
- Application Development
tools:
- description: List all Stacker accounts accessible via the integration key
  hints:
    readOnly: true
  name: list-accounts
- description: List all objects (tables) in a Stacker application stack
  hints:
    readOnly: true
  name: list-objects
- description: Search, filter, and paginate records within a Stacker object
  hints:
    openWorld: true
    readOnly: true
  name: search-records
- description: Get a single Stacker record by SID
  hints:
    readOnly: true
  name: get-record
- description: Create a new record in a Stacker object
  hints:
    readOnly: false
  name: create-record
- description: Update one or more fields on an existing Stacker record
  hints:
    idempotent: true
    readOnly: false
  name: update-record
- description: Permanently delete a Stacker record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-record
- description: Create or update up to 1000 Stacker records in a single operation
  hints:
    readOnly: false
  name: bulk-upsert-records
---
