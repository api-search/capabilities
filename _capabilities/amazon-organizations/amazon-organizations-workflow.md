---
categories: []
consumed_apis:
- organizations
description: Workflow capability composing Amazon Organizations APIs for developers and operators.
layout: capability
name: Amazon Organizations API Workflow
operations:
- description: List Amazon Organizations resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Organizations
provider_slug: amazon-organizations
search_terms:
- list resources
- list and manage openapi.yml resources
- amazon organizations
- multi-account
- Developer
- aws
- organizations
- consolidated billing
- list amazon organizations resources
- developer using amazon organizations apis
- governance
- core api workflow
- account management
- policies
- primary amazon organizations resources
- list openapi.yml
slug: amazon-organizations-workflow
source_filename: amazon-organizations-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Organizations API Workflow\n  description: Workflow capability composing Amazon Organizations APIs for developers and operators.\n  tags:\n  - Amazon Organizations\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: organizations\n    location: ./shared/organizations.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-organizations-api\n    description: Unified REST API for Amazon Organizations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Organizations resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Organizations resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace:\
  \ amazon-organizations-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Organizations operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-organizations/refs/heads/main/capabilities/amazon-organizations-workflow.yaml
tags:
- Amazon Organizations
- AWS
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
