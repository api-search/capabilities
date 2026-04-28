---
categories: []
consumed_apis:
- personalize
description: Workflow capability composing Amazon Personalize APIs for developers and operators.
layout: capability
name: Amazon Personalize API Workflow
operations:
- description: List Amazon Personalize resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Personalize
provider_slug: amazon-personalize
search_terms:
- amazon personalize
- Developer
- machine learning
- aws
- ai
- list openapi.yml
- developer using amazon personalize apis
- recommendations
- core api workflow
- list amazon personalize resources
- personalization
- ml
- list and manage openapi.yml resources
- primary amazon personalize resources
- customer experience
- list resources
slug: amazon-personalize-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Personalize API Workflow\n  description: Workflow capability composing Amazon Personalize APIs for developers and operators.\n  tags:\n  - Amazon Personalize\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: personalize\n    location: ./shared/personalize.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-personalize-api\n    description: Unified REST API for Amazon Personalize.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Personalize resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Personalize resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-personalize-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Amazon Personalize operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-personalize/refs/heads/main/capabilities/amazon-personalize-workflow.yaml
tags:
- Amazon Personalize
- AWS
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
