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
- list openshift versions.
- create a container repository.
- get repository
- openshift versions.
- container image repositories.
- list image tags.
- get vulnerability scan results for a container image.
- list available cloud providers.
- list clusters
- image vulnerability scanning.
- get manifest security
- enterprise
- quay
- available cloud providers.
- list addons
- openshift
- list cloud providers
- list repository tags
- list container image repositories.
- list all managed clusters.
- cluster machine pools.
- get cluster details.
- get container repository details.
- delete an openshift cluster.
- list tags for a container image.
- get cluster
- cloud
- list container repositories.
- list machine pools.
- list all managed openshift clusters.
- list available cluster add-ons.
- platform engineering
- list machine pools for a cluster.
- list available openshift versions.
- image tags.
- specific cluster operations.
- create a new container repository.
- containers
- kubernetes
- list cloud providers.
- create repository
- hybrid cloud
- list versions
- create cluster
- create a new openshift cluster.
- get vulnerability scan results.
- openshift clusters.
- delete a cluster.
- list machine pools
- list subscriptions
- linux
- create a new cluster.
- red hat
- delete cluster
- list cluster subscriptions.
- open source
- list repositories
- get details of a specific cluster.
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
