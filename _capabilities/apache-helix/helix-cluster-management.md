---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Helix Cluster Management
operations: []
personas: []
provider_name: Apache Helix
provider_slug: apache-helix
search_terms:
- cluster management
- replication
- distributed systems
- open source
- partitioning
- apache
slug: helix-cluster-management
source_yaml: "name: Apache Helix Cluster Management\ndescription: Workflow capability for managing distributed cluster resources and partition state in Apache Helix\npersona: Platform Engineer\nworkflow:\n  - step: list-clusters\n    name: List Clusters\n    description: Discover all Helix clusters under management\n    capability: helix-rest\n    operation: listClusters\n    server:\n      rest: http://localhost:9100\n      mcp: http://localhost:9090\n\n  - step: get-cluster\n    name: Get Cluster\n    description: Inspect configuration and live instances of a cluster\n    capability: helix-rest\n    operation: getCluster\n    server:\n      rest: http://localhost:9100\n      mcp: http://localhost:9090\n\n  - step: list-resources\n    name: List Resources\n    description: List all managed resources in the cluster\n    capability: helix-rest\n    operation: listResources\n    server:\n      rest: http://localhost:9100\n      mcp: http://localhost:9090\n\n  - step: get-external-view\n  \
  \  name: Get External View\n    description: Check actual partition state assignments for a resource\n    capability: helix-rest\n    operation: getExternalView\n    server:\n      rest: http://localhost:9100\n      mcp: http://localhost:9090\n\ntools:\n  - name: listClusters\n    description: List all Helix clusters\n    server:\n      rest:\n        baseUrl: http://localhost:9100\n        path: /clusters\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listClusters\n        method: POST\n\n  - name: getCluster\n    description: Get cluster configuration and status\n    server:\n      rest:\n        baseUrl: http://localhost:9100\n        path: /clusters/{clusterId}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getCluster\n        method: POST\n\n  - name: listResources\n    description: List resources in a Helix cluster\n    server:\n      rest:\n        baseUrl: http://localhost:9100\n   \
  \     path: /clusters/{clusterId}/resources\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listResources\n        method: POST\n\n  - name: getExternalView\n    description: Get actual partition state assignments\n    server:\n      rest:\n        baseUrl: http://localhost:9100\n        path: /clusters/{clusterId}/resources/{resourceName}/externalView\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getExternalView\n        method: POST\n\n  - name: listInstances\n    description: List instances in a Helix cluster\n    server:\n      rest:\n        baseUrl: http://localhost:9100\n        path: /clusters/{clusterId}/instances\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listInstances\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-helix/refs/heads/main/capabilities/helix-cluster-management.yaml
tags: []
tools: []
---
