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
- create a point-in-time snapshot of a volume
- infrastructure
- create a volume snapshot
- list storage volumes
- list aggregates
- retrieve cluster information
- data management
- list storage aggregates (local tiers) in the cluster
- storage management
- list storage aggregates
- list snapshots
- hybrid cloud
- cluster node management
- list network interfaces
- data protection
- list volume snapshots
- list all nodes in the ontap cluster
- storage
- list network interfaces (lifs) in the cluster
- cloud
- network interface management
- create a new volume
- list cluster nodes
- retrieve ontap cluster information including name, version, and health
- list storage virtual machines in the cluster
- update properties of an existing volume
- aggregate management
- create a new storage volume on a specified svm and aggregate
- cluster information and configuration
- create volume
- get cluster
- list svms
- retrieve detailed information about a specific volume
- list volumes
- netapp
- update volume
- individual volume operations
- get volume
- create snapshot
- delete a volume
- delete a storage volume
- storage virtual machine management
- ontap
- volume snapshot management
- list snapshots for a specific volume
- update a volume
- storage volume management
- retrieve a specific volume
- list nodes
- delete volume
- list all storage volumes across the cluster
slug: storage-management
source_filename: storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NetApp Storage Management\"\n  description: \"Unified workflow for managing NetApp ONTAP storage infrastructure including volumes, aggregates, SVMs, snapshots, and network interfaces. Used by storage administrators for provisioning and day-to-day management.\"\n  tags:\n    - NetApp\n    - Storage Management\n    - ONTAP\n    - Data Protection\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      NETAPP_USERNAME: NETAPP_USERNAME\n      NETAPP_PASSWORD: NETAPP_PASSWORD\n\ncapability:\n  consumes:\n    - import: ontap\n      location: ./shared/ontap.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: storage-management-api\n      description: \"Unified REST API for NetApp storage management.\"\n      resources:\n        - path: /v1/cluster\n          name: cluster\n          description: \"Cluster information and configuration\"\n          operations:\n       \
  \     - method: GET\n              name: get-cluster\n              description: \"Retrieve cluster information\"\n              call: \"ontap.get-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes\n          name: nodes\n          description: \"Cluster node management\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List cluster nodes\"\n              call: \"ontap.list-cluster-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/volumes\n          name: volumes\n          description: \"Storage volume management\"\n          operations:\n            - method: GET\n              name: list-volumes\n              description: \"List storage volumes\"\n              call: \"ontap.list-volumes\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n            - method: POST\n              name: create-volume\n              description: \"Create a new volume\"\n              call: \"ontap.create-volume\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/volumes/{uuid}\n          name: volume\n          description: \"Individual volume operations\"\n          operations:\n            - method: GET\n              name: get-volume\n              description: \"Retrieve a specific volume\"\n              call: \"ontap.get-volume\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-volume\n              description: \"Update a volume\"\n              call: \"ontap.update-volume\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-volume\n              description: \"Delete a volume\"\n              call: \"ontap.delete-volume\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/snapshots\n          name: snapshots\n          description: \"Volume snapshot management\"\n          operations:\n            - method: GET\n              name: list-snapshots\n              description: \"List volume snapshots\"\n              call: \"ontap.list-snapshots\"\n              with:\n                volume.uuid: \"rest.volume_uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-snapshot\n              description: \"Create a volume snapshot\"\n              call: \"\
  ontap.create-snapshot\"\n              with:\n                volume.uuid: \"rest.volume_uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/aggregates\n          name: aggregates\n          description: \"Aggregate management\"\n          operations:\n            - method: GET\n              name: list-aggregates\n              description: \"List storage aggregates\"\n              call: \"ontap.list-aggregates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/svms\n          name: svms\n          description: \"Storage virtual machine management\"\n          operations:\n            - method: GET\n              name: list-svms\n              description: \"List SVMs\"\n              call: \"ontap.list-svms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/network-interfaces\n\
  \          name: network-interfaces\n          description: \"Network interface management\"\n          operations:\n            - method: GET\n              name: list-network-interfaces\n              description: \"List network interfaces\"\n              call: \"ontap.list-network-interfaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: storage-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NetApp storage management.\"\n      tools:\n        - name: get-cluster\n          description: \"Retrieve ONTAP cluster information including name, version, and health\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.get-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-nodes\n          description: \"List all nodes in the ONTAP\
  \ cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-cluster-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-volumes\n          description: \"List all storage volumes across the cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-volumes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-volume\n          description: \"Retrieve detailed information about a specific volume\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.get-volume\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-volume\n          description: \"Create a new storage volume on a specified SVM and aggregate\"\
  \n          hints:\n            readOnly: false\n          call: \"ontap.create-volume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-volume\n          description: \"Update properties of an existing volume\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"ontap.update-volume\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-volume\n          description: \"Delete a storage volume\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ontap.delete-volume\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-snapshots\n          description: \"List snapshots for a specific volume\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-snapshots\"\n          with:\n            volume.uuid: \"tools.volume_uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-snapshot\n          description: \"Create a point-in-time snapshot of a volume\"\n          hints:\n            readOnly: false\n          call: \"ontap.create-snapshot\"\n          with:\n            volume.uuid: \"tools.volume_uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-aggregates\n          description: \"List storage aggregates (local tiers) in the cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-aggregates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-svms\n          description: \"List storage\
  \ virtual machines in the cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-svms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-network-interfaces\n          description: \"List network interfaces (LIFs) in the cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ontap.list-network-interfaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netapp/refs/heads/main/capabilities/storage-management.yaml
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
