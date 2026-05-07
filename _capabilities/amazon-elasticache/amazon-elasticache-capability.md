---
categories: []
consumed_apis: []
description: Amazon ElastiCache is a fully managed in-memory caching service supporting Redis and Memcached for improving the performance of web applications.
layout: capability
name: Amazon ElastiCache API
operations:
- description: Amazon ElastiCache Create Cache Cluster
  method: POST
  name: createcachecluster
  path: /
- description: Amazon ElastiCache Describe Cache Clusters
  method: GET
  name: describecacheclusters
  path: /
- description: Amazon ElastiCache Delete Cache Cluster
  method: POST
  name: deletecachecluster
  path: /#DeleteCacheCluster
- description: Amazon ElastiCache Create Replication Group
  method: POST
  name: createreplicationgroup
  path: /#CreateReplicationGroup
- description: Amazon ElastiCache Describe Replication Groups
  method: GET
  name: describereplicationgroups
  path: /#DescribeReplicationGroups
personas: []
provider_name: Amazon ElastiCache
provider_slug: amazon-elasticache
search_terms:
- elasticache
- amazon web services
- deletecachecluster
- api
- amazon
- developers building applications using amazon elasticache
- amazon elasticache create cache cluster
- amazon elasticache create replication group
- describecacheclusters
- describereplicationgroups
- amazon elasticache describe replication groups
- in-memory caching service supporting redis and memcached
- in-memory
- redis
- database
- memcached
- unified capability for managing amazon elasticache resources. combines amazon elasticache apis for backend developer workflows in data caching.
- createreplicationgroup
- createcachecluster
- caching
- amazon elasticache delete cache cluster
- operations teams managing amazon elasticache infrastructure
- amazon elasticache describe cache clusters
slug: amazon-elasticache-capability
source_filename: amazon-elasticache-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon ElastiCache API\n  description: Amazon ElastiCache is a fully managed in-memory caching service supporting Redis and Memcached for improving\n    the performance of web applications.\n  tags:\n  - Amazon\n  - Elasticache\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-elasticache\n    baseUri: https://elasticache.amazonaws.com\n    description: Amazon ElastiCache API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_ELASTICACHE_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: createcachecluster\n        method: POST\n        description: Amazon ElastiCache Create Cache Cluster\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describecacheclusters\n        method: GET\n        description: Amazon ElastiCache Describe Cache Clusters\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        - name: CacheClusterId\n          in: query\n          type: string\n          description: The user-supplied cluster identifier.\n        - name: ShowCacheNodeInfo\n          in: query\n          type: boolean\n          description: If true, lists individual cache node information.\n        - name: MaxRecords\n          in: query\n          type: integer\n          description: The maximum number of records to include in the response.\n        - name: Marker\n       \
  \   in: query\n          type: string\n          description: An optional marker returned from a prior request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deletecachecluster\n      path: /#DeleteCacheCluster\n      operations:\n      - name: deletecachecluster\n        method: POST\n        description: Amazon ElastiCache Delete Cache Cluster\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: createreplicationgroup\n      path: /#CreateReplicationGroup\n      operations:\n      - name: createreplicationgroup\n        method: POST\n        description: Amazon ElastiCache Create Replication Group\n\
  \        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describereplicationgroups\n      path: /#DescribeReplicationGroups\n      operations:\n      - name: describereplicationgroups\n        method: GET\n        description: Amazon ElastiCache Describe Replication Groups\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        - name: ReplicationGroupId\n          in: query\n          type: string\n          description: The identifier for the replication group to describe.\n        - name: MaxRecords\n          in: query\n\
  \          type: integer\n          description: The maximum number of records to include in the response.\n        - name: Marker\n          in: query\n          type: string\n          description: An optional marker returned from a prior request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-elasticache-rest\n    description: REST adapter for Amazon ElastiCache API.\n    resources:\n    - path: /\n      name: createcachecluster\n      operations:\n      - method: POST\n        name: createcachecluster\n        description: Amazon ElastiCache Create Cache Cluster\n        call: amazon-elasticache.createcachecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /\n      name: describecacheclusters\n      operations:\n      - method: GET\n        name: describecacheclusters\n        description: Amazon\
  \ ElastiCache Describe Cache Clusters\n        call: amazon-elasticache.describecacheclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#DeleteCacheCluster\n      name: deletecachecluster\n      operations:\n      - method: POST\n        name: deletecachecluster\n        description: Amazon ElastiCache Delete Cache Cluster\n        call: amazon-elasticache.deletecachecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#CreateReplicationGroup\n      name: createreplicationgroup\n      operations:\n      - method: POST\n        name: createreplicationgroup\n        description: Amazon ElastiCache Create Replication Group\n        call: amazon-elasticache.createreplicationgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#DescribeReplicationGroups\n      name: describereplicationgroups\n      operations:\n      - method: GET\n        name: describereplicationgroups\n\
  \        description: Amazon ElastiCache Describe Replication Groups\n        call: amazon-elasticache.describereplicationgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-elasticache-mcp\n    transport: http\n    description: MCP adapter for Amazon ElastiCache API for AI agent use.\n    tools:\n    - name: createcachecluster\n      description: Amazon ElastiCache Create Cache Cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elasticache.createcachecluster\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describecacheclusters\n\
  \      description: Amazon ElastiCache Describe Cache Clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elasticache.describecacheclusters\n      with:\n        Action: tools.Action\n        Version: tools.Version\n        CacheClusterId: tools.CacheClusterId\n        ShowCacheNodeInfo: tools.ShowCacheNodeInfo\n        MaxRecords: tools.MaxRecords\n        Marker: tools.Marker\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      - name: CacheClusterId\n        type: string\n        description: The user-supplied cluster identifier.\n      - name: ShowCacheNodeInfo\n        type: boolean\n        description: If true, lists individual cache node information.\n      - name: MaxRecords\n        type: integer\n        description: The maximum number\
  \ of records to include in the response.\n      - name: Marker\n        type: string\n        description: An optional marker returned from a prior request.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecachecluster\n      description: Amazon ElastiCache Delete Cache Cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elasticache.deletecachecluster\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreplicationgroup\n      description: Amazon ElastiCache Create Replication Group\n      hints:\n        readOnly: false\n        destructive: false\n      \
  \  idempotent: false\n      call: amazon-elasticache.createreplicationgroup\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describereplicationgroups\n      description: Amazon ElastiCache Describe Replication Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elasticache.describereplicationgroups\n      with:\n        Action: tools.Action\n        Version: tools.Version\n        ReplicationGroupId: tools.ReplicationGroupId\n        MaxRecords: tools.MaxRecords\n        Marker: tools.Marker\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required:\
  \ true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      - name: ReplicationGroupId\n        type: string\n        description: The identifier for the replication group to describe.\n      - name: MaxRecords\n        type: integer\n        description: The maximum number of records to include in the response.\n      - name: Marker\n        type: string\n        description: An optional marker returned from a prior request.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_ELASTICACHE_TOKEN: AMAZON_ELASTICACHE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elasticache/refs/heads/main/capabilities/amazon-elasticache-capability.yaml
tags:
- Amazon
- Elasticache
- API
tools:
- description: Amazon ElastiCache Create Cache Cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcachecluster
- description: Amazon ElastiCache Describe Cache Clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describecacheclusters
- description: Amazon ElastiCache Delete Cache Cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletecachecluster
- description: Amazon ElastiCache Create Replication Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreplicationgroup
- description: Amazon ElastiCache Describe Replication Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describereplicationgroups
---
