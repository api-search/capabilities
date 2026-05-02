---
categories: []
consumed_apis:
- documentdb
description: Unified capability for managing DocumentDB clusters, instances, and snapshots for DevOps and database administrators.
layout: capability
name: Amazon DocumentDB Document Database Management
operations:
- description: Amazon DocumentDB Describe DB Clusters
  method: GET
  name: describeDBClusters
  path: /v1/resource
- description: Amazon DocumentDB Create DB Cluster
  method: POST
  name: createDBCluster
  path: /v1/resource
- description: Amazon DocumentDB Delete DB Cluster
  method: POST
  name: deleteDBCluster
  path: /v1/#DeleteDBCluster
- description: Amazon DocumentDB Create DB Instance
  method: POST
  name: createDBInstance
  path: /v1/#CreateDBInstance
- description: Amazon DocumentDB Describe DB Instances
  method: GET
  name: describeDBInstances
  path: /v1/#DescribeDBInstances
personas: []
provider_name: Amazon DocumentDB
provider_slug: amazon-documentdb
search_terms:
- amazon documentdb delete db cluster
- delete db cluster
- amazon documentdb create db cluster
- amazon documentdb create db instance
- amazon documentdb describe db instances
- engineers managing amazon documentdb resources on aws.
- amazon documentdb describe db clusters
- database
- mongodb
- create db cluster
- describeDBClusters
- database administration business domain for amazon documentdb.
- document database
- describeDBInstances
- createDBInstance
- deleteDBCluster
- createDBCluster
- amazon web services
- amazon documentdb
- workflow capability for database administration.
- nosql
- managed database
- describe db clusters
- documentdb
- create db instance
- aws
- describe db instances
slug: documentdb-management
source_filename: documentdb-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon DocumentDB Document Database Management\"\n  description: \"Unified capability for managing DocumentDB clusters, instances, and snapshots for DevOps and database administrators.\"\n  tags:\n    - Amazon DocumentDB\n    - AWS\n    - Database\n    - NoSQL\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: documentdb\n      location: ./shared/documentdb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: documentdb-api\n      description: \"Unified REST API for Document Database Management.\"\n      resources:\n        - path: /v1/resource\n          name: describeDBClusters\n          description: \"Amazon DocumentDB Describe DB Clusters\"\n          operations:\n            - method: GET\n              name: describeDBClusters\n\
  \              description: \"Amazon DocumentDB Describe DB Clusters\"\n              call: \"documentdb.describeDBClusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: createDBCluster\n          description: \"Amazon DocumentDB Create DB Cluster\"\n          operations:\n            - method: POST\n              name: createDBCluster\n              description: \"Amazon DocumentDB Create DB Cluster\"\n              call: \"documentdb.createDBCluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DeleteDBCluster\n          name: deleteDBCluster\n          description: \"Amazon DocumentDB Delete DB Cluster\"\n          operations:\n            - method: POST\n              name: deleteDBCluster\n              description: \"Amazon DocumentDB Delete DB Cluster\"\n              call: \"documentdb.deleteDBCluster\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#CreateDBInstance\n          name: createDBInstance\n          description: \"Amazon DocumentDB Create DB Instance\"\n          operations:\n            - method: POST\n              name: createDBInstance\n              description: \"Amazon DocumentDB Create DB Instance\"\n              call: \"documentdb.createDBInstance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DescribeDBInstances\n          name: describeDBInstances\n          description: \"Amazon DocumentDB Describe DB Instances\"\n          operations:\n            - method: GET\n              name: describeDBInstances\n              description: \"Amazon DocumentDB Describe DB Instances\"\n              call: \"documentdb.describeDBInstances\"\n              outputParameters:\n                - type: object\n                 \
  \ mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: documentdb-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Document Database Management.\"\n      tools:\n        - name: describe-db-clusters\n          description: \"Amazon DocumentDB Describe DB Clusters\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"documentdb.describeDBClusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-db-cluster\n          description: \"Amazon DocumentDB Create DB Cluster\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"documentdb.createDBCluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-db-cluster\n          description: \"Amazon DocumentDB Delete DB Cluster\"\n          hints:\n            readOnly: false\n          \
  \  destructive: false\n          call: \"documentdb.deleteDBCluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-db-instance\n          description: \"Amazon DocumentDB Create DB Instance\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"documentdb.createDBInstance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-db-instances\n          description: \"Amazon DocumentDB Describe DB Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"documentdb.describeDBInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-documentdb/refs/heads/main/capabilities/documentdb-management.yaml
tags:
- Amazon DocumentDB
- Database
- NoSQL
tools:
- description: Amazon DocumentDB Describe DB Clusters
  hints:
    destructive: false
    readOnly: true
  name: describe-db-clusters
- description: Amazon DocumentDB Create DB Cluster
  hints:
    destructive: false
    readOnly: false
  name: create-db-cluster
- description: Amazon DocumentDB Delete DB Cluster
  hints:
    destructive: false
    readOnly: false
  name: delete-db-cluster
- description: Amazon DocumentDB Create DB Instance
  hints:
    destructive: false
    readOnly: false
  name: create-db-instance
- description: Amazon DocumentDB Describe DB Instances
  hints:
    destructive: false
    readOnly: true
  name: describe-db-instances
---
