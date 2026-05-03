---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Shardingsphere Workflow
operations: []
personas: []
provider_name: Apache ShardingSphere
provider_slug: apache-shardingsphere
search_terms:
- developer using shardingsphere transparent sharding
- sharding
- engineer deploying shardingsphere proxy
- database
- configure database sharding and read-write splitting
- open source
- dba managing distributed database topology
- horizontal scaling and data distribution across databases
- apache
- read-write splitting
- register databases and physical data sources
- sql
- transparent sql routing and federation
- distributed sql
slug: shardingsphere-workflow
source_filename: shardingsphere-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache ShardingSphere Distributed SQL Workflow\ndescription: Workflow capability for managing distributed databases, sharding rules, and read-write splitting in Apache ShardingSphere.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache ShardingSphere REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-shardingsphere/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/shardingsphere-api.yaml\nworkflow:\n  name: shardingsphere-workflow\n  description: Configure and manage distributed database sharding, read-write splitting, and data sources.\n  steps:\n    - name: create-database\n      description: Register a logical database\n      api: Apache ShardingSphere REST API\n      operation: createDatabase\n    - name: add-data-source\n      description: Register physical data sources\n      api: Apache ShardingSphere REST API\n      operation: addDataSource\n    - name: get-sharding-rules\n      description: Review sharding configuration\n   \
  \   api: Apache ShardingSphere REST API\n      operation: getShardingRules\n    - name: get-readwrite-splitting-rules\n      description: Review read-write splitting configuration\n      api: Apache ShardingSphere REST API\n      operation: getReadwriteSplittingRules\n    - name: get-cluster-status\n      description: Monitor cluster health\n      api: Apache ShardingSphere REST API\n      operation: getClusterStatus\nexposes:\n  - type: rest\n    port: 3307\n    paths:\n      - /databases\n      - /databases/{databaseName}\n      - /databases/{databaseName}/data-sources\n      - /databases/{databaseName}/rules/sharding\n      - /databases/{databaseName}/rules/readwrite-splitting\n      - /cluster/status\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-databases\n        description: List logical databases\n        operation: listDatabases\n      - name: create-database\n        description: Create a logical database\n        operation: createDatabase\n      - name: list-data-sources\n\
  \        description: List data sources\n        operation: listDataSources\n      - name: add-data-source\n        description: Add a data source\n        operation: addDataSource\n      - name: get-sharding-rules\n        description: Get sharding rules\n        operation: getShardingRules\n      - name: get-readwrite-splitting-rules\n        description: Get read-write splitting rules\n        operation: getReadwriteSplittingRules\n      - name: get-cluster-status\n        description: Get cluster status\n        operation: getClusterStatus\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-shardingsphere/refs/heads/main/capabilities/shardingsphere-workflow.yaml
tags: []
tools: []
---
