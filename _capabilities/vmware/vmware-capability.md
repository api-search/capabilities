---
categories: []
consumed_apis: []
description: RESTful API for managing VMware vSphere virtualization platform resources including virtual machines, hosts, datastores, clusters, networks, and related infrastructure. The vSphere Automation API provides modern REST endpoints for vCenter Server operations using JSON payloads and session-based or OAuth authentication. This API supersedes the legacy SOAP-based vSphere Web Services API for most automation use cases.
layout: capability
name: VMware vSphere Automation REST API
operations:
- description: Vmware Create a New Authentication Session
  method: POST
  name: createsession
  path: /session
- description: Vmware Terminate the Current Session
  method: DELETE
  name: deletesession
  path: /session
- description: Vmware Get Current Session Information
  method: GET
  name: getsessioninfo
  path: /session
- description: Vmware List Virtual Machines
  method: GET
  name: listvms
  path: /vcenter/vm
- description: Vmware Create a New Virtual Machine
  method: POST
  name: createvm
  path: /vcenter/vm
- description: Vmware Get Virtual Machine Details
  method: GET
  name: getvm
  path: /vcenter/vm/{vm}
- description: Vmware Delete a Virtual Machine
  method: DELETE
  name: deletevm
  path: /vcenter/vm/{vm}
- description: Vmware Get Vm Power State
  method: GET
  name: getvmpowerstate
  path: /vcenter/vm/{vm}/power
- description: Vmware Power on a Virtual Machine
  method: POST
  name: poweronvm
  path: /vcenter/vm/{vm}/power?action=start
- description: Vmware Power Off a Virtual Machine
  method: POST
  name: poweroffvm
  path: /vcenter/vm/{vm}/power?action=stop
- description: Vmware Suspend a Virtual Machine
  method: POST
  name: suspendvm
  path: /vcenter/vm/{vm}/power?action=suspend
- description: Vmware Reset a Virtual Machine
  method: POST
  name: resetvm
  path: /vcenter/vm/{vm}/power?action=reset
- description: Vmware Get Vm Hardware Configuration
  method: GET
  name: getvmhardware
  path: /vcenter/vm/{vm}/hardware
- description: Vmware Update Vm Hardware Configuration
  method: PATCH
  name: updatevmhardware
  path: /vcenter/vm/{vm}/hardware
- description: Vmware Get Vm Cpu Configuration
  method: GET
  name: getvmcpu
  path: /vcenter/vm/{vm}/hardware/cpu
- description: Vmware Update Vm Cpu Configuration
  method: PATCH
  name: updatevmcpu
  path: /vcenter/vm/{vm}/hardware/cpu
- description: Vmware Get Vm Memory Configuration
  method: GET
  name: getvmmemory
  path: /vcenter/vm/{vm}/hardware/memory
- description: Vmware Update Vm Memory Configuration
  method: PATCH
  name: updatevmmemory
  path: /vcenter/vm/{vm}/hardware/memory
- description: Vmware List Vm Virtual Disks
  method: GET
  name: listvmdisks
  path: /vcenter/vm/{vm}/hardware/disk
- description: Vmware Add a Virtual Disk to a Vm
  method: POST
  name: createvmdisk
  path: /vcenter/vm/{vm}/hardware/disk
- description: Vmware List Vm Network Adapters
  method: GET
  name: listvmethernet
  path: /vcenter/vm/{vm}/hardware/ethernet
- description: Vmware Add a Network Adapter to a Vm
  method: POST
  name: createvmethernet
  path: /vcenter/vm/{vm}/hardware/ethernet
- description: Vmware Get Guest Os Identity
  method: GET
  name: getvmguestidentity
  path: /vcenter/vm/{vm}/guest/identity
- description: Vmware Get Guest Networking Information
  method: GET
  name: getvmguestnetworking
  path: /vcenter/vm/{vm}/guest/networking
- description: Vmware List Esxi Hosts
  method: GET
  name: listhosts
  path: /vcenter/host
- description: Vmware Get Esxi Host Details
  method: GET
  name: gethost
  path: /vcenter/host/{host}
- description: Vmware Connect an Esxi Host
  method: POST
  name: connecthost
  path: /vcenter/host/{host}/connect
- description: Vmware Disconnect an Esxi Host
  method: POST
  name: disconnecthost
  path: /vcenter/host/{host}/disconnect
- description: Vmware List Datastores
  method: GET
  name: listdatastores
  path: /vcenter/datastore
- description: Vmware Get Datastore Details
  method: GET
  name: getdatastore
  path: /vcenter/datastore/{datastore}
- description: Vmware List Clusters
  method: GET
  name: listclusters
  path: /vcenter/cluster
- description: Vmware Get Cluster Details
  method: GET
  name: getcluster
  path: /vcenter/cluster/{cluster}
- description: Vmware List Networks
  method: GET
  name: listnetworks
  path: /vcenter/network
- description: Vmware List Datacenters
  method: GET
  name: listdatacenters
  path: /vcenter/datacenter
- description: Vmware Create a Datacenter
  method: POST
  name: createdatacenter
  path: /vcenter/datacenter
- description: Vmware Get Datacenter Details
  method: GET
  name: getdatacenter
  path: /vcenter/datacenter/{datacenter}
- description: Vmware Delete a Datacenter
  method: DELETE
  name: deletedatacenter
  path: /vcenter/datacenter/{datacenter}
- description: Vmware List Folders
  method: GET
  name: listfolders
  path: /vcenter/folder
- description: Vmware List Resource Pools
  method: GET
  name: listresourcepools
  path: /vcenter/resource-pool
- description: Vmware List Content Libraries
  method: GET
  name: listcontentlibraries
  path: /content/library
- description: Vmware Create a Content Library
  method: POST
  name: createcontentlibrary
  path: /content/library
- description: Vmware Get Content Library Details
  method: GET
  name: getcontentlibrary
  path: /content/library/{library_id}
- description: Vmware Delete a Content Library
  method: DELETE
  name: deletecontentlibrary
  path: /content/library/{library_id}
- description: Vmware List Storage Policies
  method: GET
  name: liststoragepolicies
  path: /vcenter/storage/policies
- description: Vmware List Tag Categories
  method: GET
  name: listtagcategories
  path: /cis/tagging/category
- description: Vmware Create a Tag Category
  method: POST
  name: createtagcategory
  path: /cis/tagging/category
- description: Vmware List Tags
  method: GET
  name: listtags
  path: /cis/tagging/tag
- description: Vmware Create a Tag
  method: POST
  name: createtag
  path: /cis/tagging/tag
- description: Vmware Attach a Tag to an Object
  method: POST
  name: attachtag
  path: /cis/tagging/tag-association?action=attach
personas: []
provider_name: VMware
provider_slug: vmware
search_terms:
- createsession
- getvmmemory
- vmware list esxi hosts
- vmware list virtual machines
- getvmcpu
- api
- vmware list vm network adapters
- vmware list tags
- poweronvm
- getsessioninfo
- vmware get vm cpu configuration
- getdatastore
- vmware delete a virtual machine
- vmware list resource pools
- vmware get vm memory configuration
- vmware power on a virtual machine
- vmware add a network adapter to a vm
- listresourcepools
- vmware get virtual machine details
- vmware delete a datacenter
- updatevmhardware
- deletecontentlibrary
- getvmhardware
- getdatacenter
- listdatastores
- createvm
- listnetworks
- vmware list datastores
- vmware create a new authentication session
- deletedatacenter
- vmware get current session information
- listhosts
- createdatacenter
- gethost
- listfolders
- getvmguestidentity
- connecthost
- virtualization
- vmware get content library details
- listtags
- createcontentlibrary
- vmware add a virtual disk to a vm
- getcontentlibrary
- createvmdisk
- vmware get datastore details
- vmware update vm cpu configuration
- getvmguestnetworking
- resetvm
- updatevmcpu
- vmware get guest networking information
- updatevmmemory
- poweroffvm
- vmware suspend a virtual machine
- listcontentlibraries
- liststoragepolicies
- vmware get esxi host details
- vmware get datacenter details
- vmware attach a tag to an object
- createtagcategory
- container management
- cloud computing
- infrastructure
- listvms
- disconnecthost
- vmware get vm hardware configuration
- listvmethernet
- vmware list storage policies
- vmware create a content library
- vmware list content libraries
- vmware get guest os identity
- createtag
- vmware delete a content library
- hybrid cloud
- vmware create a tag category
- vmware reset a virtual machine
- vmware list datacenters
- vmware
- vmware create a new virtual machine
- getvm
- listtagcategories
- getcluster
- vmware disconnect an esxi host
- deletesession
- getvmpowerstate
- createvmethernet
- vmware list folders
- listvmdisks
- vmware update vm memory configuration
- deletevm
- vmware terminate the current session
- vmware get cluster details
- vmware list tag categories
- listclusters
- attachtag
- vmware connect an esxi host
- vmware update vm hardware configuration
- vmware list vm virtual disks
- suspendvm
- vmware create a tag
- listdatacenters
- vmware power off a virtual machine
- vmware create a datacenter
- vmware list clusters
- vmware get vm power state
- vmware list networks
slug: vmware-capability
source_filename: vmware-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VMware vSphere Automation REST API\n  description: RESTful API for managing VMware vSphere virtualization platform resources including virtual machines, hosts,\n    datastores, clusters, networks, and related infrastructure. The vSphere Automation API provides modern REST endpoints\n    for vCenter Server operations using JSON payloads and session-based or OAuth authentication. This API supersedes the legacy\n    SOAP-based vSphere Web Services API for most automation use cases.\n  tags:\n  - Vmware\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: vmware\n    baseUri: https://vcenter.example.com/api\n    description: VMware vSphere Automation REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: vmware-api-session-id\n      value: '{{VMWARE_TOKEN}}'\n    resources:\n    - name: session\n      path: /session\n      operations:\n   \
  \   - name: createsession\n        method: POST\n        description: Vmware Create a New Authentication Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesession\n        method: DELETE\n        description: Vmware Terminate the Current Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsessioninfo\n        method: GET\n        description: Vmware Get Current Session Information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm\n      path: /vcenter/vm\n      operations:\n      - name: listvms\n        method: GET\n        description: Vmware List Virtual Machines\n        inputParameters:\n        - name: filter.vms\n          in: query\n          type: array\n          description:\
  \ Identifiers of VMs to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of VMs to filter by (exact match)\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the VMs\n        - name: filter.datacenters\n          in: query\n          type: array\n          description: Datacenters that must contain the VMs\n        - name: filter.hosts\n          in: query\n          type: array\n          description: Hosts that must contain the VMs\n        - name: filter.clusters\n          in: query\n          type: array\n          description: Clusters that must contain the VMs\n        - name: filter.resource_pools\n          in: query\n          type: array\n          description: Resource pools that must contain the VMs\n        - name: filter.power_states\n          in: query\n          type: array\n          description: Power states to filter by\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvm\n        method: POST\n        description: Vmware Create a New Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm\n      path: /vcenter/vm/{vm}\n      operations:\n      - name: getvm\n        method: GET\n        description: Vmware Get Virtual Machine Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevm\n        method: DELETE\n        description: Vmware Delete a Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-power\n      path: /vcenter/vm/{vm}/power\n      operations:\n      - name: getvmpowerstate\n\
  \        method: GET\n        description: Vmware Get Vm Power State\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-power-action-start\n      path: /vcenter/vm/{vm}/power?action=start\n      operations:\n      - name: poweronvm\n        method: POST\n        description: Vmware Power on a Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-power-action-stop\n      path: /vcenter/vm/{vm}/power?action=stop\n      operations:\n      - name: poweroffvm\n        method: POST\n        description: Vmware Power Off a Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-power-action-suspend\n      path: /vcenter/vm/{vm}/power?action=suspend\n      operations:\n\
  \      - name: suspendvm\n        method: POST\n        description: Vmware Suspend a Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-power-action-reset\n      path: /vcenter/vm/{vm}/power?action=reset\n      operations:\n      - name: resetvm\n        method: POST\n        description: Vmware Reset a Virtual Machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-hardware\n      path: /vcenter/vm/{vm}/hardware\n      operations:\n      - name: getvmhardware\n        method: GET\n        description: Vmware Get Vm Hardware Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevmhardware\n        method: PATCH\n        description: Vmware Update Vm Hardware\
  \ Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-hardware-cpu\n      path: /vcenter/vm/{vm}/hardware/cpu\n      operations:\n      - name: getvmcpu\n        method: GET\n        description: Vmware Get Vm Cpu Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevmcpu\n        method: PATCH\n        description: Vmware Update Vm Cpu Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-hardware-memory\n      path: /vcenter/vm/{vm}/hardware/memory\n      operations:\n      - name: getvmmemory\n        method: GET\n        description: Vmware Get Vm Memory Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: updatevmmemory\n        method: PATCH\n        description: Vmware Update Vm Memory Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-hardware-disk\n      path: /vcenter/vm/{vm}/hardware/disk\n      operations:\n      - name: listvmdisks\n        method: GET\n        description: Vmware List Vm Virtual Disks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvmdisk\n        method: POST\n        description: Vmware Add a Virtual Disk to a Vm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-hardware-ethernet\n      path: /vcenter/vm/{vm}/hardware/ethernet\n      operations:\n      - name: listvmethernet\n        method:\
  \ GET\n        description: Vmware List Vm Network Adapters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvmethernet\n        method: POST\n        description: Vmware Add a Network Adapter to a Vm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-guest-identity\n      path: /vcenter/vm/{vm}/guest/identity\n      operations:\n      - name: getvmguestidentity\n        method: GET\n        description: Vmware Get Guest Os Identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-vm-vm-guest-networking\n      path: /vcenter/vm/{vm}/guest/networking\n      operations:\n      - name: getvmguestnetworking\n        method: GET\n        description: Vmware Get Guest Networking Information\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-host\n      path: /vcenter/host\n      operations:\n      - name: listhosts\n        method: GET\n        description: Vmware List Esxi Hosts\n        inputParameters:\n        - name: filter.hosts\n          in: query\n          type: array\n          description: Identifiers of hosts to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of hosts to filter by\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the hosts\n        - name: filter.datacenters\n          in: query\n          type: array\n          description: Datacenters that must contain the hosts\n        - name: filter.clusters\n          in: query\n          type: array\n          description: Clusters that must contain the hosts\n        -\
  \ name: filter.connection_states\n          in: query\n          type: array\n          description: Connection states to filter by\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-host-host\n      path: /vcenter/host/{host}\n      operations:\n      - name: gethost\n        method: GET\n        description: Vmware Get Esxi Host Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-host-host-connect\n      path: /vcenter/host/{host}/connect\n      operations:\n      - name: connecthost\n        method: POST\n        description: Vmware Connect an Esxi Host\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-host-host-disconnect\n      path: /vcenter/host/{host}/disconnect\n      operations:\n \
  \     - name: disconnecthost\n        method: POST\n        description: Vmware Disconnect an Esxi Host\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-datastore\n      path: /vcenter/datastore\n      operations:\n      - name: listdatastores\n        method: GET\n        description: Vmware List Datastores\n        inputParameters:\n        - name: filter.datastores\n          in: query\n          type: array\n          description: Identifiers of datastores to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of datastores to filter by\n        - name: filter.types\n          in: query\n          type: array\n          description: Types of datastores to filter by\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the datastores\n        - name: filter.datacenters\n\
  \          in: query\n          type: array\n          description: Datacenters that must contain the datastores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-datastore-datastore\n      path: /vcenter/datastore/{datastore}\n      operations:\n      - name: getdatastore\n        method: GET\n        description: Vmware Get Datastore Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-cluster\n      path: /vcenter/cluster\n      operations:\n      - name: listclusters\n        method: GET\n        description: Vmware List Clusters\n        inputParameters:\n        - name: filter.clusters\n          in: query\n          type: array\n          description: Identifiers of clusters to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description:\
  \ Names of clusters to filter by\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the clusters\n        - name: filter.datacenters\n          in: query\n          type: array\n          description: Datacenters that must contain the clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-cluster-cluster\n      path: /vcenter/cluster/{cluster}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Vmware Get Cluster Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-network\n      path: /vcenter/network\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Vmware List Networks\n        inputParameters:\n        - name: filter.networks\n    \
  \      in: query\n          type: array\n          description: Identifiers of networks to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of networks to filter by\n        - name: filter.types\n          in: query\n          type: array\n          description: Types of networks to filter by\n        - name: filter.datacenters\n          in: query\n          type: array\n          description: Datacenters that must contain the networks\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the networks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-datacenter\n      path: /vcenter/datacenter\n      operations:\n      - name: listdatacenters\n        method: GET\n        description: Vmware List Datacenters\n        inputParameters:\n        - name: filter.datacenters\n\
  \          in: query\n          type: array\n          description: Identifiers of datacenters to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of datacenters to filter by\n        - name: filter.folders\n          in: query\n          type: array\n          description: Folders that must contain the datacenters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatacenter\n        method: POST\n        description: Vmware Create a Datacenter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-datacenter-datacenter\n      path: /vcenter/datacenter/{datacenter}\n      operations:\n      - name: getdatacenter\n        method: GET\n        description: Vmware Get Datacenter Details\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletedatacenter\n        method: DELETE\n        description: Vmware Delete a Datacenter\n        inputParameters:\n        - name: force\n          in: query\n          type: boolean\n          description: Force delete even if datacenter is not empty\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-folder\n      path: /vcenter/folder\n      operations:\n      - name: listfolders\n        method: GET\n        description: Vmware List Folders\n        inputParameters:\n        - name: filter.folders\n          in: query\n          type: array\n          description: Identifiers of folders to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of folders to filter by\n        - name: filter.type\n          in: query\n          type: string\n   \
  \       description: Type of folder to filter by\n        - name: filter.parent_folders\n          in: query\n          type: array\n          description: Parent folders to filter by\n        - name: filter.datacenters\n          in: query\n          type: array\n          description: Datacenters that must contain the folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vcenter-resource-pool\n      path: /vcenter/resource-pool\n      operations:\n      - name: listresourcepools\n        method: GET\n        description: Vmware List Resource Pools\n        inputParameters:\n        - name: filter.resource_pools\n          in: query\n          type: array\n          description: Identifiers of resource pools to filter by\n        - name: filter.names\n          in: query\n          type: array\n          description: Names of resource pools to filter by\n        - name: filter.clusters\n    \
  \      in: query\n          type: array\n          description: Clusters that must contain the resource pools\n        - name: filter.hosts\n          in: query\n          type: array\n          description: Hosts that must contain the resource pools\n        - name: filter.parent_resource_pools\n          in: query\n          type: array\n          description: Parent resource pools to filter by\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-library\n      path: /content/library\n      operations:\n      - name: listcontentlibraries\n        method: GET\n        description: Vmware List Content Libraries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontentlibrary\n        method: POST\n        description: Vmware Create a Content Library\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: content-library-library-id\n      path: /content/library/{library_id}\n      operations:\n      - name: getcontentlibrary\n        method: GET\n        description: Vmware Get Content Library Details\n        inputParameters:\n        - name: library_id\n          in: path\n          type: string\n          required: true\n          description: Identifier of the content library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontentlibrary\n        method: DELETE\n        description: Vmware Delete a Content Library\n        inputParameters:\n        - name: library_id\n          in: path\n          type: string\n          required: true\n          description: Identifier of the content library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: vcenter-storage-policies\n      path: /vcenter/storage/policies\n      operations:\n      - name: liststoragepolicies\n        method: GET\n        description: Vmware List Storage Policies\n        inputParameters:\n        - name: filter.policies\n          in: query\n          type: array\n          description: Identifiers of storage policies to filter by\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cis-tagging-category\n      path: /cis/tagging/category\n      operations:\n      - name: listtagcategories\n        method: GET\n        description: Vmware List Tag Categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtagcategory\n        method: POST\n        description: Vmware Create a Tag Category\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: cis-tagging-tag\n      path: /cis/tagging/tag\n      operations:\n      - name: listtags\n        method: GET\n        description: Vmware List Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtag\n        method: POST\n        description: Vmware Create a Tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cis-tagging-tag-association-action-attach\n      path: /cis/tagging/tag-association?action=attach\n      operations:\n      - name: attachtag\n        method: POST\n        description: Vmware Attach a Tag to an Object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vmware-rest\n\
  \    description: REST adapter for VMware vSphere Automation REST API.\n    resources:\n    - path: /session\n      name: createsession\n      operations:\n      - method: POST\n        name: createsession\n        description: Vmware Create a New Authentication Session\n        call: vmware.createsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /session\n      name: deletesession\n      operations:\n      - method: DELETE\n        name: deletesession\n        description: Vmware Terminate the Current Session\n        call: vmware.deletesession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /session\n      name: getsessioninfo\n      operations:\n      - method: GET\n        name: getsessioninfo\n        description: Vmware Get Current Session Information\n        call: vmware.getsessioninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm\n      name:\
  \ listvms\n      operations:\n      - method: GET\n        name: listvms\n        description: Vmware List Virtual Machines\n        call: vmware.listvms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm\n      name: createvm\n      operations:\n      - method: POST\n        name: createvm\n        description: Vmware Create a New Virtual Machine\n        call: vmware.createvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}\n      name: getvm\n      operations:\n      - method: GET\n        name: getvm\n        description: Vmware Get Virtual Machine Details\n        call: vmware.getvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}\n      name: deletevm\n      operations:\n      - method: DELETE\n        name: deletevm\n        description: Vmware Delete a Virtual Machine\n        call: vmware.deletevm\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/power\n      name: getvmpowerstate\n      operations:\n      - method: GET\n        name: getvmpowerstate\n        description: Vmware Get Vm Power State\n        call: vmware.getvmpowerstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/power?action=start\n      name: poweronvm\n      operations:\n      - method: POST\n        name: poweronvm\n        description: Vmware Power on a Virtual Machine\n        call: vmware.poweronvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/power?action=stop\n      name: poweroffvm\n      operations:\n      - method: POST\n        name: poweroffvm\n        description: Vmware Power Off a Virtual Machine\n        call: vmware.poweroffvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/power?action=suspend\n \
  \     name: suspendvm\n      operations:\n      - method: POST\n        name: suspendvm\n        description: Vmware Suspend a Virtual Machine\n        call: vmware.suspendvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/power?action=reset\n      name: resetvm\n      operations:\n      - method: POST\n        name: resetvm\n        description: Vmware Reset a Virtual Machine\n        call: vmware.resetvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware\n      name: getvmhardware\n      operations:\n      - method: GET\n        name: getvmhardware\n        description: Vmware Get Vm Hardware Configuration\n        call: vmware.getvmhardware\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware\n      name: updatevmhardware\n      operations:\n      - method: PATCH\n        name: updatevmhardware\n        description:\
  \ Vmware Update Vm Hardware Configuration\n        call: vmware.updatevmhardware\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/cpu\n      name: getvmcpu\n      operations:\n      - method: GET\n        name: getvmcpu\n        description: Vmware Get Vm Cpu Configuration\n        call: vmware.getvmcpu\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/cpu\n      name: updatevmcpu\n      operations:\n      - method: PATCH\n        name: updatevmcpu\n        description: Vmware Update Vm Cpu Configuration\n        call: vmware.updatevmcpu\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/memory\n      name: getvmmemory\n      operations:\n      - method: GET\n        name: getvmmemory\n        description: Vmware Get Vm Memory Configuration\n        call: vmware.getvmmemory\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/memory\n      name: updatevmmemory\n      operations:\n      - method: PATCH\n        name: updatevmmemory\n        description: Vmware Update Vm Memory Configuration\n        call: vmware.updatevmmemory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/disk\n      name: listvmdisks\n      operations:\n      - method: GET\n        name: listvmdisks\n        description: Vmware List Vm Virtual Disks\n        call: vmware.listvmdisks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/disk\n      name: createvmdisk\n      operations:\n      - method: POST\n        name: createvmdisk\n        description: Vmware Add a Virtual Disk to a Vm\n        call: vmware.createvmdisk\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/ethernet\n\
  \      name: listvmethernet\n      operations:\n      - method: GET\n        name: listvmethernet\n        description: Vmware List Vm Network Adapters\n        call: vmware.listvmethernet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/hardware/ethernet\n      name: createvmethernet\n      operations:\n      - method: POST\n        name: createvmethernet\n        description: Vmware Add a Network Adapter to a Vm\n        call: vmware.createvmethernet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/guest/identity\n      name: getvmguestidentity\n      operations:\n      - method: GET\n        name: getvmguestidentity\n        description: Vmware Get Guest Os Identity\n        call: vmware.getvmguestidentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/vm/{vm}/guest/networking\n      name: getvmguestnetworking\n      operations:\n\
  \      - method: GET\n        name: getvmguestnetworking\n        description: Vmware Get Guest Networking Information\n        call: vmware.getvmguestnetworking\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/host\n      name: listhosts\n      operations:\n      - method: GET\n        name: listhosts\n        description: Vmware List Esxi Hosts\n        call: vmware.listhosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/host/{host}\n      name: gethost\n      operations:\n      - method: GET\n        name: gethost\n        description: Vmware Get Esxi Host Details\n        call: vmware.gethost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/host/{host}/connect\n      name: connecthost\n      operations:\n      - method: POST\n        name: connecthost\n        description: Vmware Connect an Esxi Host\n        call: vmware.connecthost\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/host/{host}/disconnect\n      name: disconnecthost\n      operations:\n      - method: POST\n        name: disconnecthost\n        description: Vmware Disconnect an Esxi Host\n        call: vmware.disconnecthost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datastore\n      name: listdatastores\n      operations:\n      - method: GET\n        name: listdatastores\n        description: Vmware List Datastores\n        call: vmware.listdatastores\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datastore/{datastore}\n      name: getdatastore\n      operations:\n      - method: GET\n        name: getdatastore\n        description: Vmware Get Datastore Details\n        call: vmware.getdatastore\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/cluster\n      name:\
  \ listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Vmware List Clusters\n        call: vmware.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/cluster/{cluster}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Vmware Get Cluster Details\n        call: vmware.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/network\n      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Vmware List Networks\n        call: vmware.listnetworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datacenter\n      name: listdatacenters\n      operations:\n      - method: GET\n        name: listdatacenters\n        description: Vmware List Datacenters\n        call: vmware.listdatacenters\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datacenter\n      name: createdatacenter\n      operations:\n      - method: POST\n        name: createdatacenter\n        description: Vmware Create a Datacenter\n        call: vmware.createdatacenter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datacenter/{datacenter}\n      name: getdatacenter\n      operations:\n      - method: GET\n        name: getdatacenter\n        description: Vmware Get Datacenter Details\n        call: vmware.getdatacenter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/datacenter/{datacenter}\n      name: deletedatacenter\n      operations:\n      - method: DELETE\n        name: deletedatacenter\n        description: Vmware Delete a Datacenter\n        call: vmware.deletedatacenter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /vcenter/folder\n      name: listfolders\n      operations:\n      - method: GET\n        name: listfolders\n        description: Vmware List Folders\n        call: vmware.listfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vcenter/resource-pool\n      name: listresourcepools\n      operations:\n      - method: GET\n        name: listresourcepools\n        description: Vmware List Resource Pools\n        call: vmware.listresourcepools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/library\n      name: listcontentlibraries\n      operations:\n      - method: GET\n        name: listcontentlibraries\n        description: Vmware List Content Libraries\n        call: vmware.listcontentlibraries\n        out\n\n# --- truncated at 32 KB (54 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/vmware/refs/heads/main/capabilities/vmware-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vmware/refs/heads/main/capabilities/vmware-capability.yaml
tags:
- Vmware
- API
tools:
- description: Vmware Create a New Authentication Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsession
- description: Vmware Terminate the Current Session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesession
- description: Vmware Get Current Session Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsessioninfo
- description: Vmware List Virtual Machines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvms
- description: Vmware Create a New Virtual Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvm
- description: Vmware Get Virtual Machine Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvm
- description: Vmware Delete a Virtual Machine
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevm
- description: Vmware Get Vm Power State
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmpowerstate
- description: Vmware Power on a Virtual Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: poweronvm
- description: Vmware Power Off a Virtual Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: poweroffvm
- description: Vmware Suspend a Virtual Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suspendvm
- description: Vmware Reset a Virtual Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resetvm
- description: Vmware Get Vm Hardware Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmhardware
- description: Vmware Update Vm Hardware Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatevmhardware
- description: Vmware Get Vm Cpu Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmcpu
- description: Vmware Update Vm Cpu Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatevmcpu
- description: Vmware Get Vm Memory Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmmemory
- description: Vmware Update Vm Memory Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatevmmemory
- description: Vmware List Vm Virtual Disks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvmdisks
- description: Vmware Add a Virtual Disk to a Vm
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvmdisk
- description: Vmware List Vm Network Adapters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvmethernet
- description: Vmware Add a Network Adapter to a Vm
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvmethernet
- description: Vmware Get Guest Os Identity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmguestidentity
- description: Vmware Get Guest Networking Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmguestnetworking
- description: Vmware List Esxi Hosts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhosts
- description: Vmware Get Esxi Host Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethost
- description: Vmware Connect an Esxi Host
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: connecthost
- description: Vmware Disconnect an Esxi Host
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: disconnecthost
- description: Vmware List Datastores
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatastores
- description: Vmware Get Datastore Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatastore
- description: Vmware List Clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Vmware Get Cluster Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Vmware List Networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Vmware List Datacenters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatacenters
- description: Vmware Create a Datacenter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatacenter
- description: Vmware Get Datacenter Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatacenter
- description: Vmware Delete a Datacenter
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatacenter
- description: Vmware List Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfolders
- description: Vmware List Resource Pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresourcepools
- description: Vmware List Content Libraries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontentlibraries
- description: Vmware Create a Content Library
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontentlibrary
- description: Vmware Get Content Library Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontentlibrary
- description: Vmware Delete a Content Library
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontentlibrary
- description: Vmware List Storage Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststoragepolicies
- description: Vmware List Tag Categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtagcategories
- description: Vmware Create a Tag Category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtagcategory
- description: Vmware List Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
- description: Vmware Create a Tag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtag
- description: Vmware Attach a Tag to an Object
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: attachtag
---
