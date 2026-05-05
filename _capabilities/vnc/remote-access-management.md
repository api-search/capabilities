---
api_specs:
- filename: vnc-cloud-openapi.yml
  format: yaml
  label: vnc-cloud
  slug: vnc-cloud
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vnc/refs/heads/main/openapi/vnc-cloud-openapi.yml
categories: []
consumed_apis:
- vnc-cloud
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
- rotate cloud address password
- retrieve full configuration details for a cloud address.
- vnc
- remote access
- inspect cloud address
- it operations
- manage vnc cloud addresses for device connectivity.
- cloud
- device management
- list cloud addresses
- reset cloud address password
- check propagation status of a cloud address.
- deprovision cloud address
- update group membership and access control for a cloud address.
- create cloud address
- provision a new vnc cloud address for a device to join vnc cloud.
- list all cloud addresses provisioned in the vnc account.
- reset the password for a cloud address.
- update groups and access control for a cloud address.
- list all provisioned cloud addresses.
- reconfigure cloud address
- reset the cloud password for a specific address.
- permanently remove a cloud address from the account.
- screen sharing
- provision a new cloud address for a device.
- inspect and manage a specific cloud address.
- retrieve details of a cloud address.
- get cloud address
- networking
- check cloud address ready
- update cloud address
- verify configuration changes have propagated.
- delete cloud address
- generate a new cloud password for a cloud address.
- check address propagation
- provision cloud address
- deprovision and remove a cloud address.
- verify whether recent changes to a cloud address have been fully propagated.
- remote desktop
slug: remote-access-management
source_filename: remote-access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VNC Remote Access Management\"\n  description: >-\n    Unified capability for managing VNC Cloud remote access infrastructure.\n    Covers provisioning and deprovisioning cloud addresses, configuring\n    access control groups, monitoring address readiness, and automating\n    device lifecycle management for IT administrators and DevOps teams.\n  tags:\n    - VNC\n    - Remote Access\n    - Device Management\n    - Cloud\n    - IT Operations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VNC_CLOUD_API_KEY: VNC_CLOUD_API_KEY\n      VNC_CLOUD_API_SECRET: VNC_CLOUD_API_SECRET\n\ncapability:\n  consumes:\n    - import: vnc-cloud\n      location: ./shared/vnc-cloud.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vnc-remote-access-api\n      description: \"Unified REST API for VNC remote access infrastructure management.\"\n      resources:\n        - path:\
  \ /v1/cloud-addresses\n          name: cloud-addresses\n          description: \"Manage VNC cloud addresses for device connectivity.\"\n          operations:\n            - method: POST\n              name: create-cloud-address\n              description: \"Provision a new cloud address for a device.\"\n              call: \"vnc-cloud.create-cloud-address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-cloud-addresses\n              description: \"List all provisioned cloud addresses.\"\n              call: \"vnc-cloud.list-cloud-addresses\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cloud-addresses/{cloudAddress}\n          name: cloud-address-detail\n          description: \"Inspect and manage a specific cloud address.\"\n          operations:\n\
  \            - method: GET\n              name: get-cloud-address\n              description: \"Retrieve details of a cloud address.\"\n              call: \"vnc-cloud.get-cloud-address\"\n              with:\n                cloudAddress: \"rest.cloudAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-cloud-address\n              description: \"Update groups and access control for a cloud address.\"\n              call: \"vnc-cloud.update-cloud-address\"\n              with:\n                cloudAddress: \"rest.cloudAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cloud-address\n              description: \"Deprovision and remove a cloud address.\"\n              call: \"vnc-cloud.delete-cloud-address\"\n              with:\n                cloudAddress: \"\
  rest.cloudAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cloud-addresses/{cloudAddress}/password-reset\n          name: cloud-address-password\n          description: \"Reset the cloud password for a specific address.\"\n          operations:\n            - method: POST\n              name: reset-cloud-address-password\n              description: \"Reset the password for a cloud address.\"\n              call: \"vnc-cloud.reset-cloud-address-password\"\n              with:\n                cloudAddress: \"rest.cloudAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cloud-addresses/{cloudAddress}/ready\n          name: cloud-address-readiness\n          description: \"Check propagation status of a cloud address.\"\n          operations:\n            - method: GET\n              name: check-cloud-address-ready\n          \
  \    description: \"Verify configuration changes have propagated.\"\n              call: \"vnc-cloud.check-cloud-address-ready\"\n              with:\n                cloudAddress: \"rest.cloudAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vnc-remote-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VNC remote access infrastructure management.\"\n      tools:\n        - name: provision-cloud-address\n          description: \"Provision a new VNC cloud address for a device to join VNC Cloud.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vnc-cloud.create-cloud-address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cloud-addresses\n          description: \"List all cloud addresses provisioned\
  \ in the VNC account.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"vnc-cloud.list-cloud-addresses\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: inspect-cloud-address\n          description: \"Retrieve full configuration details for a cloud address.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"vnc-cloud.get-cloud-address\"\n          with:\n            cloudAddress: \"tools.cloudAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reconfigure-cloud-address\n          description: \"Update group membership and access control for a cloud address.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ true\n          call: \"vnc-cloud.update-cloud-address\"\n          with:\n            cloudAddress: \"tools.cloudAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rotate-cloud-address-password\n          description: \"Generate a new cloud password for a cloud address.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vnc-cloud.reset-cloud-address-password\"\n          with:\n            cloudAddress: \"tools.cloudAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deprovision-cloud-address\n          description: \"Permanently remove a cloud address from the account.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vnc-cloud.delete-cloud-address\"\n          with:\n            cloudAddress: \"\
  tools.cloudAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-address-propagation\n          description: \"Verify whether recent changes to a cloud address have been fully propagated.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"vnc-cloud.check-cloud-address-ready\"\n          with:\n            cloudAddress: \"tools.cloudAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
