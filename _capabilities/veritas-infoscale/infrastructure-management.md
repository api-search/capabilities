---
categories: []
consumed_apis:
- infoscale-rest
description: Unified infrastructure management workflow combining the Veritas InfoScale REST API for managing clusters, service groups, storage volumes, disk groups, and alerts. Used by infrastructure engineers, storage administrators, and site reliability engineers.
layout: capability
name: Veritas InfoScale Infrastructure Management
operations:
- description: List all clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Get cluster details
  method: GET
  name: get-cluster
  path: /v1/clusters/{clusterId}
- description: List service groups in a cluster
  method: GET
  name: list-service-groups
  path: /v1/clusters/{clusterId}/servicegroups
- description: List all disk groups
  method: GET
  name: list-disk-groups
  path: /v1/diskgroups
- description: List volumes in a disk group
  method: GET
  name: list-volumes
  path: /v1/diskgroups/{diskGroupName}/volumes
- description: List all active alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
personas: []
provider_name: Veritas InfoScale
provider_slug: veritas-infoscale
search_terms:
- disk group management
- list all active alerts
- list systems
- clustering
- create a new storage volume
- get cluster details
- list disk groups
- get service group
- Storage Administrator
- list all clusters
- list all infoscale clusters
- switch service group
- unified infrastructure management workflow for managing clusters, service groups, storage volumes, and alerts.
- list volumes in a disk group
- list volumes
- veritas infoscale
- bring a service group online on a system
- service group management
- online service group
- get disk group details
- create a volume snapshot
- take a service group offline
- monitors cluster health, alerts, and performs failover operations.
- manages disk groups, volumes, snapshots, and storage capacity.
- create volume
- virtualization
- list service groups in a cluster
- create snapshot
- get cluster
- switch a service group to another system
- disaster recovery
- disk groups, volumes, and snapshot operations
- resize volume
- list all active cluster alerts
- alert management
- single cluster operations
- list all vxvm disk groups
- list all disk groups
- high availability
- get service group details
- list alerts
- cluster lifecycle management
- offline service group
- list all cluster nodes
- list clusters
- acknowledge a cluster alert
- resize a storage volume
- get details of a specific cluster
- Infrastructure Engineer
- cluster lifecycle, service groups, and node management
- acknowledge alert
- storage management
- alert management and health monitoring
- get disk group
- manages cluster configurations, service groups, and high availability operations.
- list all service groups in a cluster
- list service groups
- data management
- volume management
slug: infrastructure-management
tags:
- Veritas InfoScale
- Clustering
- High Availability
- Storage Management
- Disaster Recovery
tools:
- description: List all InfoScale clusters
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Get details of a specific cluster
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster
- description: List all service groups in a cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-service-groups
- description: Get service group details
  hints:
    idempotent: true
    readOnly: true
  name: get-service-group
- description: Bring a service group online on a system
  hints:
    readOnly: false
  name: online-service-group
- description: Take a service group offline
  hints:
    readOnly: false
  name: offline-service-group
- description: Switch a service group to another system
  hints:
    readOnly: false
  name: switch-service-group
- description: List all cluster nodes
  hints:
    readOnly: true
  name: list-systems
- description: List all VxVM disk groups
  hints:
    openWorld: true
    readOnly: true
  name: list-disk-groups
- description: Get disk group details
  hints:
    idempotent: true
    readOnly: true
  name: get-disk-group
- description: List volumes in a disk group
  hints:
    idempotent: true
    readOnly: true
  name: list-volumes
- description: Create a new storage volume
  hints:
    readOnly: false
  name: create-volume
- description: Resize a storage volume
  hints:
    readOnly: false
  name: resize-volume
- description: Create a volume snapshot
  hints:
    readOnly: false
  name: create-snapshot
- description: List all active cluster alerts
  hints:
    readOnly: true
  name: list-alerts
- description: Acknowledge a cluster alert
  hints:
    readOnly: false
  name: acknowledge-alert
---
