---
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
- list clusters v2
- broadcasting
- amazon msk media processing workflow
- list configurations
- workflow
- create cluster v2
- batch associate scram secret
- list jobs
- Media Developer
- list clusters
- Broadcast Engineer
- listclustersv2
- batchdisassociatescramsecret
- batchassociatescramsecret
- aws media processing and delivery
- listconfigurations
- media processing
- aws
- create cluster
- list scram secrets
- manage media processing jobs
- createclusterv2
- createcluster
- engineer managing broadcast media workflows
- batch disassociate scram secret
- developer building media processing applications
- media
- listclusters
- listscramsecrets
slug: amazon-msk-media-workflow
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
