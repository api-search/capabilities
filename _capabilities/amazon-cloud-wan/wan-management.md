---
categories: []
consumed_apis:
- cloudwan
description: Workflow for wan management using Amazon Cloud WAN for Network Engineer personas.
layout: capability
name: Amazon Cloud WAN WAN Management
operations: []
personas: []
provider_name: Amazon Cloud WAN
provider_slug: amazon-cloud-wan
search_terms:
- networking
- amazon cloud wan
- aws
- Network Engineer
- cloud wan
- wide area network
- sd-wan
- amazon web services
slug: wan-management
source_filename: wan-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Cloud WAN WAN Management\"\n  description: \"Workflow for wan management using Amazon Cloud WAN for Network Engineer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon Cloud WAN\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudwan\n      location: ./shared/cloud-wan.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudwan-workflow-api\n      description: \"Unified REST API for Amazon Cloud WAN wan management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudwan-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Cloud WAN wan management.\"\n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloud-wan/refs/heads/main/capabilities/wan-management.yaml
tags:
- Amazon Web Services
- Amazon Cloud WAN
tools: []
---
