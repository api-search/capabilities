---
categories: []
consumed_apis:
- lakeformation
description: Unified workflow capability for AWS Lake Formation combining resource management and operations.
layout: capability
name: AWS Lake Formation Workflow
operations: []
personas: []
provider_name: AWS Lake Formation
provider_slug: amazon-lakeformation
search_terms:
- data lake
- analytics
- aws lake formation
- creates a new database in the data catalog.
- databases create database
- unified workflow for aws lake formation resource management
- manages resources and configurations
- Administrator
- governance
- databases list databases
- Developer
- workflow
- aws
- integrates api into applications
- retrieves the definition of a specified database.
- databases get database
- lists all the registered databases in the data catalog.
slug: amazon-lakeformation-workflow
source_filename: amazon-lakeformation-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: AWS Lake Formation Workflow\n  description: Unified workflow capability for AWS Lake Formation combining resource management and operations.\n  tags:\n  - AWS Lake Formation\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: lakeformation\n    location: ./shared/lakeformation.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lakeformation-api\n    description: REST API for AWS Lake Formation workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lakeformation-mcp\n    transport: http\n    description: MCP server for AWS Lake Formation.\n    tools:\n    - name: databases-create-database\n      description: Creates a new database in the Data Catalog.\n      hints:\n        readOnly: false\n        idempotent: false\n\
  \      call: lakeformation.createdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: databases-get-database\n      description: Retrieves the definition of a specified database.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lakeformation.getdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: databases-list-databases\n      description: Lists all the registered databases in the Data Catalog.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lakeformation.listdatabases\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lakeformation/refs/heads/main/capabilities/amazon-lakeformation-workflow.yaml
tags:
- AWS Lake Formation
- AWS
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
