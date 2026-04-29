---
categories: []
consumed_apis:
- cloudtrail
description: Workflow for audit trail management using Amazon CloudTrail for Security Analyst personas.
layout: capability
name: Amazon CloudTrail Audit Trail Management
operations: []
personas: []
provider_name: Amazon CloudTrail
provider_slug: amazon-cloudtrail
search_terms:
- compliance
- audit
- amazon cloudtrail
- security
- governance
- cloudtrail
- aws
- amazon web services
- Security Analyst
slug: audit-trail-management
source_filename: audit-trail-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudTrail Audit Trail Management\"\n  description: \"Workflow for audit trail management using Amazon CloudTrail for Security Analyst personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudTrail\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudtrail\n      location: ./shared/cloudtrail.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudtrail-workflow-api\n      description: \"Unified REST API for Amazon CloudTrail audit trail management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudtrail-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudTrail audit trail management.\"\n      tools:\
  \ []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudtrail/refs/heads/main/capabilities/audit-trail-management.yaml
tags:
- Amazon Web Services
- Amazon CloudTrail
tools: []
---
