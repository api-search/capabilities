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
- get task
- approval task state changes.
- get approvable document details.
- auctions
- manages strategic sourcing events, rfx processes, and contract workflows.
- get document
- external approval workflow for sourcing projects, contracts, and supplier management
- Sourcing Manager
- approvable documents.
- deny task
- supplier management
- rfx
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- b2b
- get sourcing document
- supplier management projects requiring external approval.
- sap
- ariba
- list members
- Procurement Approver
- approvals
- contracts
- submit action
- approval group members.
- get approval task details.
- sourcing
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
- get task details
- list pending approval tasks.
- pending approval tasks.
- list pending sap ariba sourcing approval tasks awaiting action.
- get details for a specific sap ariba sourcing approval task including approvers.
- list changes
- approval task details.
- list pending approvals
- approve task
- list approval changes
- procurement
- list changed approval tasks.
- submit approve or deny action.
- list sap ariba sourcing approval tasks that have recently changed state.
- list members of an sap ariba approval group to identify eligible approvers.
- reviews and approves or denies sourcing documents, events, and contracts.
- list group members.
- contract workspaces and contract content requiring approval.
- list pending
- rfx events, auctions, and sourcing projects requiring approval.
- list approval group members
- supply chain
- approval actions.
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
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
