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
- list scram secrets
- listscramsecrets
- createcluster
- aws media processing and delivery
- batchdisassociatescramsecret
- listconfigurations
- workflow
- create cluster
- list clusters
- developer building media processing applications
- list configurations
- Broadcast Engineer
- media processing
- batch associate scram secret
- broadcasting
- listclustersv2
- list jobs
- create cluster v2
- media
- engineer managing broadcast media workflows
- Media Developer
- listclusters
- aws
- createclusterv2
- batchassociatescramsecret
- batch disassociate scram secret
- list clusters v2
- manage media processing jobs
- amazon msk media processing workflow
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
