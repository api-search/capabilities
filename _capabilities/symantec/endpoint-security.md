---
categories: []
consumed_apis:
- sepm
description: Unified endpoint security management capability for Symantec/Broadcom products. Enables security operations teams to manage endpoint protection infrastructure, query protected devices, administer groups, and manage administrator accounts via the SEPM REST API.
layout: capability
name: Symantec Endpoint Security Management
operations:
- description: List Computers
  method: GET
  name: list-computers
  path: /v1/computers
- description: Remove Computer
  method: DELETE
  name: remove-computer
  path: /v1/computers/{computerId}
- description: List Groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create Group
  method: POST
  name: create-group
  path: /v1/groups
- description: List Administrators
  method: GET
  name: list-administrators
  path: /v1/administrators
personas: []
provider_name: Symantec
provider_slug: symantec
search_terms:
- list all endpoints managed by sepm with status, os, sep version, and last scan time
- dlp
- search for specific computers by hostname in sepm
- create a new computer group in sepm for policy segmentation
- security
- manage protected endpoint computers
- sepm administrator accounts
- symantec
- cybersecurity
- create group
- groups
- edr
- list all sepm administrator accounts and their roles
- list all sepm groups with computer counts and policy settings
- sepm
- endpoint security
- security operations
- list computers
- broadcom
- endpoint protection
- search computers by name
- sepm group management
- remove computer
- list administrators
- single computer management
- list groups
slug: endpoint-security
source_filename: endpoint-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Symantec Endpoint Security Management\"\n  description: >-\n    Unified endpoint security management capability for Symantec/Broadcom\n    products. Enables security operations teams to manage endpoint protection\n    infrastructure, query protected devices, administer groups, and manage\n    administrator accounts via the SEPM REST API.\n  tags:\n    - Broadcom\n    - Cybersecurity\n    - Endpoint Protection\n    - Endpoint Security\n    - Groups\n    - SEPM\n    - Security Operations\n    - Symantec\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEPM_USERNAME: SEPM_USERNAME\n      SEPM_PASSWORD: SEPM_PASSWORD\n      SEPM_HOST: SEPM_HOST\n      SEPM_BEARER_TOKEN: SEPM_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: sepm\n      location: ./shared/symantec-sepm.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: symantec-security-api\n      description:\
  \ \"Unified REST API for Symantec endpoint security management.\"\n      resources:\n        - path: /v1/computers\n          name: computers\n          description: \"Manage protected endpoint computers\"\n          operations:\n            - method: GET\n              name: list-computers\n              description: \"List Computers\"\n              call: \"sepm.list-computers\"\n              with:\n                computerName: \"rest.computerName\"\n                pageSize: \"rest.pageSize\"\n                pageIndex: \"rest.pageIndex\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/computers/{computerId}\n          name: computer-detail\n          description: \"Single computer management\"\n          operations:\n            - method: DELETE\n              name: remove-computer\n              description: \"Remove Computer\"\n              call: \"sepm.list-computers\"\n              with:\n          \
  \      computerId: \"rest.computerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/groups\n          name: groups\n          description: \"SEPM group management\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List Groups\"\n              call: \"sepm.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create Group\"\n              call: \"sepm.create-group\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/administrators\n          name: administrators\n          description: \"SEPM administrator accounts\"\n \
  \         operations:\n            - method: GET\n              name: list-administrators\n              description: \"List Administrators\"\n              call: \"sepm.list-administrators\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: symantec-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Symantec endpoint security management.\"\n      tools:\n        - name: list-computers\n          description: \"List all endpoints managed by SEPM with status, OS, SEP version, and last scan time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sepm.list-computers\"\n          with:\n            computerName: \"tools.computerName\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-computers-by-name\n\
  \          description: \"Search for specific computers by hostname in SEPM\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sepm.list-computers\"\n          with:\n            computerName: \"tools.computerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-groups\n          description: \"List all SEPM groups with computer counts and policy settings\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sepm.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-group\n          description: \"Create a new computer group in SEPM for policy segmentation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sepm.create-group\"\n          with:\n            name: \"tools.name\"\n     \
  \       description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-administrators\n          description: \"List all SEPM administrator accounts and their roles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sepm.list-administrators\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/symantec/refs/heads/main/capabilities/endpoint-security.yaml
tags:
- Broadcom
- Cybersecurity
- Endpoint Protection
- Endpoint Security
- Groups
- SEPM
- Security Operations
- Symantec
tools:
- description: List all endpoints managed by SEPM with status, OS, SEP version, and last scan time
  hints:
    idempotent: true
    readOnly: true
  name: list-computers
- description: Search for specific computers by hostname in SEPM
  hints:
    idempotent: true
    readOnly: true
  name: search-computers-by-name
- description: List all SEPM groups with computer counts and policy settings
  hints:
    idempotent: true
    readOnly: true
  name: list-groups
- description: Create a new computer group in SEPM for policy segmentation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-group
- description: List all SEPM administrator accounts and their roles
  hints:
    idempotent: true
    readOnly: true
  name: list-administrators
---
