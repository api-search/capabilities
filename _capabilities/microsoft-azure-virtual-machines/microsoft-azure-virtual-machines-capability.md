---
categories: []
consumed_apis: []
description: REST API for creating and managing Azure Virtual Machines. Provides operations for provisioning, starting, stopping, deallocating, restarting, reimaging, capturing, and deleting virtual machines, as well as managing data disks, extensions, patching, and run commands. All operations follow the Azure Resource Manager pattern and require OAuth 2.0 authentication via Microsoft Entra ID.
layout: capability
name: Azure Virtual Machines REST API
operations:
- description: Azure Virtual Machines List virtual machines in a resource group
  method: GET
  name: virtualmachines-list
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines
- description: Azure Virtual Machines List all virtual machines in a subscription
  method: GET
  name: virtualmachines-listall
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/virtualMachines
- description: Azure Virtual Machines List virtual machines by location
  method: GET
  name: virtualmachines-listbylocation
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/locations/{location}/virtualMachines
- description: Azure Virtual Machines Create or update a virtual machine
  method: PUT
  name: virtualmachines-createorupdate
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}
- description: Azure Virtual Machines Get a virtual machine
  method: GET
  name: virtualmachines-get
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}
- description: Azure Virtual Machines Update a virtual machine
  method: PATCH
  name: virtualmachines-update
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}
- description: Azure Virtual Machines Delete a virtual machine
  method: DELETE
  name: virtualmachines-delete
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}
- description: Azure Virtual Machines Get the instance view of a virtual machine
  method: GET
  name: virtualmachines-instanceview
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/instanceView
- description: Azure Virtual Machines Start a virtual machine
  method: POST
  name: virtualmachines-start
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/start
- description: Azure Virtual Machines Power off a virtual machine
  method: POST
  name: virtualmachines-poweroff
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/powerOff
- description: Azure Virtual Machines Deallocate a virtual machine
  method: POST
  name: virtualmachines-deallocate
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/deallocate
- description: Azure Virtual Machines Restart a virtual machine
  method: POST
  name: virtualmachines-restart
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/restart
- description: Azure Virtual Machines Redeploy a virtual machine
  method: POST
  name: virtualmachines-redeploy
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/redeploy
- description: Azure Virtual Machines Reimage a virtual machine
  method: POST
  name: virtualmachines-reimage
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reimage
- description: Azure Virtual Machines Capture a virtual machine
  method: POST
  name: virtualmachines-capture
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/capture
- description: Azure Virtual Machines Generalize a virtual machine
  method: POST
  name: virtualmachines-generalize
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/generalize
- description: Azure Virtual Machines Convert to managed disks
  method: POST
  name: virtualmachines-converttomanageddisks
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/convertToManagedDisks
- description: Azure Virtual Machines Perform maintenance on a virtual machine
  method: POST
  name: virtualmachines-performmaintenance
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/performMaintenance
- description: Azure Virtual Machines Simulate eviction of a spot virtual machine
  method: POST
  name: virtualmachines-simulateeviction
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/simulateEviction
- description: Azure Virtual Machines Reapply a virtual machine state
  method: POST
  name: virtualmachines-reapply
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reapply
- description: Azure Virtual Machines Retrieve boot diagnostics data
  method: POST
  name: virtualmachines-retrievebootdiagnosticsdata
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/retrieveBootDiagnosticsData
- description: Azure Virtual Machines Assess patches on a virtual machine
  method: POST
  name: virtualmachines-assesspatches
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/assessPatches
- description: Azure Virtual Machines Install patches on a virtual machine
  method: POST
  name: virtualmachines-installpatches
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/installPatches
- description: Azure Virtual Machines Attach or detach data disks
  method: POST
  name: virtualmachines-attachdetachdatadisks
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/attachDetachDataDisks
- description: Azure Virtual Machines List available sizes for a virtual machine
  method: GET
  name: virtualmachines-listavailablesizes
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/vmSizes
- description: Azure Virtual Machines Run command on a virtual machine
  method: POST
  name: virtualmachines-runcommand
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/runCommand
personas: []
provider_name: Azure Virtual Machines
provider_slug: microsoft-azure-virtual-machines
search_terms:
- virtualmachines generalize
- azure virtual machines get the instance view of a virtual machine
- virtualmachines assesspatches
- compute
- virtualmachines installpatches
- azure virtual machines start a virtual machine
- infrastructure
- virtualmachines list
- azure virtual machines perform maintenance on a virtual machine
- virtualmachines delete
- azure virtual machines get a virtual machine
- azure virtual machines assess patches on a virtual machine
- virtualmachines listavailablesizes
- machines
- azure virtual machines redeploy a virtual machine
- azure virtual machines list available sizes for a virtual machine
- azure virtual machines run command on a virtual machine
- azure
- azure virtual machines deallocate a virtual machine
- iaas
- virtual machines
- virtualmachines start
- virtualmachines reimage
- virtualmachines retrievebootdiagnosticsdata
- azure virtual machines restart a virtual machine
- azure virtual machines create or update a virtual machine
- virtualmachines get
- azure virtual machines capture a virtual machine
- virtualmachines simulateeviction
- cloud computing
- virtualmachines listall
- azure virtual machines install patches on a virtual machine
- azure virtual machines attach or detach data disks
- virtualmachines poweroff
- virtualmachines reapply
- virtualmachines restart
- azure virtual machines reimage a virtual machine
- virtualmachines converttomanageddisks
- virtual
- virtualmachines runcommand
- azure virtual machines list virtual machines by location
- azure virtual machines convert to managed disks
- api
- virtualmachines createorupdate
- virtualmachines capture
- azure virtual machines generalize a virtual machine
- azure virtual machines reapply a virtual machine state
- virtualmachines instanceview
- azure virtual machines list virtual machines in a resource group
- azure virtual machines retrieve boot diagnostics data
- azure virtual machines simulate eviction of a spot virtual machine
- virtualmachines redeploy
- virtualmachines deallocate
- azure virtual machines power off a virtual machine
- virtualmachines performmaintenance
- virtualmachines attachdetachdatadisks
- azure virtual machines list all virtual machines in a subscription
- virtualmachines update
- azure virtual machines update a virtual machine
- microsoft
- azure virtual machines delete a virtual machine
- virtualmachines listbylocation
slug: microsoft-azure-virtual-machines-capability
source_filename: microsoft-azure-virtual-machines-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Virtual Machines REST API\n  description: REST API for creating and managing Azure Virtual Machines. Provides operations for provisioning, starting,\n    stopping, deallocating, restarting, reimaging, capturing, and deleting virtual machines, as well as managing data disks,\n    extensions, patching, and run commands. All operations follow the Azure Resource Manager pattern and require OAuth 2.0\n    authentication via Microsoft Entra ID.\n  tags:\n  - Microsoft\n  - Azure\n  - Virtual\n  - Machines\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-virtual-machines\n    baseUri: https://management.azure.com\n    description: Azure Virtual Machines REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_VIRTUAL_MACHINES_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n    \
  \  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines\n      operations:\n      - name: virtualmachines-list\n        method: GET\n        description: Azure Virtual Machines List virtual machines in a resource group\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          description: The system query option to filter VMs returned in the response. Allowed value is 'virtualMachineScaleSet/id'\n            eq /subscriptions/{subId}/resourceGroups/{rgName}/p\n        - name: $expand\n          in: query\n          type: string\n          description: The expand expression to apply on the operation. 'instanceView' retrieves a snapshot of the runtime\n            properties of the virtual machine that is managed by the pla\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n\
  \      path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/virtualMachines\n      operations:\n      - name: virtualmachines-listall\n        method: GET\n        description: Azure Virtual Machines List all virtual machines in a subscription\n        inputParameters:\n        - name: statusOnly\n          in: query\n          type: string\n          description: statusOnly=true enables fetching run time status of all Virtual Machines in the subscription.\n        - name: $filter\n          in: query\n          type: string\n          description: The system query option to filter VMs returned in the response.\n        - name: $expand\n          in: query\n          type: string\n          description: The expand expression to apply on the operation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/locations/{location}/virtualMachines\n\
  \      operations:\n      - name: virtualmachines-listbylocation\n        method: GET\n        description: Azure Virtual Machines List virtual machines by location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}\n      operations:\n      - name: virtualmachines-createorupdate\n        method: PUT\n        description: Azure Virtual Machines Create or update a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: virtualmachines-get\n        method: GET\n        description: Azure Virtual Machines Get a virtual machine\n        inputParameters:\n        - name: $expand\n          in: query\n          type: string\n\
  \          description: The expand expression to apply on the operation. 'instanceView' retrieves a snapshot of the runtime\n            properties of the virtual machine.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: virtualmachines-update\n        method: PATCH\n        description: Azure Virtual Machines Update a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: virtualmachines-delete\n        method: DELETE\n        description: Azure Virtual Machines Delete a virtual machine\n        inputParameters:\n        - name: forceDeletion\n          in: query\n          type: boolean\n          description: Optional parameter to force delete virtual machines.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/instanceView\n      operations:\n      - name: virtualmachines-instanceview\n        method: GET\n        description: Azure Virtual Machines Get the instance view of a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/start\n      operations:\n      - name: virtualmachines-start\n        method: POST\n        description: Azure Virtual Machines Start a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n\
  \      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/powerOff\n      operations:\n      - name: virtualmachines-poweroff\n        method: POST\n        description: Azure Virtual Machines Power off a virtual machine\n        inputParameters:\n        - name: skipShutdown\n          in: query\n          type: boolean\n          description: The parameter to request non-graceful VM shutdown. True value for this flag indicates non-graceful\n            shutdown whereas false indicates otherwise.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/deallocate\n      operations:\n      - name: virtualmachines-deallocate\n        method: POST\n    \
  \    description: Azure Virtual Machines Deallocate a virtual machine\n        inputParameters:\n        - name: hibernate\n          in: query\n          type: boolean\n          description: Optional parameter to hibernate a virtual machine.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/restart\n      operations:\n      - name: virtualmachines-restart\n        method: POST\n        description: Azure Virtual Machines Restart a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/redeploy\n\
  \      operations:\n      - name: virtualmachines-redeploy\n        method: POST\n        description: Azure Virtual Machines Redeploy a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reimage\n      operations:\n      - name: virtualmachines-reimage\n        method: POST\n        description: Azure Virtual Machines Reimage a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/capture\n      operations:\n      - name: virtualmachines-capture\n\
  \        method: POST\n        description: Azure Virtual Machines Capture a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/generalize\n      operations:\n      - name: virtualmachines-generalize\n        method: POST\n        description: Azure Virtual Machines Generalize a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/convertToManagedDisks\n      operations:\n      - name: virtualmachines-converttomanageddisks\n\
  \        method: POST\n        description: Azure Virtual Machines Convert to managed disks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/performMaintenance\n      operations:\n      - name: virtualmachines-performmaintenance\n        method: POST\n        description: Azure Virtual Machines Perform maintenance on a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/simulateEviction\n      operations:\n      - name: virtualmachines-simulateeviction\n\
  \        method: POST\n        description: Azure Virtual Machines Simulate eviction of a spot virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reapply\n      operations:\n      - name: virtualmachines-reapply\n        method: POST\n        description: Azure Virtual Machines Reapply a virtual machine state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/retrieveBootDiagnosticsData\n      operations:\n      - name: virtualmachines-retrievebootdiagnosticsdata\n\
  \        method: POST\n        description: Azure Virtual Machines Retrieve boot diagnostics data\n        inputParameters:\n        - name: sasUriExpirationTimeInMinutes\n          in: query\n          type: integer\n          description: Expiration duration in minutes for the SAS URIs with a value between 1 to 1440 minutes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/assessPatches\n      operations:\n      - name: virtualmachines-assesspatches\n        method: POST\n        description: Azure Virtual Machines Assess patches on a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n\
  \      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/installPatches\n      operations:\n      - name: virtualmachines-installpatches\n        method: POST\n        description: Azure Virtual Machines Install patches on a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/attachDetachDataDisks\n      operations:\n      - name: virtualmachines-attachdetachdatadisks\n        method: POST\n        description: Azure Virtual Machines Attach or detach data disks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n\
  \      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/vmSizes\n      operations:\n      - name: virtualmachines-listavailablesizes\n        method: GET\n        description: Azure Virtual Machines List available sizes for a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/runCommand\n      operations:\n      - name: virtualmachines-runcommand\n        method: POST\n        description: Azure Virtual Machines Run command on a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ microsoft-azure-virtual-machines-rest\n    description: REST adapter for Azure Virtual Machines REST API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines\n      name: virtualmachines-list\n      operations:\n      - method: GET\n        name: virtualmachines-list\n        description: Azure Virtual Machines List virtual machines in a resource group\n        call: microsoft-azure-virtual-machines.virtualmachines-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/virtualMachines\n      name: virtualmachines-listall\n      operations:\n      - method: GET\n        name: virtualmachines-listall\n        description: Azure Virtual Machines List all virtual machines in a subscription\n        call: microsoft-azure-virtual-machines.virtualmachines-listall\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Compute/locations/{location}/virtualMachines\n      name: virtualmachines-listbylocation\n      operations:\n      - method: GET\n        name: virtualmachines-listbylocation\n        description: Azure Virtual Machines List virtual machines by location\n        call: microsoft-azure-virtual-machines.virtualmachines-listbylocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}\n      name: virtualmachines-createorupdate\n      operations:\n      - method: PUT\n        name: virtualmachines-createorupdate\n        description: Azure Virtual Machines Create or update a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-createorupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}\n      name: virtualmachines-get\n      operations:\n      - method: GET\n        name: virtualmachines-get\n        description: Azure Virtual Machines Get a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}\n      name: virtualmachines-update\n      operations:\n      - method: PATCH\n        name: virtualmachines-update\n        description: Azure Virtual Machines Update a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}\n\
  \      name: virtualmachines-delete\n      operations:\n      - method: DELETE\n        name: virtualmachines-delete\n        description: Azure Virtual Machines Delete a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/instanceView\n      name: virtualmachines-instanceview\n      operations:\n      - method: GET\n        name: virtualmachines-instanceview\n        description: Azure Virtual Machines Get the instance view of a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-instanceview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/start\n      name: virtualmachines-start\n\
  \      operations:\n      - method: POST\n        name: virtualmachines-start\n        description: Azure Virtual Machines Start a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/powerOff\n      name: virtualmachines-poweroff\n      operations:\n      - method: POST\n        name: virtualmachines-poweroff\n        description: Azure Virtual Machines Power off a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-poweroff\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/deallocate\n      name: virtualmachines-deallocate\n      operations:\n      - method: POST\n \
  \       name: virtualmachines-deallocate\n        description: Azure Virtual Machines Deallocate a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-deallocate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/restart\n      name: virtualmachines-restart\n      operations:\n      - method: POST\n        name: virtualmachines-restart\n        description: Azure Virtual Machines Restart a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-restart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/redeploy\n      name: virtualmachines-redeploy\n      operations:\n      - method: POST\n        name: virtualmachines-redeploy\n\
  \        description: Azure Virtual Machines Redeploy a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-redeploy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reimage\n      name: virtualmachines-reimage\n      operations:\n      - method: POST\n        name: virtualmachines-reimage\n        description: Azure Virtual Machines Reimage a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-reimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/capture\n      name: virtualmachines-capture\n      operations:\n      - method: POST\n        name: virtualmachines-capture\n        description: Azure Virtual Machines Capture\
  \ a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-capture\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/generalize\n      name: virtualmachines-generalize\n      operations:\n      - method: POST\n        name: virtualmachines-generalize\n        description: Azure Virtual Machines Generalize a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-generalize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/convertToManagedDisks\n      name: virtualmachines-converttomanageddisks\n      operations:\n      - method: POST\n        name: virtualmachines-converttomanageddisks\n        description: Azure Virtual Machines\
  \ Convert to managed disks\n        call: microsoft-azure-virtual-machines.virtualmachines-converttomanageddisks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/performMaintenance\n      name: virtualmachines-performmaintenance\n      operations:\n      - method: POST\n        name: virtualmachines-performmaintenance\n        description: Azure Virtual Machines Perform maintenance on a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-performmaintenance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/simulateEviction\n      name: virtualmachines-simulateeviction\n      operations:\n      - method: POST\n        name: virtualmachines-simulateeviction\n\
  \        description: Azure Virtual Machines Simulate eviction of a spot virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-simulateeviction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/reapply\n      name: virtualmachines-reapply\n      operations:\n      - method: POST\n        name: virtualmachines-reapply\n        description: Azure Virtual Machines Reapply a virtual machine state\n        call: microsoft-azure-virtual-machines.virtualmachines-reapply\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/retrieveBootDiagnosticsData\n      name: virtualmachines-retrievebootdiagnosticsdata\n      operations:\n      - method: POST\n        name: virtualmachines-retrievebootdiagnosticsdata\n\
  \        description: Azure Virtual Machines Retrieve boot diagnostics data\n        call: microsoft-azure-virtual-machines.virtualmachines-retrievebootdiagnosticsdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/assessPatches\n      name: virtualmachines-assesspatches\n      operations:\n      - method: POST\n        name: virtualmachines-assesspatches\n        description: Azure Virtual Machines Assess patches on a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-assesspatches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/installPatches\n      name: virtualmachines-installpatches\n      operations:\n      - method: POST\n        name: virtualmachines-installpatches\n\
  \        description: Azure Virtual Machines Install patches on a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-installpatches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/attachDetachDataDisks\n      name: virtualmachines-attachdetachdatadisks\n      operations:\n      - method: POST\n        name: virtualmachines-attachdetachdatadisks\n        description: Azure Virtual Machines Attach or detach data disks\n        call: microsoft-azure-virtual-machines.virtualmachines-attachdetachdatadisks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/vmSizes\n      name: virtualmachines-listavailablesizes\n      operations:\n      - method: GET\n \
  \       name: virtualmachines-listavailablesizes\n        description: Azure Virtual Machines List available sizes for a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-listavailablesizes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/virtualMachines/{vmName}/runCommand\n      name: virtualmachines-runcommand\n      operations:\n      - method: POST\n        name: virtualmachines-runcommand\n        description: Azure Virtual Machines Run command on a virtual machine\n        call: microsoft-azure-virtual-machines.virtualmachines-runcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-virtual-machines-mcp\n    transport: http\n    description: MCP adapter for Azure Virtual Machines REST API for AI agent use.\n    tools:\n    - name:\
  \ virtualmachines-list\n      description: Azure Virtual Machines List virtual machines in a resource group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-list\n      with:\n        $filter: tools.$filter\n        $expand: tools.$expand\n      inputParameters:\n      - name: $filter\n        type: string\n        description: The system query option to filter VMs returned in the response. Allowed value is 'virtualMachineScaleSet/id'\n          eq /subscriptions/{subId}/resourceGroups/{rgName}/p\n      - name: $expand\n        type: string\n        description: The expand expression to apply on the operation. 'instanceView' retrieves a snapshot of the runtime properties\n          of the virtual machine that is managed by the pla\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-listall\n      description: Azure Virtual Machines List all\
  \ virtual machines in a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-listall\n      with:\n        statusOnly: tools.statusOnly\n        $filter: tools.$filter\n        $expand: tools.$expand\n      inputParameters:\n      - name: statusOnly\n        type: string\n        description: statusOnly=true enables fetching run time status of all Virtual Machines in the subscription.\n      - name: $filter\n        type: string\n        description: The system query option to filter VMs returned in the response.\n      - name: $expand\n        type: string\n        description: The expand expression to apply on the operation.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-listbylocation\n      description: Azure Virtual Machines List virtual machines by location\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-listbylocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-createorupdate\n      description: Azure Virtual Machines Create or update a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-createorupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-get\n      description: Azure Virtual Machines Get a virtual machine\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-get\n      with:\n        $expand: tools.$expand\n      inputParameters:\n      - name: $expand\n        type: string\n        description: The expand expression to apply on the operation. 'instanceView' retrieves a snapshot\
  \ of the runtime properties\n          of the virtual machine.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-update\n      description: Azure Virtual Machines Update a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-virtual-machines.virtualmachines-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-delete\n      description: Azure Virtual Machines Delete a virtual machine\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-delete\n      with:\n        forceDeletion: tools.forceDeletion\n      inputParameters:\n      - name: forceDeletion\n        type: boolean\n        description: Optional parameter to force delete virtual machines.\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: virtualmachines-instanceview\n      description: Azure Virtual Machines Get the instance view of a virtual machine\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-virtual-machines.virtualmachines-instanceview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-start\n      description: Azure Virtual Machines Start a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-virtual-machines.virtualmachines-start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: virtualmachines-poweroff\n      description: Azure Virtual Machines Power off a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-virtual-machines.virtualmachines-poweroff\n      with:\n        skipShutdown:\
  \ tools.skipShutdown\n      inputParameters:\n      - name: skipShutdown\n        type: b\n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-virtual-machines/refs/heads/main/capabilities/microsoft-azure-virtual-machines-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-virtual-machines/refs/heads/main/capabilities/microsoft-azure-virtual-machines-capability.yaml
tags:
- Microsoft
- Azure
- Virtual
- Machines
- API
tools:
- description: Azure Virtual Machines List virtual machines in a resource group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-list
- description: Azure Virtual Machines List all virtual machines in a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-listall
- description: Azure Virtual Machines List virtual machines by location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-listbylocation
- description: Azure Virtual Machines Create or update a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: virtualmachines-createorupdate
- description: Azure Virtual Machines Get a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-get
- description: Azure Virtual Machines Update a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-update
- description: Azure Virtual Machines Delete a virtual machine
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: virtualmachines-delete
- description: Azure Virtual Machines Get the instance view of a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-instanceview
- description: Azure Virtual Machines Start a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-start
- description: Azure Virtual Machines Power off a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-poweroff
- description: Azure Virtual Machines Deallocate a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-deallocate
- description: Azure Virtual Machines Restart a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-restart
- description: Azure Virtual Machines Redeploy a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-redeploy
- description: Azure Virtual Machines Reimage a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-reimage
- description: Azure Virtual Machines Capture a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-capture
- description: Azure Virtual Machines Generalize a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-generalize
- description: Azure Virtual Machines Convert to managed disks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-converttomanageddisks
- description: Azure Virtual Machines Perform maintenance on a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-performmaintenance
- description: Azure Virtual Machines Simulate eviction of a spot virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-simulateeviction
- description: Azure Virtual Machines Reapply a virtual machine state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-reapply
- description: Azure Virtual Machines Retrieve boot diagnostics data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-retrievebootdiagnosticsdata
- description: Azure Virtual Machines Assess patches on a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-assesspatches
- description: Azure Virtual Machines Install patches on a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-installpatches
- description: Azure Virtual Machines Attach or detach data disks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-attachdetachdatadisks
- description: Azure Virtual Machines List available sizes for a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: virtualmachines-listavailablesizes
- description: Azure Virtual Machines Run command on a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: virtualmachines-runcommand
---
