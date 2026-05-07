---
categories: []
consumed_apis: []
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
- amazon memorydb describeacls
- delete acl
- update cluster
- describe ac ls
- developer building media processing applications
- amazon memorydb updateacl
- amazon memorydb deleteacl
- delete cluster
- engineer managing broadcast media workflows
- Media Developer
- amazon memorydb media processing workflow
- workflow
- create acl
- amazon memorydb updatecluster
- describe clusters
- amazon memorydb createcluster
- amazon memorydb createacl
- aws media processing and delivery
- list jobs
- manage media processing jobs
- media
- create cluster
- media processing
- aws
- broadcasting
- Broadcast Engineer
- update acl
- amazon memorydb deletecluster
- amazon memorydb describeclusters
slug: amazon-memorydb-media-workflow
source_filename: amazon-memorydb-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon MemoryDB Workflow\n  description: Workflow capability for Amazon MemoryDB media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: memorydb\n    baseUri: https://memory-db.us-east-1.amazonaws.com\n    description: Amazon MemoryDB REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon MemoryDB resources\n      operations:\n      - name: describe-ac-ls\n        method: GET\n        description: Amazon MemoryDB DescribeACLs\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-acl\n        method: POST\n        description: Amazon MemoryDB CreateACL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: update-acl\n        method: PUT\n        description: Amazon MemoryDB UpdateACL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-acl\n        method: DELETE\n        description: Amazon MemoryDB DeleteACL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-clusters\n        method: GET\n        description: Amazon MemoryDB DescribeClusters\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Amazon MemoryDB CreateCluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: update-cluster\n        method: PUT\n        description: Amazon MemoryDB UpdateCluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-cluster\n        method: DELETE\n        description: Amazon MemoryDB DeleteCluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-engine-versions\n        method: GET\n    \
  \    description: Amazon MemoryDB DescribeEngineVersions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-events\n        method: GET\n        description: Amazon MemoryDB DescribeEvents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-allowed-node-type-updates\n        method: GET\n        description: Amazon MemoryDB ListAllowedNodeTypeUpdates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-parameter-groups\n        method: GET\n        description: Amazon MemoryDB DescribeParameterGroups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-parameter-group\n        method: POST\n        description:\
  \ Amazon MemoryDB CreateParameterGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: update-parameter-group\n        method: PUT\n        description: Amazon MemoryDB UpdateParameterGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-parameter-group\n        method: DELETE\n        description: Amazon MemoryDB DeleteParameterGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-reserved-nodes\n        method: GET\n        description: Amazon MemoryDB DescribeReservedNodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: purchase-reserved-nodes-offering\n        method: POST\n        description: Amazon MemoryDB PurchaseReservedNodesOffering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: describe-reserved-nodes-offerings\n        method: GET\n        description: Amazon MemoryDB DescribeReservedNodesOfferings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: failover-shard\n        method: POST\n        description: Amazon MemoryDB FailoverShard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: describe-snapshots\n        method: GET\n        description: Amazon MemoryDB DescribeSnapshots\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-snapshot\n        method: POST\n        description: Amazon MemoryDB CreateSnapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-snapshot\n        method: DELETE\n        description: Amazon MemoryDB DeleteSnapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: copy-snapshot\n        method: POST\n        description: Amazon MemoryDB CopySnapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: describe-subnet-groups\n        method: GET\n \
  \       description: Amazon MemoryDB DescribeSubnetGroups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subnet-group\n        method: POST\n        description: Amazon MemoryDB CreateSubnetGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: update-subnet-group\n        method: PUT\n        description: Amazon MemoryDB UpdateSubnetGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-subnet-group\n        method: DELETE\n        description: Amazon MemoryDB DeleteSubnetGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: list-tags\n        method: GET\n        description: Amazon MemoryDB ListTags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tag-resource\n        method: POST\n        description: Amazon MemoryDB TagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: untag-resource\n        method: DELETE\n        description: Amazon MemoryDB UntagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-users\n        method: GET\n        description: Amazon MemoryDB DescribeUsers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ create-user\n        method: POST\n        description: Amazon MemoryDB CreateUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: update-user\n        method: PUT\n        description: Amazon MemoryDB UpdateUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-user\n        method: DELETE\n        description: Amazon MemoryDB DeleteUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: memorydb-workflow-api\n    description: Unified REST API for Amazon MemoryDB workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description:\
  \ Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: memorydb.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: memorydb-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MemoryDB workflow management.\n    tools:\n    - name: describe-ac-ls\n      description: Amazon MemoryDB DescribeACLs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: memorydb.describe-ac-ls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-acl\n      description: Amazon MemoryDB CreateACL\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.create-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-acl\n      description: Amazon MemoryDB UpdateACL\n      hints:\n        readOnly:\
  \ false\n        openWorld: true\n      call: memorydb.update-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-acl\n      description: Amazon MemoryDB DeleteACL\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.delete-acl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-clusters\n      description: Amazon MemoryDB DescribeClusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: memorydb.describe-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Amazon MemoryDB CreateCluster\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.create-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-cluster\n      description: Amazon MemoryDB UpdateCluster\n      hints:\n        readOnly: false\n        openWorld:\
  \ true\n      call: memorydb.update-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Amazon MemoryDB DeleteCluster\n      hints:\n        readOnly: false\n        openWorld: true\n      call: memorydb.delete-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-memorydb/refs/heads/main/capabilities/amazon-memorydb-media-workflow.yaml
tags:
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
