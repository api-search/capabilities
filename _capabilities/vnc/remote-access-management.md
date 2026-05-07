---
categories: []
consumed_apis: []
description: Unified capability for managing VNC Cloud remote access infrastructure. Covers provisioning and deprovisioning cloud addresses, configuring access control groups, monitoring address readiness, and automating device lifecycle management for IT administrators and DevOps teams.
layout: capability
name: VNC Remote Access Management
operations:
- description: Provision a new cloud address for a device.
  method: POST
  name: create-cloud-address
  path: /v1/cloud-addresses
- description: List all provisioned cloud addresses.
  method: GET
  name: list-cloud-addresses
  path: /v1/cloud-addresses
- description: Retrieve details of a cloud address.
  method: GET
  name: get-cloud-address
  path: /v1/cloud-addresses/{cloudAddress}
- description: Update groups and access control for a cloud address.
  method: PUT
  name: update-cloud-address
  path: /v1/cloud-addresses/{cloudAddress}
- description: Deprovision and remove a cloud address.
  method: DELETE
  name: delete-cloud-address
  path: /v1/cloud-addresses/{cloudAddress}
- description: Reset the password for a cloud address.
  method: POST
  name: reset-cloud-address-password
  path: /v1/cloud-addresses/{cloudAddress}/password-reset
- description: Verify configuration changes have propagated.
  method: GET
  name: check-cloud-address-ready
  path: /v1/cloud-addresses/{cloudAddress}/ready
personas: []
provider_name: VNC
provider_slug: vnc
search_terms:
- provision a new vnc cloud address for a device to join vnc cloud.
- networking
- screen sharing
- delete cloud address
- permanently remove a cloud address from the account.
- deprovision cloud address
- verify configuration changes have propagated.
- inspect cloud address
- update cloud address
- reconfigure cloud address
- list all cloud addresses provisioned in the vnc account.
- update groups and access control for a cloud address.
- check cloud address ready
- rotate cloud address password
- create cloud address
- vnc
- it operations
- remote desktop
- manage vnc cloud addresses for device connectivity.
- deprovision and remove a cloud address.
- update group membership and access control for a cloud address.
- provision a new cloud address for a device.
- retrieve details of a cloud address.
- inspect and manage a specific cloud address.
- check address propagation
- reset cloud address password
- get cloud address
- verify whether recent changes to a cloud address have been fully propagated.
- remote access
- provision cloud address
- cloud
- reset the cloud password for a specific address.
- reset the password for a cloud address.
- check propagation status of a cloud address.
- list cloud addresses
- retrieve full configuration details for a cloud address.
- device management
- list all provisioned cloud addresses.
- generate a new cloud password for a cloud address.
slug: remote-access-management
source_filename: remote-access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VNC Remote Access Management\n  description: Unified capability for managing VNC Cloud remote access infrastructure. Covers provisioning and deprovisioning\n    cloud addresses, configuring access control groups, monitoring address readiness, and automating device lifecycle management\n    for IT administrators and DevOps teams.\n  tags:\n  - VNC\n  - Remote Access\n  - Device Management\n  - Cloud\n  - IT Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VNC_CLOUD_API_KEY: VNC_CLOUD_API_KEY\n    VNC_CLOUD_API_SECRET: VNC_CLOUD_API_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: vnc-cloud\n    baseUri: https://api.vnc.com/cloud/1.1\n    description: VNC Cloud REST API for managing cloud addresses.\n    authentication:\n      type: basic\n      username: '{{VNC_CLOUD_API_KEY}}'\n      password: '{{VNC_CLOUD_API_SECRET}}'\n    resources:\n    - name: cloud-addresses\n \
  \     path: /static-address\n      description: Manage static cloud addresses for VNC Cloud connectivity.\n      operations:\n      - name: create-cloud-address\n        method: POST\n        description: Create a new static cloud address.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            allowedActions: '{{tools.allowedActions}}'\n            groups: '{{tools.groups}}'\n      - name: list-cloud-addresses\n        method: GET\n        description: List all cloud addresses with pagination.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max addresses per page (1-99, default 20).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-address-detail\n\
  \      path: /static-address/{cloudAddress}\n      description: Operate on a specific cloud address.\n      operations:\n      - name: get-cloud-address\n        method: GET\n        description: Retrieve details of a specific cloud address.\n        inputParameters:\n        - name: cloudAddress\n          in: path\n          type: string\n          required: true\n          description: The cloud address identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cloud-address\n        method: PUT\n        description: Update cloud address groups and access control.\n        inputParameters:\n        - name: cloudAddress\n          in: path\n          type: string\n          required: true\n          description: The cloud address identifier.\n        - name: If-Match\n          in: header\n          type: string\n          required: false\n          description: ETag for optimistic concurrency.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            allowedActions: '{{tools.allowedActions}}'\n            groups: '{{tools.groups}}'\n      - name: reset-cloud-address-password\n        method: POST\n        description: Reset the cloud password for a cloud address.\n        inputParameters:\n        - name: cloudAddress\n          in: path\n          type: string\n          required: true\n          description: The cloud address identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cloud-address\n        method: DELETE\n        description: Permanently remove a cloud address.\n        inputParameters:\n        - name: cloudAddress\n          in: path\n          type: string\n          required: true\n          description: The cloud address\
  \ identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-address-readiness\n      path: /static-address/{cloudAddress}/ready\n      description: Check whether a cloud address change has propagated.\n      operations:\n      - name: check-cloud-address-ready\n        method: GET\n        description: Check readiness status of a cloud address.\n        inputParameters:\n        - name: cloudAddress\n          in: path\n          type: string\n          required: true\n          description: The cloud address identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vnc-remote-access-api\n    description: Unified REST API for VNC remote access infrastructure management.\n    resources:\n    - path: /v1/cloud-addresses\n      name: cloud-addresses\n\
  \      description: Manage VNC cloud addresses for device connectivity.\n      operations:\n      - method: POST\n        name: create-cloud-address\n        description: Provision a new cloud address for a device.\n        call: vnc-cloud.create-cloud-address\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-cloud-addresses\n        description: List all provisioned cloud addresses.\n        call: vnc-cloud.list-cloud-addresses\n        with:\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloud-addresses/{cloudAddress}\n      name: cloud-address-detail\n      description: Inspect and manage a specific cloud address.\n      operations:\n      - method: GET\n        name: get-cloud-address\n        description: Retrieve details of a cloud address.\n        call: vnc-cloud.get-cloud-address\n        with:\n          cloudAddress: rest.cloudAddress\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-cloud-address\n        description: Update groups and access control for a cloud address.\n        call: vnc-cloud.update-cloud-address\n        with:\n          cloudAddress: rest.cloudAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cloud-address\n        description: Deprovision and remove a cloud address.\n        call: vnc-cloud.delete-cloud-address\n        with:\n          cloudAddress: rest.cloudAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloud-addresses/{cloudAddress}/password-reset\n      name: cloud-address-password\n      description: Reset the cloud password for a specific address.\n      operations:\n      - method: POST\n        name: reset-cloud-address-password\n        description: Reset the password for a cloud address.\n\
  \        call: vnc-cloud.reset-cloud-address-password\n        with:\n          cloudAddress: rest.cloudAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloud-addresses/{cloudAddress}/ready\n      name: cloud-address-readiness\n      description: Check propagation status of a cloud address.\n      operations:\n      - method: GET\n        name: check-cloud-address-ready\n        description: Verify configuration changes have propagated.\n        call: vnc-cloud.check-cloud-address-ready\n        with:\n          cloudAddress: rest.cloudAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vnc-remote-access-mcp\n    transport: http\n    description: MCP server for AI-assisted VNC remote access infrastructure management.\n    tools:\n    - name: provision-cloud-address\n      description: Provision a new VNC cloud address for a device to join VNC Cloud.\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vnc-cloud.create-cloud-address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cloud-addresses\n      description: List all cloud addresses provisioned in the VNC account.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: vnc-cloud.list-cloud-addresses\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-cloud-address\n      description: Retrieve full configuration details for a cloud address.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: vnc-cloud.get-cloud-address\n      with:\n        cloudAddress: tools.cloudAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reconfigure-cloud-address\n      description: Update group membership and\
  \ access control for a cloud address.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vnc-cloud.update-cloud-address\n      with:\n        cloudAddress: tools.cloudAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rotate-cloud-address-password\n      description: Generate a new cloud password for a cloud address.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vnc-cloud.reset-cloud-address-password\n      with:\n        cloudAddress: tools.cloudAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deprovision-cloud-address\n      description: Permanently remove a cloud address from the account.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vnc-cloud.delete-cloud-address\n      with:\n        cloudAddress: tools.cloudAddress\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: check-address-propagation\n      description: Verify whether recent changes to a cloud address have been fully propagated.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: vnc-cloud.check-cloud-address-ready\n      with:\n        cloudAddress: tools.cloudAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vnc/refs/heads/main/capabilities/remote-access-management.yaml
tags:
- VNC
- Remote Access
- Device Management
- Cloud
- IT Operations
tools:
- description: Provision a new VNC cloud address for a device to join VNC Cloud.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provision-cloud-address
- description: List all cloud addresses provisioned in the VNC account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-cloud-addresses
- description: Retrieve full configuration details for a cloud address.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-cloud-address
- description: Update group membership and access control for a cloud address.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reconfigure-cloud-address
- description: Generate a new cloud password for a cloud address.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotate-cloud-address-password
- description: Permanently remove a cloud address from the account.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deprovision-cloud-address
- description: Verify whether recent changes to a cloud address have been fully propagated.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: check-address-propagation
---
