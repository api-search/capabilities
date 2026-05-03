---
categories: []
consumed_apis:
- outposts
description: Workflow capability composing Amazon Outposts APIs for developers and operators.
layout: capability
name: Amazon Outposts API Workflow
operations:
- description: List Amazon Outposts resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Outposts
provider_slug: amazon-outposts
search_terms:
- hybrid cloud
- list openapi.yml
- amazon outposts
- Developer
- on-premises
- list amazon outposts resources
- list resources
- core api workflow
- developer using amazon outposts apis
- edge computing
- aws
- infrastructure
- primary amazon outposts resources
- list and manage openapi.yml resources
slug: amazon-outposts-workflow
source_filename: amazon-outposts-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Outposts API Workflow\n  description: Workflow capability composing Amazon Outposts APIs for developers and operators.\n  tags:\n  - Amazon Outposts\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: outposts\n    location: ./shared/outposts.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-outposts-api\n    description: Unified REST API for Amazon Outposts.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Outposts resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Outposts resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-outposts-mcp\n    transport: http\n \
  \   description: MCP server for AI-assisted Amazon Outposts operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-outposts/refs/heads/main/capabilities/amazon-outposts-workflow.yaml
tags:
- Amazon Outposts
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
