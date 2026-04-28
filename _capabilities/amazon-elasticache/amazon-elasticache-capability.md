---
categories: []
consumed_apis:
- elasticache
description: Unified capability for managing Amazon ElastiCache resources. Combines Amazon ElastiCache APIs for Backend Developer workflows in Data Caching.
layout: capability
name: Amazon ElastiCache Management
operations:
- description: Amazon ElastiCache Describe Cache Clusters
  method: GET
  name: describeCacheClusters
  path: /v1/describeCacheClusters
- description: Amazon ElastiCache Create Cache Cluster
  method: POST
  name: createCacheCluster
  path: /v1/createCacheCluster
- description: Amazon ElastiCache Delete Cache Cluster
  method: POST
  name: deleteCacheCluster
  path: /v1/deleteCacheCluster
- description: Amazon ElastiCache Create Replication Group
  method: POST
  name: createReplicationGroup
  path: /v1/createReplicationGroup
- description: Amazon ElastiCache Describe Replication Groups
  method: GET
  name: describeReplicationGroups
  path: /v1/describeReplicationGroups
personas: []
provider_name: Amazon ElastiCache
provider_slug: amazon-elasticache
search_terms:
- describeCacheClusters
- caching
- in-memory caching service supporting redis and memcached
- amazon elasticache create cache cluster
- describeReplicationGroups
- amazon elasticache create replication group
- developers building applications using amazon elasticache
- amazon web services
- in-memory
- aws
- deleteCacheCluster
- redis
- amazon elasticache describe replication groups
- unified capability for managing amazon elasticache resources. combines amazon elasticache apis for backend developer workflows in data caching.
- amazon elasticache delete cache cluster
- database
- createReplicationGroup
- amazon elasticache describe cache clusters
- elasticache
- createCacheCluster
- memcached
- operations teams managing amazon elasticache infrastructure
slug: amazon-elasticache-capability
tags:
- Amazon Web Services
- Caching
- Database
tools:
- description: Amazon ElastiCache Describe Cache Clusters
  hints:
    readOnly: true
  name: describeCacheClusters
- description: Amazon ElastiCache Create Cache Cluster
  hints:
    readOnly: false
  name: createCacheCluster
- description: Amazon ElastiCache Delete Cache Cluster
  hints:
    readOnly: false
  name: deleteCacheCluster
- description: Amazon ElastiCache Create Replication Group
  hints:
    readOnly: false
  name: createReplicationGroup
- description: Amazon ElastiCache Describe Replication Groups
  hints:
    readOnly: true
  name: describeReplicationGroups
---
