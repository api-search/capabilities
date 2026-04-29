---
categories: []
consumed_apis:
- cloudformation
description: Workflow for infrastructure as code deployment using Amazon CloudFormation for DevOps Engineer personas.
layout: capability
name: Amazon CloudFormation Infrastructure as Code Deployment
operations: []
personas: []
provider_name: Amazon CloudFormation
provider_slug: amazon-cloudformation
search_terms:
- cloudformation
- DevOps Engineer
- iac
- infrastructure as code
- amazon cloudformation
- amazon web services
- devops
- aws
slug: infrastructure-as-code
source_filename: infrastructure-as-code.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudFormation Infrastructure as Code Deployment\"\n  description: \"Workflow for infrastructure as code deployment using Amazon CloudFormation for DevOps Engineer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudFormation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudformation\n      location: ./shared/cloudformation.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudformation-workflow-api\n      description: \"Unified REST API for Amazon CloudFormation infrastructure as code deployment.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudformation-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Amazon CloudFormation infrastructure as code deployment.\"\n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudformation/refs/heads/main/capabilities/infrastructure-as-code.yaml
tags:
- Amazon Web Services
- Amazon CloudFormation
tools: []
---
