---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Shield. Enables automation of Amazon Shield resources for cloud operations teams.
layout: capability
name: Amazon Shield Operations
operations:
- description: List Amazon Shield resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Shield
provider_slug: amazon-shield
search_terms:
- list amazon shield resources
- list resources
- aws cloud resource management
- cloud operations
- ddos protection
- networking
- aws
- amazon shield
- amazon shield resources
- security
- automation workflow for amazon shield
- engineer managing amazon shield resources
slug: amazon-shield
source_filename: amazon-shield.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Shield Operations\n  description: Workflow capability for Amazon Shield. Enables automation of Amazon Shield resources for cloud operations teams.\n  tags:\n  - Amazon Shield\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-shield\n    baseUri: https://shield.us-east-1.amazonaws.com\n    description: Amazon Shield REST API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: ''\n      path: /\n      description: ' operations'\n      operations:\n      - name: createProtection\n        method: POST\n        description: Amazon Shield Create Protection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: '#ListProtections'\n      path: /#ListProtections\n      description: '#ListProtections operations'\n      operations:\n      - name: listProtections\n        method: POST\n        description: Amazon Shield List Protections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '#DescribeProtection'\n      path: /#DescribeProtection\n      description: '#DescribeProtection operations'\n      operations:\n      - name: describeProtection\n        method: POST\n        description: Amazon Shield Describe Protection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '#DescribeAttack'\n      path: /#DescribeAttack\n      description: '#DescribeAttack operations'\n      operations:\n      - name: describeAttack\n        method: POST\n        description: Amazon Shield Describe Attack\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '#CreateSubscription'\n      path: /#CreateSubscription\n      description: '#CreateSubscription operations'\n      operations:\n      - name: createSubscription\n        method: POST\n        description: Amazon Shield Create Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '#DescribeSubscription'\n      path: /#DescribeSubscription\n      description: '#DescribeSubscription operations'\n      operations:\n      - name: describeSubscription\n        method: POST\n        description: Amazon Shield Describe Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '#CreateProtectionGroup'\n      path: /#CreateProtectionGroup\n      description: '#CreateProtectionGroup operations'\n\
  \      operations:\n      - name: createProtectionGroup\n        method: POST\n        description: Amazon Shield Create Protection Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-shield-api\n    description: Unified REST API for Amazon Shield operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Shield resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Shield resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-shield-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Shield operations.\n    tools:\n    - name: list-amazon-shield-resources\n      description: List Amazon Shield resources\n      hints:\n        readOnly:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-shield/refs/heads/main/capabilities/amazon-shield.yaml
tags:
- Amazon Shield
- Cloud Operations
tools:
- description: List Amazon Shield resources
  hints:
    readOnly: true
  name: list-amazon-shield-resources
---
