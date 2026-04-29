---
api_specs:
- filename: supply-chain-management.yml
  format: yaml
  label: scm
  slug: scm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/supply-chain-management.yml
- filename: approval-workflow-engine.yml
  format: yaml
  label: approval-workflow
  slug: approval-workflow
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/approval-workflow-engine.yml
categories:
- procurement-supply-chain
consumed_apis:
- scm
- approval-workflow
description: Unified workflow for supply chain managers combining procurement, inventory, order fulfillment, and approval workflows across PeopleSoft Supply Chain Management and Approval Workflow Engine APIs.
layout: capability
name: PeopleSoft Supply Chain And Procurement
operations:
- description: Retrieve procurement requisitions.
  method: GET
  name: list-requisitions
  path: /v1/requisitions
- description: Retrieve purchase orders.
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: Retrieve inventory items and stock levels.
  method: GET
  name: list-inventory-items
  path: /v1/inventory-items
- description: Retrieve order fulfillment records.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Retrieve pending supply chain approval requests.
  method: GET
  name: list-pending-approvals
  path: /v1/approvals
- description: Approve, deny, or push back a supply chain approval request.
  method: PUT
  name: process-approval
  path: /v1/approvals/{approvalId}
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- list inventory items
- retrieve pending supply chain approval requests.
- campus solutions.
- inventory
- supply chain approval requests
- enterprise software
- crm
- inventory items and stock levels
- individual approval operations
- supply chain
- human capital management.
- list requisitions
- hcm
- order fulfillment records
- process approval
- order fulfillment
- purchase orders
- procurement
- erp
- financial management
- financial and supply chain management.
- list pending approvals
- supply chain management
- retrieve inventory items and stock levels.
- retrieve order fulfillment records.
- campus solutions
- peopletools platform services.
- peoplesoft
- retrieve procurement requisitions.
- approve, deny, or push back a supply chain approval request.
- list purchase orders
- list orders
- procurement requisitions
- retrieve purchase orders.
slug: supply-chain-and-procurement
source_filename: supply-chain-and-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Supply Chain And Procurement\"\n  description: \"Unified workflow for supply chain managers combining procurement, inventory, order fulfillment, and approval workflows across PeopleSoft Supply Chain Management and Approval Workflow Engine APIs.\"\n  tags:\n    - PeopleSoft\n    - Supply Chain\n    - Procurement\n    - Inventory\n    - Order Fulfillment\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: scm\n      location: ./shared/supply-chain-management.yaml\n    - import: approval-workflow\n      location: ./shared/approval-workflow-engine.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: supply-chain-api\n      description: \"Unified REST API for PeopleSoft supply chain and procurement workflows.\"\n      resources:\n\
  \        - path: /v1/requisitions\n          name: requisitions\n          description: \"Procurement requisitions\"\n          operations:\n            - method: GET\n              name: list-requisitions\n              description: \"Retrieve procurement requisitions.\"\n              call: \"scm.list-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/purchase-orders\n          name: purchase-orders\n          description: \"Purchase orders\"\n          operations:\n            - method: GET\n              name: list-purchase-orders\n              description: \"Retrieve purchase orders.\"\n              call: \"scm.list-purchase-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory-items\n          name: inventory-items\n          description: \"Inventory items and stock levels\"\n          operations:\n          \
  \  - method: GET\n              name: list-inventory-items\n              description: \"Retrieve inventory items and stock levels.\"\n              call: \"scm.list-inventory-items\"\n              with:\n                businessUnit: \"rest.businessUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Order fulfillment records\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"Retrieve order fulfillment records.\"\n              call: \"scm.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals\n          name: approvals\n          description: \"Supply chain approval requests\"\n          operations:\n            - method: GET\n              name: list-pending-approvals\n              description: \"Retrieve\
  \ pending supply chain approval requests.\"\n              call: \"approval-workflow.list-pending-approvals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals/{approvalId}\n          name: approval-detail\n          description: \"Individual approval operations\"\n          operations:\n            - method: PUT\n              name: process-approval\n              description: \"Approve, deny, or push back a supply chain approval request.\"\n              call: \"approval-workflow.process-approval\"\n              with:\n                approvalId: \"rest.approvalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: supply-chain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PeopleSoft supply chain and procurement workflows.\"\n      tools:\n        - name: list-requisitions\n\
  \          description: \"Retrieve procurement requisitions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scm.list-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-purchase-orders\n          description: \"Retrieve purchase orders.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scm.list-purchase-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inventory-items\n          description: \"Retrieve inventory items and stock levels.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scm.list-inventory-items\"\n          with:\n            businessUnit: \"tools.businessUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description:\
  \ \"Retrieve order fulfillment records.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scm.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pending-approvals\n          description: \"Retrieve pending supply chain approval requests.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"approval-workflow.list-pending-approvals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-approval\n          description: \"Approve, deny, or push back a supply chain approval request.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"approval-workflow.process-approval\"\n          with:\n            approvalId: \"tools.approvalId\"\n            action: \"tools.action\"\n            comments: \"tools.comments\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/supply-chain-and-procurement.yaml
tags:
- PeopleSoft
- Supply Chain
- Procurement
- Inventory
- Order Fulfillment
tools:
- description: Retrieve procurement requisitions.
  hints:
    openWorld: true
    readOnly: true
  name: list-requisitions
- description: Retrieve purchase orders.
  hints:
    openWorld: true
    readOnly: true
  name: list-purchase-orders
- description: Retrieve inventory items and stock levels.
  hints:
    openWorld: true
    readOnly: true
  name: list-inventory-items
- description: Retrieve order fulfillment records.
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Retrieve pending supply chain approval requests.
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-approvals
- description: Approve, deny, or push back a supply chain approval request.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: process-approval
---
