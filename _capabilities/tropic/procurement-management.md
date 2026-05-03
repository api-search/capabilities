---
categories: []
consumed_apis:
- tropic
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
- get a specific procurement request by id
- list contracts
- saas procurement
- list procurement requests
- cost optimization
- update a contract
- list procurement requests with optional status filter
- approve a pending procurement request
- tropic
- procurement request management
- create a new vendor contract in tropic
- spend management
- reject a pending request
- list organization users
- create request
- saas management
- list requests
- create webhook
- get request
- supplier relationship management
- create a new supplier profile
- delete contract
- reject a pending procurement request with a reason
- create a new webhook subscription for procurement events
- benchmarking
- list webhook subscriptions
- list configured webhook subscriptions
- contract lifecycle management
- create a new contract record
- create supplier
- update supplier
- individual contract operations
- list all suppliers
- reject request
- submit a new procurement request
- get a request by id
- get contract
- list users
- renewals
- user management
- approval workflows
- create contract
- get a contract by id
- delete a contract
- list webhooks
- update contract details (status, renewal date, value)
- create a new supplier
- approve request
- get a supplier by id
- create a webhook subscription
- update a supplier
- procurement
- list all supplier profiles
- get supplier
- list suppliers
- event webhook management
- list all contracts with optional status and supplier filters
- get a specific contract by id
- update contract
- list all contracts with optional filters
- contract management
- get a specific supplier by id
- list organization users in tropic
- approve a pending request
- supplier management
slug: procurement-management
source_filename: procurement-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tropic Procurement Management\"\n  description: >-\n    Workflow capability for managing the full procurement lifecycle in Tropic —\n    from intake and request approval through contract execution and supplier management.\n    Used by procurement teams, finance managers, and operations leads.\n  tags:\n    - Tropic\n    - Procurement\n    - Contract Management\n    - Supplier Management\n    - Spend Management\n    - Approval Workflows\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TROPIC_API_KEY: TROPIC_API_KEY\n\ncapability:\n  consumes:\n    - import: tropic\n      location: ./shared/tropic-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tropic-procurement-api\n      description: \"Unified REST API for Tropic procurement lifecycle management.\"\n      resources:\n        - path: /v1/contracts\n          name: contracts\n          description:\
  \ \"Contract lifecycle management\"\n          operations:\n            - method: GET\n              name: list-contracts\n              description: \"List all contracts with optional filters\"\n              call: \"tropic.list-contracts\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                status: \"rest.status\"\n                supplier_id: \"rest.supplier_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contract\n              description: \"Create a new contract record\"\n              call: \"tropic.create-contract\"\n              with:\n                name: \"rest.name\"\n                supplier_id: \"rest.supplier_id\"\n                start_date: \"rest.start_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contracts/{id}\n\
  \          name: contract\n          description: \"Individual contract operations\"\n          operations:\n            - method: GET\n              name: get-contract\n              description: \"Get a contract by ID\"\n              call: \"tropic.get-contract\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-contract\n              description: \"Update a contract\"\n              call: \"tropic.update-contract\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-contract\n              description: \"Delete a contract\"\n              call: \"tropic.delete-contract\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supplier relationship management\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List all suppliers\"\n              call: \"tropic.list-suppliers\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-supplier\n              description: \"Create a new supplier\"\n              call: \"tropic.create-supplier\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suppliers/{id}\n          name: supplier\n          operations:\n            - method: GET\n              name: get-supplier\n              description:\
  \ \"Get a supplier by ID\"\n              call: \"tropic.get-supplier\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-supplier\n              description: \"Update a supplier\"\n              call: \"tropic.update-supplier\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests\n          name: requests\n          description: \"Procurement request management\"\n          operations:\n            - method: GET\n              name: list-requests\n              description: \"List procurement requests\"\n              call: \"tropic.list-requests\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: POST\n              name: create-request\n              description: \"Submit a new procurement request\"\n              call: \"tropic.create-request\"\n              with:\n                title: \"rest.title\"\n                amount: \"rest.amount\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests/{id}\n          name: request\n          operations:\n            - method: GET\n              name: get-request\n              description: \"Get a request by ID\"\n              call: \"tropic.get-request\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests/{id}/approve\n          name: request-approve\n          operations:\n            - method: POST\n              name: approve-request\n              description: \"Approve a pending request\"\
  \n              call: \"tropic.approve-request\"\n              with:\n                id: \"rest.id\"\n                notes: \"rest.notes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests/{id}/reject\n          name: request-reject\n          operations:\n            - method: POST\n              name: reject-request\n              description: \"Reject a pending request\"\n              call: \"tropic.reject-request\"\n              with:\n                id: \"rest.id\"\n                reason: \"rest.reason\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Event webhook management\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhook subscriptions\"\n              call: \"tropic.list-webhooks\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a webhook subscription\"\n              call: \"tropic.create-webhook\"\n              with:\n                url: \"rest.url\"\n                events: \"rest.events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List organization users\"\n              call: \"tropic.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tropic-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted procurement\
  \ management in Tropic.\"\n      tools:\n        - name: list-contracts\n          description: \"List all contracts with optional status and supplier filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tropic.list-contracts\"\n          with:\n            status: \"tools.status\"\n            supplier_id: \"tools.supplier_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contract\n          description: \"Get a specific contract by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tropic.get-contract\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-contract\n          description: \"Create a new vendor contract in Tropic\"\n          hints:\n            readOnly: false\n          call: \"tropic.create-contract\"\
  \n          with:\n            name: \"tools.name\"\n            supplier_id: \"tools.supplier_id\"\n            start_date: \"tools.start_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-contract\n          description: \"Update contract details (status, renewal date, value)\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tropic.update-contract\"\n          with:\n            id: \"tools.id\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-suppliers\n          description: \"List all supplier profiles\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tropic.list-suppliers\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-supplier\n\
  \          description: \"Get a specific supplier by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tropic.get-supplier\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-supplier\n          description: \"Create a new supplier profile\"\n          hints:\n            readOnly: false\n          call: \"tropic.create-supplier\"\n          with:\n            name: \"tools.name\"\n            website: \"tools.website\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-requests\n          description: \"List procurement requests with optional status filter\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tropic.list-requests\"\n          with:\n            status: \"tools.status\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-request\n          description: \"Get a specific procurement request by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tropic.get-request\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-request\n          description: \"Submit a new procurement request\"\n          hints:\n            readOnly: false\n          call: \"tropic.create-request\"\n          with:\n            title: \"tools.title\"\n            amount: \"tools.amount\"\n            supplier_id: \"tools.supplier_id\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: approve-request\n          description: \"Approve a pending procurement request\"\n          hints:\n\
  \            readOnly: false\n            idempotent: true\n          call: \"tropic.approve-request\"\n          with:\n            id: \"tools.id\"\n            notes: \"tools.notes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reject-request\n          description: \"Reject a pending procurement request with a reason\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tropic.reject-request\"\n          with:\n            id: \"tools.id\"\n            reason: \"tools.reason\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List configured webhook subscriptions\"\n          hints:\n            readOnly: true\n          call: \"tropic.list-webhooks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description:\
  \ \"Create a new webhook subscription for procurement events\"\n          hints:\n            readOnly: false\n          call: \"tropic.create-webhook\"\n          with:\n            url: \"tools.url\"\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List organization users in Tropic\"\n          hints:\n            readOnly: true\n          call: \"tropic.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
