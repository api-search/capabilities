---
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
- procurement
- manages strategic sourcing events, rfx processes, and contract workflows.
- reviews and approves or denies sourcing documents, events, and contracts.
- ariba
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
- deny task
- get task
- pending approval tasks.
- contracts
- approval task state changes.
- get sourcing document
- list sap ariba sourcing approval tasks that have recently changed state.
- approval group members.
- list pending sap ariba sourcing approval tasks awaiting action.
- list changes
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- get document
- list approval group members
- list pending
- approvals
- submit approve or deny action.
- external approval workflow for sourcing projects, contracts, and supplier management
- list pending approval tasks.
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
- get task details
- list members of an sap ariba approval group to identify eligible approvers.
- sap
- submit action
- b2b
- get details for a specific sap ariba sourcing approval task including approvers.
- approval actions.
- approval task details.
- supplier management
- approvable documents.
- supply chain
- rfx
- list group members.
- rfx events, auctions, and sourcing projects requiring approval.
- supplier management projects requiring external approval.
- get approvable document details.
- list members
- Sourcing Manager
- get approval task details.
- list pending approvals
- Procurement Approver
- sourcing
- list approval changes
- contract workspaces and contract content requiring approval.
- auctions
- list changed approval tasks.
- approve task
slug: sourcing-approvals
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
