---
categories: []
consumed_apis: []
description: RESTful public-facing API. The API is accessible through HTTP calls on specific URLs carrying JSON modeled data. The transport medium is a Unix Domain Socket.
layout: capability
name: Firecracker API
operations:
- description: Returns general information about an instance.
  method: GET
  name: describeinstance
  path: /
- description: Creates a synchronous action.
  method: PUT
  name: createsyncaction
  path: /actions
- description: Returns the current balloon device configuration.
  method: GET
  name: describeballoonconfig
  path: /balloon
- description: Creates or updates a balloon device.
  method: PUT
  name: putballoon
  path: /balloon
- description: Updates a balloon device.
  method: PATCH
  name: patchballoon
  path: /balloon
- description: Returns the latest balloon device statistics, only if enabled pre-boot.
  method: GET
  name: describeballoonstats
  path: /balloon/statistics
- description: Updates a balloon device statistics polling interval.
  method: PATCH
  name: patchballoonstatsinterval
  path: /balloon/statistics
- description: Starts a free page hinting run only if enabled pre-boot.
  method: PATCH
  name: startballoonhinting
  path: /balloon/hinting/start
- description: Returns the balloon hinting statistics, only if enabled pre-boot.
  method: GET
  name: describeballoonhinting
  path: /balloon/hinting/status
- description: Stops a free page hinting run only if enabled pre-boot.
  method: PATCH
  name: stopballoonhinting
  path: /balloon/hinting/stop
- description: Creates or updates the boot source. Pre-boot only.
  method: PUT
  name: putguestbootsource
  path: /boot-source
- description: Configures CPU features flags for the vCPUs of the guest VM. Pre-boot only.
  method: PUT
  name: putcpuconfiguration
  path: /cpu-config
- description: Creates or updates a drive. Pre-boot only.
  method: PUT
  name: putguestdrivebyid
  path: /drives/{drive_id}
- description: Updates the properties of a drive. Post-boot only.
  method: PATCH
  name: patchguestdrivebyid
  path: /drives/{drive_id}
- description: Creates or updates a pmem device. Pre-boot only.
  method: PUT
  name: putguestpmembyid
  path: /pmem/{id}
- description: Updates the rate limiter of a pmem device. Post-boot only.
  method: PATCH
  name: patchguestpmembyid
  path: /pmem/{id}
- description: Initializes the logger by specifying a named pipe or a file for the logs output.
  method: PUT
  name: putlogger
  path: /logger
- description: Gets the machine configuration of the VM.
  method: GET
  name: getmachineconfiguration
  path: /machine-config
- description: Updates the Machine Configuration of the VM. Pre-boot only.
  method: PUT
  name: putmachineconfiguration
  path: /machine-config
- description: Partially updates the Machine Configuration of the VM. Pre-boot only.
  method: PATCH
  name: patchmachineconfiguration
  path: /machine-config
- description: Initializes the metrics system by specifying a named pipe or a file for the metrics output.
  method: PUT
  name: putmetrics
  path: /metrics
- description: Creates a MMDS (Microvm Metadata Service) data store.
  method: PUT
  name: putmmds
  path: /mmds
- description: Updates the MMDS data store.
  method: PATCH
  name: patchmmds
  path: /mmds
- description: Get the MMDS data store.
  method: GET
  name: getmmds
  path: /mmds
- description: Set MMDS configuration. Pre-boot only.
  method: PUT
  name: putmmdsconfig
  path: /mmds/config
- description: Creates an entropy device. Pre-boot only.
  method: PUT
  name: putentropydevice
  path: /entropy
- description: Configures the serial console
  method: PUT
  name: putserialdevice
  path: /serial
- description: Configures the hotpluggable memory
  method: PUT
  name: putmemoryhotplug
  path: /hotplug/memory
- description: Updates the size of the hotpluggable memory region
  method: PATCH
  name: patchmemoryhotplug
  path: /hotplug/memory
- description: Retrieves the status of the hotpluggable memory
  method: GET
  name: getmemoryhotplug
  path: /hotplug/memory
- description: Creates a network interface. Pre-boot only.
  method: PUT
  name: putguestnetworkinterfacebyid
  path: /network-interfaces/{iface_id}
- description: Updates the rate limiters applied to a network interface. Post-boot only.
  method: PATCH
  name: patchguestnetworkinterfacebyid
  path: /network-interfaces/{iface_id}
- description: Creates a full or diff snapshot. Post-boot only.
  method: PUT
  name: createsnapshot
  path: /snapshot/create
- description: Loads a snapshot. Pre-boot only.
  method: PUT
  name: loadsnapshot
  path: /snapshot/load
- description: Gets the Firecracker version.
  method: GET
  name: getfirecrackerversion
  path: /version
- description: Updates the microVM state.
  method: PATCH
  name: patchvm
  path: /vm
- description: Gets the full VM configuration.
  method: GET
  name: getexportvmconfig
  path: /vm/config
- description: Creates/updates a vsock device. Pre-boot only.
  method: PUT
  name: putguestvsock
  path: /vsock
personas: []
provider_name: Firecracker
provider_slug: firecracker
search_terms:
- putserialdevice
- patchballoonstatsinterval
- putmachineconfiguration
- updates the microvm state.
- stopballoonhinting
- updates the properties of a drive. post-boot only.
- initializes the metrics system by specifying a named pipe or a file for the metrics output.
- gets the firecracker version.
- putlogger
- api
- stops a free page hinting run only if enabled pre-boot.
- kvm
- creates or updates a balloon device.
- putguestbootsource
- putmmds
- patchvm
- creates a mmds (microvm metadata service) data store.
- patchmemoryhotplug
- creates or updates a drive. pre-boot only.
- getmachineconfiguration
- patchmmds
- describeballoonconfig
- microvms
- updates the mmds data store.
- virtualization
- serverless
- returns the current balloon device configuration.
- updates a balloon device.
- putguestpmembyid
- putcpuconfiguration
- putmemoryhotplug
- open source
- returns the latest balloon device statistics, only if enabled pre-boot.
- startballoonhinting
- gets the machine configuration of the vm.
- creates/updates a vsock device. pre-boot only.
- updates the rate limiters applied to a network interface. post-boot only.
- gets the full vm configuration.
- updates a balloon device statistics polling interval.
- putentropydevice
- initializes the logger by specifying a named pipe or a file for the logs output.
- updates the rate limiter of a pmem device. post-boot only.
- creates or updates the boot source. pre-boot only.
- get the mmds data store.
- patchmachineconfiguration
- createsnapshot
- putguestvsock
- putmetrics
- configures the hotpluggable memory
- starts a free page hinting run only if enabled pre-boot.
- creates or updates a pmem device. pre-boot only.
- putguestdrivebyid
- set mmds configuration. pre-boot only.
- createsyncaction
- loadsnapshot
- patchballoon
- retrieves the status of the hotpluggable memory
- patchguestdrivebyid
- returns the balloon hinting statistics, only if enabled pre-boot.
- creates a synchronous action.
- patchguestpmembyid
- patchguestnetworkinterfacebyid
- getexportvmconfig
- loads a snapshot. pre-boot only.
- getfirecrackerversion
- returns general information about an instance.
- configures cpu features flags for the vcpus of the guest vm. pre-boot only.
- updates the machine configuration of the vm. pre-boot only.
- putmmdsconfig
- putguestnetworkinterfacebyid
- configures the serial console
- containers
- firecracker
- describeballoonhinting
- partially updates the machine configuration of the vm. pre-boot only.
- describeinstance
- getmemoryhotplug
- describeballoonstats
- creates an entropy device. pre-boot only.
- creates a network interface. pre-boot only.
- putballoon
- updates the size of the hotpluggable memory region
- creates a full or diff snapshot. post-boot only.
- getmmds
slug: firecracker-capability
source_filename: firecracker-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Firecracker API\n  description: RESTful public-facing API. The API is accessible through HTTP calls on specific URLs carrying JSON modeled\n    data. The transport medium is a Unix Domain Socket.\n  tags:\n  - Firecracker\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: firecracker\n    baseUri: https://api.example.com\n    description: Firecracker API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: describeinstance\n        method: GET\n        description: Returns general information about an instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions\n      path: /actions\n      operations:\n      - name: createsyncaction\n        method: PUT\n        description: Creates a synchronous action.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balloon\n      path: /balloon\n      operations:\n      - name: describeballoonconfig\n        method: GET\n        description: Returns the current balloon device configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putballoon\n        method: PUT\n        description: Creates or updates a balloon device.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchballoon\n        method: PATCH\n        description: Updates a balloon device.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balloon-statistics\n      path: /balloon/statistics\n      operations:\n      - name: describeballoonstats\n    \
  \    method: GET\n        description: Returns the latest balloon device statistics, only if enabled pre-boot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchballoonstatsinterval\n        method: PATCH\n        description: Updates a balloon device statistics polling interval.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balloon-hinting-start\n      path: /balloon/hinting/start\n      operations:\n      - name: startballoonhinting\n        method: PATCH\n        description: Starts a free page hinting run only if enabled pre-boot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balloon-hinting-status\n      path: /balloon/hinting/status\n      operations:\n      - name: describeballoonhinting\n        method:\
  \ GET\n        description: Returns the balloon hinting statistics, only if enabled pre-boot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balloon-hinting-stop\n      path: /balloon/hinting/stop\n      operations:\n      - name: stopballoonhinting\n        method: PATCH\n        description: Stops a free page hinting run only if enabled pre-boot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: boot-source\n      path: /boot-source\n      operations:\n      - name: putguestbootsource\n        method: PUT\n        description: Creates or updates the boot source. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cpu-config\n      path: /cpu-config\n      operations:\n      - name: putcpuconfiguration\n\
  \        method: PUT\n        description: Configures CPU features flags for the vCPUs of the guest VM. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drives-drive-id\n      path: /drives/{drive_id}\n      operations:\n      - name: putguestdrivebyid\n        method: PUT\n        description: Creates or updates a drive. Pre-boot only.\n        inputParameters:\n        - name: drive_id\n          in: path\n          type: string\n          required: true\n          description: The id of the guest drive\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchguestdrivebyid\n        method: PATCH\n        description: Updates the properties of a drive. Post-boot only.\n        inputParameters:\n        - name: drive_id\n          in: path\n          type: string\n          required: true\n \
  \         description: The id of the guest drive\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pmem-id\n      path: /pmem/{id}\n      operations:\n      - name: putguestpmembyid\n        method: PUT\n        description: Creates or updates a pmem device. Pre-boot only.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the guest pmem device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchguestpmembyid\n        method: PATCH\n        description: Updates the rate limiter of a pmem device. Post-boot only.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the guest pmem device\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logger\n      path: /logger\n      operations:\n      - name: putlogger\n        method: PUT\n        description: Initializes the logger by specifying a named pipe or a file for the logs output.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machine-config\n      path: /machine-config\n      operations:\n      - name: getmachineconfiguration\n        method: GET\n        description: Gets the machine configuration of the VM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmachineconfiguration\n        method: PUT\n        description: Updates the Machine Configuration of the VM. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: patchmachineconfiguration\n        method: PATCH\n        description: Partially updates the Machine Configuration of the VM. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      operations:\n      - name: putmetrics\n        method: PUT\n        description: Initializes the metrics system by specifying a named pipe or a file for the metrics output.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mmds\n      path: /mmds\n      operations:\n      - name: putmmds\n        method: PUT\n        description: Creates a MMDS (Microvm Metadata Service) data store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchmmds\n       \
  \ method: PATCH\n        description: Updates the MMDS data store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmmds\n        method: GET\n        description: Get the MMDS data store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mmds-config\n      path: /mmds/config\n      operations:\n      - name: putmmdsconfig\n        method: PUT\n        description: Set MMDS configuration. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entropy\n      path: /entropy\n      operations:\n      - name: putentropydevice\n        method: PUT\n        description: Creates an entropy device. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: serial\n      path: /serial\n      operations:\n      - name: putserialdevice\n        method: PUT\n        description: Configures the serial console\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hotplug-memory\n      path: /hotplug/memory\n      operations:\n      - name: putmemoryhotplug\n        method: PUT\n        description: Configures the hotpluggable memory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchmemoryhotplug\n        method: PATCH\n        description: Updates the size of the hotpluggable memory region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmemoryhotplug\n        method: GET\n        description: Retrieves the status of the hotpluggable memory\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-interfaces-iface-id\n      path: /network-interfaces/{iface_id}\n      operations:\n      - name: putguestnetworkinterfacebyid\n        method: PUT\n        description: Creates a network interface. Pre-boot only.\n        inputParameters:\n        - name: iface_id\n          in: path\n          type: string\n          required: true\n          description: The id of the guest network interface\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchguestnetworkinterfacebyid\n        method: PATCH\n        description: Updates the rate limiters applied to a network interface. Post-boot only.\n        inputParameters:\n        - name: iface_id\n          in: path\n          type: string\n          required: true\n          description: The id of the guest\
  \ network interface\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snapshot-create\n      path: /snapshot/create\n      operations:\n      - name: createsnapshot\n        method: PUT\n        description: Creates a full or diff snapshot. Post-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snapshot-load\n      path: /snapshot/load\n      operations:\n      - name: loadsnapshot\n        method: PUT\n        description: Loads a snapshot. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: version\n      path: /version\n      operations:\n      - name: getfirecrackerversion\n        method: GET\n        description: Gets the Firecracker version.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: vm\n      path: /vm\n      operations:\n      - name: patchvm\n        method: PATCH\n        description: Updates the microVM state.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vm-config\n      path: /vm/config\n      operations:\n      - name: getexportvmconfig\n        method: GET\n        description: Gets the full VM configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vsock\n      path: /vsock\n      operations:\n      - name: putguestvsock\n        method: PUT\n        description: Creates/updates a vsock device. Pre-boot only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ firecracker-rest\n    description: REST adapter for Firecracker API.\n    resources:\n    - path: /\n      name: describeinstance\n      operations:\n      - method: GET\n        name: describeinstance\n        description: Returns general information about an instance.\n        call: firecracker.describeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /actions\n      name: createsyncaction\n      operations:\n      - method: PUT\n        name: createsyncaction\n        description: Creates a synchronous action.\n        call: firecracker.createsyncaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon\n      name: describeballoonconfig\n      operations:\n      - method: GET\n        name: describeballoonconfig\n        description: Returns the current balloon device configuration.\n        call: firecracker.describeballoonconfig\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /balloon\n      name: putballoon\n      operations:\n      - method: PUT\n        name: putballoon\n        description: Creates or updates a balloon device.\n        call: firecracker.putballoon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon\n      name: patchballoon\n      operations:\n      - method: PATCH\n        name: patchballoon\n        description: Updates a balloon device.\n        call: firecracker.patchballoon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon/statistics\n      name: describeballoonstats\n      operations:\n      - method: GET\n        name: describeballoonstats\n        description: Returns the latest balloon device statistics, only if enabled pre-boot.\n        call: firecracker.describeballoonstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon/statistics\n      name: patchballoonstatsinterval\n\
  \      operations:\n      - method: PATCH\n        name: patchballoonstatsinterval\n        description: Updates a balloon device statistics polling interval.\n        call: firecracker.patchballoonstatsinterval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon/hinting/start\n      name: startballoonhinting\n      operations:\n      - method: PATCH\n        name: startballoonhinting\n        description: Starts a free page hinting run only if enabled pre-boot.\n        call: firecracker.startballoonhinting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balloon/hinting/status\n      name: describeballoonhinting\n      operations:\n      - method: GET\n        name: describeballoonhinting\n        description: Returns the balloon hinting statistics, only if enabled pre-boot.\n        call: firecracker.describeballoonhinting\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /balloon/hinting/stop\n      name: stopballoonhinting\n      operations:\n      - method: PATCH\n        name: stopballoonhinting\n        description: Stops a free page hinting run only if enabled pre-boot.\n        call: firecracker.stopballoonhinting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /boot-source\n      name: putguestbootsource\n      operations:\n      - method: PUT\n        name: putguestbootsource\n        description: Creates or updates the boot source. Pre-boot only.\n        call: firecracker.putguestbootsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cpu-config\n      name: putcpuconfiguration\n      operations:\n      - method: PUT\n        name: putcpuconfiguration\n        description: Configures CPU features flags for the vCPUs of the guest VM. Pre-boot only.\n        call: firecracker.putcpuconfiguration\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /drives/{drive_id}\n      name: putguestdrivebyid\n      operations:\n      - method: PUT\n        name: putguestdrivebyid\n        description: Creates or updates a drive. Pre-boot only.\n        call: firecracker.putguestdrivebyid\n        with:\n          drive_id: rest.drive_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /drives/{drive_id}\n      name: patchguestdrivebyid\n      operations:\n      - method: PATCH\n        name: patchguestdrivebyid\n        description: Updates the properties of a drive. Post-boot only.\n        call: firecracker.patchguestdrivebyid\n        with:\n          drive_id: rest.drive_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pmem/{id}\n      name: putguestpmembyid\n      operations:\n      - method: PUT\n        name: putguestpmembyid\n        description: Creates or updates a pmem device. Pre-boot only.\n        call: firecracker.putguestpmembyid\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pmem/{id}\n      name: patchguestpmembyid\n      operations:\n      - method: PATCH\n        name: patchguestpmembyid\n        description: Updates the rate limiter of a pmem device. Post-boot only.\n        call: firecracker.patchguestpmembyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /logger\n      name: putlogger\n      operations:\n      - method: PUT\n        name: putlogger\n        description: Initializes the logger by specifying a named pipe or a file for the logs output.\n        call: firecracker.putlogger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machine-config\n      name: getmachineconfiguration\n      operations:\n      - method: GET\n        name: getmachineconfiguration\n        description: Gets the machine configuration\
  \ of the VM.\n        call: firecracker.getmachineconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machine-config\n      name: putmachineconfiguration\n      operations:\n      - method: PUT\n        name: putmachineconfiguration\n        description: Updates the Machine Configuration of the VM. Pre-boot only.\n        call: firecracker.putmachineconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machine-config\n      name: patchmachineconfiguration\n      operations:\n      - method: PATCH\n        name: patchmachineconfiguration\n        description: Partially updates the Machine Configuration of the VM. Pre-boot only.\n        call: firecracker.patchmachineconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics\n      name: putmetrics\n      operations:\n      - method: PUT\n        name: putmetrics\n        description: Initializes\
  \ the metrics system by specifying a named pipe or a file for the metrics output.\n        call: firecracker.putmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mmds\n      name: putmmds\n      operations:\n      - method: PUT\n        name: putmmds\n        description: Creates a MMDS (Microvm Metadata Service) data store.\n        call: firecracker.putmmds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mmds\n      name: patchmmds\n      operations:\n      - method: PATCH\n        name: patchmmds\n        description: Updates the MMDS data store.\n        call: firecracker.patchmmds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mmds\n      name: getmmds\n      operations:\n      - method: GET\n        name: getmmds\n        description: Get the MMDS data store.\n        call: firecracker.getmmds\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /mmds/config\n      name: putmmdsconfig\n      operations:\n      - method: PUT\n        name: putmmdsconfig\n        description: Set MMDS configuration. Pre-boot only.\n        call: firecracker.putmmdsconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entropy\n      name: putentropydevice\n      operations:\n      - method: PUT\n        name: putentropydevice\n        description: Creates an entropy device. Pre-boot only.\n        call: firecracker.putentropydevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /serial\n      name: putserialdevice\n      operations:\n      - method: PUT\n        name: putserialdevice\n        description: Configures the serial console\n        call: firecracker.putserialdevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hotplug/memory\n      name: putmemoryhotplug\n      operations:\n      - method:\
  \ PUT\n        name: putmemoryhotplug\n        description: Configures the hotpluggable memory\n        call: firecracker.putmemoryhotplug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hotplug/memory\n      name: patchmemoryhotplug\n      operations:\n      - method: PATCH\n        name: patchmemoryhotplug\n        description: Updates the size of the hotpluggable memory region\n        call: firecracker.patchmemoryhotplug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hotplug/memory\n      name: getmemoryhotplug\n      operations:\n      - method: GET\n        name: getmemoryhotplug\n        description: Retrieves the status of the hotpluggable memory\n        call: firecracker.getmemoryhotplug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network-interfaces/{iface_id}\n      name: putguestnetworkinterfacebyid\n      operations:\n      - method: PUT\n        name:\
  \ putguestnetworkinterfacebyid\n        description: Creates a network interface. Pre-boot only.\n        call: firecracker.putguestnetworkinterfacebyid\n        with:\n          iface_id: rest.iface_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network-interfaces/{iface_id}\n      name: patchguestnetworkinterfacebyid\n      operations:\n      - method: PATCH\n        name: patchguestnetworkinterfacebyid\n        description: Updates the rate limiters applied to a network interface. Post-boot only.\n        call: firecracker.patchguestnetworkinterfacebyid\n        with:\n          iface_id: rest.iface_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /snapshot/create\n      name: createsnapshot\n      operations:\n      - method: PUT\n        name: createsnapshot\n        description: Creates a full or diff snapshot. Post-boot only.\n        call: firecracker.createsnapshot\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /snapshot/load\n      name: loadsnapshot\n      operations:\n      - method: PUT\n        name: loadsnapshot\n        description: Loads a snapshot. Pre-boot only.\n        call: firecracker.loadsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /version\n      name: getfirecrackerversion\n      operations:\n      - method: GET\n        name: getfirecrackerversion\n        description: Gets the Firecracker version.\n        call: firecracker.getfirecrackerversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vm\n      name: patchvm\n      operations:\n      - method: PATCH\n        name: patchvm\n        description: Updates the microVM state.\n        call: firecracker.patchvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vm/config\n      name: getexportvmconfig\n      operations:\n      - method: GET\n\
  \        name: getexportvmconfig\n        description: Gets the full VM configuration.\n        call: firecracker.getexportvmconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vsock\n      name: putguestvsock\n      operations:\n      - method: PUT\n        name: putguestvsock\n        description: Creates/updates a vsock device. Pre-boot only.\n        call: firecracker.putguestvsock\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: firecracker-mcp\n    transport: http\n    description: MCP adapter for Firecracker API for AI agent use.\n    tools:\n    - name: describeinstance\n      description: Returns general information about an instance.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.describeinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsyncaction\n\
  \      description: Creates a synchronous action.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.createsyncaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeballoonconfig\n      description: Returns the current balloon device configuration.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.describeballoonconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putballoon\n      description: Creates or updates a balloon device.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putballoon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchballoon\n      description: Updates a balloon device.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: firecracker.patchballoon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeballoonstats\n      description: Returns the latest balloon device statistics, only if enabled pre-boot.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.describeballoonstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchballoonstatsinterval\n      description: Updates a balloon device statistics polling interval.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firecracker.patchballoonstatsinterval\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startballoonhinting\n      description: Starts a free page hinting run only if enabled pre-boot.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firecracker.startballoonhinting\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeballoonhinting\n      description: Returns the balloon hinting statistics, only if enabled pre-boot.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.describeballoonhinting\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopballoonhinting\n      description: Stops a free page hinting run only if enabled pre-boot.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firecracker.stopballoonhinting\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putguestbootsource\n      description: Creates or updates the boot source. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putguestbootsource\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: putcpuconfiguration\n      description: Configures CPU features flags for the vCPUs of the guest VM. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putcpuconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putguestdrivebyid\n      description: Creates or updates a drive. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putguestdrivebyid\n      with:\n        drive_id: tools.drive_id\n      inputParameters:\n      - name: drive_id\n        type: string\n        description: The id of the guest drive\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchguestdrivebyid\n      description: Updates the properties of a drive. Post-boot only.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: firecracker.patchguestdrivebyid\n      with:\n        drive_id: tools.drive_id\n      inputParameters:\n      - name: drive_id\n        type: string\n        description: The id of the guest drive\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putguestpmembyid\n      description: Creates or updates a pmem device. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putguestpmembyid\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: The id of the guest pmem device\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchguestpmembyid\n      description: Updates the rate limiter of a pmem device. Post-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n    \
  \    idempotent: false\n      call: firecracker.patchguestpmembyid\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: The id of the guest pmem device\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putlogger\n      description: Initializes the logger by specifying a named pipe or a file for the logs output.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putlogger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmachineconfiguration\n      description: Gets the machine configuration of the VM.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.getmachineconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmachineconfiguration\n      description: Updates\
  \ the Machine Configuration of the VM. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putmachineconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchmachineconfiguration\n      description: Partially updates the Machine Configuration of the VM. Pre-boot only.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firecracker.patchmachineconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmetrics\n      description: Initializes the metrics system by specifying a named pipe or a file for the metrics output.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmmds\n      description: Creates a MMDS (Microvm\
  \ Metadata Service) data store.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: firecracker.putmmds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchmmds\n      description: Updates the MMDS data store.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firecracker.patchmmds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmmds\n      description: Get the MMDS data store.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firecracker.getmmds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmmdsconfig\n      description: Se\n\n# --- truncated at 32 KB (36 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/firecracker/refs/heads/main/capabilities/firecracker-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/firecracker/refs/heads/main/capabilities/firecracker-capability.yaml
tags:
- Firecracker
- API
tools:
- description: Returns general information about an instance.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeinstance
- description: Creates a synchronous action.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsyncaction
- description: Returns the current balloon device configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeballoonconfig
- description: Creates or updates a balloon device.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putballoon
- description: Updates a balloon device.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchballoon
- description: Returns the latest balloon device statistics, only if enabled pre-boot.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeballoonstats
- description: Updates a balloon device statistics polling interval.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchballoonstatsinterval
- description: Starts a free page hinting run only if enabled pre-boot.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startballoonhinting
- description: Returns the balloon hinting statistics, only if enabled pre-boot.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeballoonhinting
- description: Stops a free page hinting run only if enabled pre-boot.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopballoonhinting
- description: Creates or updates the boot source. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putguestbootsource
- description: Configures CPU features flags for the vCPUs of the guest VM. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcpuconfiguration
- description: Creates or updates a drive. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putguestdrivebyid
- description: Updates the properties of a drive. Post-boot only.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchguestdrivebyid
- description: Creates or updates a pmem device. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putguestpmembyid
- description: Updates the rate limiter of a pmem device. Post-boot only.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchguestpmembyid
- description: Initializes the logger by specifying a named pipe or a file for the logs output.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putlogger
- description: Gets the machine configuration of the VM.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmachineconfiguration
- description: Updates the Machine Configuration of the VM. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmachineconfiguration
- description: Partially updates the Machine Configuration of the VM. Pre-boot only.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchmachineconfiguration
- description: Initializes the metrics system by specifying a named pipe or a file for the metrics output.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmetrics
- description: Creates a MMDS (Microvm Metadata Service) data store.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmmds
- description: Updates the MMDS data store.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchmmds
- description: Get the MMDS data store.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmmds
- description: Set MMDS configuration. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmmdsconfig
- description: Creates an entropy device. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putentropydevice
- description: Configures the serial console
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putserialdevice
- description: Configures the hotpluggable memory
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmemoryhotplug
- description: Updates the size of the hotpluggable memory region
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchmemoryhotplug
- description: Retrieves the status of the hotpluggable memory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmemoryhotplug
- description: Creates a network interface. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putguestnetworkinterfacebyid
- description: Updates the rate limiters applied to a network interface. Post-boot only.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchguestnetworkinterfacebyid
- description: Creates a full or diff snapshot. Post-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsnapshot
- description: Loads a snapshot. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: loadsnapshot
- description: Gets the Firecracker version.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfirecrackerversion
- description: Updates the microVM state.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchvm
- description: Gets the full VM configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexportvmconfig
- description: Creates/updates a vsock device. Pre-boot only.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putguestvsock
---
