---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Quicksight. Enables automation of Amazon Quicksight resources for cloud operations teams.
layout: capability
name: Amazon Quicksight Operations
operations:
- description: List Amazon Quicksight resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon QuickSight
provider_slug: amazon-quicksight
search_terms:
- visualization
- analytics
- list resources
- aws cloud resource management
- cloud operations
- bi
- dashboards
- aws
- reporting
- engineer managing amazon quicksight resources
- automation workflow for amazon quicksight
- amazon quicksight
- business intelligence
- machine learning
- list amazon quicksight resources
- amazon quicksight resources
slug: amazon-quicksight
source_filename: amazon-quicksight.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Quicksight Operations\n  description: Workflow capability for Amazon Quicksight. Enables automation of Amazon Quicksight resources for cloud operations\n    teams.\n  tags:\n  - Amazon Quicksight\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-quicksight\n    baseUri: https://quicksight.{region}.amazonaws.com\n    description: Amazon QuickSight API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: accounts\n      path: /accounts/{AwsAccountId}/dashboards\n      description: accounts operations\n      operations:\n      - name: ListDashboards\n        method: GET\n        description: Amazon QuickSight List dashboards\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: DescribeDashboard\n        method: GET\n        description: Amazon QuickSight Describe a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListDataSets\n        method: GET\n        description: Amazon QuickSight List datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-quicksight-api\n    description: Unified REST API for Amazon Quicksight operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Quicksight resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Quicksight resources\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-quicksight-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Quicksight operations.\n    tools:\n    - name: list-amazon-quicksight-resources\n      description: List Amazon Quicksight resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-quicksight/refs/heads/main/capabilities/amazon-quicksight.yaml
tags:
- Amazon Quicksight
- Cloud Operations
tools:
- description: List Amazon Quicksight resources
  hints:
    readOnly: true
  name: list-amazon-quicksight-resources
---
