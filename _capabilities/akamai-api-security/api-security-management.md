---
categories: []
consumed_apis:
- akamai-api-security
description: Unified workflow for managing Akamai API Security configurations, policies, and threat protection. Covers security posture management, API discovery, and configuration activation for security teams.
layout: capability
name: Akamai API Security Management
operations:
- description: List all API security configurations
  method: GET
  name: list-configurations
  path: /v1/configurations
- description: Create a new API security configuration
  method: POST
  name: create-configuration
  path: /v1/configurations
- description: List security policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Get API discovery results
  method: GET
  name: get-api-discovery
  path: /v1/api-discovery
- description: List configuration activations
  method: GET
  name: list-activations
  path: /v1/activations
personas: []
provider_name: Akamai API Security
provider_slug: akamai-api-security
search_terms:
- list policies
- manages api security configurations and activations
- discover apis
- monitors api discovery, threat detection, and posture findings
- threat protection
- api inventory and discovery
- create security configuration
- posture management
- create a new api security configuration
- get api discovery results
- akamai
- api discovery
- list configurations
- list security policies
- create configuration
- create a new akamai api security configuration
- Security Engineer
- list activations
- API Security Analyst
- security automation
- list security configurations
- list all api security configurations
- get api discovery
- manage api security configurations and posture
- list all akamai api security configurations
- check activation status
- list security policies within a configuration
- runtime protection
- cloud security
- list and check status of security configuration activations
- get api inventory including shadow and zombie api findings
- list configuration activations
- security policy management
- api posture assessment and vulnerability management
- api security configuration management
- api security configuration and policy management
- configuration activations
- api security
- real-time api threat detection and blocking
slug: api-security-management
source_filename: api-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Akamai API Security Management\"\n  description: \"Unified workflow for managing Akamai API Security configurations, policies, and threat protection. Covers security posture management, API discovery, and configuration activation for security teams.\"\n  tags:\n    - Akamai\n    - API Security\n    - Posture Management\n    - Runtime Protection\n    - Security Automation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AKAMAI_CLIENT_TOKEN: AKAMAI_CLIENT_TOKEN\n      AKAMAI_CLIENT_SECRET: AKAMAI_CLIENT_SECRET\n      AKAMAI_ACCESS_TOKEN: AKAMAI_ACCESS_TOKEN\n      AKAMAI_HOST: AKAMAI_HOST\n\ncapability:\n  consumes:\n    - import: akamai-api-security\n      location: ./shared/api-security.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-security-management-api\n      description: \"Unified REST API for Akamai API Security management workflows.\"\n \
  \     resources:\n        - path: /v1/configurations\n          name: configurations\n          description: \"API security configuration management\"\n          operations:\n            - method: GET\n              name: list-configurations\n              description: \"List all API security configurations\"\n              call: \"akamai-api-security.list-configs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-configuration\n              description: \"Create a new API security configuration\"\n              call: \"akamai-api-security.create-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Security policy management\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List\
  \ security policies\"\n              call: \"akamai-api-security.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-discovery\n          name: api-discovery\n          description: \"API inventory and discovery\"\n          operations:\n            - method: GET\n              name: get-api-discovery\n              description: \"Get API discovery results\"\n              call: \"akamai-api-security.get-api-discovery\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activations\n          name: activations\n          description: \"Configuration activations\"\n          operations:\n            - method: GET\n              name: list-activations\n              description: \"List configuration activations\"\n              call: \"akamai-api-security.list-activations\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-security-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Akamai API Security management.\"\n      tools:\n        - name: list-security-configurations\n          description: \"List all Akamai API Security configurations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-api-security.list-configs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-security-configuration\n          description: \"Create a new Akamai API Security configuration\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"akamai-api-security.create-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-security-policies\n          description: \"List security\
  \ policies within a configuration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-api-security.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-apis\n          description: \"Get API inventory including shadow and zombie API findings\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-api-security.get-api-discovery\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-activation-status\n          description: \"List and check status of security configuration activations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-api-security.list-activations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/akamai-api-security/refs/heads/main/capabilities/api-security-management.yaml
tags:
- Akamai
- API Security
- Posture Management
- Runtime Protection
- Security Automation
tools:
- description: List all Akamai API Security configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-security-configurations
- description: Create a new Akamai API Security configuration
  hints:
    destructive: false
    readOnly: false
  name: create-security-configuration
- description: List security policies within a configuration
  hints:
    openWorld: true
    readOnly: true
  name: list-security-policies
- description: Get API inventory including shadow and zombie API findings
  hints:
    openWorld: true
    readOnly: true
  name: discover-apis
- description: List and check status of security configuration activations
  hints:
    openWorld: true
    readOnly: true
  name: check-activation-status
---
