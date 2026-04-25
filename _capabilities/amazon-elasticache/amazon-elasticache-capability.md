---
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
- in-memory
- elasticache
- describeReplicationGroups
- amazon web services
- in-memory caching service supporting redis and memcached
- describeCacheClusters
- database
- caching
- unified capability for managing amazon elasticache resources. combines amazon elasticache apis for backend developer workflows in data caching.
- createReplicationGroup
- developers building applications using amazon elasticache
- redis
- createCacheCluster
- memcached
- amazon elasticache describe replication groups
- operations teams managing amazon elasticache infrastructure
- aws
- amazon elasticache create replication group
- deleteCacheCluster
- amazon elasticache create cache cluster
- amazon elasticache describe cache clusters
- amazon elasticache delete cache cluster
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
