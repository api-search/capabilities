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
- amazon documentdb create db cluster
- describe db clusters
- amazon documentdb
- database
- amazon documentdb describe db instances
- createDBCluster
- create db cluster
- engineers managing amazon documentdb resources on aws.
- documentdb
- deleteDBCluster
- amazon documentdb delete db cluster
- managed database
- amazon documentdb create db instance
- createDBInstance
- describeDBClusters
- amazon documentdb describe db clusters
- describeDBInstances
- document database
- database administration business domain for amazon documentdb.
- create db instance
- aws
- workflow capability for database administration.
- mongodb
- delete db cluster
- describe db instances
- amazon web services
- nosql
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
