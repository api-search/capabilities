---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Rds. Enables automation of Amazon Rds resources for cloud operations teams.
layout: capability
name: Amazon Rds Operations
operations:
- description: List Amazon Rds resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon RDS
provider_slug: amazon-rds
search_terms:
- managed databases
- list resources
- engineer managing amazon rds resources
- cloud operations
- aws cloud resource management
- amazon rds
- aws
- dbaas
- cloud databases
- list amazon rds resources
- relational databases
- amazon rds resources
- database service
- automation workflow for amazon rds
slug: amazon-rds
source_filename: amazon-rds.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Rds Operations\n  description: Workflow capability for Amazon Rds. Enables automation of Amazon Rds resources for cloud operations teams.\n  tags:\n  - Amazon Rds\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-rds\n    baseUri: https://rds.{region}.amazonaws.com\n    description: Amazon RDS API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: ?Action=CreateDBInstance\n      path: /?Action=CreateDBInstance\n      description: ?Action=CreateDBInstance operations\n      operations:\n      - name: createDBInstance\n        method: GET\n        description: Amazon RDS Create a new DB instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: ?Action=DescribeDBInstances\n      path: /?Action=DescribeDBInstances\n      description: ?Action=DescribeDBInstances operations\n      operations:\n      - name: describeDBInstances\n        method: GET\n        description: Amazon RDS Describe DB instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=ModifyDBInstance\n      path: /?Action=ModifyDBInstance\n      description: ?Action=ModifyDBInstance operations\n      operations:\n      - name: modifyDBInstance\n        method: GET\n        description: Amazon RDS Modify a DB instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeleteDBInstance\n      path: /?Action=DeleteDBInstance\n      description: ?Action=DeleteDBInstance operations\n      operations:\n      - name: deleteDBInstance\n\
  \        method: GET\n        description: Amazon RDS Delete a DB instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=RebootDBInstance\n      path: /?Action=RebootDBInstance\n      description: ?Action=RebootDBInstance operations\n      operations:\n      - name: rebootDBInstance\n        method: GET\n        description: Amazon RDS Reboot a DB instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=CreateDBSnapshot\n      path: /?Action=CreateDBSnapshot\n      description: ?Action=CreateDBSnapshot operations\n      operations:\n      - name: createDBSnapshot\n        method: GET\n        description: Amazon RDS Create a DB snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeDBSnapshots\n\
  \      path: /?Action=DescribeDBSnapshots\n      description: ?Action=DescribeDBSnapshots operations\n      operations:\n      - name: describeDBSnapshots\n        method: GET\n        description: Amazon RDS Describe DB snapshots\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeleteDBSnapshot\n      path: /?Action=DeleteDBSnapshot\n      description: ?Action=DeleteDBSnapshot operations\n      operations:\n      - name: deleteDBSnapshot\n        method: GET\n        description: Amazon RDS Delete a DB snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=CreateDBCluster\n      path: /?Action=CreateDBCluster\n      description: ?Action=CreateDBCluster operations\n      operations:\n      - name: createDBCluster\n        method: GET\n        description: Amazon RDS Create a new DB cluster\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeDBClusters\n      path: /?Action=DescribeDBClusters\n      description: ?Action=DescribeDBClusters operations\n      operations:\n      - name: describeDBClusters\n        method: GET\n        description: Amazon RDS Describe DB clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeleteDBCluster\n      path: /?Action=DeleteDBCluster\n      description: ?Action=DeleteDBCluster operations\n      operations:\n      - name: deleteDBCluster\n        method: GET\n        description: Amazon RDS Delete a DB cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeDBEngineVersions\n      path: /?Action=DescribeDBEngineVersions\n   \
  \   description: ?Action=DescribeDBEngineVersions operations\n      operations:\n      - name: describeDBEngineVersions\n        method: GET\n        description: Amazon RDS Describe DB engine versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-rds-api\n    description: Unified REST API for Amazon Rds operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Rds resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Rds resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-rds-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Rds operations.\n    tools:\n    - name: list-amazon-rds-resources\n      description: List Amazon Rds\
  \ resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-rds/refs/heads/main/capabilities/amazon-rds.yaml
tags:
- Amazon Rds
- Cloud Operations
tools:
- description: List Amazon Rds resources
  hints:
    readOnly: true
  name: list-amazon-rds-resources
---
