---
categories: []
consumed_apis:
- msk
description: Workflow capability for Amazon MSK media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MSK Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MSK
provider_slug: amazon-msk
search_terms:
- broadcasting
- batchdisassociatescramsecret
- aws media processing and delivery
- manage media processing jobs
- media
- developer building media processing applications
- create cluster
- list configurations
- workflow
- list scram secrets
- media processing
- create cluster v2
- amazon msk media processing workflow
- aws
- Media Developer
- list jobs
- list clusters
- createclusterv2
- listconfigurations
- batch disassociate scram secret
- listscramsecrets
- batch associate scram secret
- Broadcast Engineer
- listclustersv2
- engineer managing broadcast media workflows
- createcluster
- batchassociatescramsecret
- list clusters v2
- listclusters
slug: amazon-msk-media-workflow
source_filename: amazon-msk-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MSK Workflow\n  description: Workflow capability for Amazon MSK media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: msk\n    location: ./shared/msk.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: msk-workflow-api\n    description: Unified REST API for Amazon MSK workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: msk.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: msk-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MSK workflow management.\n    tools:\n    - name: list-scram-secrets\n      description: ListScramSecrets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: msk.list-scram-secrets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-associate-scram-secret\n      description: BatchAssociateScramSecret\n      hints:\n        readOnly: false\n        openWorld: true\n      call: msk.batch-associate-scram-secret\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-disassociate-scram-secret\n      description: BatchDisassociateScramSecret\n      hints:\n        readOnly: false\n        openWorld: true\n      call: msk.batch-disassociate-scram-secret\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clusters\n      description: ListClusters\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: msk.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: CreateCluster\n      hints:\n        readOnly: false\n        openWorld: true\n      call: msk.create-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clusters-v2\n      description: ListClustersV2\n      hints:\n        readOnly: true\n        openWorld: true\n      call: msk.list-clusters-v2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster-v2\n      description: CreateClusterV2\n      hints:\n        readOnly: false\n        openWorld: true\n      call: msk.create-cluster-v2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configurations\n      description: ListConfigurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ msk.list-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-msk/refs/heads/main/capabilities/amazon-msk-media-workflow.yaml
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: ListScramSecrets
  hints:
    openWorld: true
    readOnly: true
  name: list-scram-secrets
- description: BatchAssociateScramSecret
  hints:
    openWorld: true
    readOnly: false
  name: batch-associate-scram-secret
- description: BatchDisassociateScramSecret
  hints:
    openWorld: true
    readOnly: false
  name: batch-disassociate-scram-secret
- description: ListClusters
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: CreateCluster
  hints:
    openWorld: true
    readOnly: false
  name: create-cluster
- description: ListClustersV2
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters-v2
- description: CreateClusterV2
  hints:
    openWorld: true
    readOnly: false
  name: create-cluster-v2
- description: ListConfigurations
  hints:
    openWorld: true
    readOnly: true
  name: list-configurations
---
