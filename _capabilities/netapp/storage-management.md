---
categories: []
consumed_apis: []
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
- cluster information and configuration
- netapp
- create a point-in-time snapshot of a volume
- network interface management
- list cluster nodes
- get cluster
- volume snapshot management
- update a volume
- list snapshots
- list aggregates
- list snapshots for a specific volume
- delete volume
- cluster node management
- storage virtual machine management
- data management
- individual volume operations
- list network interfaces
- list all storage volumes across the cluster
- data protection
- infrastructure
- list storage virtual machines in the cluster
- list volume snapshots
- create volume
- retrieve a specific volume
- create a volume snapshot
- ontap
- create a new volume
- delete a volume
- create a new storage volume on a specified svm and aggregate
- list network interfaces (lifs) in the cluster
- cloud
- storage
- storage management
- update properties of an existing volume
- retrieve detailed information about a specific volume
- list storage aggregates (local tiers) in the cluster
- hybrid cloud
- list storage aggregates
- list nodes
- retrieve cluster information
- list storage volumes
- create snapshot
- list svms
- storage volume management
- update volume
- retrieve ontap cluster information including name, version, and health
- delete a storage volume
- aggregate management
- list all nodes in the ontap cluster
- list volumes
- get volume
slug: storage-management
source_filename: storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NetApp Storage Management\n  description: Unified workflow for managing NetApp ONTAP storage infrastructure including volumes, aggregates, SVMs, snapshots,\n    and network interfaces. Used by storage administrators for provisioning and day-to-day management.\n  tags:\n  - NetApp\n  - Storage Management\n  - ONTAP\n  - Data Protection\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NETAPP_USERNAME: NETAPP_USERNAME\n    NETAPP_PASSWORD: NETAPP_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: ontap\n    baseUri: https://{clusterMgmtIp}/api\n    description: NetApp ONTAP REST API for storage management\n    authentication:\n      type: basic\n      username: '{{NETAPP_USERNAME}}'\n      password: '{{NETAPP_PASSWORD}}'\n    resources:\n    - name: cluster\n      path: /cluster\n      description: Cluster configuration and node management\n      operations:\n      - name: get-cluster\n\
  \        method: GET\n        description: Retrieve cluster information\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cluster\n        method: PATCH\n        description: Update cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: cluster-nodes\n      path: /cluster/nodes\n      description: Cluster node management\n      operations:\n      - name: list-cluster-nodes\n        method: GET\n        description: List cluster nodes\n        inputParameters:\n        - name: fields\n          in: query\n      \
  \    type: string\n          required: false\n          description: Fields to return\n        - name: max_records\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-node\n      path: /cluster/nodes/{uuid}\n      description: Individual cluster node operations\n      operations:\n      - name: get-cluster-node\n        method: GET\n        description: Retrieve a specific cluster node\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Node UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses\n      path: /cluster/licensing/licenses\n      description: License management\n      operations:\n\
  \      - name: list-licenses\n        method: GET\n        description: List cluster licenses\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volumes\n      path: /storage/volumes\n      description: Storage volume management\n      operations:\n      - name: list-volumes\n        method: GET\n        description: List storage volumes\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        - name: max_records\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: svm.name\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by SVM name\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by volume name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by volume state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-volume\n        method: POST\n        description: Create a new volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            svm: '{{tools.svm}}'\n    - name: volume\n      path: /storage/volumes/{uuid}\n      description: Individual volume operations\n      operations:\n      - name: get-volume\n        method: GET\n        description: Retrieve a\
  \ specific volume\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Volume UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-volume\n        method: PATCH\n        description: Update a volume\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Volume UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-volume\n        method: DELETE\n        description: Delete a volume\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Volume\
  \ UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snapshots\n      path: /storage/volumes/{volume.uuid}/snapshots\n      description: Volume snapshot management\n      operations:\n      - name: list-snapshots\n        method: GET\n        description: List snapshots for a volume\n        inputParameters:\n        - name: volume.uuid\n          in: path\n          type: string\n          required: true\n          description: Volume UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-snapshot\n        method: POST\n        description: Create a volume snapshot\n        inputParameters:\n        - name: volume.uuid\n          in: path\n          type: string\n          required: true\n          description: Volume UUID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: aggregates\n      path: /storage/aggregates\n      description: Aggregate (local tier) management\n      operations:\n      - name: list-aggregates\n        method: GET\n        description: List storage aggregates\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        - name: max_records\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-aggregate\n        method: POST\n        description: Create a new aggregate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: aggregate\n      path: /storage/aggregates/{uuid}\n      description: Individual aggregate operations\n      operations:\n      - name: get-aggregate\n        method: GET\n        description: Retrieve a specific aggregate\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Aggregate UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-aggregate\n        method: PATCH\n        description: Update an aggregate\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Aggregate UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-aggregate\n        method: DELETE\n        description: Delete an aggregate\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Aggregate UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: svms\n      path: /svm/svms\n      description: Storage virtual machine management\n      operations:\n      - name: list-svms\n        method: GET\n        description: List storage virtual machines\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        - name: max_records\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Maximum records to return\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by SVM name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-svm\n        method: POST\n        description: Create a new SVM\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: svm\n      path: /svm/svms/{uuid}\n      description: Individual SVM operations\n      operations:\n      - name: get-svm\n        method: GET\n        description: Retrieve a specific SVM\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: SVM UUID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-svm\n        method: PATCH\n        description: Update an SVM\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: SVM UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-svm\n        method: DELETE\n        description: Delete an SVM\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: SVM UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-interfaces\n      path: /network/ip/interfaces\n      description: Network interface management\n\
  \      operations:\n      - name: list-network-interfaces\n        method: GET\n        description: List network interfaces\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        - name: max_records\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: storage-management-api\n    description: Unified REST API for NetApp storage management.\n    resources:\n    - path: /v1/cluster\n      name: cluster\n      description: Cluster information and configuration\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Retrieve cluster information\n        call: ontap.get-cluster\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: nodes\n      description: Cluster node management\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List cluster nodes\n        call: ontap.list-cluster-nodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes\n      name: volumes\n      description: Storage volume management\n      operations:\n      - method: GET\n        name: list-volumes\n        description: List storage volumes\n        call: ontap.list-volumes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-volume\n        description: Create a new volume\n        call: ontap.create-volume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{uuid}\n      name: volume\n      description: Individual volume operations\n      operations:\n      - method:\
  \ GET\n        name: get-volume\n        description: Retrieve a specific volume\n        call: ontap.get-volume\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-volume\n        description: Update a volume\n        call: ontap.update-volume\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-volume\n        description: Delete a volume\n        call: ontap.delete-volume\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/snapshots\n      name: snapshots\n      description: Volume snapshot management\n      operations:\n      - method: GET\n        name: list-snapshots\n        description: List volume snapshots\n        call: ontap.list-snapshots\n        with:\n          volume.uuid: rest.volume_uuid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-snapshot\n        description: Create a volume snapshot\n        call: ontap.create-snapshot\n        with:\n          volume.uuid: rest.volume_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aggregates\n      name: aggregates\n      description: Aggregate management\n      operations:\n      - method: GET\n        name: list-aggregates\n        description: List storage aggregates\n        call: ontap.list-aggregates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/svms\n      name: svms\n      description: Storage virtual machine management\n      operations:\n      - method: GET\n        name: list-svms\n        description: List SVMs\n        call: ontap.list-svms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/network-interfaces\n   \
  \   name: network-interfaces\n      description: Network interface management\n      operations:\n      - method: GET\n        name: list-network-interfaces\n        description: List network interfaces\n        call: ontap.list-network-interfaces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: storage-management-mcp\n    transport: http\n    description: MCP server for AI-assisted NetApp storage management.\n    tools:\n    - name: get-cluster\n      description: Retrieve ONTAP cluster information including name, version, and health\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.get-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all nodes in the ONTAP cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-cluster-nodes\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-volumes\n      description: List all storage volumes across the cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-volumes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-volume\n      description: Retrieve detailed information about a specific volume\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.get-volume\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-volume\n      description: Create a new storage volume on a specified SVM and aggregate\n      hints:\n        readOnly: false\n      call: ontap.create-volume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-volume\n      description: Update properties of an existing volume\n      hints:\n        readOnly: false\n        idempotent: true\n      call: ontap.update-volume\n\
  \      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-volume\n      description: Delete a storage volume\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ontap.delete-volume\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-snapshots\n      description: List snapshots for a specific volume\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-snapshots\n      with:\n        volume.uuid: tools.volume_uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-snapshot\n      description: Create a point-in-time snapshot of a volume\n      hints:\n        readOnly: false\n      call: ontap.create-snapshot\n      with:\n        volume.uuid: tools.volume_uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-aggregates\n      description: List storage aggregates (local tiers) in the cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-aggregates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-svms\n      description: List storage virtual machines in the cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-svms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-network-interfaces\n      description: List network interfaces (LIFs) in the cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ontap.list-network-interfaces\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
