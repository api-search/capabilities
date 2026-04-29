---
categories: []
consumed_apis:
- cloudfront
description: Workflow for content delivery network management using Amazon CloudFront for Platform Engineer personas.
layout: capability
name: Amazon CloudFront Content Delivery Network Management
operations: []
personas: []
provider_name: Amazon CloudFront
provider_slug: amazon-cloudfront
search_terms:
- content delivery
- amazon cloudfront
- cdn
- edge
- Platform Engineer
- amazon web services
- cloudfront
- aws
slug: content-delivery
source_filename: content-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudFront Content Delivery Network Management\"\n  description: \"Workflow for content delivery network management using Amazon CloudFront for Platform Engineer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudFront\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudfront\n      location: ./shared/cloudfront.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudfront-workflow-api\n      description: \"Unified REST API for Amazon CloudFront content delivery network management.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudfront-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudFront\
  \ content delivery network management.\"\n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudfront/refs/heads/main/capabilities/content-delivery.yaml
tags:
- Amazon Web Services
- Amazon CloudFront
tools: []
---
