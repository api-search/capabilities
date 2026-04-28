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
- media processing
- batch associate scram secret
- Broadcast Engineer
- workflow
- createcluster
- broadcasting
- batchdisassociatescramsecret
- list scram secrets
- engineer managing broadcast media workflows
- Media Developer
- batchassociatescramsecret
- list clusters v2
- aws media processing and delivery
- aws
- listconfigurations
- create cluster v2
- manage media processing jobs
- listclusters
- listclustersv2
- list jobs
- amazon msk media processing workflow
- create cluster
- createclusterv2
- list configurations
- listscramsecrets
- list clusters
- media
- developer building media processing applications
- batch disassociate scram secret
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
