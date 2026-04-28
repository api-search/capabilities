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
- create cluster v2
- Broadcast Engineer
- batch disassociate scram secret
- manage media processing jobs
- createcluster
- listclustersv2
- create cluster
- aws media processing and delivery
- listscramsecrets
- list clusters
- list scram secrets
- batchassociatescramsecret
- batchdisassociatescramsecret
- media
- Media Developer
- createclusterv2
- list jobs
- listconfigurations
- media processing
- aws
- workflow
- list clusters v2
- developer building media processing applications
- batch associate scram secret
- list configurations
- amazon msk media processing workflow
- engineer managing broadcast media workflows
- listclusters
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
