---
categories: []
consumed_apis:
- ontap
description: Unified workflow for managing NetApp ONTAP storage infrastructure including volumes, aggregates, SVMs, snapshots, and network interfaces. Used by storage administrators for provisioning and day-to-day management.
layout: capability
name: NetApp Storage Management
operations:
- description: Retrieve cluster information
  method: GET
  name: get-cluster
  path: /v1/cluster
- description: List cluster nodes
  method: GET
  name: list-nodes
  path: /v1/nodes
- description: List storage volumes
  method: GET
  name: list-volumes
  path: /v1/volumes
- description: Create a new volume
  method: POST
  name: create-volume
  path: /v1/volumes
- description: Retrieve a specific volume
  method: GET
  name: get-volume
  path: /v1/volumes/{uuid}
- description: Update a volume
  method: PATCH
  name: update-volume
  path: /v1/volumes/{uuid}
- description: Delete a volume
  method: DELETE
  name: delete-volume
  path: /v1/volumes/{uuid}
- description: List volume snapshots
  method: GET
  name: list-snapshots
  path: /v1/snapshots
- description: Create a volume snapshot
  method: POST
  name: create-snapshot
  path: /v1/snapshots
- description: List storage aggregates
  method: GET
  name: list-aggregates
  path: /v1/aggregates
- description: List SVMs
  method: GET
  name: list-svms
  path: /v1/svms
- description: List network interfaces
  method: GET
  name: list-network-interfaces
  path: /v1/network-interfaces
personas: []
provider_name: NetApp
provider_slug: netapp
search_terms:
- list nodes
- get volume
- create snapshot
- delete a volume
- list snapshots
- aggregate management
- create a new volume
- list snapshots for a specific volume
- list storage aggregates (local tiers) in the cluster
- hybrid cloud
- retrieve detailed information about a specific volume
- list storage virtual machines in the cluster
- list storage aggregates
- update properties of an existing volume
- data protection
- list volume snapshots
- list volumes
- list network interfaces (lifs) in the cluster
- create a new storage volume on a specified svm and aggregate
- list cluster nodes
- individual volume operations
- infrastructure
- volume snapshot management
- network interface management
- storage volume management
- retrieve ontap cluster information including name, version, and health
- create a volume snapshot
- retrieve a specific volume
- ontap
- update a volume
- cluster node management
- list network interfaces
- create volume
- cloud
- delete a storage volume
- retrieve cluster information
- update volume
- list all storage volumes across the cluster
- storage management
- get cluster
- list aggregates
- cluster information and configuration
- create a point-in-time snapshot of a volume
- data management
- netapp
- list all nodes in the ontap cluster
- storage
- storage virtual machine management
- delete volume
- list storage volumes
- list svms
slug: storage-management
tags:
- NetApp
- Storage Management
- ONTAP
- Data Protection
tools:
- description: Retrieve ONTAP cluster information including name, version, and health
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster
- description: List all nodes in the ONTAP cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-nodes
- description: List all storage volumes across the cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-volumes
- description: Retrieve detailed information about a specific volume
  hints:
    idempotent: true
    readOnly: true
  name: get-volume
- description: Create a new storage volume on a specified SVM and aggregate
  hints:
    readOnly: false
  name: create-volume
- description: Update properties of an existing volume
  hints:
    idempotent: true
    readOnly: false
  name: update-volume
- description: Delete a storage volume
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-volume
- description: List snapshots for a specific volume
  hints:
    idempotent: true
    readOnly: true
  name: list-snapshots
- description: Create a point-in-time snapshot of a volume
  hints:
    readOnly: false
  name: create-snapshot
- description: List storage aggregates (local tiers) in the cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-aggregates
- description: List storage virtual machines in the cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-svms
- description: List network interfaces (LIFs) in the cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-network-interfaces
---
