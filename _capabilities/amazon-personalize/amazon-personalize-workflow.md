---
categories: []
consumed_apis: []
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
- developer using amazon personalize apis
- list resources
- list and manage openapi.yml resources
- ml
- aws
- core api workflow
- machine learning
- list amazon personalize resources
- amazon personalize
- recommendations
- list openapi.yml
- primary amazon personalize resources
- ai
- customer experience
- Developer
- personalization
slug: amazon-personalize-workflow
source_filename: amazon-personalize-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Personalize API Workflow\n  description: Workflow capability composing Amazon Personalize APIs for developers and operators.\n  tags:\n  - Amazon Personalize\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - type: http\n    namespace: openapi.yml\n    baseUri: https://personalize.{region}.amazonaws.com\n    description: The Amazon Personalize API enables you to create, manage, and deploy personalization models. You can\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_AUTH}}'\n      placement: header\n    resources:\n    - name: datasets\n      path: /datasets\n      description: Datasets operations for Amazon Personalize API\n      operations:\n      - name: CreateDatasetGroup\n        method: POST\n        description: Amazon Personalize Create a Dataset Group\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-personalize-api\n    description: Unified REST API for Amazon Personalize.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Personalize resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Personalize resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-personalize-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Personalize operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-personalize/refs/heads/main/capabilities/amazon-personalize-workflow.yaml
tags:
- Amazon Personalize
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
