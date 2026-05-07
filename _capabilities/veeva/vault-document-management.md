---
categories: []
consumed_apis: []
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
- create a new vault document record
- permanently delete a vault document and all its versions
- regulatory
- list records for a vault business object (studies, products, sites, etc.)
- list and create vault object records (studies, products, sites)
- retrieve a single vault object record by object type and record id
- execute a lifecycle action on a document (approve, submit for review, archive)
- get, update, or delete a specific vault object record
- document management
- create a new vault object record for studies, products, sites, or custom objects
- get, update, or delete a specific vault document
- create document
- update a vault document's field values
- list vault users
- list object records
- delete a vault object record
- vault
- execute a lifecycle action (approve, submit for review, archive)
- create a new controlled document in vault with lifecycle and type
- run a vql query to search documents, objects, users, or workflows in vault
- pharma
- update document
- create object record
- get object record
- get document
- retrieve metadata and properties for a specific vault document by id
- execute vql queries across vault data
- clinical
- veeva
- delete object record
- execute vql query
- list users
- retrieve metadata for a specific vault document
- update field values on a vault object record
- life sciences
- perform lifecycle actions on a vault document
- list all active users in the vault
- qms
- update object record
- retrieve a single vault object record
- list records for a vault business object
- update fields on a vault object record
- run a vql query to retrieve documents, objects, or user data
- perform document action
- update field values on an existing vault document
- list documents
- delete a vault document and all its versions
- create a new vault object record
- list and create vault documents
- delete document
- list all vault documents accessible to the authenticated user
slug: vault-document-management
source_filename: vault-document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Veeva Vault Document Management\n  description: Customer workflow capability for life sciences document lifecycle management in Veeva Vault. Combines document\n    CRUD, lifecycle actions, VQL queries, and object management for regulatory affairs teams, QMS coordinators, and clinical\n    operations staff managing controlled documents through approval and archival workflows.\n  tags:\n  - Veeva\n  - Vault\n  - Life Sciences\n  - Pharma\n  - Document Management\n  - Regulatory\n  - QMS\n  - Clinical\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VEEVA_VAULT_SESSION_ID: VEEVA_VAULT_SESSION_ID\n    VEEVA_VAULT_DOMAIN: VEEVA_VAULT_DOMAIN\ncapability:\n  consumes:\n  - type: http\n    namespace: vault-api\n    baseUri: https://{{env.VEEVA_VAULT_DOMAIN}}/api/v25.3\n    description: Veeva Vault REST API v25.3\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{env.VEEVA_VAULT_SESSION_ID}}'\n\
  \      placement: header\n    resources:\n    - name: authentication\n      path: /auth\n      description: Session management — authenticate and obtain Vault session IDs\n      operations:\n      - name: authenticate-user\n        method: POST\n        description: Authenticate with username and password to obtain a Vault session ID\n        inputParameters:\n        - name: username\n          in: body\n          type: string\n          required: true\n          description: Vault username (email address)\n        - name: password\n          in: body\n          type: string\n          required: true\n          description: Vault password\n        - name: vaultDNS\n          in: body\n          type: string\n          required: false\n          description: Target Vault DNS for multi-vault environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /objects/documents\n \
  \     description: Document lifecycle management — list, create, retrieve, update, and delete documents\n      operations:\n      - name: list-documents\n        method: GET\n        description: List all documents accessible to the authenticated user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (default 200, max 1000)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field and direction (e.g. name__v asc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-document\n        method: POST\n        description: Create a new document record in Vault with optional\
  \ source file upload\n        inputParameters:\n        - name: name__v\n          in: body\n          type: string\n          required: true\n          description: Document name\n        - name: type__v\n          in: body\n          type: string\n          required: true\n          description: Document type API name\n        - name: lifecycle__v\n          in: body\n          type: string\n          required: true\n          description: Document lifecycle API name\n        - name: status__v\n          in: body\n          type: string\n          required: false\n          description: Initial lifecycle state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document\n      path: /objects/documents/{documentId}\n      description: Single document operations — get, update, delete\n      operations:\n      - name: get-document\n        method: GET\n        description: Retrieve metadata and properties\
  \ for a specific document\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Vault document ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-document\n        method: PUT\n        description: Update document field values\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Vault document ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-document\n        method: DELETE\n        description: Delete a document and all versions\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Vault document ID\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document-actions\n      path: /objects/documents/{documentId}/actions/{actionName}\n      description: Document lifecycle actions — perform state transitions\n      operations:\n      - name: perform-document-action\n        method: POST\n        description: Execute a user action on a document to change its lifecycle state\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Vault document ID\n        - name: actionName\n          in: path\n          type: string\n          required: true\n          description: Lifecycle action API name (e.g. Approve, Submit for Review)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /vobjects/{objectName}\n \
  \     description: Vault object records — list and create configurable business entities\n      operations:\n      - name: list-object-records\n        method: GET\n        description: Return records for a Vault object (studies, products, sites, etc.)\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Vault object API name (e.g. study__v)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: create-object-record\n        method: POST\n        description: Create a new record for the specified Vault object\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Vault object API name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-record\n      path: /vobjects/{objectName}/{recordId}\n      description: Single object record operations — get, update, delete\n      operations:\n      - name: get-object-record\n        method: GET\n        description: Return a single record for a Vault object\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Vault object API name\n        - name: recordId\n          in: path\n          type: string\n          required: true\n     \
  \     description: Object record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-object-record\n        method: PUT\n        description: Update fields on an existing Vault object record\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Vault object API name\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: Object record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-object-record\n        method: DELETE\n        description: Delete a specific Vault object record\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Vault object\
  \ API name\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: Object record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /query\n      description: VQL query execution — SQL-like queries across documents, objects, and users\n      operations:\n      - name: execute-vql-query\n        method: GET\n        description: Execute a Vault Query Language (VQL) query to retrieve Vault data\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: VQL query string (e.g. SELECT id, name__v FROM documents)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /objects/users\n      description: User management — list Vault users\n\
  \      operations:\n      - name: list-users\n        method: GET\n        description: Return all active users in the Vault\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum users to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vault-document-management-api\n    description: Unified REST API for Veeva Vault document lifecycle management workflows.\n    resources:\n    - path: /v1/documents\n      name: documents\n      description: List and create Vault documents\n      operations:\n      - method: GET\n        name: list-documents\n        description: List all Vault documents accessible to the authenticated\
  \ user\n        call: vault-api.list-documents\n        with:\n          limit: rest.limit\n          offset: rest.offset\n          sort: rest.sort\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-document\n        description: Create a new Vault document record\n        call: vault-api.create-document\n        with:\n          name__v: rest.name__v\n          type__v: rest.type__v\n          lifecycle__v: rest.lifecycle__v\n          status__v: rest.status__v\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{documentId}\n      name: document\n      description: Get, update, or delete a specific Vault document\n      operations:\n      - method: GET\n        name: get-document\n        description: Retrieve metadata for a specific Vault document\n        call: vault-api.get-document\n        with:\n          documentId: rest.documentId\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n      - method: PUT\n        name: update-document\n        description: Update a Vault document's field values\n        call: vault-api.update-document\n        with:\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-document\n        description: Delete a Vault document and all its versions\n        call: vault-api.delete-document\n        with:\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{documentId}/actions/{actionName}\n      name: document-actions\n      description: Perform lifecycle actions on a Vault document\n      operations:\n      - method: POST\n        name: perform-document-action\n        description: Execute a lifecycle action (Approve, Submit for Review, Archive)\n        call: vault-api.perform-document-action\n      \
  \  with:\n          documentId: rest.documentId\n          actionName: rest.actionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects/{objectName}\n      name: objects\n      description: List and create Vault object records (studies, products, sites)\n      operations:\n      - method: GET\n        name: list-object-records\n        description: List records for a Vault business object\n        call: vault-api.list-object-records\n        with:\n          objectName: rest.objectName\n          limit: rest.limit\n          offset: rest.offset\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-object-record\n        description: Create a new Vault object record\n        call: vault-api.create-object-record\n        with:\n          objectName: rest.objectName\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/objects/{objectName}/{recordId}\n      name: object-record\n      description: Get, update, or delete a specific Vault object record\n      operations:\n      - method: GET\n        name: get-object-record\n        description: Retrieve a single Vault object record\n        call: vault-api.get-object-record\n        with:\n          objectName: rest.objectName\n          recordId: rest.recordId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-object-record\n        description: Update fields on a Vault object record\n        call: vault-api.update-object-record\n        with:\n          objectName: rest.objectName\n          recordId: rest.recordId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object-record\n        description: Delete a Vault object record\n        call: vault-api.delete-object-record\n        with:\n          objectName:\
  \ rest.objectName\n          recordId: rest.recordId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: Execute VQL queries across Vault data\n      operations:\n      - method: GET\n        name: execute-vql-query\n        description: Run a VQL query to retrieve documents, objects, or user data\n        call: vault-api.execute-vql-query\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: List Vault users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all active users in the Vault\n        call: vault-api.list-users\n        with:\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vault-document-management-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Veeva Vault document lifecycle management.\n    tools:\n    - name: list-documents\n      description: List all Vault documents accessible to the authenticated user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-api.list-documents\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        sort: tools.sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-document\n      description: Create a new controlled document in Vault with lifecycle and type\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vault-api.create-document\n      with:\n        name__v: tools.name__v\n        type__v: tools.type__v\n        lifecycle__v: tools.lifecycle__v\n        status__v: tools.status__v\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n   \
  \   description: Retrieve metadata and properties for a specific Vault document by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-api.get-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-document\n      description: Update field values on an existing Vault document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vault-api.update-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Permanently delete a Vault document and all its versions\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vault-api.delete-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: perform-document-action\n      description: Execute a lifecycle action on a document (Approve, Submit for Review, Archive)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vault-api.perform-document-action\n      with:\n        documentId: tools.documentId\n        actionName: tools.actionName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-object-records\n      description: List records for a Vault business object (studies, products, sites, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-api.list-object-records\n      with:\n        objectName: tools.objectName\n        limit: tools.limit\n        offset: tools.offset\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-object-record\n      description: Create a new Vault object record for studies, products, sites, or\
  \ custom objects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vault-api.create-object-record\n      with:\n        objectName: tools.objectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object-record\n      description: Retrieve a single Vault object record by object type and record ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-api.get-object-record\n      with:\n        objectName: tools.objectName\n        recordId: tools.recordId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-object-record\n      description: Update field values on a Vault object record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vault-api.update-object-record\n      with:\n        objectName: tools.objectName\n        recordId: tools.recordId\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: delete-object-record\n      description: Delete a Vault object record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vault-api.delete-object-record\n      with:\n        objectName: tools.objectName\n        recordId: tools.recordId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-vql-query\n      description: Run a VQL query to search documents, objects, users, or workflows in Vault\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vault-api.execute-vql-query\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all active users in the Vault\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-api.list-users\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
