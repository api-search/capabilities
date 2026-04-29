---
categories: []
consumed_apis:
- memorydb
description: Workflow capability for Amazon MemoryDB media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MemoryDB Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MemoryDB
provider_slug: amazon-memorydb
search_terms:
- amazon memorydb deletecluster
- aws media processing and delivery
- amazon memorydb updateacl
- Media Developer
- delete acl
- media
- delete cluster
- Broadcast Engineer
- list jobs
- workflow
- amazon memorydb createcluster
- amazon memorydb describeacls
- manage media processing jobs
- describe clusters
- amazon memorydb media processing workflow
- aws
- amazon memorydb updatecluster
- engineer managing broadcast media workflows
- amazon memorydb describeclusters
- developer building media processing applications
- create acl
- amazon memorydb deleteacl
- amazon memorydb createacl
- describe ac ls
- update acl
- broadcasting
- media processing
- update cluster
- create cluster
slug: amazon-memorydb-media-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MemoryDB Workflow\n  description: Workflow capability for Amazon MemoryDB media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: memorydb\n    location: ./shared/memorydb.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: memorydb-workflow-api\n    description: Unified REST API for Amazon MemoryDB workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: memorydb.list-jobs\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: memorydb-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MemoryDB workflow management.\n    tools:\n    - name: describe-ac-ls\n      description: Amazon MemoryDB DescribeACLs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: memorydb.describe-ac-ls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-acl\n      description: Amazon MemoryDB CreateACL\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.create-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-acl\n      description: Amazon MemoryDB UpdateACL\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.update-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-acl\n      description: Amazon MemoryDB DeleteACL\n      hints:\n\
  \        readOnly: false\n        openWorld: true\n      call: memorydb.delete-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-clusters\n      description: Amazon MemoryDB DescribeClusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: memorydb.describe-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Amazon MemoryDB CreateCluster\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.create-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-cluster\n      description: Amazon MemoryDB UpdateCluster\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.update-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Amazon MemoryDB DeleteCluster\n      hints:\n      \
  \  readOnly: false\n        openWorld: true\n      call: memorydb.delete-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-memorydb/refs/heads/main/capabilities/amazon-memorydb-media-workflow.yaml
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: Amazon MemoryDB DescribeACLs
  hints:
    openWorld: true
    readOnly: true
  name: describe-ac-ls
- description: Amazon MemoryDB CreateACL
  hints:
    openWorld: true
    readOnly: false
  name: create-acl
- description: Amazon MemoryDB UpdateACL
  hints:
    openWorld: true
    readOnly: false
  name: update-acl
- description: Amazon MemoryDB DeleteACL
  hints:
    openWorld: true
    readOnly: false
  name: delete-acl
- description: Amazon MemoryDB DescribeClusters
  hints:
    openWorld: true
    readOnly: true
  name: describe-clusters
- description: Amazon MemoryDB CreateCluster
  hints:
    openWorld: true
    readOnly: false
  name: create-cluster
- description: Amazon MemoryDB UpdateCluster
  hints:
    openWorld: true
    readOnly: false
  name: update-cluster
- description: Amazon MemoryDB DeleteCluster
  hints:
    openWorld: true
    readOnly: false
  name: delete-cluster
---
