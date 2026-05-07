---
categories: []
consumed_apis: []
description: REST API for managing Configuration Manager resources including collections, deployments, applications, and device queries. The administration service is based on the OData v4 protocol and supports both WMI and versioned OData routes. Class names are case-sensitive.
layout: capability
name: Microsoft Endpoint Configuration Management Configuration Manager REST API (AdminService)
operations:
- description: Microsoft Endpoint Configuration Management List devices via WMI route
  method: GET
  name: listdeviceswmi
  path: /wmi/SMS_Device
- description: Microsoft Endpoint Configuration Management List systems
  method: GET
  name: listsystems
  path: /wmi/SMS_R_System
- description: Microsoft Endpoint Configuration Management List collections
  method: GET
  name: listcollections
  path: /wmi/SMS_Collection
- description: Microsoft Endpoint Configuration Management Create a collection
  method: POST
  name: createcollection
  path: /wmi/SMS_Collection
- description: Microsoft Endpoint Configuration Management Get a collection
  method: GET
  name: getcollection
  path: /wmi/SMS_Collection('{collectionId}')
- description: Microsoft Endpoint Configuration Management List applications
  method: GET
  name: listapplications
  path: /wmi/SMS_Application
- description: Microsoft Endpoint Configuration Management Create an application
  method: POST
  name: createapplication
  path: /wmi/SMS_Application
- description: Microsoft Endpoint Configuration Management Get an application
  method: GET
  name: getapplication
  path: /wmi/SMS_Application('{applicationId}')
- description: Microsoft Endpoint Configuration Management List application deployments
  method: GET
  name: listdeployments
  path: /wmi/SMS_ApplicationDeployment
- description: Microsoft Endpoint Configuration Management List packages
  method: GET
  name: listpackages
  path: /wmi/SMS_Package
- description: Microsoft Endpoint Configuration Management List task sequences
  method: GET
  name: listtasksequences
  path: /wmi/SMS_TaskSequence
- description: Microsoft Endpoint Configuration Management List software updates
  method: GET
  name: listsoftwareupdates
  path: /wmi/SMS_SoftwareUpdate
- description: Microsoft Endpoint Configuration Management List sites
  method: GET
  name: listsites
  path: /wmi/SMS_Site
- description: Microsoft Endpoint Configuration Management List compliance baseline assignments
  method: GET
  name: listbaselineassignments
  path: /wmi/SMS_BaselineAssignment
- description: Microsoft Endpoint Configuration Management List devices (versioned route)
  method: GET
  name: listdevicesv1
  path: /v1.0/Device
- description: Microsoft Endpoint Configuration Management Get a device (versioned route)
  method: GET
  name: getdevicev1
  path: /v1.0/Device({deviceId})
- description: Microsoft Endpoint Configuration Management List collections (versioned route)
  method: GET
  name: listcollectionsv1
  path: /v1.0/Collections
- description: Microsoft Endpoint Configuration Management List scripts
  method: GET
  name: listscripts
  path: /v1.0/Scripts
personas: []
provider_name: Microsoft Endpoint Configuration Management
provider_slug: microsoft-endpoint-configuration-management
search_terms:
- microsoft endpoint configuration management list software updates
- endpoint
- listcollectionsv1
- microsoft endpoint configuration management list applications
- microsoft endpoint configuration management list task sequences
- microsoft endpoint configuration management list packages
- listscripts
- microsoft endpoint configuration management list devices via wmi route
- api
- endpoint management
- mobile device management
- createcollection
- listcollections
- configuration
- listsites
- listtasksequences
- getdevicev1
- compliance
- getcollection
- createapplication
- listbaselineassignments
- microsoft
- microsoft endpoint configuration management create an application
- listdevicesv1
- listsystems
- microsoft endpoint configuration management list scripts
- microsoft endpoint configuration management list compliance baseline assignments
- configuration management
- management
- getapplication
- patch management
- microsoft endpoint configuration management get an application
- listsoftwareupdates
- microsoft endpoint configuration management list collections
- microsoft endpoint configuration management create a collection
- microsoft endpoint configuration management list sites
- listdeviceswmi
- microsoft endpoint configuration management list application deployments
- software deployment
- microsoft endpoint configuration management list collections (versioned route)
- listdeployments
- microsoft endpoint configuration management get a collection
- listpackages
- microsoft endpoint configuration management list systems
- listapplications
- microsoft endpoint configuration management list devices (versioned route)
- device management
- microsoft endpoint configuration management get a device (versioned route)
slug: microsoft-endpoint-configuration-management-capability
source_filename: microsoft-endpoint-configuration-management-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Endpoint Configuration Management Configuration Manager REST API (AdminService)\n  description: REST API for managing Configuration Manager resources including collections, deployments, applications, and\n    device queries. The administration service is based on the OData v4 protocol and supports both WMI and versioned OData\n    routes. Class names are case-sensitive.\n  tags:\n  - Microsoft\n  - Endpoint\n  - Configuration\n  - Management\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-endpoint-configuration-management\n    baseUri: https://smsproviderfqdn/AdminService\n    description: Microsoft Endpoint Configuration Management Configuration Manager REST API (AdminService) HTTP API.\n    resources:\n    - name: wmi-sms-device\n      path: /wmi/SMS_Device\n      operations:\n      - name: listdeviceswmi\n        method: GET\n        description:\
  \ Microsoft Endpoint Configuration Management List devices via WMI route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-r-system\n      path: /wmi/SMS_R_System\n      operations:\n      - name: listsystems\n        method: GET\n        description: Microsoft Endpoint Configuration Management List systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-collection\n      path: /wmi/SMS_Collection\n      operations:\n      - name: listcollections\n        method: GET\n        description: Microsoft Endpoint Configuration Management List collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcollection\n        method: POST\n        description: Microsoft Endpoint Configuration Management\
  \ Create a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-collection-collectionid\n      path: /wmi/SMS_Collection('{collectionId}')\n      operations:\n      - name: getcollection\n        method: GET\n        description: Microsoft Endpoint Configuration Management Get a collection\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the collection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-application\n      path: /wmi/SMS_Application\n      operations:\n      - name: listapplications\n        method: GET\n        description: Microsoft Endpoint Configuration Management List applications\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Microsoft Endpoint Configuration Management Create an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-application-applicationid\n      path: /wmi/SMS_Application('{applicationId}')\n      operations:\n      - name: getapplication\n        method: GET\n        description: Microsoft Endpoint Configuration Management Get an application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-applicationdeployment\n      path: /wmi/SMS_ApplicationDeployment\n      operations:\n      - name: listdeployments\n        method:\
  \ GET\n        description: Microsoft Endpoint Configuration Management List application deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-package\n      path: /wmi/SMS_Package\n      operations:\n      - name: listpackages\n        method: GET\n        description: Microsoft Endpoint Configuration Management List packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-tasksequence\n      path: /wmi/SMS_TaskSequence\n      operations:\n      - name: listtasksequences\n        method: GET\n        description: Microsoft Endpoint Configuration Management List task sequences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-softwareupdate\n      path: /wmi/SMS_SoftwareUpdate\n      operations:\n\
  \      - name: listsoftwareupdates\n        method: GET\n        description: Microsoft Endpoint Configuration Management List software updates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-site\n      path: /wmi/SMS_Site\n      operations:\n      - name: listsites\n        method: GET\n        description: Microsoft Endpoint Configuration Management List sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wmi-sms-baselineassignment\n      path: /wmi/SMS_BaselineAssignment\n      operations:\n      - name: listbaselineassignments\n        method: GET\n        description: Microsoft Endpoint Configuration Management List compliance baseline assignments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-0-device\n\
  \      path: /v1.0/Device\n      operations:\n      - name: listdevicesv1\n        method: GET\n        description: Microsoft Endpoint Configuration Management List devices (versioned route)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-0-device-deviceid\n      path: /v1.0/Device({deviceId})\n      operations:\n      - name: getdevicev1\n        method: GET\n        description: Microsoft Endpoint Configuration Management Get a device (versioned route)\n        inputParameters:\n        - name: deviceId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-0-collections\n      path: /v1.0/Collections\n      operations:\n      - name: listcollectionsv1\n        method: GET\n        description: Microsoft Endpoint Configuration Management\
  \ List collections (versioned route)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-0-scripts\n      path: /v1.0/Scripts\n      operations:\n      - name: listscripts\n        method: GET\n        description: Microsoft Endpoint Configuration Management List scripts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-endpoint-configuration-management-rest\n    description: REST adapter for Microsoft Endpoint Configuration Management Configuration Manager REST API (AdminService).\n    resources:\n    - path: /wmi/SMS_Device\n      name: listdeviceswmi\n      operations:\n      - method: GET\n        name: listdeviceswmi\n        description: Microsoft Endpoint Configuration Management List devices via WMI route\n        call: microsoft-endpoint-configuration-management.listdeviceswmi\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_R_System\n      name: listsystems\n      operations:\n      - method: GET\n        name: listsystems\n        description: Microsoft Endpoint Configuration Management List systems\n        call: microsoft-endpoint-configuration-management.listsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Collection\n      name: listcollections\n      operations:\n      - method: GET\n        name: listcollections\n        description: Microsoft Endpoint Configuration Management List collections\n        call: microsoft-endpoint-configuration-management.listcollections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Collection\n      name: createcollection\n      operations:\n      - method: POST\n        name: createcollection\n        description: Microsoft Endpoint Configuration Management Create a collection\n\
  \        call: microsoft-endpoint-configuration-management.createcollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Collection('{collectionId}')\n      name: getcollection\n      operations:\n      - method: GET\n        name: getcollection\n        description: Microsoft Endpoint Configuration Management Get a collection\n        call: microsoft-endpoint-configuration-management.getcollection\n        with:\n          collectionId: rest.collectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Application\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Microsoft Endpoint Configuration Management List applications\n        call: microsoft-endpoint-configuration-management.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Application\n      name:\
  \ createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Microsoft Endpoint Configuration Management Create an application\n        call: microsoft-endpoint-configuration-management.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Application('{applicationId}')\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Microsoft Endpoint Configuration Management Get an application\n        call: microsoft-endpoint-configuration-management.getapplication\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_ApplicationDeployment\n      name: listdeployments\n      operations:\n      - method: GET\n        name: listdeployments\n        description: Microsoft Endpoint Configuration Management List application\
  \ deployments\n        call: microsoft-endpoint-configuration-management.listdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Package\n      name: listpackages\n      operations:\n      - method: GET\n        name: listpackages\n        description: Microsoft Endpoint Configuration Management List packages\n        call: microsoft-endpoint-configuration-management.listpackages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_TaskSequence\n      name: listtasksequences\n      operations:\n      - method: GET\n        name: listtasksequences\n        description: Microsoft Endpoint Configuration Management List task sequences\n        call: microsoft-endpoint-configuration-management.listtasksequences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_SoftwareUpdate\n      name: listsoftwareupdates\n      operations:\n      - method: GET\n\
  \        name: listsoftwareupdates\n        description: Microsoft Endpoint Configuration Management List software updates\n        call: microsoft-endpoint-configuration-management.listsoftwareupdates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_Site\n      name: listsites\n      operations:\n      - method: GET\n        name: listsites\n        description: Microsoft Endpoint Configuration Management List sites\n        call: microsoft-endpoint-configuration-management.listsites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wmi/SMS_BaselineAssignment\n      name: listbaselineassignments\n      operations:\n      - method: GET\n        name: listbaselineassignments\n        description: Microsoft Endpoint Configuration Management List compliance baseline assignments\n        call: microsoft-endpoint-configuration-management.listbaselineassignments\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1.0/Device\n      name: listdevicesv1\n      operations:\n      - method: GET\n        name: listdevicesv1\n        description: Microsoft Endpoint Configuration Management List devices (versioned route)\n        call: microsoft-endpoint-configuration-management.listdevicesv1\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1.0/Device({deviceId})\n      name: getdevicev1\n      operations:\n      - method: GET\n        name: getdevicev1\n        description: Microsoft Endpoint Configuration Management Get a device (versioned route)\n        call: microsoft-endpoint-configuration-management.getdevicev1\n        with:\n          deviceId: rest.deviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1.0/Collections\n      name: listcollectionsv1\n      operations:\n      - method: GET\n        name: listcollectionsv1\n        description: Microsoft Endpoint Configuration\
  \ Management List collections (versioned route)\n        call: microsoft-endpoint-configuration-management.listcollectionsv1\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1.0/Scripts\n      name: listscripts\n      operations:\n      - method: GET\n        name: listscripts\n        description: Microsoft Endpoint Configuration Management List scripts\n        call: microsoft-endpoint-configuration-management.listscripts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-endpoint-configuration-management-mcp\n    transport: http\n    description: MCP adapter for Microsoft Endpoint Configuration Management Configuration Manager REST API (AdminService)\n      for AI agent use.\n    tools:\n    - name: listdeviceswmi\n      description: Microsoft Endpoint Configuration Management List devices via WMI route\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: microsoft-endpoint-configuration-management.listdeviceswmi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsystems\n      description: Microsoft Endpoint Configuration Management List systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listsystems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcollections\n      description: Microsoft Endpoint Configuration Management List collections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listcollections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcollection\n      description: Microsoft Endpoint Configuration Management Create a collection\n      hints:\n        readOnly: false\n     \
  \   destructive: false\n        idempotent: false\n      call: microsoft-endpoint-configuration-management.createcollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcollection\n      description: Microsoft Endpoint Configuration Management Get a collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.getcollection\n      with:\n        collectionId: tools.collectionId\n      inputParameters:\n      - name: collectionId\n        type: string\n        description: The unique identifier of the collection.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapplications\n      description: Microsoft Endpoint Configuration Management List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listapplications\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapplication\n      description: Microsoft Endpoint Configuration Management Create an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-endpoint-configuration-management.createapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplication\n      description: Microsoft Endpoint Configuration Management Get an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.getapplication\n      with:\n        applicationId: tools.applicationId\n      inputParameters:\n      - name: applicationId\n        type: string\n        description: applicationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeployments\n      description:\
  \ Microsoft Endpoint Configuration Management List application deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpackages\n      description: Microsoft Endpoint Configuration Management List packages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listpackages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasksequences\n      description: Microsoft Endpoint Configuration Management List task sequences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listtasksequences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listsoftwareupdates\n      description: Microsoft Endpoint Configuration Management List software updates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listsoftwareupdates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsites\n      description: Microsoft Endpoint Configuration Management List sites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbaselineassignments\n      description: Microsoft Endpoint Configuration Management List compliance baseline assignments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listbaselineassignments\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listdevicesv1\n      description: Microsoft Endpoint Configuration Management List devices (versioned route)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listdevicesv1\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevicev1\n      description: Microsoft Endpoint Configuration Management Get a device (versioned route)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.getdevicev1\n      with:\n        deviceId: tools.deviceId\n      inputParameters:\n      - name: deviceId\n        type: integer\n        description: deviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcollectionsv1\n      description: Microsoft Endpoint Configuration\
  \ Management List collections (versioned route)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listcollectionsv1\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscripts\n      description: Microsoft Endpoint Configuration Management List scripts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-endpoint-configuration-management.listscripts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-endpoint-configuration-management/refs/heads/main/capabilities/microsoft-endpoint-configuration-management-capability.yaml
tags:
- Microsoft
- Endpoint
- Configuration
- Management
- API
tools:
- description: Microsoft Endpoint Configuration Management List devices via WMI route
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeviceswmi
- description: Microsoft Endpoint Configuration Management List systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsystems
- description: Microsoft Endpoint Configuration Management List collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollections
- description: Microsoft Endpoint Configuration Management Create a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcollection
- description: Microsoft Endpoint Configuration Management Get a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollection
- description: Microsoft Endpoint Configuration Management List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Microsoft Endpoint Configuration Management Create an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Microsoft Endpoint Configuration Management Get an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Microsoft Endpoint Configuration Management List application deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Microsoft Endpoint Configuration Management List packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpackages
- description: Microsoft Endpoint Configuration Management List task sequences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasksequences
- description: Microsoft Endpoint Configuration Management List software updates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsoftwareupdates
- description: Microsoft Endpoint Configuration Management List sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
- description: Microsoft Endpoint Configuration Management List compliance baseline assignments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbaselineassignments
- description: Microsoft Endpoint Configuration Management List devices (versioned route)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevicesv1
- description: Microsoft Endpoint Configuration Management Get a device (versioned route)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevicev1
- description: Microsoft Endpoint Configuration Management List collections (versioned route)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollectionsv1
- description: Microsoft Endpoint Configuration Management List scripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscripts
---
