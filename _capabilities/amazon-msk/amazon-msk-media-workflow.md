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
- Broadcast Engineer
- list clusters v2
- listscramsecrets
- engineer managing broadcast media workflows
- broadcasting
- create cluster v2
- batchdisassociatescramsecret
- Media Developer
- list scram secrets
- manage media processing jobs
- batch associate scram secret
- developer building media processing applications
- list configurations
- listclusters
- createcluster
- workflow
- media processing
- list jobs
- list clusters
- listclustersv2
- amazon msk media processing workflow
- createclusterv2
- listconfigurations
- aws
- aws media processing and delivery
- batchassociatescramsecret
- batch disassociate scram secret
- media
- create cluster
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
