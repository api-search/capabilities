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
- linux
- enterprise
- get manifest security
- create a new container repository.
- delete an openshift cluster.
- quay
- list clusters
- image vulnerability scanning.
- openshift versions.
- get details of a specific cluster.
- available cloud providers.
- image tags.
- openshift clusters.
- cloud
- get container repository details.
- container image repositories.
- list machine pools
- list available cluster add-ons.
- list cloud providers
- list all managed clusters.
- list addons
- create a new cluster.
- open source
- get vulnerability scan results.
- list available cloud providers.
- list cloud providers.
- list repository tags
- list container repositories.
- create a new openshift cluster.
- list repositories
- containers
- list cluster subscriptions.
- openshift
- list machine pools.
- get vulnerability scan results for a container image.
- list image tags.
- list container image repositories.
- delete cluster
- list openshift versions.
- list machine pools for a cluster.
- hybrid cloud
- list tags for a container image.
- cluster machine pools.
- get cluster
- create repository
- delete a cluster.
- create a container repository.
- red hat
- get repository
- list subscriptions
- kubernetes
- get cluster details.
- platform engineering
- list versions
- create cluster
- list available openshift versions.
- list all managed openshift clusters.
- specific cluster operations.
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
