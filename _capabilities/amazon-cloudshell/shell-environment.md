---
categories: []
consumed_apis:
- cloudshell
description: Workflow for cloud shell environment management using Amazon CloudShell for Cloud Administrator personas.
layout: capability
name: Amazon CloudShell Cloud Shell Environment Management
operations: []
personas: []
provider_name: Amazon CloudShell
provider_slug: amazon-cloudshell
search_terms:
- cloudshell
- aws
- cli
- terminal
- amazon cloudshell
- browser-based
- Cloud Administrator
- amazon web services
slug: shell-environment
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudShell Cloud Shell Environment Management\"\n  description: \"Workflow for cloud shell environment management using Amazon CloudShell for Cloud Administrator personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudShell\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudshell\n      location: ./shared/cloudshell.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudshell-workflow-api\n      description: \"Unified REST API for Amazon CloudShell cloud shell environment management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudshell-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudShell\
  \ cloud shell environment management.\"\n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudshell/refs/heads/main/capabilities/shell-environment.yaml
tags:
- Amazon Web Services
- Amazon CloudShell
tools: []
---
