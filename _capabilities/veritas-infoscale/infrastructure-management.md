---
categories: []
consumed_apis: []
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
- list all service groups in a cluster
- get disk group details
- clustering
- get cluster details
- get cluster
- list service groups
- volume management
- list service groups in a cluster
- cluster lifecycle, service groups, and node management
- disk group management
- offline service group
- disk groups, volumes, and snapshot operations
- high availability
- Infrastructure Engineer
- list all vxvm disk groups
- get service group details
- resize a storage volume
- virtualization
- data management
- bring a service group online on a system
- single cluster operations
- list all active cluster alerts
- cluster lifecycle management
- monitors cluster health, alerts, and performs failover operations.
- unified infrastructure management workflow for managing clusters, service groups, storage volumes, and alerts.
- get details of a specific cluster
- list clusters
- create a new storage volume
- Storage Administrator
- list all clusters
- list all active alerts
- alert management and health monitoring
- manages cluster configurations, service groups, and high availability operations.
- disaster recovery
- alert management
- acknowledge alert
- create volume
- create a volume snapshot
- list volumes in a disk group
- list alerts
- switch service group
- acknowledge a cluster alert
- switch a service group to another system
- storage management
- take a service group offline
- get disk group
- list all disk groups
- veritas infoscale
- get service group
- online service group
- list systems
- resize volume
- list disk groups
- list all cluster nodes
- create snapshot
- manages disk groups, volumes, snapshots, and storage capacity.
- service group management
- list all infoscale clusters
- list volumes
slug: infrastructure-management
source_filename: infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Veritas InfoScale Infrastructure Management\n  description: Unified infrastructure management workflow combining the Veritas InfoScale REST API for managing clusters,\n    service groups, storage volumes, disk groups, and alerts. Used by infrastructure engineers, storage administrators, and\n    site reliability engineers.\n  tags:\n  - Veritas InfoScale\n  - Clustering\n  - High Availability\n  - Storage Management\n  - Disaster Recovery\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INFOSCALE_API_TOKEN: INFOSCALE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: infoscale-rest\n    baseUri: https://{infoscale-server}:14149/api/v1\n    description: Veritas InfoScale REST API\n    authentication:\n      type: bearer\n      token: '{{INFOSCALE_API_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /clusters\n      description: Manage clusters\n      operations:\n   \
  \   - name: list-clusters\n        method: GET\n        description: List all clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-groups\n      path: /clusters/{clusterId}/servicegroups\n      description: Manage service groups\n      operations:\n      - name: list-service-groups\n        method: GET\n        description: List all service groups in a cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-group\n        method: POST\n        description: Create a new service group\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            systemList: '{{tools.systemList}}'\n      - name: get-service-group\n        method: GET\n        description: Get service group details\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        - name: serviceGroupName\n          in: path\n\
  \          type: string\n          required: true\n          description: Service group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: online-service-group\n        method: POST\n        description: Bring a service group online\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        - name: serviceGroupName\n          in: path\n          type: string\n          required: true\n          description: Service group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: offline-service-group\n        method: POST\n        description: Take a service group offline\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n\
  \          description: Cluster identifier\n        - name: serviceGroupName\n          in: path\n          type: string\n          required: true\n          description: Service group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: switch-service-group\n        method: POST\n        description: Switch a service group to another system\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        - name: serviceGroupName\n          in: path\n          type: string\n          required: true\n          description: Service group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetSystem: '{{tools.targetSystem}}'\n    - name: systems\n\
  \      path: /clusters/{clusterId}/systems\n      description: Manage cluster nodes\n      operations:\n      - name: list-systems\n        method: GET\n        description: List all cluster nodes\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-system\n        method: GET\n        description: Get cluster node details\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        - name: systemName\n          in: path\n          type: string\n          required: true\n          description: System hostname\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: disk-groups\n      path: /diskgroups\n      description: Manage VxVM disk groups\n      operations:\n      - name: list-disk-groups\n        method: GET\n        description: List all disk groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-disk-group\n        method: GET\n        description: Get disk group details\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-disk-group\n        method: POST\n        description: Create a disk group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            name: '{{tools.name}}'\n            disks: '{{tools.disks}}'\n    - name: volumes\n      path: /diskgroups/{diskGroupName}/volumes\n      description: Manage storage volumes\n      operations:\n      - name: list-volumes\n        method: GET\n        description: List all volumes in a disk group\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-volume\n        method: GET\n        description: Get volume details\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        - name: volumeName\n          in: path\n          type: string\n          required: true\n          description: Volume\
  \ name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-volume\n        method: POST\n        description: Create a volume\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            size: '{{tools.size}}'\n      - name: resize-volume\n        method: POST\n        description: Resize a volume\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        - name: volumeName\n          in: path\n          type: string\n          required: true\n \
  \         description: Volume name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            newSize: '{{tools.newSize}}'\n      - name: create-snapshot\n        method: POST\n        description: Create a volume snapshot\n        inputParameters:\n        - name: diskGroupName\n          in: path\n          type: string\n          required: true\n          description: Disk group name\n        - name: volumeName\n          in: path\n          type: string\n          required: true\n          description: Volume name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /alerts\n      description: Manage cluster alerts\n      operations:\n      - name: list-alerts\n        method: GET\n        description: List all active alerts\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-alert\n        method: GET\n        description: Get alert details\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Alert identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: acknowledge-alert\n        method: POST\n        description: Acknowledge an alert\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Alert identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infrastructure-management-api\n    description: Unified REST API for Veritas\
  \ InfoScale infrastructure management workflows.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: Cluster lifecycle management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all clusters\n        call: infoscale-rest.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{clusterId}\n      name: cluster-detail\n      description: Single cluster operations\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get cluster details\n        call: infoscale-rest.get-cluster\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{clusterId}/servicegroups\n      name: service-groups\n      description: Service group management\n      operations:\n      - method: GET\n        name: list-service-groups\n        description:\
  \ List service groups in a cluster\n        call: infoscale-rest.list-service-groups\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diskgroups\n      name: disk-groups\n      description: Disk group management\n      operations:\n      - method: GET\n        name: list-disk-groups\n        description: List all disk groups\n        call: infoscale-rest.list-disk-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diskgroups/{diskGroupName}/volumes\n      name: volumes\n      description: Volume management\n      operations:\n      - method: GET\n        name: list-volumes\n        description: List volumes in a disk group\n        call: infoscale-rest.list-volumes\n        with:\n          diskGroupName: rest.diskGroupName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n     \
  \ description: Alert management\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List all active alerts\n        call: infoscale-rest.list-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: infrastructure-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Veritas InfoScale infrastructure management.\n    tools:\n    - name: list-clusters\n      description: List all InfoScale clusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: infoscale-rest.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get details of a specific cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: infoscale-rest.get-cluster\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-service-groups\n      description: List all service groups in a cluster\n      hints:\n        readOnly: true\n        idempotent: true\n      call: infoscale-rest.list-service-groups\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-group\n      description: Get service group details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: infoscale-rest.get-service-group\n      with:\n        clusterId: tools.clusterId\n        serviceGroupName: tools.serviceGroupName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: online-service-group\n      description: Bring a service group online on a system\n      hints:\n        readOnly: false\n      call: infoscale-rest.online-service-group\n      with:\n        clusterId: tools.clusterId\n        serviceGroupName: tools.serviceGroupName\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: offline-service-group\n      description: Take a service group offline\n      hints:\n        readOnly: false\n      call: infoscale-rest.offline-service-group\n      with:\n        clusterId: tools.clusterId\n        serviceGroupName: tools.serviceGroupName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: switch-service-group\n      description: Switch a service group to another system\n      hints:\n        readOnly: false\n      call: infoscale-rest.switch-service-group\n      with:\n        clusterId: tools.clusterId\n        serviceGroupName: tools.serviceGroupName\n        targetSystem: tools.targetSystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-systems\n      description: List all cluster nodes\n      hints:\n        readOnly: true\n      call: infoscale-rest.list-systems\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-disk-groups\n      description: List all VxVM disk groups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: infoscale-rest.list-disk-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-disk-group\n      description: Get disk group details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: infoscale-rest.get-disk-group\n      with:\n        diskGroupName: tools.diskGroupName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-volumes\n      description: List volumes in a disk group\n      hints:\n        readOnly: true\n        idempotent: true\n      call: infoscale-rest.list-volumes\n      with:\n        diskGroupName: tools.diskGroupName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-volume\n      description: Create a new storage volume\n      hints:\n        readOnly: false\n   \
  \   call: infoscale-rest.create-volume\n      with:\n        diskGroupName: tools.diskGroupName\n        name: tools.name\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resize-volume\n      description: Resize a storage volume\n      hints:\n        readOnly: false\n      call: infoscale-rest.resize-volume\n      with:\n        diskGroupName: tools.diskGroupName\n        volumeName: tools.volumeName\n        newSize: tools.newSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-snapshot\n      description: Create a volume snapshot\n      hints:\n        readOnly: false\n      call: infoscale-rest.create-snapshot\n      with:\n        diskGroupName: tools.diskGroupName\n        volumeName: tools.volumeName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: List all active cluster alerts\n      hints:\n        readOnly: true\n \
  \     call: infoscale-rest.list-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge-alert\n      description: Acknowledge a cluster alert\n      hints:\n        readOnly: false\n      call: infoscale-rest.acknowledge-alert\n      with:\n        alertId: tools.alertId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
