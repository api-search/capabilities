---
consumed_apis:
- openshift-cluster-manager
- quay
description: Unified workflow for managing OpenShift clusters and Quay container registries. Used by platform engineers and DevOps teams to provision clusters, manage machine pools, and maintain container image repositories.
layout: capability
name: Red Hat Platform Management
operations:
- description: List all managed clusters.
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new cluster.
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: Get cluster details.
  method: GET
  name: get-cluster
  path: /v1/clusters/{cluster_id}
- description: Delete a cluster.
  method: DELETE
  name: delete-cluster
  path: /v1/clusters/{cluster_id}
- description: List machine pools.
  method: GET
  name: list-machine-pools
  path: /v1/clusters/{cluster_id}/machine-pools
- description: List cloud providers.
  method: GET
  name: list-cloud-providers
  path: /v1/cloud-providers
- description: List OpenShift versions.
  method: GET
  name: list-versions
  path: /v1/versions
- description: List container repositories.
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: Create a container repository.
  method: POST
  name: create-repository
  path: /v1/repositories
- description: List image tags.
  method: GET
  name: list-repository-tags
  path: /v1/repositories/{repository}/tags
- description: Get vulnerability scan results.
  method: GET
  name: get-manifest-security
  path: /v1/repositories/{repository}/manifests/{manifestref}/security
personas: []
provider_name: Red Hat
provider_slug: red-hat
search_terms:
- list addons
- list cloud providers.
- delete cluster
- list container repositories.
- create a container repository.
- list clusters
- enterprise
- containers
- openshift clusters.
- kubernetes
- specific cluster operations.
- create a new cluster.
- create a new openshift cluster.
- list all managed openshift clusters.
- list machine pools for a cluster.
- linux
- list cluster subscriptions.
- list cloud providers
- list repository tags
- list image tags.
- list subscriptions
- list machine pools
- delete a cluster.
- image tags.
- container image repositories.
- get vulnerability scan results.
- platform engineering
- cluster machine pools.
- get details of a specific cluster.
- get container repository details.
- list machine pools.
- get cluster details.
- list versions
- list repositories
- get manifest security
- available cloud providers.
- list openshift versions.
- delete an openshift cluster.
- get vulnerability scan results for a container image.
- red hat
- list all managed clusters.
- list container image repositories.
- quay
- list available cloud providers.
- hybrid cloud
- list tags for a container image.
- cloud
- create cluster
- image vulnerability scanning.
- get cluster
- create a new container repository.
- list available openshift versions.
- create repository
- openshift
- get repository
- open source
- list available cluster add-ons.
- openshift versions.
slug: platform-management
tags:
- Red Hat
- OpenShift
- Quay
- Platform Engineering
tools:
- description: List all managed OpenShift clusters.
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Get details of a specific cluster.
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster
- description: Create a new OpenShift cluster.
  hints:
    readOnly: false
  name: create-cluster
- description: Delete an OpenShift cluster.
  hints:
    destructive: true
    readOnly: false
  name: delete-cluster
- description: List machine pools for a cluster.
  hints:
    readOnly: true
  name: list-machine-pools
- description: List available cloud providers.
  hints:
    readOnly: true
  name: list-cloud-providers
- description: List available OpenShift versions.
  hints:
    readOnly: true
  name: list-versions
- description: List available cluster add-ons.
  hints:
    readOnly: true
  name: list-addons
- description: List cluster subscriptions.
  hints:
    readOnly: true
  name: list-subscriptions
- description: List container image repositories.
  hints:
    openWorld: true
    readOnly: true
  name: list-repositories
- description: Get container repository details.
  hints:
    idempotent: true
    readOnly: true
  name: get-repository
- description: Create a new container repository.
  hints:
    readOnly: false
  name: create-repository
- description: List tags for a container image.
  hints:
    readOnly: true
  name: list-repository-tags
- description: Get vulnerability scan results for a container image.
  hints:
    readOnly: true
  name: get-manifest-security
---
