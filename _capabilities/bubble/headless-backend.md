---
categories: []
consumed_apis: []
description: Use a Bubble app as a headless backend for an external mobile or web client. Combines the Data API for CRUD plus the Workflow API for business logic into a single capability that exposes a unified REST surface and an MCP tool surface.
layout: capability
name: Bubble Headless Backend
operations:
- description: List records of a type
  method: GET
  name: list-records
  path: /records/{typename}
- description: Create a new record
  method: POST
  name: create-record
  path: /records/{typename}
- description: Get a record by id
  method: GET
  name: get-record
  path: /records/{typename}/{uid}
- description: Patch a record
  method: PATCH
  name: modify-record
  path: /records/{typename}/{uid}
- description: Delete a record
  method: DELETE
  name: delete-record
  path: /records/{typename}/{uid}
- description: Trigger a backend workflow
  method: POST
  name: trigger-workflow
  path: /workflows/{workflow_name}
personas: []
provider_name: Bubble
provider_slug: bubble
search_terms:
- get a bubble record by id
- create a new record
- patch an existing bubble record
- create record
- workflow automation
- patch a record
- records of a data type
- create a new bubble record
- modify record
- search records
- get record
- plugins
- delete a bubble record
- integration
- bubble
- delete record
- individual record
- list records
- trigger workflows
- trigger a backend workflow
- database
- backend
- get a record by id
- trigger a bubble backend workflow by name
- delete a record
- application platform
- headless
- list records of a type
- trigger workflow
- no-code
- search records of a bubble data type with constraints
slug: headless-backend
source_filename: headless-backend.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bubble Headless Backend\n  description: Use a Bubble app as a headless backend for an external mobile or web client. Combines the Data API for CRUD plus the Workflow API for business logic into a single capability that exposes a unified REST surface and an MCP tool surface.\n  tags:\n    - Bubble\n    - Headless\n    - No-Code\n    - Backend\n    - Integration\n  created: '2026-05-06'\n  modified: '2026-05-06'\nbinds:\n  - namespace: env\n    keys:\n      BUBBLE_API_TOKEN: BUBBLE_API_TOKEN\n      BUBBLE_APP_NAME: BUBBLE_APP_NAME\ncapability:\n  consumes:\n    - type: http\n      namespace: bubble-data\n      baseUri: https://{{BUBBLE_APP_NAME}}.bubbleapps.io/api/1.1\n      description: Bubble Data API for CRUD against the app database\n      authentication:\n        type: bearer\n        token: '{{BUBBLE_API_TOKEN}}'\n      resources:\n        - name: things\n          path: /obj/{typename}\n          description: Records of a data type\n\
  \          operations:\n            - name: search-things\n              method: GET\n              description: Search records of a data type\n              inputParameters:\n                - name: typename\n                  in: path\n                  type: string\n                  required: true\n                  description: Lowercase data type name\n                - name: constraints\n                  in: query\n                  type: string\n                  required: false\n                  description: JSON-encoded constraints\n                - name: cursor\n                  in: query\n                  type: integer\n                  required: false\n                  description: Pagination cursor\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                  description: Page size\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n\
  \                  type: object\n                  value: $.\n            - name: create-thing\n              method: POST\n              description: Create a record\n              inputParameters:\n                - name: typename\n                  in: path\n                  type: string\n                  required: true\n                  description: Lowercase data type name\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n        - name: thing\n          path: /obj/{typename}/{uid}\n          description: Single record operations\n          operations:\n            - name: get-thing\n              method: GET\n              description: Get a record by id\n              inputParameters:\n                - name: typename\n                  in: path\n                  type: string\n                  required: true\n                  description: Lowercase data type name\n\
  \                - name: uid\n                  in: path\n                  type: string\n                  required: true\n                  description: Unique record id\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n            - name: modify-thing\n              method: PATCH\n              description: Patch a record\n              inputParameters:\n                - name: typename\n                  in: path\n                  type: string\n                  required: true\n                  description: Lowercase data type name\n                - name: uid\n                  in: path\n                  type: string\n                  required: true\n                  description: Unique record id\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n     \
  \       - name: delete-thing\n              method: DELETE\n              description: Delete a record\n              inputParameters:\n                - name: typename\n                  in: path\n                  type: string\n                  required: true\n                  description: Lowercase data type name\n                - name: uid\n                  in: path\n                  type: string\n                  required: true\n                  description: Unique record id\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n    - type: http\n      namespace: bubble-workflow\n      baseUri: https://{{BUBBLE_APP_NAME}}.bubbleapps.io/api/1.1\n      description: Bubble Workflow API for backend business logic\n      authentication:\n        type: bearer\n        token: '{{BUBBLE_API_TOKEN}}'\n      resources:\n        - name: workflow\n          path: /wf/{workflow_name}\n\
  \          description: Trigger a workflow by name\n          operations:\n            - name: trigger-workflow\n              method: POST\n              description: Invoke a backend workflow with JSON parameters\n              inputParameters:\n                - name: workflow_name\n                  in: path\n                  type: string\n                  required: true\n                  description: Workflow slug\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bubble-headless-api\n      description: Unified REST API for the Bubble headless backend\n      resources:\n        - path: /records/{typename}\n          name: records\n          description: Records of a data type\n          operations:\n            - method: GET\n              name: list-records\n              description: List records of a\
  \ type\n              call: bubble-data.search-things\n              with:\n                typename: rest.typename\n              outputParameters:\n                - type: object\n                  mapping: $.\n            - method: POST\n              name: create-record\n              description: Create a new record\n              call: bubble-data.create-thing\n              with:\n                typename: rest.typename\n              outputParameters:\n                - type: object\n                  mapping: $.\n        - path: /records/{typename}/{uid}\n          name: record\n          description: Individual record\n          operations:\n            - method: GET\n              name: get-record\n              description: Get a record by id\n              call: bubble-data.get-thing\n              with:\n                typename: rest.typename\n                uid: rest.uid\n              outputParameters:\n                - type: object\n                  mapping: $.\n \
  \           - method: PATCH\n              name: modify-record\n              description: Patch a record\n              call: bubble-data.modify-thing\n              with:\n                typename: rest.typename\n                uid: rest.uid\n              outputParameters:\n                - type: object\n                  mapping: $.\n            - method: DELETE\n              name: delete-record\n              description: Delete a record\n              call: bubble-data.delete-thing\n              with:\n                typename: rest.typename\n                uid: rest.uid\n              outputParameters:\n                - type: object\n                  mapping: $.\n        - path: /workflows/{workflow_name}\n          name: workflows\n          description: Trigger workflows\n          operations:\n            - method: POST\n              name: trigger-workflow\n              description: Trigger a backend workflow\n              call: bubble-workflow.trigger-workflow\n  \
  \            with:\n                workflow_name: rest.workflow_name\n              outputParameters:\n                - type: object\n                  mapping: $.\n    - type: mcp\n      port: 9080\n      namespace: bubble-headless-mcp\n      transport: http\n      description: MCP server enabling AI agents to operate a Bubble app as a headless backend.\n      tools:\n        - name: search-records\n          description: Search records of a Bubble data type with constraints\n          hints:\n            readOnly: true\n            openWorld: false\n          call: bubble-data.search-things\n          with:\n            typename: tools.typename\n          outputParameters:\n            - type: object\n              mapping: $.\n        - name: get-record\n          description: Get a Bubble record by id\n          hints:\n            readOnly: true\n          call: bubble-data.get-thing\n          with:\n            typename: tools.typename\n            uid: tools.uid\n          outputParameters:\n\
  \            - type: object\n              mapping: $.\n        - name: create-record\n          description: Create a new Bubble record\n          hints:\n            readOnly: false\n            destructive: false\n          call: bubble-data.create-thing\n          with:\n            typename: tools.typename\n          outputParameters:\n            - type: object\n              mapping: $.\n        - name: modify-record\n          description: Patch an existing Bubble record\n          hints:\n            readOnly: false\n            destructive: false\n          call: bubble-data.modify-thing\n          with:\n            typename: tools.typename\n            uid: tools.uid\n          outputParameters:\n            - type: object\n              mapping: $.\n        - name: delete-record\n          description: Delete a Bubble record\n          hints:\n            readOnly: false\n            destructive: true\n          call: bubble-data.delete-thing\n          with:\n           \
  \ typename: tools.typename\n            uid: tools.uid\n          outputParameters:\n            - type: object\n              mapping: $.\n        - name: trigger-workflow\n          description: Trigger a Bubble backend workflow by name\n          hints:\n            readOnly: false\n            destructive: false\n          call: bubble-workflow.trigger-workflow\n          with:\n            workflow_name: tools.workflow_name\n          outputParameters:\n            - type: object\n              mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bubble/refs/heads/main/capabilities/headless-backend.yaml
tags:
- Bubble
- Headless
- No-Code
- Backend
- Integration
tools:
- description: Search records of a Bubble data type with constraints
  hints:
    openWorld: false
    readOnly: true
  name: search-records
- description: Get a Bubble record by id
  hints:
    readOnly: true
  name: get-record
- description: Create a new Bubble record
  hints:
    destructive: false
    readOnly: false
  name: create-record
- description: Patch an existing Bubble record
  hints:
    destructive: false
    readOnly: false
  name: modify-record
- description: Delete a Bubble record
  hints:
    destructive: true
    readOnly: false
  name: delete-record
- description: Trigger a Bubble backend workflow by name
  hints:
    destructive: false
    readOnly: false
  name: trigger-workflow
---
