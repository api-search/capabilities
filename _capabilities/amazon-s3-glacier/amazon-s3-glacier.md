---
categories: []
consumed_apis: []
description: Workflow capability for Amazon S3 Glacier. Enables automation of Amazon S3 Glacier resources for cloud operations teams.
layout: capability
name: Amazon S3 Glacier Operations
operations:
- description: List Amazon S3 Glacier resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon S3 Glacier
provider_slug: amazon-s3-glacier
search_terms:
- automation workflow for amazon s3 glacier
- list resources
- list amazon s3 glacier resources
- cloud operations
- aws cloud resource management
- archive
- backup
- aws
- engineer managing amazon s3 glacier resources
- amazon s3 glacier resources
- amazon s3 glacier
- storage
slug: amazon-s3-glacier
source_filename: amazon-s3-glacier.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon S3 Glacier Operations\n  description: Workflow capability for Amazon S3 Glacier. Enables automation of Amazon S3 Glacier resources for cloud operations\n    teams.\n  tags:\n  - Amazon S3 Glacier\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-s3-glacier\n    baseUri: https://glacier.{region}.amazonaws.com\n    description: Amazon S3 Glacier REST API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: accountId\n      path: /{accountId}/vaults\n      description: accountId operations\n      operations:\n      - name: listVaults\n        method: GET\n        description: Amazon S3 Glacier List Vaults\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: describeVault\n        method: GET\n        description: Amazon S3 Glacier Describe Vault\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createVault\n        method: PUT\n        description: Amazon S3 Glacier Create Vault\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteVault\n        method: DELETE\n        description: Amazon S3 Glacier Delete Vault\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadArchive\n        method: POST\n        description: Amazon S3 Glacier Upload Archive\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listJobs\n     \
  \   method: GET\n        description: Amazon S3 Glacier List Jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: initiateJob\n        method: POST\n        description: Amazon S3 Glacier Initiate Job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-s3-glacier-api\n    description: Unified REST API for Amazon S3 Glacier operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon S3 Glacier resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon S3 Glacier resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-s3-glacier-mcp\n    transport: http\n    description: MCP server\
  \ for AI-assisted Amazon S3 Glacier operations.\n    tools:\n    - name: list-amazon-s3-glacier-resources\n      description: List Amazon S3 Glacier resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-s3-glacier/refs/heads/main/capabilities/amazon-s3-glacier.yaml
tags:
- Amazon S3 Glacier
- Cloud Operations
tools:
- description: List Amazon S3 Glacier resources
  hints:
    readOnly: true
  name: list-amazon-s3-glacier-resources
---
