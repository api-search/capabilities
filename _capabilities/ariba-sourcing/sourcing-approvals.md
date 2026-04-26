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
- get document
- approval task details.
- list members
- rfx events, auctions, and sourcing projects requiring approval.
- list changed approval tasks.
- approvable documents.
- get task details
- deny task
- list sap ariba sourcing approval tasks that have recently changed state.
- list pending approvals
- list approval changes
- contracts
- submit approve or deny action.
- supplier management projects requiring external approval.
- b2b
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- list pending
- approvals
- get approval task details.
- external approval workflow for sourcing projects, contracts, and supplier management
- submit action
- list members of an sap ariba approval group to identify eligible approvers.
- procurement
- get approvable document details.
- approval task state changes.
- list group members.
- manages strategic sourcing events, rfx processes, and contract workflows.
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
- supplier management
- Procurement Approver
- get task
- rfx
- reviews and approves or denies sourcing documents, events, and contracts.
- list pending sap ariba sourcing approval tasks awaiting action.
- approve task
- list pending approval tasks.
- ariba
- list changes
- Sourcing Manager
- sap
- approval actions.
- get details for a specific sap ariba sourcing approval task including approvers.
- sourcing
- auctions
- pending approval tasks.
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
- supply chain
- list approval group members
- approval group members.
- contract workspaces and contract content requiring approval.
- get sourcing document
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
