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
- amazon elasticache create replication group
- describeCacheClusters
- memcached
- amazon elasticache describe replication groups
- redis
- operations teams managing amazon elasticache infrastructure
- amazon elasticache create cache cluster
- developers building applications using amazon elasticache
- in-memory caching service supporting redis and memcached
- amazon web services
- database
- elasticache
- unified capability for managing amazon elasticache resources. combines amazon elasticache apis for backend developer workflows in data caching.
- caching
- amazon elasticache delete cache cluster
- createCacheCluster
- createReplicationGroup
- describeReplicationGroups
- deleteCacheCluster
- aws
- in-memory
- amazon elasticache describe cache clusters
slug: amazon-elasticache-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon ElastiCache Management\n  description: Unified capability for managing Amazon ElastiCache resources. Combines Amazon ElastiCache APIs for Backend Developer workflows in Data Caching.\n  tags:\n  - Amazon Web Services\n  - Caching\n  - Database\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: elasticache\n    location: ./shared/elasticache.yaml\n  exposes:\n  - type: rest\n    port: 8186\n    namespace: amazon-elasticache-workflow-api\n    description: Unified REST API for Amazon ElastiCache management.\n    resources:\n    - path: /v1/describeCacheClusters\n      name: describeCacheClusters\n      description: Amazon ElastiCache Describe Cache Clusters\n      operations:\n      - method: GET\n        name: describeCacheClusters\n        description: Amazon ElastiCache Describe Cache Clusters\n   \
  \     call: api.describeCacheClusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/createCacheCluster\n      name: createCacheCluster\n      description: Amazon ElastiCache Create Cache Cluster\n      operations:\n      - method: POST\n        name: createCacheCluster\n        description: Amazon ElastiCache Create Cache Cluster\n        call: api.createCacheCluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deleteCacheCluster\n      name: deleteCacheCluster\n      description: Amazon ElastiCache Delete Cache Cluster\n      operations:\n      - method: POST\n        name: deleteCacheCluster\n        description: Amazon ElastiCache Delete Cache Cluster\n        call: api.deleteCacheCluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/createReplicationGroup\n      name: createReplicationGroup\n      description: Amazon ElastiCache Create Replication\
  \ Group\n      operations:\n      - method: POST\n        name: createReplicationGroup\n        description: Amazon ElastiCache Create Replication Group\n        call: api.createReplicationGroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeReplicationGroups\n      name: describeReplicationGroups\n      description: Amazon ElastiCache Describe Replication Groups\n      operations:\n      - method: GET\n        name: describeReplicationGroups\n        description: Amazon ElastiCache Describe Replication Groups\n        call: api.describeReplicationGroups\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9196\n    namespace: amazon-elasticache-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon ElastiCache management.\n    tools:\n    - name: describeCacheClusters\n      description: Amazon ElastiCache Describe Cache Clusters\n      hints:\n        readOnly: true\n\
  \      call: api.describeCacheClusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createCacheCluster\n      description: Amazon ElastiCache Create Cache Cluster\n      hints:\n        readOnly: false\n      call: api.createCacheCluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteCacheCluster\n      description: Amazon ElastiCache Delete Cache Cluster\n      hints:\n        readOnly: false\n      call: api.deleteCacheCluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createReplicationGroup\n      description: Amazon ElastiCache Create Replication Group\n      hints:\n        readOnly: false\n      call: api.createReplicationGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeReplicationGroups\n      description: Amazon ElastiCache Describe Replication Groups\n      hints:\n        readOnly: true\n      call: api.describeReplicationGroups\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elasticache/refs/heads/main/capabilities/amazon-elasticache-capability.yaml
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
