---
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
- create db instance
- nosql
- database
- create db cluster
- workflow capability for database administration.
- describeDBClusters
- amazon web services
- document database
- amazon documentdb
- deleteDBCluster
- describe db instances
- amazon documentdb create db cluster
- amazon documentdb delete db cluster
- describeDBInstances
- delete db cluster
- describe db clusters
- amazon documentdb describe db clusters
- mongodb
- engineers managing amazon documentdb resources on aws.
- createDBCluster
- managed database
- documentdb
- amazon documentdb describe db instances
- aws
- createDBInstance
- database administration business domain for amazon documentdb.
- amazon documentdb create db instance
slug: documentdb-management
tags:
- Amazon DocumentDB
- AWS
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
