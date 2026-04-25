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
- get approval task details.
- b2b
- list members
- list approval changes
- contract workspaces and contract content requiring approval.
- approval task state changes.
- list sap ariba sourcing approval tasks that have recently changed state.
- manages strategic sourcing events, rfx processes, and contract workflows.
- list pending sap ariba sourcing approval tasks awaiting action.
- get document
- list changed approval tasks.
- approvable documents.
- sourcing
- contracts
- get details for a specific sap ariba sourcing approval task including approvers.
- Sourcing Manager
- approval actions.
- get task details
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- deny task
- rfx events, auctions, and sourcing projects requiring approval.
- list pending
- sap
- approvals
- submit action
- pending approval tasks.
- list pending approvals
- external approval workflow for sourcing projects, contracts, and supplier management
- get task
- supplier management projects requiring external approval.
- approve task
- approval group members.
- supplier management
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
- get sourcing document
- list pending approval tasks.
- list changes
- list approval group members
- list members of an sap ariba approval group to identify eligible approvers.
- ariba
- get approvable document details.
- procurement
- submit approve or deny action.
- Procurement Approver
- list group members.
- reviews and approves or denies sourcing documents, events, and contracts.
- approval task details.
- rfx
- auctions
- supply chain
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
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
