---
categories: []
consumed_apis:
- keyspaces
description: Unified workflow capability for Amazon Keyspaces combining resource management and operations.
layout: capability
name: Amazon Keyspaces Workflow
operations: []
personas: []
provider_name: Amazon Keyspaces
provider_slug: amazon-keyspaces
search_terms:
- keyspaces get keyspace
- nosql
- tables list tables
- tables get table
- workflow
- keyspaces create keyspace
- returns information about the table.
- keyspaces list keyspaces
- returns a list of tables for a specified keyspace.
- database
- cassandra
- unified workflow for amazon keyspaces resource management
- amazon keyspaces
- creates a new keyspace.
- tables create table
- manages resources and configurations
- integrates api into applications
- wide column
- returns a list of keyspaces.
- aws
- returns the name and the amazon resource name (arn) of a keyspace.
- Developer
- Administrator
- managed database
- the createtable operation adds a new table to the specified keyspace.
slug: amazon-keyspaces-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Keyspaces Workflow\n  description: Unified workflow capability for Amazon Keyspaces combining resource management and operations.\n  tags:\n  - Amazon Keyspaces\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: keyspaces\n    location: ./shared/keyspaces.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: keyspaces-api\n    description: REST API for Amazon Keyspaces workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: keyspaces-mcp\n    transport: http\n    description: MCP server for Amazon Keyspaces.\n    tools:\n    - name: keyspaces-create-keyspace\n      description: Creates a new keyspace.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: keyspaces.createkeyspace\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: keyspaces-list-keyspaces\n      description: Returns a list of keyspaces.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: keyspaces.listkeyspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keyspaces-get-keyspace\n      description: Returns the name and the Amazon Resource Name (ARN) of a keyspace.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: keyspaces.getkeyspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tables-create-table\n      description: The CreateTable operation adds a new table to the specified keyspace.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: keyspaces.createtable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tables-list-tables\n      description: Returns a list of tables for a specified keyspace.\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: keyspaces.listtables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tables-get-table\n      description: Returns information about the table.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: keyspaces.gettable\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-keyspaces/refs/heads/main/capabilities/amazon-keyspaces-workflow.yaml
tags:
- Amazon Keyspaces
- AWS
- Workflow
tools:
- description: Creates a new keyspace.
  hints:
    idempotent: false
    readOnly: false
  name: keyspaces-create-keyspace
- description: Returns a list of keyspaces.
  hints:
    idempotent: true
    readOnly: true
  name: keyspaces-list-keyspaces
- description: Returns the name and the Amazon Resource Name (ARN) of a keyspace.
  hints:
    idempotent: true
    readOnly: true
  name: keyspaces-get-keyspace
- description: The CreateTable operation adds a new table to the specified keyspace.
  hints:
    idempotent: false
    readOnly: false
  name: tables-create-table
- description: Returns a list of tables for a specified keyspace.
  hints:
    idempotent: true
    readOnly: true
  name: tables-list-tables
- description: Returns information about the table.
  hints:
    idempotent: true
    readOnly: true
  name: tables-get-table
---
