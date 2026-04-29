---
categories: []
consumed_apis:
- cloud9
description: Workflow for development environment management using Amazon Cloud9 for Software Developer personas.
layout: capability
name: Amazon Cloud9 Development Environment Management
operations: []
personas: []
provider_name: Amazon Cloud9
provider_slug: amazon-cloud9
search_terms:
- cloud9
- aws
- ide
- development
- Software Developer
- browser-based
- amazon web services
- amazon cloud9
slug: development-environment
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Cloud9 Development Environment Management\"\n  description: \"Workflow for development environment management using Amazon Cloud9 for Software Developer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon Cloud9\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloud9\n      location: ./shared/cloud9.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloud9-workflow-api\n      description: \"Unified REST API for Amazon Cloud9 development environment management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloud9-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Cloud9 development environment management.\"\
  \n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloud9/refs/heads/main/capabilities/development-environment.yaml
tags:
- Amazon Web Services
- Amazon Cloud9
tools: []
---
