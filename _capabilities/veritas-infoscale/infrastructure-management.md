---
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
- get details of a specific cluster
- online service group
- resize a storage volume
- disaster recovery
- Storage Administrator
- manages disk groups, volumes, snapshots, and storage capacity.
- volume management
- create volume
- bring a service group online on a system
- veritas infoscale
- list all active alerts
- list systems
- service group management
- list volumes
- list disk groups
- get cluster details
- list alerts
- monitors cluster health, alerts, and performs failover operations.
- disk groups, volumes, and snapshot operations
- alert management and health monitoring
- list all cluster nodes
- list volumes in a disk group
- get service group details
- take a service group offline
- single cluster operations
- data management
- virtualization
- get disk group
- list service groups in a cluster
- list all disk groups
- high availability
- unified infrastructure management workflow for managing clusters, service groups, storage volumes, and alerts.
- cluster lifecycle, service groups, and node management
- storage management
- cluster lifecycle management
- acknowledge a cluster alert
- list all service groups in a cluster
- acknowledge alert
- list all infoscale clusters
- resize volume
- create snapshot
- list all clusters
- list clusters
- alert management
- Infrastructure Engineer
- offline service group
- manages cluster configurations, service groups, and high availability operations.
- list all active cluster alerts
- clustering
- switch service group
- disk group management
- list all vxvm disk groups
- create a volume snapshot
- get disk group details
- create a new storage volume
- list service groups
- switch a service group to another system
- get cluster
- get service group
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
