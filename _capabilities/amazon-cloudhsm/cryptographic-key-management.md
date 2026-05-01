---
categories: []
consumed_apis:
- cloudhsm
description: Workflow for cryptographic key management using Amazon CloudHSM for Security Engineer personas.
layout: capability
name: Amazon CloudHSM Cryptographic Key Management
operations: []
personas: []
provider_name: Amazon CloudHSM
provider_slug: amazon-cloudhsm
search_terms:
- cloudhsm
- amazon cloudhsm
- compliance
- security
- cryptography
- aws
- Security Engineer
- amazon web services
- hsm
slug: cryptographic-key-management
source_filename: cryptographic-key-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudHSM Cryptographic Key Management\"\n  description: \"Workflow for cryptographic key management using Amazon CloudHSM for Security Engineer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudHSM\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudhsm\n      location: ./shared/cloudhsm.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudhsm-workflow-api\n      description: \"Unified REST API for Amazon CloudHSM cryptographic key management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudhsm-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudHSM cryptographic key management.\"\n    \
  \  tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudhsm/refs/heads/main/capabilities/cryptographic-key-management.yaml
tags:
- Amazon Web Services
- Amazon CloudHSM
tools: []
---
