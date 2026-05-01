---
api_specs:
- filename: amazon-route53-resolver-openapi.yml
  format: yaml
  label: amazon-route53-resolver
  slug: amazon-route53-resolver
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-route53-resolver/refs/heads/main/openapi/amazon-route53-resolver-openapi.yml
categories: []
consumed_apis:
- amazon-route53-resolver
description: Workflow capability for Amazon Route53 Resolver. Enables automation of Amazon Route53 Resolver resources for cloud operations teams.
layout: capability
name: Amazon Route53 Resolver Operations
operations:
- description: List Amazon Route53 Resolver resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Route 53 Resolver
provider_slug: amazon-route53-resolver
search_terms:
- cloud operations
- amazon route53 resolver
- list amazon route53 resolver resources
- aws cloud resource management
- list resources
- amazon route53 resolver resources
- aws
- hybrid cloud
- dns
- networking
- engineer managing amazon route53 resolver resources
- automation workflow for amazon route53 resolver
slug: amazon-route53-resolver
source_filename: amazon-route53-resolver.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Route53 Resolver Operations\n  description: Workflow capability for Amazon Route53 Resolver. Enables automation of Amazon Route53 Resolver resources for cloud operations teams.\n  tags:\n  - Amazon Route53 Resolver\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-route53-resolver\n    location: ./shared/amazon-route53-resolver.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-route53-resolver-api\n    description: Unified REST API for Amazon Route53 Resolver operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Route53 Resolver resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Route53 Resolver resources\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-route53-resolver-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Route53 Resolver operations.\n    tools:\n    - name: list-amazon-route53-resolver-resources\n      description: List Amazon Route53 Resolver resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-route53-resolver/refs/heads/main/capabilities/amazon-route53-resolver.yaml
tags:
- Amazon Route53 Resolver
- AWS
- Cloud Operations
tools:
- description: List Amazon Route53 Resolver resources
  hints:
    readOnly: true
  name: list-amazon-route53-resolver-resources
---
