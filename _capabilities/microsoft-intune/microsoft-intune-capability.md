---
categories: []
consumed_apis: []
description: The Microsoft Graph API for Intune enables programmatic access to Intune information and actions for your tenant. The API performs the same Intune operations as those available through the Microsoft Intune admin center, including managed device management, device configuration, and compliance policy enforcement. Requires an active Intune license for the tenant.
layout: capability
name: Microsoft Intune Graph API
operations:
- description: Microsoft Intune List managed devices
  method: GET
  name: listmanageddevices
  path: /deviceManagement/managedDevices
- description: Microsoft Intune Create managed device
  method: POST
  name: createmanageddevice
  path: /deviceManagement/managedDevices
- description: Microsoft Intune Get managed device
  method: GET
  name: getmanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}
- description: Microsoft Intune Update managed device
  method: PATCH
  name: updatemanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}
- description: Microsoft Intune Delete managed device
  method: DELETE
  name: deletemanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}
- description: Microsoft Intune Retire a device
  method: POST
  name: retiremanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/retire
- description: Microsoft Intune Wipe a device
  method: POST
  name: wipemanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/wipe
- description: Microsoft Intune Sync a device
  method: POST
  name: syncmanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/syncDevice
- description: Microsoft Intune Remote lock a device
  method: POST
  name: remotelockmanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/remoteLock
- description: Microsoft Intune Reset device passcode
  method: POST
  name: resetpasscodemanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/resetPasscode
- description: Microsoft Intune Reboot a device
  method: POST
  name: rebootmanageddevice
  path: /deviceManagement/managedDevices/{managedDeviceId}/rebootNow
- description: Microsoft Intune List device configurations
  method: GET
  name: listdeviceconfigurations
  path: /deviceManagement/deviceConfigurations
- description: Microsoft Intune Get device configuration
  method: GET
  name: getdeviceconfiguration
  path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}
- description: Microsoft Intune Update device configuration
  method: PATCH
  name: updatedeviceconfiguration
  path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}
- description: Microsoft Intune Delete device configuration
  method: DELETE
  name: deletedeviceconfiguration
  path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}
- description: Microsoft Intune Assign device configuration
  method: POST
  name: assigndeviceconfiguration
  path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}/assign
- description: Microsoft Intune List device compliance policies
  method: GET
  name: listdevicecompliancepolicies
  path: /deviceManagement/deviceCompliancePolicies
- description: Microsoft Intune Get device compliance policy
  method: GET
  name: getdevicecompliancepolicy
  path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}
- description: Microsoft Intune Update device compliance policy
  method: PATCH
  name: updatedevicecompliancepolicy
  path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}
- description: Microsoft Intune Delete device compliance policy
  method: DELETE
  name: deletedevicecompliancepolicy
  path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}
- description: Microsoft Intune Assign device compliance policy
  method: POST
  name: assigndevicecompliancepolicy
  path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/assign
- description: Microsoft Intune Schedule actions for compliance rules
  method: POST
  name: scheduleactionsforrules
  path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/scheduleActionsForRules
personas: []
provider_name: Microsoft Intune
provider_slug: microsoft-intune
search_terms:
- listmanageddevices
- microsoft intune update device configuration
- listdevicecompliancepolicies
- microsoft intune update device compliance policy
- microsoft intune list managed devices
- microsoft intune delete managed device
- microsoft intune delete device configuration
- microsoft intune assign device compliance policy
- getdeviceconfiguration
- api
- assigndeviceconfiguration
- endpoint management
- mobile device management
- deletemanageddevice
- microsoft intune update managed device
- rebootmanageddevice
- microsoft intune reboot a device
- app protection
- getmanageddevice
- microsoft intune wipe a device
- microsoft intune assign device configuration
- updatedeviceconfiguration
- microsoft intune delete device compliance policy
- scheduleactionsforrules
- compliance
- mdm
- mobile application management
- microsoft intune schedule actions for compliance rules
- createmanageddevice
- getdevicecompliancepolicy
- microsoft
- updatemanageddevice
- microsoft intune list device compliance policies
- microsoft intune reset device passcode
- microsoft intune get device configuration
- syncmanageddevice
- deletedevicecompliancepolicy
- device configuration
- wipemanageddevice
- listdeviceconfigurations
- microsoft intune get managed device
- assigndevicecompliancepolicy
- resetpasscodemanageddevice
- remotelockmanageddevice
- microsoft intune remote lock a device
- enrollment
- microsoft graph
- microsoft intune get device compliance policy
- deletedeviceconfiguration
- intune
- microsoft intune sync a device
- mam
- azure
- microsoft intune create managed device
- retiremanageddevice
- updatedevicecompliancepolicy
- security
- microsoft intune list device configurations
- microsoft intune retire a device
slug: microsoft-intune-capability
source_filename: microsoft-intune-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Intune Graph API\n  description: The Microsoft Graph API for Intune enables programmatic access to Intune information and actions for your tenant.\n    The API performs the same Intune operations as those available through the Microsoft Intune admin center, including managed\n    device management, device configuration, and compliance policy enforcement. Requires an active Intune license for the\n    tenant.\n  tags:\n  - Microsoft\n  - Intune\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-intune\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Intune Graph API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_INTUNE_TOKEN}}'\n    resources:\n    - name: devicemanagement-manageddevices\n      path: /deviceManagement/managedDevices\n      operations:\n      - name: listmanageddevices\n        method:\
  \ GET\n        description: Microsoft Intune List managed devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmanageddevice\n        method: POST\n        description: Microsoft Intune Create managed device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid\n      path: /deviceManagement/managedDevices/{managedDeviceId}\n      operations:\n      - name: getmanageddevice\n        method: GET\n        description: Microsoft Intune Get managed device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemanageddevice\n        method: PATCH\n        description: Microsoft Intune Update managed device\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: deletemanageddevice\n        method: DELETE\n        description: Microsoft Intune Delete managed device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/retire\n      operations:\n      - name: retiremanageddevice\n        method: POST\n        description: Microsoft Intune Retire a device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/wipe\n      operations:\n      - name: wipemanageddevice\n        method: POST\n        description: Microsoft Intune Wipe a device\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/syncDevice\n      operations:\n      - name: syncmanageddevice\n        method: POST\n        description: Microsoft Intune Sync a device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/remoteLock\n      operations:\n      - name: remotelockmanageddevice\n        method: POST\n        description: Microsoft Intune Remote lock a device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/resetPasscode\n\
  \      operations:\n      - name: resetpasscodemanageddevice\n        method: POST\n        description: Microsoft Intune Reset device passcode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-manageddevices-manageddeviceid-\n      path: /deviceManagement/managedDevices/{managedDeviceId}/rebootNow\n      operations:\n      - name: rebootmanageddevice\n        method: POST\n        description: Microsoft Intune Reboot a device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-deviceconfigurations\n      path: /deviceManagement/deviceConfigurations\n      operations:\n      - name: listdeviceconfigurations\n        method: GET\n        description: Microsoft Intune List device configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: devicemanagement-deviceconfigurations-deviceconf\n      path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}\n      operations:\n      - name: getdeviceconfiguration\n        method: GET\n        description: Microsoft Intune Get device configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedeviceconfiguration\n        method: PATCH\n        description: Microsoft Intune Update device configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeviceconfiguration\n        method: DELETE\n        description: Microsoft Intune Delete device configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-deviceconfigurations-deviceconf\n\
  \      path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}/assign\n      operations:\n      - name: assigndeviceconfiguration\n        method: POST\n        description: Microsoft Intune Assign device configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-devicecompliancepolicies\n      path: /deviceManagement/deviceCompliancePolicies\n      operations:\n      - name: listdevicecompliancepolicies\n        method: GET\n        description: Microsoft Intune List device compliance policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-devicecompliancepolicies-device\n      path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}\n      operations:\n      - name: getdevicecompliancepolicy\n        method: GET\n        description:\
  \ Microsoft Intune Get device compliance policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedevicecompliancepolicy\n        method: PATCH\n        description: Microsoft Intune Update device compliance policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedevicecompliancepolicy\n        method: DELETE\n        description: Microsoft Intune Delete device compliance policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-devicecompliancepolicies-device\n      path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/assign\n      operations:\n      - name: assigndevicecompliancepolicy\n        method: POST\n        description: Microsoft Intune Assign device compliance\
  \ policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devicemanagement-devicecompliancepolicies-device\n      path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/scheduleActionsForRules\n      operations:\n      - name: scheduleactionsforrules\n        method: POST\n        description: Microsoft Intune Schedule actions for compliance rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-intune-rest\n    description: REST adapter for Microsoft Intune Graph API.\n    resources:\n    - path: /deviceManagement/managedDevices\n      name: listmanageddevices\n      operations:\n      - method: GET\n        name: listmanageddevices\n        description: Microsoft Intune List managed devices\n        call: microsoft-intune.listmanageddevices\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices\n      name: createmanageddevice\n      operations:\n      - method: POST\n        name: createmanageddevice\n        description: Microsoft Intune Create managed device\n        call: microsoft-intune.createmanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}\n      name: getmanageddevice\n      operations:\n      - method: GET\n        name: getmanageddevice\n        description: Microsoft Intune Get managed device\n        call: microsoft-intune.getmanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}\n      name: updatemanageddevice\n      operations:\n      - method: PATCH\n        name: updatemanageddevice\n        description: Microsoft Intune Update managed device\n\
  \        call: microsoft-intune.updatemanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}\n      name: deletemanageddevice\n      operations:\n      - method: DELETE\n        name: deletemanageddevice\n        description: Microsoft Intune Delete managed device\n        call: microsoft-intune.deletemanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/retire\n      name: retiremanageddevice\n      operations:\n      - method: POST\n        name: retiremanageddevice\n        description: Microsoft Intune Retire a device\n        call: microsoft-intune.retiremanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/wipe\n      name: wipemanageddevice\n      operations:\n      - method: POST\n        name:\
  \ wipemanageddevice\n        description: Microsoft Intune Wipe a device\n        call: microsoft-intune.wipemanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/syncDevice\n      name: syncmanageddevice\n      operations:\n      - method: POST\n        name: syncmanageddevice\n        description: Microsoft Intune Sync a device\n        call: microsoft-intune.syncmanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/remoteLock\n      name: remotelockmanageddevice\n      operations:\n      - method: POST\n        name: remotelockmanageddevice\n        description: Microsoft Intune Remote lock a device\n        call: microsoft-intune.remotelockmanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/resetPasscode\n\
  \      name: resetpasscodemanageddevice\n      operations:\n      - method: POST\n        name: resetpasscodemanageddevice\n        description: Microsoft Intune Reset device passcode\n        call: microsoft-intune.resetpasscodemanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/managedDevices/{managedDeviceId}/rebootNow\n      name: rebootmanageddevice\n      operations:\n      - method: POST\n        name: rebootmanageddevice\n        description: Microsoft Intune Reboot a device\n        call: microsoft-intune.rebootmanageddevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceConfigurations\n      name: listdeviceconfigurations\n      operations:\n      - method: GET\n        name: listdeviceconfigurations\n        description: Microsoft Intune List device configurations\n        call: microsoft-intune.listdeviceconfigurations\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}\n      name: getdeviceconfiguration\n      operations:\n      - method: GET\n        name: getdeviceconfiguration\n        description: Microsoft Intune Get device configuration\n        call: microsoft-intune.getdeviceconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}\n      name: updatedeviceconfiguration\n      operations:\n      - method: PATCH\n        name: updatedeviceconfiguration\n        description: Microsoft Intune Update device configuration\n        call: microsoft-intune.updatedeviceconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}\n      name: deletedeviceconfiguration\n      operations:\n      - method: DELETE\n        name:\
  \ deletedeviceconfiguration\n        description: Microsoft Intune Delete device configuration\n        call: microsoft-intune.deletedeviceconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceConfigurations/{deviceConfigurationId}/assign\n      name: assigndeviceconfiguration\n      operations:\n      - method: POST\n        name: assigndeviceconfiguration\n        description: Microsoft Intune Assign device configuration\n        call: microsoft-intune.assigndeviceconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies\n      name: listdevicecompliancepolicies\n      operations:\n      - method: GET\n        name: listdevicecompliancepolicies\n        description: Microsoft Intune List device compliance policies\n        call: microsoft-intune.listdevicecompliancepolicies\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}\n      name: getdevicecompliancepolicy\n      operations:\n      - method: GET\n        name: getdevicecompliancepolicy\n        description: Microsoft Intune Get device compliance policy\n        call: microsoft-intune.getdevicecompliancepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}\n      name: updatedevicecompliancepolicy\n      operations:\n      - method: PATCH\n        name: updatedevicecompliancepolicy\n        description: Microsoft Intune Update device compliance policy\n        call: microsoft-intune.updatedevicecompliancepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}\n      name: deletedevicecompliancepolicy\n      operations:\n      - method:\
  \ DELETE\n        name: deletedevicecompliancepolicy\n        description: Microsoft Intune Delete device compliance policy\n        call: microsoft-intune.deletedevicecompliancepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/assign\n      name: assigndevicecompliancepolicy\n      operations:\n      - method: POST\n        name: assigndevicecompliancepolicy\n        description: Microsoft Intune Assign device compliance policy\n        call: microsoft-intune.assigndevicecompliancepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deviceManagement/deviceCompliancePolicies/{deviceCompliancePolicyId}/scheduleActionsForRules\n      name: scheduleactionsforrules\n      operations:\n      - method: POST\n        name: scheduleactionsforrules\n        description: Microsoft Intune Schedule actions for compliance rules\n        call: microsoft-intune.scheduleactionsforrules\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-intune-mcp\n    transport: http\n    description: MCP adapter for Microsoft Intune Graph API for AI agent use.\n    tools:\n    - name: listmanageddevices\n      description: Microsoft Intune List managed devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-intune.listmanageddevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmanageddevice\n      description: Microsoft Intune Create managed device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.createmanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanageddevice\n      description: Microsoft Intune Get managed device\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: microsoft-intune.getmanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemanageddevice\n      description: Microsoft Intune Update managed device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.updatemanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemanageddevice\n      description: Microsoft Intune Delete managed device\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-intune.deletemanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retiremanageddevice\n      description: Microsoft Intune Retire a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.retiremanageddevice\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: wipemanageddevice\n      description: Microsoft Intune Wipe a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.wipemanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: syncmanageddevice\n      description: Microsoft Intune Sync a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.syncmanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remotelockmanageddevice\n      description: Microsoft Intune Remote lock a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.remotelockmanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resetpasscodemanageddevice\n      description: Microsoft\
  \ Intune Reset device passcode\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.resetpasscodemanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rebootmanageddevice\n      description: Microsoft Intune Reboot a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.rebootmanageddevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeviceconfigurations\n      description: Microsoft Intune List device configurations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-intune.listdeviceconfigurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeviceconfiguration\n      description: Microsoft Intune Get device configuration\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: microsoft-intune.getdeviceconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedeviceconfiguration\n      description: Microsoft Intune Update device configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.updatedeviceconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeviceconfiguration\n      description: Microsoft Intune Delete device configuration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-intune.deletedeviceconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assigndeviceconfiguration\n      description: Microsoft Intune Assign device configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: microsoft-intune.assigndeviceconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdevicecompliancepolicies\n      description: Microsoft Intune List device compliance policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-intune.listdevicecompliancepolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevicecompliancepolicy\n      description: Microsoft Intune Get device compliance policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-intune.getdevicecompliancepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedevicecompliancepolicy\n      description: Microsoft Intune Update device compliance policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ microsoft-intune.updatedevicecompliancepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedevicecompliancepolicy\n      description: Microsoft Intune Delete device compliance policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-intune.deletedevicecompliancepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assigndevicecompliancepolicy\n      description: Microsoft Intune Assign device compliance policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.assigndevicecompliancepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scheduleactionsforrules\n      description: Microsoft Intune Schedule actions for compliance rules\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-intune.scheduleactionsforrules\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_INTUNE_TOKEN: MICROSOFT_INTUNE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-intune/refs/heads/main/capabilities/microsoft-intune-capability.yaml
tags:
- Microsoft
- Intune
- API
tools:
- description: Microsoft Intune List managed devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmanageddevices
- description: Microsoft Intune Create managed device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmanageddevice
- description: Microsoft Intune Get managed device
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanageddevice
- description: Microsoft Intune Update managed device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemanageddevice
- description: Microsoft Intune Delete managed device
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemanageddevice
- description: Microsoft Intune Retire a device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retiremanageddevice
- description: Microsoft Intune Wipe a device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: wipemanageddevice
- description: Microsoft Intune Sync a device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: syncmanageddevice
- description: Microsoft Intune Remote lock a device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: remotelockmanageddevice
- description: Microsoft Intune Reset device passcode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resetpasscodemanageddevice
- description: Microsoft Intune Reboot a device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rebootmanageddevice
- description: Microsoft Intune List device configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeviceconfigurations
- description: Microsoft Intune Get device configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeviceconfiguration
- description: Microsoft Intune Update device configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedeviceconfiguration
- description: Microsoft Intune Delete device configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeviceconfiguration
- description: Microsoft Intune Assign device configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assigndeviceconfiguration
- description: Microsoft Intune List device compliance policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevicecompliancepolicies
- description: Microsoft Intune Get device compliance policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevicecompliancepolicy
- description: Microsoft Intune Update device compliance policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedevicecompliancepolicy
- description: Microsoft Intune Delete device compliance policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedevicecompliancepolicy
- description: Microsoft Intune Assign device compliance policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assigndevicecompliancepolicy
- description: Microsoft Intune Schedule actions for compliance rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scheduleactionsforrules
---
