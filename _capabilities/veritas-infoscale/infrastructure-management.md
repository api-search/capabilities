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
- list all vxvm disk groups
- list service groups
- list all active cluster alerts
- disaster recovery
- create volume
- cluster lifecycle management
- create a new storage volume
- service group management
- resize volume
- veritas infoscale
- Infrastructure Engineer
- storage management
- list all clusters
- create snapshot
- virtualization
- get cluster details
- list service groups in a cluster
- alert management and health monitoring
- manages cluster configurations, service groups, and high availability operations.
- single cluster operations
- get cluster
- list alerts
- manages disk groups, volumes, snapshots, and storage capacity.
- list volumes in a disk group
- list all disk groups
- list all infoscale clusters
- acknowledge a cluster alert
- list clusters
- unified infrastructure management workflow for managing clusters, service groups, storage volumes, and alerts.
- switch a service group to another system
- acknowledge alert
- get disk group details
- get service group details
- get details of a specific cluster
- disk group management
- high availability
- list systems
- create a volume snapshot
- monitors cluster health, alerts, and performs failover operations.
- list volumes
- list all service groups in a cluster
- clustering
- cluster lifecycle, service groups, and node management
- online service group
- volume management
- list disk groups
- alert management
- list all active alerts
- get service group
- bring a service group online on a system
- take a service group offline
- get disk group
- Storage Administrator
- switch service group
- disk groups, volumes, and snapshot operations
- resize a storage volume
- data management
- list all cluster nodes
- offline service group
slug: infrastructure-management
source_filename: infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veritas InfoScale Infrastructure Management\"\n  description: \"Unified infrastructure management workflow combining the Veritas InfoScale REST API for managing clusters, service groups, storage volumes, disk groups, and alerts. Used by infrastructure engineers, storage administrators, and site reliability engineers.\"\n  tags:\n    - Veritas InfoScale\n    - Clustering\n    - High Availability\n    - Storage Management\n    - Disaster Recovery\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INFOSCALE_API_TOKEN: INFOSCALE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: infoscale-rest\n      location: ./shared/infoscale-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: infrastructure-management-api\n      description: \"Unified REST API for Veritas InfoScale infrastructure management workflows.\"\n      resources:\n        - path: /v1/clusters\n\
  \          name: clusters\n          description: \"Cluster lifecycle management\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all clusters\"\n              call: \"infoscale-rest.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{clusterId}\n          name: cluster-detail\n          description: \"Single cluster operations\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details\"\n              call: \"infoscale-rest.get-cluster\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{clusterId}/servicegroups\n          name: service-groups\n          description: \"Service group management\"\n  \
  \        operations:\n            - method: GET\n              name: list-service-groups\n              description: \"List service groups in a cluster\"\n              call: \"infoscale-rest.list-service-groups\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/diskgroups\n          name: disk-groups\n          description: \"Disk group management\"\n          operations:\n            - method: GET\n              name: list-disk-groups\n              description: \"List all disk groups\"\n              call: \"infoscale-rest.list-disk-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/diskgroups/{diskGroupName}/volumes\n          name: volumes\n          description: \"Volume management\"\n          operations:\n            - method: GET\n              name: list-volumes\n\
  \              description: \"List volumes in a disk group\"\n              call: \"infoscale-rest.list-volumes\"\n              with:\n                diskGroupName: \"rest.diskGroupName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Alert management\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List all active alerts\"\n              call: \"infoscale-rest.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: infrastructure-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Veritas InfoScale infrastructure management.\"\n      tools:\n        - name: list-clusters\n          description: \"List all InfoScale clusters\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"infoscale-rest.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster\n          description: \"Get details of a specific cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"infoscale-rest.get-cluster\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-groups\n          description: \"List all service groups in a cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"infoscale-rest.list-service-groups\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-group\n          description:\
  \ \"Get service group details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"infoscale-rest.get-service-group\"\n          with:\n            clusterId: \"tools.clusterId\"\n            serviceGroupName: \"tools.serviceGroupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: online-service-group\n          description: \"Bring a service group online on a system\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.online-service-group\"\n          with:\n            clusterId: \"tools.clusterId\"\n            serviceGroupName: \"tools.serviceGroupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: offline-service-group\n          description: \"Take a service group offline\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.offline-service-group\"\n          with:\n\
  \            clusterId: \"tools.clusterId\"\n            serviceGroupName: \"tools.serviceGroupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: switch-service-group\n          description: \"Switch a service group to another system\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.switch-service-group\"\n          with:\n            clusterId: \"tools.clusterId\"\n            serviceGroupName: \"tools.serviceGroupName\"\n            targetSystem: \"tools.targetSystem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-systems\n          description: \"List all cluster nodes\"\n          hints:\n            readOnly: true\n          call: \"infoscale-rest.list-systems\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-disk-groups\n          description: \"List all VxVM disk groups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"infoscale-rest.list-disk-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-disk-group\n          description: \"Get disk group details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"infoscale-rest.get-disk-group\"\n          with:\n            diskGroupName: \"tools.diskGroupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-volumes\n          description: \"List volumes in a disk group\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"infoscale-rest.list-volumes\"\n          with:\n            diskGroupName: \"tools.diskGroupName\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: create-volume\n          description: \"Create a new storage volume\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.create-volume\"\n          with:\n            diskGroupName: \"tools.diskGroupName\"\n            name: \"tools.name\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resize-volume\n          description: \"Resize a storage volume\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.resize-volume\"\n          with:\n            diskGroupName: \"tools.diskGroupName\"\n            volumeName: \"tools.volumeName\"\n            newSize: \"tools.newSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-snapshot\n          description: \"Create a volume snapshot\"\n          hints:\n            readOnly: false\n      \
  \    call: \"infoscale-rest.create-snapshot\"\n          with:\n            diskGroupName: \"tools.diskGroupName\"\n            volumeName: \"tools.volumeName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alerts\n          description: \"List all active cluster alerts\"\n          hints:\n            readOnly: true\n          call: \"infoscale-rest.list-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acknowledge-alert\n          description: \"Acknowledge a cluster alert\"\n          hints:\n            readOnly: false\n          call: \"infoscale-rest.acknowledge-alert\"\n          with:\n            alertId: \"tools.alertId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veritas-infoscale/refs/heads/main/capabilities/infrastructure-management.yaml
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
