---
categories: []
consumed_apis:
- vault-api
description: Customer workflow capability for life sciences document lifecycle management in Veeva Vault. Combines document CRUD, lifecycle actions, VQL queries, and object management for regulatory affairs teams, QMS coordinators, and clinical operations staff managing controlled documents through approval and archival workflows.
layout: capability
name: Veeva Vault Document Management
operations:
- description: List all Vault documents accessible to the authenticated user
  method: GET
  name: list-documents
  path: /v1/documents
- description: Create a new Vault document record
  method: POST
  name: create-document
  path: /v1/documents
- description: Retrieve metadata for a specific Vault document
  method: GET
  name: get-document
  path: /v1/documents/{documentId}
- description: Update a Vault document's field values
  method: PUT
  name: update-document
  path: /v1/documents/{documentId}
- description: Delete a Vault document and all its versions
  method: DELETE
  name: delete-document
  path: /v1/documents/{documentId}
- description: Execute a lifecycle action (Approve, Submit for Review, Archive)
  method: POST
  name: perform-document-action
  path: /v1/documents/{documentId}/actions/{actionName}
- description: List records for a Vault business object
  method: GET
  name: list-object-records
  path: /v1/objects/{objectName}
- description: Create a new Vault object record
  method: POST
  name: create-object-record
  path: /v1/objects/{objectName}
- description: Retrieve a single Vault object record
  method: GET
  name: get-object-record
  path: /v1/objects/{objectName}/{recordId}
- description: Update fields on a Vault object record
  method: PUT
  name: update-object-record
  path: /v1/objects/{objectName}/{recordId}
- description: Delete a Vault object record
  method: DELETE
  name: delete-object-record
  path: /v1/objects/{objectName}/{recordId}
- description: Run a VQL query to retrieve documents, objects, or user data
  method: GET
  name: execute-vql-query
  path: /v1/query
- description: List all active users in the Vault
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: veeva
provider_slug: veeva
search_terms:
- get, update, or delete a specific vault document
- delete document
- document management
- list and create vault object records (studies, products, sites)
- retrieve metadata and properties for a specific vault document by id
- list users
- create a new vault document record
- run a vql query to search documents, objects, users, or workflows in vault
- vault
- list records for a vault business object
- create a new vault object record for studies, products, sites, or custom objects
- retrieve a single vault object record
- execute vql queries across vault data
- run a vql query to retrieve documents, objects, or user data
- execute a lifecycle action on a document (approve, submit for review, archive)
- clinical
- create object record
- retrieve metadata for a specific vault document
- list and create vault documents
- list all vault documents accessible to the authenticated user
- create a new controlled document in vault with lifecycle and type
- delete a vault document and all its versions
- get document
- list object records
- life sciences
- qms
- perform document action
- list records for a vault business object (studies, products, sites, etc.)
- list vault users
- create document
- get object record
- create a new vault object record
- update a vault document's field values
- execute a lifecycle action (approve, submit for review, archive)
- pharma
- get, update, or delete a specific vault object record
- update object record
- delete a vault object record
- list all active users in the vault
- update field values on an existing vault document
- veeva
- update document
- delete object record
- execute vql query
- list documents
- update fields on a vault object record
- retrieve a single vault object record by object type and record id
- update field values on a vault object record
- permanently delete a vault document and all its versions
- perform lifecycle actions on a vault document
- regulatory
slug: vault-document-management
source_filename: vault-document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veeva Vault Document Management\"\n  description: >-\n    Customer workflow capability for life sciences document lifecycle management in Veeva Vault.\n    Combines document CRUD, lifecycle actions, VQL queries, and object management for\n    regulatory affairs teams, QMS coordinators, and clinical operations staff managing\n    controlled documents through approval and archival workflows.\n  tags:\n    - Veeva\n    - Vault\n    - Life Sciences\n    - Pharma\n    - Document Management\n    - Regulatory\n    - QMS\n    - Clinical\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VEEVA_VAULT_SESSION_ID: VEEVA_VAULT_SESSION_ID\n      VEEVA_VAULT_DOMAIN: VEEVA_VAULT_DOMAIN\n\ncapability:\n  consumes:\n    - import: vault-api\n      location: ./shared/vault-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vault-document-management-api\n      description:\
  \ \"Unified REST API for Veeva Vault document lifecycle management workflows.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          description: \"List and create Vault documents\"\n          operations:\n            - method: GET\n              name: list-documents\n              description: \"List all Vault documents accessible to the authenticated user\"\n              call: \"vault-api.list-documents\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-document\n              description: \"Create a new Vault document record\"\n              call: \"vault-api.create-document\"\n              with:\n                name__v: \"rest.name__v\"\n                type__v: \"rest.type__v\"\n                lifecycle__v:\
  \ \"rest.lifecycle__v\"\n                status__v: \"rest.status__v\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents/{documentId}\n          name: document\n          description: \"Get, update, or delete a specific Vault document\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Retrieve metadata for a specific Vault document\"\n              call: \"vault-api.get-document\"\n              with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-document\n              description: \"Update a Vault document's field values\"\n              call: \"vault-api.update-document\"\n              with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-document\n              description: \"Delete a Vault document and all its versions\"\n              call: \"vault-api.delete-document\"\n              with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents/{documentId}/actions/{actionName}\n          name: document-actions\n          description: \"Perform lifecycle actions on a Vault document\"\n          operations:\n            - method: POST\n              name: perform-document-action\n              description: \"Execute a lifecycle action (Approve, Submit for Review, Archive)\"\n              call: \"vault-api.perform-document-action\"\n              with:\n                documentId: \"rest.documentId\"\n                actionName: \"rest.actionName\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/objects/{objectName}\n          name: objects\n          description: \"List and create Vault object records (studies, products, sites)\"\n          operations:\n            - method: GET\n              name: list-object-records\n              description: \"List records for a Vault business object\"\n              call: \"vault-api.list-object-records\"\n              with:\n                objectName: \"rest.objectName\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-object-record\n              description: \"Create a new Vault object record\"\n              call: \"vault-api.create-object-record\"\n              with:\n                objectName: \"rest.objectName\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/objects/{objectName}/{recordId}\n          name: object-record\n          description: \"Get, update, or delete a specific Vault object record\"\n          operations:\n            - method: GET\n              name: get-object-record\n              description: \"Retrieve a single Vault object record\"\n              call: \"vault-api.get-object-record\"\n              with:\n                objectName: \"rest.objectName\"\n                recordId: \"rest.recordId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-object-record\n              description: \"Update fields on a Vault object record\"\n              call: \"vault-api.update-object-record\"\n              with:\n                objectName: \"rest.objectName\"\n                recordId: \"rest.recordId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-object-record\n              description: \"Delete a Vault object record\"\n              call: \"vault-api.delete-object-record\"\n              with:\n                objectName: \"rest.objectName\"\n                recordId: \"rest.recordId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/query\n          name: query\n          description: \"Execute VQL queries across Vault data\"\n          operations:\n            - method: GET\n              name: execute-vql-query\n              description: \"Run a VQL query to retrieve documents, objects, or user data\"\n              call: \"vault-api.execute-vql-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"List Vault users\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all active users in the Vault\"\n              call: \"vault-api.list-users\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vault-document-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Veeva Vault document lifecycle management.\"\n      tools:\n        - name: list-documents\n          description: \"List all Vault documents accessible to the authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-api.list-documents\"\n          with:\n            limit: \"\
  tools.limit\"\n            offset: \"tools.offset\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-document\n          description: \"Create a new controlled document in Vault with lifecycle and type\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vault-api.create-document\"\n          with:\n            name__v: \"tools.name__v\"\n            type__v: \"tools.type__v\"\n            lifecycle__v: \"tools.lifecycle__v\"\n            status__v: \"tools.status__v\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-document\n          description: \"Retrieve metadata and properties for a specific Vault document by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-api.get-document\"\n          with:\n\
  \            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-document\n          description: \"Update field values on an existing Vault document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vault-api.update-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-document\n          description: \"Permanently delete a Vault document and all its versions\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vault-api.delete-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: perform-document-action\n\
  \          description: \"Execute a lifecycle action on a document (Approve, Submit for Review, Archive)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vault-api.perform-document-action\"\n          with:\n            documentId: \"tools.documentId\"\n            actionName: \"tools.actionName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-object-records\n          description: \"List records for a Vault business object (studies, products, sites, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-api.list-object-records\"\n          with:\n            objectName: \"tools.objectName\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \n        - name: create-object-record\n          description: \"Create a new Vault object record for studies, products, sites, or custom objects\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vault-api.create-object-record\"\n          with:\n            objectName: \"tools.objectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-object-record\n          description: \"Retrieve a single Vault object record by object type and record ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-api.get-object-record\"\n          with:\n            objectName: \"tools.objectName\"\n            recordId: \"tools.recordId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-object-record\n          description: \"Update field values on\
  \ a Vault object record\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vault-api.update-object-record\"\n          with:\n            objectName: \"tools.objectName\"\n            recordId: \"tools.recordId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-object-record\n          description: \"Delete a Vault object record\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vault-api.delete-object-record\"\n          with:\n            objectName: \"tools.objectName\"\n            recordId: \"tools.recordId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: execute-vql-query\n          description: \"Run a VQL query to search documents, objects, users, or workflows in Vault\"\n          hints:\n          \
  \  readOnly: true\n            openWorld: true\n          call: \"vault-api.execute-vql-query\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List all active users in the Vault\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-api.list-users\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veeva/refs/heads/main/capabilities/vault-document-management.yaml
tags:
- Veeva
- Vault
- Life Sciences
- Pharma
- Document Management
- Regulatory
- QMS
- Clinical
tools:
- description: List all Vault documents accessible to the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: list-documents
- description: Create a new controlled document in Vault with lifecycle and type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-document
- description: Retrieve metadata and properties for a specific Vault document by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-document
- description: Update field values on an existing Vault document
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-document
- description: Permanently delete a Vault document and all its versions
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document
- description: Execute a lifecycle action on a document (Approve, Submit for Review, Archive)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: perform-document-action
- description: List records for a Vault business object (studies, products, sites, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-object-records
- description: Create a new Vault object record for studies, products, sites, or custom objects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-object-record
- description: Retrieve a single Vault object record by object type and record ID
  hints:
    openWorld: false
    readOnly: true
  name: get-object-record
- description: Update field values on a Vault object record
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-object-record
- description: Delete a Vault object record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-object-record
- description: Run a VQL query to search documents, objects, users, or workflows in Vault
  hints:
    openWorld: true
    readOnly: true
  name: execute-vql-query
- description: List all active users in the Vault
  hints:
    openWorld: false
    readOnly: true
  name: list-users
---
