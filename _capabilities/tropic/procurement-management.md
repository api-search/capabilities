---
categories: []
consumed_apis: []
description: Workflow capability for managing the full procurement lifecycle in Tropic — from intake and request approval through contract execution and supplier management. Used by procurement teams, finance managers, and operations leads.
layout: capability
name: Tropic Procurement Management
operations:
- description: List all contracts with optional filters
  method: GET
  name: list-contracts
  path: /v1/contracts
- description: Create a new contract record
  method: POST
  name: create-contract
  path: /v1/contracts
- description: Get a contract by ID
  method: GET
  name: get-contract
  path: /v1/contracts/{id}
- description: Update a contract
  method: PUT
  name: update-contract
  path: /v1/contracts/{id}
- description: Delete a contract
  method: DELETE
  name: delete-contract
  path: /v1/contracts/{id}
- description: List all suppliers
  method: GET
  name: list-suppliers
  path: /v1/suppliers
- description: Create a new supplier
  method: POST
  name: create-supplier
  path: /v1/suppliers
- description: Get a supplier by ID
  method: GET
  name: get-supplier
  path: /v1/suppliers/{id}
- description: Update a supplier
  method: PUT
  name: update-supplier
  path: /v1/suppliers/{id}
- description: List procurement requests
  method: GET
  name: list-requests
  path: /v1/requests
- description: Submit a new procurement request
  method: POST
  name: create-request
  path: /v1/requests
- description: Get a request by ID
  method: GET
  name: get-request
  path: /v1/requests/{id}
- description: Approve a pending request
  method: POST
  name: approve-request
  path: /v1/requests/{id}/approve
- description: Reject a pending request
  method: POST
  name: reject-request
  path: /v1/requests/{id}/reject
- description: List webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook subscription
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: List organization users
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Tropic
provider_slug: tropic
search_terms:
- contract management
- list organization users
- reject a pending procurement request with a reason
- procurement
- update a contract
- list suppliers
- individual contract operations
- list all supplier profiles
- renewals
- list all suppliers
- approve a pending procurement request
- tropic
- update a supplier
- list all contracts with optional status and supplier filters
- event webhook management
- get contract
- create a new supplier profile
- cost optimization
- list organization users in tropic
- create webhook
- get a specific supplier by id
- reject request
- approve a pending request
- get supplier
- update contract
- supplier relationship management
- saas management
- get a contract by id
- procurement request management
- reject a pending request
- list contracts
- list users
- get a specific contract by id
- spend management
- create a new webhook subscription for procurement events
- create a new vendor contract in tropic
- benchmarking
- delete a contract
- create a new supplier
- list webhooks
- update supplier
- create supplier
- list procurement requests
- get request
- update contract details (status, renewal date, value)
- approval workflows
- create a new contract record
- create a webhook subscription
- user management
- create contract
- get a supplier by id
- create request
- list all contracts with optional filters
- list procurement requests with optional status filter
- supplier management
- submit a new procurement request
- list webhook subscriptions
- contract lifecycle management
- list requests
- get a specific procurement request by id
- list configured webhook subscriptions
- saas procurement
- get a request by id
- approve request
- delete contract
slug: procurement-management
source_filename: procurement-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tropic Procurement Management\n  description: Workflow capability for managing the full procurement lifecycle in Tropic — from intake and request approval\n    through contract execution and supplier management. Used by procurement teams, finance managers, and operations leads.\n  tags:\n  - Tropic\n  - Procurement\n  - Contract Management\n  - Supplier Management\n  - Spend Management\n  - Approval Workflows\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TROPIC_API_KEY: TROPIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tropic\n    baseUri: https://api.tropicapp.io/v1\n    description: Tropic procurement and spend management API\n    authentication:\n      type: bearer\n      token: '{{TROPIC_API_KEY}}'\n    resources:\n    - name: contracts\n      path: /contracts\n      description: Contract lifecycle management\n      operations:\n      - name: list-contracts\n     \
  \   method: GET\n        description: List all contracts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: supplier_id\n          in: query\n          type: string\n          required: false\n          description: Filter by supplier ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contract\n        method: POST\n        description: Create a new contract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            name: '{{tools.name}}'\n            supplier_id: '{{tools.supplier_id}}'\n            start_date: '{{tools.start_date}}'\n            end_date: '{{tools.end_date}}'\n            total_value: '{{tools.total_value}}'\n    - name: contract\n      path: /contracts/{id}\n      description: Individual contract operations\n      operations:\n      - name: get-contract\n        method: GET\n        description: Get contract by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contract ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contract\n        method: PUT\n        description: Update an existing contract\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contract\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            renewal_date: '{{tools.renewal_date}}'\n            total_value: '{{tools.total_value}}'\n      - name: delete-contract\n        method: DELETE\n        description: Delete a contract\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suppliers\n      path: /suppliers\n      description: Supplier profile management\n      operations:\n      - name: list-suppliers\n        method: GET\n        description: List all suppliers\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n     \
  \   - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-supplier\n        method: POST\n        description: Create a new supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            website: '{{tools.website}}'\n            category: '{{tools.category}}'\n    - name: supplier\n      path: /suppliers/{id}\n      description: Individual supplier operations\n      operations:\n      - name: get-supplier\n        method: GET\n        description: Get supplier by ID\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-supplier\n        method: PUT\n        description: Update a supplier\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            status: '{{tools.status}}'\n    - name: requests\n      path: /requests\n      description: Procurement request management\n      operations:\n      - name: list-requests\n        method: GET\n        description: List procurement requests\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n\
  \        - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-request\n        method: POST\n        description: Create a procurement request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            amount: '{{tools.amount}}'\n            supplier_id: '{{tools.supplier_id}}'\n            category: '{{tools.category}}'\n    - name: request\n      path: /requests/{id}\n      description: Individual request operations\n      operations:\n      - name: get-request\n        method: GET\n        description: Get request by ID\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: request-approve\n      path: /requests/{id}/approve\n      description: Approve a procurement request\n      operations:\n      - name: approve-request\n        method: POST\n        description: Approve a pending request\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            notes: '{{tools.notes}}'\n    - name: request-reject\n      path: /requests/{id}/reject\n      description: Reject a procurement request\n      operations:\n      - name: reject-request\n        method: POST\n        description: Reject a\
  \ pending request\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reason: '{{tools.reason}}'\n    - name: webhooks\n      path: /webhooks\n      description: Webhook subscription management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n\
  \            events: '{{tools.events}}'\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List organization users\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tropic-procurement-api\n    description: Unified REST API for Tropic procurement lifecycle management.\n    resources:\n    - path: /v1/contracts\n      name: contracts\n      description: Contract lifecycle management\n      operations:\n      - method: GET\n        name: list-contracts\n        description: List all contracts with optional filters\n        call:\
  \ tropic.list-contracts\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          status: rest.status\n          supplier_id: rest.supplier_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contract\n        description: Create a new contract record\n        call: tropic.create-contract\n        with:\n          name: rest.name\n          supplier_id: rest.supplier_id\n          start_date: rest.start_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts/{id}\n      name: contract\n      description: Individual contract operations\n      operations:\n      - method: GET\n        name: get-contract\n        description: Get a contract by ID\n        call: tropic.get-contract\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-contract\n\
  \        description: Update a contract\n        call: tropic.update-contract\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-contract\n        description: Delete a contract\n        call: tropic.delete-contract\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suppliers\n      name: suppliers\n      description: Supplier relationship management\n      operations:\n      - method: GET\n        name: list-suppliers\n        description: List all suppliers\n        call: tropic.list-suppliers\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-supplier\n        description: Create a new supplier\n        call: tropic.create-supplier\n        with:\n          name: rest.name\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/suppliers/{id}\n      name: supplier\n      operations:\n      - method: GET\n        name: get-supplier\n        description: Get a supplier by ID\n        call: tropic.get-supplier\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-supplier\n        description: Update a supplier\n        call: tropic.update-supplier\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests\n      name: requests\n      description: Procurement request management\n      operations:\n      - method: GET\n        name: list-requests\n        description: List procurement requests\n        call: tropic.list-requests\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n   \
  \     name: create-request\n        description: Submit a new procurement request\n        call: tropic.create-request\n        with:\n          title: rest.title\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests/{id}\n      name: request\n      operations:\n      - method: GET\n        name: get-request\n        description: Get a request by ID\n        call: tropic.get-request\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests/{id}/approve\n      name: request-approve\n      operations:\n      - method: POST\n        name: approve-request\n        description: Approve a pending request\n        call: tropic.approve-request\n        with:\n          id: rest.id\n          notes: rest.notes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests/{id}/reject\n      name: request-reject\n\
  \      operations:\n      - method: POST\n        name: reject-request\n        description: Reject a pending request\n        call: tropic.reject-request\n        with:\n          id: rest.id\n          reason: rest.reason\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Event webhook management\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhook subscriptions\n        call: tropic.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a webhook subscription\n        call: tropic.create-webhook\n        with:\n          url: rest.url\n          events: rest.events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n\
  \      - method: GET\n        name: list-users\n        description: List organization users\n        call: tropic.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tropic-procurement-mcp\n    transport: http\n    description: MCP server for AI-assisted procurement management in Tropic.\n    tools:\n    - name: list-contracts\n      description: List all contracts with optional status and supplier filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tropic.list-contracts\n      with:\n        status: tools.status\n        supplier_id: tools.supplier_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contract\n      description: Get a specific contract by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tropic.get-contract\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: create-contract\n      description: Create a new vendor contract in Tropic\n      hints:\n        readOnly: false\n      call: tropic.create-contract\n      with:\n        name: tools.name\n        supplier_id: tools.supplier_id\n        start_date: tools.start_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contract\n      description: Update contract details (status, renewal date, value)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: tropic.update-contract\n      with:\n        id: tools.id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-suppliers\n      description: List all supplier profiles\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tropic.list-suppliers\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-supplier\n\
  \      description: Get a specific supplier by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tropic.get-supplier\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-supplier\n      description: Create a new supplier profile\n      hints:\n        readOnly: false\n      call: tropic.create-supplier\n      with:\n        name: tools.name\n        website: tools.website\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requests\n      description: List procurement requests with optional status filter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tropic.list-requests\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-request\n      description: Get a specific procurement request by ID\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: tropic.get-request\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-request\n      description: Submit a new procurement request\n      hints:\n        readOnly: false\n      call: tropic.create-request\n      with:\n        title: tools.title\n        amount: tools.amount\n        supplier_id: tools.supplier_id\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-request\n      description: Approve a pending procurement request\n      hints:\n        readOnly: false\n        idempotent: true\n      call: tropic.approve-request\n      with:\n        id: tools.id\n        notes: tools.notes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reject-request\n      description: Reject a pending procurement request with a reason\n      hints:\n        readOnly: false\n     \
  \   idempotent: true\n      call: tropic.reject-request\n      with:\n        id: tools.id\n        reason: tools.reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List configured webhook subscriptions\n      hints:\n        readOnly: true\n      call: tropic.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Create a new webhook subscription for procurement events\n      hints:\n        readOnly: false\n      call: tropic.create-webhook\n      with:\n        url: tools.url\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List organization users in Tropic\n      hints:\n        readOnly: true\n      call: tropic.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tropic/refs/heads/main/capabilities/procurement-management.yaml
tags:
- Tropic
- Procurement
- Contract Management
- Supplier Management
- Spend Management
- Approval Workflows
tools:
- description: List all contracts with optional status and supplier filters
  hints:
    openWorld: true
    readOnly: true
  name: list-contracts
- description: Get a specific contract by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-contract
- description: Create a new vendor contract in Tropic
  hints:
    readOnly: false
  name: create-contract
- description: Update contract details (status, renewal date, value)
  hints:
    idempotent: true
    readOnly: false
  name: update-contract
- description: List all supplier profiles
  hints:
    openWorld: true
    readOnly: true
  name: list-suppliers
- description: Get a specific supplier by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-supplier
- description: Create a new supplier profile
  hints:
    readOnly: false
  name: create-supplier
- description: List procurement requests with optional status filter
  hints:
    openWorld: true
    readOnly: true
  name: list-requests
- description: Get a specific procurement request by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-request
- description: Submit a new procurement request
  hints:
    readOnly: false
  name: create-request
- description: Approve a pending procurement request
  hints:
    idempotent: true
    readOnly: false
  name: approve-request
- description: Reject a pending procurement request with a reason
  hints:
    idempotent: true
    readOnly: false
  name: reject-request
- description: List configured webhook subscriptions
  hints:
    readOnly: true
  name: list-webhooks
- description: Create a new webhook subscription for procurement events
  hints:
    readOnly: false
  name: create-webhook
- description: List organization users in Tropic
  hints:
    readOnly: true
  name: list-users
---
