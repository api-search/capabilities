---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Lake Formation combining resource management and operations.
layout: capability
name: Amazon Lake Formation Workflow
operations: []
personas: []
provider_name: Amazon Lake Formation
provider_slug: amazon-lake-formation
search_terms:
- Administrator
- aws
- lists the resources registered as managed by lake formation.
- workflow
- retrieves the current data access role for the given resource registered in lake formation.
- analytics
- Developer
- resources register resource
- integrates api into applications
- amazon lake formation
- data governance
- manages resources and configurations
- resources list resources
- data lake
- access control
- registers an amazon s3 path as a data lake location managed by lake formation.
- unified workflow for amazon lake formation resource management
- resources describe resource
- s3
slug: amazon-lake-formation-workflow
source_filename: amazon-lake-formation-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Lake Formation Workflow\n  description: Unified workflow capability for Amazon Lake Formation combining resource management and operations.\n  tags:\n  - Amazon Lake Formation\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: lake-formation\n    baseUri: https://lakeformation.us-east-1.amazonaws.com\n    description: Amazon Lake Formation service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: resources\n      path: /resources\n      description: Data lake resource management\n      operations:\n      - name: registerresource\n        method: POST\n        description: Registers an Amazon S3 path as a data lake location\
  \ managed by Lake Formation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listresources\n        method: GET\n        description: Lists the resources registered as managed by Lake Formation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describeresource\n        method: GET\n        description: Retrieves the current data access role for the given resource registered in Lake Formation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lake-formation-api\n    description: REST API for Amazon Lake Formation workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lake-formation-mcp\n    transport: http\n    description: MCP server for Amazon Lake\
  \ Formation.\n    tools:\n    - name: resources-register-resource\n      description: Registers an Amazon S3 path as a data lake location managed by Lake Formation.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lake-formation.registerresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resources-list-resources\n      description: Lists the resources registered as managed by Lake Formation.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lake-formation.listresources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resources-describe-resource\n      description: Retrieves the current data access role for the given resource registered in Lake Formation.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lake-formation.describeresource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lake-formation/refs/heads/main/capabilities/amazon-lake-formation-workflow.yaml
tags:
- Amazon Lake Formation
- Workflow
tools:
- description: Registers an Amazon S3 path as a data lake location managed by Lake Formation.
  hints:
    idempotent: false
    readOnly: false
  name: resources-register-resource
- description: Lists the resources registered as managed by Lake Formation.
  hints:
    idempotent: true
    readOnly: true
  name: resources-list-resources
- description: Retrieves the current data access role for the given resource registered in Lake Formation.
  hints:
    idempotent: true
    readOnly: true
  name: resources-describe-resource
---
