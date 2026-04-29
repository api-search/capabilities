---
categories:
- monitoring
consumed_apis:
- cloudwatch
description: Workflow for observability and monitoring using Amazon CloudWatch for Operations Engineer personas.
layout: capability
name: Amazon CloudWatch Observability and Monitoring
operations: []
personas: []
provider_name: Amazon CloudWatch
provider_slug: amazon-cloudwatch
search_terms:
- observability
- monitoring
- logs
- aws
- cloudwatch
- amazon cloudwatch
- Operations Engineer
- metrics
- amazon web services
slug: observability
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CloudWatch Observability and Monitoring\"\n  description: \"Workflow for observability and monitoring using Amazon CloudWatch for Operations Engineer personas.\"\n  tags:\n    - Amazon Web Services\n    - Amazon CloudWatch\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudwatch\n      location: ./shared/cloudwatch.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloudwatch-workflow-api\n      description: \"Unified REST API for Amazon CloudWatch observability and monitoring.\"\n      resources: []\n\n    - type: mcp\n      port: 9090\n      namespace: cloudwatch-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon CloudWatch observability and\
  \ monitoring.\"\n      tools: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloudwatch/refs/heads/main/capabilities/observability.yaml
tags:
- Amazon Web Services
- Amazon CloudWatch
tools: []
---
