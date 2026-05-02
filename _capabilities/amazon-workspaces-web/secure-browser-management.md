---
categories: []
consumed_apis:
- workspaces-web
description: Unified workflow for IT administrators to manage Amazon WorkSpaces Web portals, user settings, browser policies, network configurations, and trust stores for enterprise secure browser deployments.
layout: capability
name: Amazon WorkSpaces Web Secure Browser Management
operations:
- description: List secure browser portals.
  method: GET
  name: list-portals
  path: /v1/portals
- description: Create a portal.
  method: POST
  name: create-portal
  path: /v1/portals
- description: List user settings.
  method: GET
  name: list-user-settings
  path: /v1/user-settings
- description: List browser settings.
  method: GET
  name: list-browser-settings
  path: /v1/browser-settings
- description: List network settings.
  method: GET
  name: list-network-settings
  path: /v1/network-settings
- description: List trust stores.
  method: GET
  name: list-trust-stores
  path: /v1/trust-stores
personas: []
provider_name: Amazon WorkSpaces Web
provider_slug: amazon-workspaces-web
search_terms:
- administration
- list user settings
- browser policy and access control enforcement
- virtual desktop
- list secure browser portals.
- list ssl certificate trust stores.
- portal and resource provisioning
- list user settings.
- list network settings for portal connectivity.
- end user computing
- workflow for it administrators to manage workspaces web portals and their associated security and network configurations.
- Security Engineer
- list browser settings.
- create a new secure browser portal.
- list user settings configurations for portals.
- create portal
- list trust stores.
- secure remote browser access infrastructure
- create a portal.
- manages workspaces web portals and configurations.
- browser policy management.
- portal management.
- user settings management.
- zero trust
- list network settings.
- list trust stores
- trust store management.
- secure browser
- list browser settings
- configures browser policies and access controls.
- IT Administrator
- list portals
- list all workspaces web secure browser portals.
- network configuration management.
- list browser policy settings for portals.
- list network settings
- aws
slug: secure-browser-management
source_filename: secure-browser-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon WorkSpaces Web Secure Browser Management\"\n  description: >-\n    Unified workflow for IT administrators to manage Amazon WorkSpaces Web\n    portals, user settings, browser policies, network configurations, and\n    trust stores for enterprise secure browser deployments.\n  tags:\n    - AWS\n    - Secure Browser\n    - End User Computing\n    - Administration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: workspaces-web\n      location: ./shared/workspaces-web.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: secure-browser-management-api\n      description: \"Unified REST API for Amazon WorkSpaces Web secure browser management.\"\n      resources:\n        - path: /v1/portals\n   \
  \       name: portals\n          description: \"Portal management.\"\n          operations:\n            - method: GET\n              name: list-portals\n              description: \"List secure browser portals.\"\n              call: \"workspaces-web.list-portals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-portal\n              description: \"Create a portal.\"\n              call: \"workspaces-web.create-portal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user-settings\n          name: user-settings\n          description: \"User settings management.\"\n          operations:\n            - method: GET\n              name: list-user-settings\n              description: \"List user settings.\"\n              call: \"workspaces-web.list-user-settings\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n        - path: /v1/browser-settings\n          name: browser-settings\n          description: \"Browser policy management.\"\n          operations:\n            - method: GET\n              name: list-browser-settings\n              description: \"List browser settings.\"\n              call: \"workspaces-web.list-browser-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/network-settings\n          name: network-settings\n          description: \"Network configuration management.\"\n          operations:\n            - method: GET\n              name: list-network-settings\n              description: \"List network settings.\"\n              call: \"workspaces-web.list-network-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trust-stores\n          name: trust-stores\n\
  \          description: \"Trust store management.\"\n          operations:\n            - method: GET\n              name: list-trust-stores\n              description: \"List trust stores.\"\n              call: \"workspaces-web.list-trust-stores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: secure-browser-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon WorkSpaces Web management.\"\n      tools:\n        - name: list-portals\n          description: \"List all WorkSpaces Web secure browser portals.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces-web.list-portals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-portal\n          description: \"Create a new secure browser portal.\"\n          hints:\n          \
  \  readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"workspaces-web.create-portal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-user-settings\n          description: \"List user settings configurations for portals.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces-web.list-user-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-browser-settings\n          description: \"List browser policy settings for portals.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces-web.list-browser-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-network-settings\n          description: \"List network settings for portal connectivity.\"\n     \
  \     hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces-web.list-network-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trust-stores\n          description: \"List SSL certificate trust stores.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workspaces-web.list-trust-stores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-workspaces-web/refs/heads/main/capabilities/secure-browser-management.yaml
tags:
- Secure Browser
- End User Computing
- Administration
tools:
- description: List all WorkSpaces Web secure browser portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-portals
- description: Create a new secure browser portal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-portal
- description: List user settings configurations for portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-user-settings
- description: List browser policy settings for portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-browser-settings
- description: List network settings for portal connectivity.
  hints:
    openWorld: true
    readOnly: true
  name: list-network-settings
- description: List SSL certificate trust stores.
  hints:
    openWorld: true
    readOnly: true
  name: list-trust-stores
---
