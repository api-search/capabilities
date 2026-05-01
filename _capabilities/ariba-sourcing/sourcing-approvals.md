---
categories:
- procurement-supply-chain
consumed_apis:
- ariba-sourcing-approval
description: Workflow for managing external approval tasks in SAP Ariba strategic sourcing projects, contracts, and supplier management. Used by procurement approvers and sourcing managers.
layout: capability
name: Ariba Sourcing - Sourcing Approvals
operations:
- description: List changed approval tasks.
  method: GET
  name: list-changes
  path: /v1/changes
- description: List pending approval tasks.
  method: GET
  name: list-pending
  path: /v1/pending-approvables
- description: Get approval task details.
  method: GET
  name: get-task
  path: /v1/tasks/{taskId}
- description: Get approvable document details.
  method: GET
  name: get-document
  path: /v1/documents/{entityType}/{entityId}
- description: Submit approve or deny action.
  method: POST
  name: submit-action
  path: /v1/actions
- description: List group members.
  method: GET
  name: list-members
  path: /v1/groups/{groupId}/members
personas: []
provider_name: Ariba Sourcing
provider_slug: ariba-sourcing
search_terms:
- list sap ariba sourcing approval tasks that have recently changed state.
- pending approval tasks.
- submit approve or deny action.
- contract workspaces and contract content requiring approval.
- list group members.
- sap
- Sourcing Manager
- approvable documents.
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
- approval task details.
- Procurement Approver
- supplier management projects requiring external approval.
- approval group members.
- list pending approvals
- get details for a specific sap ariba sourcing approval task including approvers.
- deny task
- get task
- list approval changes
- sourcing
- list members of an sap ariba approval group to identify eligible approvers.
- list members
- supply chain
- list changed approval tasks.
- approval actions.
- b2b
- approve task
- get document
- ariba
- submit action
- external approval workflow for sourcing projects, contracts, and supplier management
- auctions
- get approval task details.
- list approval group members
- list pending
- get task details
- get sourcing document
- list changes
- approval task state changes.
- list pending approval tasks.
- rfx
- approvals
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
- procurement
- get approvable document details.
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- rfx events, auctions, and sourcing projects requiring approval.
- reviews and approves or denies sourcing documents, events, and contracts.
- supplier management
- manages strategic sourcing events, rfx processes, and contract workflows.
- contracts
- list pending sap ariba sourcing approval tasks awaiting action.
slug: sourcing-approvals
source_filename: sourcing-approvals.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ariba Sourcing - Sourcing Approvals\"\n  description: \"Workflow for managing external approval tasks in SAP Ariba strategic sourcing projects, contracts, and supplier management. Used by procurement approvers and sourcing managers.\"\n  tags:\n    - Approvals\n    - Ariba\n    - Contracts\n    - Procurement\n    - SAP\n    - Sourcing\n    - Supplier Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ARIBA_SOURCING_OAUTH_TOKEN: ARIBA_SOURCING_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: ariba-sourcing-approval\n      location: ./shared/external-approval-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ariba-sourcing-workflow-api\n      description: \"Unified REST API for SAP Ariba Sourcing external approval workflows.\"\n      resources:\n        - path: /v1/changes\n          name: changes\n          description: \"Approval task\
  \ state changes.\"\n          operations:\n            - method: GET\n              name: list-changes\n              description: \"List changed approval tasks.\"\n              call: \"ariba-sourcing-approval.list-approval-changes\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pending-approvables\n          name: pending-approvables\n          description: \"Pending approval tasks.\"\n          operations:\n            - method: GET\n              name: list-pending\n              description: \"List pending approval tasks.\"\n              call: \"ariba-sourcing-approval.list-pending-approvables\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks/{taskId}\n          name: task-details\n          description: \"Approval\
  \ task details.\"\n          operations:\n            - method: GET\n              name: get-task\n              description: \"Get approval task details.\"\n              call: \"ariba-sourcing-approval.get-approval-task\"\n              with:\n                entity_id: \"rest.taskId\"\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{entityType}/{entityId}\n          name: approvable-documents\n          description: \"Approvable documents.\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Get approvable document details.\"\n              call: \"ariba-sourcing-approval.get-approvable-document\"\n              with:\n                entity_type: \"rest.entityType\"\n                entity_id: \"rest.entityId\"\n                realm: \"rest.realm\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n        - path: /v1/actions\n          name: actions\n          description: \"Approval actions.\"\n          operations:\n            - method: POST\n              name: submit-action\n              description: \"Submit approve or deny action.\"\n              call: \"ariba-sourcing-approval.submit-approval-action\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/members\n          name: group-members\n          description: \"Approval group members.\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List group members.\"\n              call: \"ariba-sourcing-approval.list-group-members\"\n              with:\n                group_id: \"rest.groupId\"\n                realm: \"rest.realm\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ariba-sourcing-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Ariba sourcing approval workflows.\"\n      tools:\n        - name: list-approval-changes\n          description: \"List SAP Ariba sourcing approval tasks that have recently changed state.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-sourcing-approval.list-approval-changes\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pending-approvals\n          description: \"List pending SAP Ariba sourcing approval tasks awaiting action.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-sourcing-approval.list-pending-approvables\"\n          with:\n  \
  \          realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task-details\n          description: \"Get details for a specific SAP Ariba sourcing approval task including approvers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-sourcing-approval.get-approval-task\"\n          with:\n            entity_id: \"tools.taskId\"\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sourcing-document\n          description: \"Get details about an SAP Ariba approvable sourcing document, RFX event, or contract workspace.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-sourcing-approval.get-approvable-document\"\n          with:\n            entity_type: \"tools.entityType\"\n            entity_id: \"tools.entityId\"\n\
  \            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: approve-task\n          description: \"Approve an SAP Ariba sourcing approval task on behalf of an authorized approver.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"ariba-sourcing-approval.submit-approval-action\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deny-task\n          description: \"Deny an SAP Ariba sourcing approval task on behalf of an authorized approver.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"ariba-sourcing-approval.submit-approval-action\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-approval-group-members\n          description: \"List members of an SAP Ariba approval group to identify eligible approvers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-sourcing-approval.list-group-members\"\n          with:\n            group_id: \"tools.groupId\"\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ariba-sourcing/refs/heads/main/capabilities/sourcing-approvals.yaml
tags:
- Approvals
- Ariba
- Contracts
- Procurement
- SAP
- Sourcing
- Supplier Management
tools:
- description: List SAP Ariba sourcing approval tasks that have recently changed state.
  hints:
    openWorld: false
    readOnly: true
  name: list-approval-changes
- description: List pending SAP Ariba sourcing approval tasks awaiting action.
  hints:
    openWorld: false
    readOnly: true
  name: list-pending-approvals
- description: Get details for a specific SAP Ariba sourcing approval task including approvers.
  hints:
    openWorld: false
    readOnly: true
  name: get-task-details
- description: Get details about an SAP Ariba approvable sourcing document, RFX event, or contract workspace.
  hints:
    openWorld: false
    readOnly: true
  name: get-sourcing-document
- description: Approve an SAP Ariba sourcing approval task on behalf of an authorized approver.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approve-task
- description: Deny an SAP Ariba sourcing approval task on behalf of an authorized approver.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deny-task
- description: List members of an SAP Ariba approval group to identify eligible approvers.
  hints:
    openWorld: false
    readOnly: true
  name: list-approval-group-members
---
