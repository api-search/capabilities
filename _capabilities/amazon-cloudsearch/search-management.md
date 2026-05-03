---
categories: []
consumed_apis:
- cloudsearch
description: Workflow for search domain management using Amazon CloudSearch for Application Developer personas.
layout: capability
name: Amazon CloudSearch Search Domain Management
operations: []
personas: []
provider_name: Amazon CloudSearch
provider_slug: amazon-cloudsearch
search_terms:
- Application Developer
- full-text search
- search
- amazon cloudsearch
- managed
- cloudsearch
- amazon web services
slug: search-management
source_filename: search-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudSearch Search Domain Management\"\n  description: \"Workflow for search domain management using Amazon CloudSearch for Application Developer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudSearch\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudsearch\n      location: ./shared/cloudsearch.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudsearch-workflow-api\n      description: \"Unified REST API for Amazon CloudSearch search domain management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudsearch-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudSearch search domain management.\"\
  \n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudsearch/refs/heads/main/capabilities/search-management.yaml
tags:
- Amazon Web Services
- Amazon CloudSearch
tools: []
---
