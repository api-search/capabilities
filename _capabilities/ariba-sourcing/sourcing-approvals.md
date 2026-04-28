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
- Procurement Approver
- supplier management
- approve an sap ariba sourcing approval task on behalf of an authorized approver.
- get details about an sap ariba approvable sourcing document, rfx event, or contract workspace.
- approvals
- approval task state changes.
- get document
- approval task details.
- get sourcing document
- list pending approval tasks.
- rfx
- reviews and approves or denies sourcing documents, events, and contracts.
- auctions
- sap
- contracts
- ariba
- list members of an sap ariba approval group to identify eligible approvers.
- list members
- approval actions.
- list approval changes
- sourcing
- deny an sap ariba sourcing approval task on behalf of an authorized approver.
- list changes
- manages strategic sourcing events, rfx processes, and contract workflows.
- list changed approval tasks.
- b2b
- Sourcing Manager
- list group members.
- get details for a specific sap ariba sourcing approval task including approvers.
- deny task
- procurement
- approve task
- supply chain
- list pending approvals
- submit action
- rfx events, auctions, and sourcing projects requiring approval.
- list pending
- list sap ariba sourcing approval tasks that have recently changed state.
- approvable documents.
- get approvable document details.
- approval group members.
- contract workspaces and contract content requiring approval.
- get approval task details.
- supplier management projects requiring external approval.
- list pending sap ariba sourcing approval tasks awaiting action.
- get task details
- pending approval tasks.
- external approval workflow for sourcing projects, contracts, and supplier management
- list approval group members
- get task
- submit approve or deny action.
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
