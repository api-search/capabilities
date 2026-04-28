---
categories: []
consumed_apis: []
description: Workflow capability for managing FinSpace environments, kdb clusters, databases, and users for financial analytics.
layout: capability
name: Amazon FinSpace Financial Analytics
operations: []
personas: []
provider_name: Amazon FinSpace
provider_slug: amazon-finspace
search_terms:
- tick data
- financial services
- kdb
- data analytics
- financial analytics
- aws
- data management
- capital markets
- market data
slug: amazon-finspace-financial-analytics
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon FinSpace Financial Analytics\n  description: Workflow capability for managing FinSpace environments, kdb clusters, databases, and users for financial analytics.\n  tags:\n  - Financial Analytics\n  - Kdb\n  - AWS\n  - Tick Data\n  - Market Data\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: finspace\n    ref: capabilities/shared/finspace.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: createEnvironment\n    description: Create a new FinSpace environment\n    inputSchema:\n      type: object\n      properties:\n        name:\n          type: string\n        description:\n          type: string\n        kmsKeyId:\n          type: string\n        federationMode:\n          type: string\n      required:\n      - name\n  - name: listEnvironments\n\
  \    description: List all FinSpace environments in the account\n    inputSchema:\n      type: object\n      properties: {}\n  - name: getEnvironment\n    description: Get details for a specific FinSpace environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n      required:\n      - environmentId\n  - name: updateEnvironment\n    description: Update a FinSpace environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        name:\n          type: string\n        description:\n          type: string\n      required:\n      - environmentId\n  - name: deleteEnvironment\n    description: Delete a FinSpace environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n      required:\n      - environmentId\n  - name: createKxEnvironment\n    description: Create a managed kdb environment\n    inputSchema:\n      type:\
  \ object\n      properties:\n        name:\n          type: string\n        kmsKeyId:\n          type: string\n        description:\n          type: string\n      required:\n      - name\n      - kmsKeyId\n  - name: listKxEnvironments\n    description: List all kdb environments\n    inputSchema:\n      type: object\n      properties: {}\n  - name: getKxEnvironment\n    description: Get a kdb environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n      required:\n      - environmentId\n  - name: createKxCluster\n    description: Create a cluster in a kdb environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        clusterName:\n          type: string\n        clusterType:\n          type: string\n        capacityConfiguration:\n          type: object\n        releaseLabel:\n          type: string\n        azMode:\n          type: string\n      required:\n     \
  \ - environmentId\n      - clusterName\n      - clusterType\n      - capacityConfiguration\n      - releaseLabel\n      - azMode\n  - name: listKxClusters\n    description: List clusters in a kdb environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n      required:\n      - environmentId\n  - name: getKxCluster\n    description: Get details for a kdb cluster\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        clusterName:\n          type: string\n      required:\n      - environmentId\n      - clusterName\n  - name: deleteKxCluster\n    description: Delete a kdb cluster\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        clusterName:\n          type: string\n      required:\n      - environmentId\n      - clusterName\n  - name: createKxDatabase\n    description: Create a kdb database in an environment\n\
  \    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        databaseName:\n          type: string\n        description:\n          type: string\n      required:\n      - environmentId\n      - databaseName\n  - name: listKxDatabases\n    description: List kdb databases in an environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n      required:\n      - environmentId\n  - name: createKxUser\n    description: Create a user in a kdb environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type: string\n        userName:\n          type: string\n        iamRole:\n          type: string\n      required:\n      - environmentId\n      - userName\n      - iamRole\n  - name: listKxUsers\n    description: List users in a kdb environment\n    inputSchema:\n      type: object\n      properties:\n        environmentId:\n          type:\
  \ string\n      required:\n      - environmentId\n  - name: listTagsForResource\n    description: List tags for a FinSpace resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n      required:\n      - resourceArn\n  - name: tagResource\n    description: Add tags to a FinSpace resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n        tags:\n          type: object\n      required:\n      - resourceArn\n      - tags\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-finspace/refs/heads/main/capabilities/amazon-finspace-financial-analytics.yaml
tags:
- Financial Analytics
- Kdb
- AWS
- Tick Data
- Market Data
tools: []
---
