---
categories: []
consumed_apis:
- license-manager
description: Unified workflow capability for Amazon License Manager combining resource management and operations.
layout: capability
name: Amazon License Manager Workflow
operations: []
personas: []
provider_name: Amazon License Manager
provider_slug: amazon-license-manager
search_terms:
- manages resources and configurations
- workflow
- integrates api into applications
- creates a license configuration.
- license configurations get license configuration
- lists the license configurations for your account.
- aws
- gets detailed information about the specified license configuration.
- Developer
- compliance
- amazon license manager
- unified workflow for amazon license manager resource management
- Administrator
- cost management
- license management
- software licensing
- license configurations create license configuratio
- license configurations list license configurations
slug: amazon-license-manager-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon License Manager Workflow\n  description: Unified workflow capability for Amazon License Manager combining resource management and operations.\n  tags:\n  - Amazon License Manager\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: license-manager\n    location: ./shared/license-manager.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: license-manager-api\n    description: REST API for Amazon License Manager workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: license-manager-mcp\n    transport: http\n    description: MCP server for Amazon License Manager.\n    tools:\n    - name: license-configurations-create-license-configuratio\n      description: Creates a license configuration.\n      hints:\n        readOnly:\
  \ false\n        idempotent: false\n      call: license-manager.createlicenseconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: license-configurations-list-license-configurations\n      description: Lists the license configurations for your account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: license-manager.listlicenseconfigurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: license-configurations-get-license-configuration\n      description: Gets detailed information about the specified license configuration.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: license-manager.getlicenseconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-license-manager/refs/heads/main/capabilities/amazon-license-manager-workflow.yaml
tags:
- Amazon License Manager
- AWS
- Workflow
tools:
- description: Creates a license configuration.
  hints:
    idempotent: false
    readOnly: false
  name: license-configurations-create-license-configuratio
- description: Lists the license configurations for your account.
  hints:
    idempotent: true
    readOnly: true
  name: license-configurations-list-license-configurations
- description: Gets detailed information about the specified license configuration.
  hints:
    idempotent: true
    readOnly: true
  name: license-configurations-get-license-configuration
---
