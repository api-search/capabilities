---
categories: []
consumed_apis: []
description: Unified workflow capability for AWS Lake Formation combining resource management and operations.
layout: capability
name: AWS Lake Formation Workflow
operations: []
personas: []
provider_name: AWS Lake Formation
provider_slug: amazon-lakeformation
search_terms:
- manages resources and configurations
- unified workflow for aws lake formation resource management
- databases get database
- databases list databases
- aws
- lists all the registered databases in the data catalog.
- Administrator
- integrates api into applications
- data lake
- creates a new database in the data catalog.
- databases create database
- governance
- workflow
- aws lake formation
- retrieves the definition of a specified database.
- analytics
- Developer
slug: amazon-lakeformation-workflow
source_filename: amazon-lakeformation-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Lake Formation Workflow\n  description: Unified workflow capability for AWS Lake Formation combining resource management and operations.\n  tags:\n  - AWS Lake Formation\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: lakeformation\n    baseUri: https://lakeformation.us-east-1.amazonaws.com\n    description: AWS Lake Formation service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: databases\n      path: /databases\n      description: Data Catalog database management\n      operations:\n      - name: createdatabase\n        method: POST\n        description: Creates a new database in the Data Catalog.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdatabase\n        method: GET\n        description: Retrieves the definition of a specified database.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listdatabases\n        method: GET\n        description: Lists all the registered databases in the Data Catalog.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lakeformation-api\n    description: REST API for AWS Lake Formation workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lakeformation-mcp\n    transport: http\n    description: MCP server for AWS Lake Formation.\n    tools:\n    - name: databases-create-database\n      description: Creates a new database in the\
  \ Data Catalog.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lakeformation.createdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: databases-get-database\n      description: Retrieves the definition of a specified database.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lakeformation.getdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: databases-list-databases\n      description: Lists all the registered databases in the Data Catalog.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lakeformation.listdatabases\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lakeformation/refs/heads/main/capabilities/amazon-lakeformation-workflow.yaml
tags:
- AWS Lake Formation
- Workflow
tools:
- description: Creates a new database in the Data Catalog.
  hints:
    idempotent: false
    readOnly: false
  name: databases-create-database
- description: Retrieves the definition of a specified database.
  hints:
    idempotent: true
    readOnly: true
  name: databases-get-database
- description: Lists all the registered databases in the Data Catalog.
  hints:
    idempotent: true
    readOnly: true
  name: databases-list-databases
---
