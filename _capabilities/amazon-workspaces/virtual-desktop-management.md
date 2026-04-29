---
categories: []
consumed_apis:
- workspaces
description: Unified workflow for IT administrators and end user computing teams to provision, manage, and maintain Amazon WorkSpaces virtual desktops at scale, including workspace lifecycle, bundle management, directory integration, and image management.
layout: capability
name: Amazon WorkSpaces Virtual Desktop Management
operations:
- description: List virtual desktops.
  method: GET
  name: describe-workspaces
  path: /v1/workspaces
- description: Provision new virtual desktops.
  method: POST
  name: create-workspaces
  path: /v1/workspaces
- description: List available bundles.
  method: GET
  name: describe-workspace-bundles
  path: /v1/bundles
- description: List directories.
  method: GET
  name: describe-workspace-directories
  path: /v1/directories
- description: List workspace images.
  method: GET
  name: describe-workspace-images
  path: /v1/images
personas: []
provider_name: Amazon WorkSpaces
provider_slug: amazon-workspaces
search_terms:
- list workspace images.
- virtual desktop
- permanently terminate virtual desktop workspaces.
- hardware bundle catalog.
- it administration of desktop resources
- end user computing
- directory management.
- desktop as a service
- reboot workspaces
- manages workspaces provisioning, lifecycle, and policy.
- create workspaces
- list available bundles.
- list available hardware configuration bundles.
- list registered directories for workspace deployment.
- list directories.
- list virtual desktops.
- aws
- designs and operates virtual desktop infrastructure.
- virtual desktop lifecycle management.
- describe workspace bundles
- IT Administrator
- describe workspaces
- remote work and desktop-as-a-service infrastructure
- End User Computing Engineer
- list and describe all virtual desktop workspaces.
- provision new virtual desktops.
- workspace image management.
- describe workspace images
- reboot virtual desktop workspaces to resolve issues.
- desktop
- cloud-based virtual desktop provisioning and management
- list available workspace images for provisioning.
- terminate workspaces
- describe workspace directories
- provision new virtual desktop workspaces for users.
- administration
- workflow for it administrators to provision and manage amazon workspaces virtual desktops including lifecycle, bundles, directories, and images.
slug: virtual-desktop-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon WorkSpaces Virtual Desktop Management\"\n  description: >-\n    Unified workflow for IT administrators and end user computing teams to\n    provision, manage, and maintain Amazon WorkSpaces virtual desktops at scale,\n    including workspace lifecycle, bundle management, directory integration,\n    and image management.\n  tags:\n    - AWS\n    - Virtual Desktop\n    - End User Computing\n    - Desktop as a Service\n    - Administration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: workspaces\n      location: ./shared/workspaces.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: virtual-desktop-management-api\n      description: \"Unified REST API for Amazon WorkSpaces virtual desktop\
  \ management.\"\n      resources:\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Virtual desktop lifecycle management.\"\n          operations:\n            - method: GET\n              name: describe-workspaces\n              description: \"List virtual desktops.\"\n              call: \"workspaces.describe-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspaces\n              description: \"Provision new virtual desktops.\"\n              call: \"workspaces.create-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bundles\n          name: bundles\n          description: \"Hardware bundle catalog.\"\n          operations:\n            - method: GET\n              name: describe-workspace-bundles\n              description: \"List available bundles.\"\
  \n              call: \"workspaces.describe-workspace-bundles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/directories\n          name: directories\n          description: \"Directory management.\"\n          operations:\n            - method: GET\n              name: describe-workspace-directories\n              description: \"List directories.\"\n              call: \"workspaces.describe-workspace-directories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images\n          name: images\n          description: \"Workspace image management.\"\n          operations:\n            - method: GET\n              name: describe-workspace-images\n              description: \"List workspace images.\"\n              call: \"workspaces.describe-workspace-images\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: virtual-desktop-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon WorkSpaces virtual desktop management.\"\n      tools:\n        - name: describe-workspaces\n          description: \"List and describe all virtual desktop workspaces.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces.describe-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspaces\n          description: \"Provision new virtual desktop workspaces for users.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"workspaces.create-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-workspaces\n          description: \"Permanently\
  \ terminate virtual desktop workspaces.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"workspaces.terminate-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reboot-workspaces\n          description: \"Reboot virtual desktop workspaces to resolve issues.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"workspaces.reboot-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-workspace-bundles\n          description: \"List available hardware configuration bundles.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces.describe-workspace-bundles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: describe-workspace-directories\n          description: \"List registered directories for workspace deployment.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces.describe-workspace-directories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-workspace-images\n          description: \"List available workspace images for provisioning.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces.describe-workspace-images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-workspaces/refs/heads/main/capabilities/virtual-desktop-management.yaml
tags:
- AWS
- Virtual Desktop
- End User Computing
- Desktop as a Service
- Administration
tools:
- description: List and describe all virtual desktop workspaces.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspaces
- description: Provision new virtual desktop workspaces for users.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workspaces
- description: Permanently terminate virtual desktop workspaces.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-workspaces
- description: Reboot virtual desktop workspaces to resolve issues.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reboot-workspaces
- description: List available hardware configuration bundles.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-bundles
- description: List registered directories for workspace deployment.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-directories
- description: List available workspace images for provisioning.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-images
---
