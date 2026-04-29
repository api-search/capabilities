---
categories: []
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
- container image repositories.
- specific cluster operations.
- platform engineering
- list image tags.
- openshift
- get repository
- list available cluster add-ons.
- delete a cluster.
- get vulnerability scan results for a container image.
- openshift clusters.
- list all managed openshift clusters.
- delete an openshift cluster.
- list available openshift versions.
- containers
- image vulnerability scanning.
- red hat
- get container repository details.
- kubernetes
- list all managed clusters.
- create cluster
- list available cloud providers.
- enterprise
- list container image repositories.
- quay
- create a new cluster.
- list machine pools
- list machine pools.
- create repository
- list repositories
- get vulnerability scan results.
- list machine pools for a cluster.
- create a new container repository.
- open source
- get cluster
- image tags.
- list addons
- hybrid cloud
- cluster machine pools.
- list container repositories.
- list versions
- available cloud providers.
- list subscriptions
- openshift versions.
- list cloud providers
- list repository tags
- list openshift versions.
- get cluster details.
- list clusters
- get manifest security
- create a new openshift cluster.
- linux
- get details of a specific cluster.
- list cloud providers.
- list tags for a container image.
- cloud
- list cluster subscriptions.
- delete cluster
- create a container repository.
slug: platform-management
source_filename: platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat Platform Management\"\n  description: \"Unified workflow for managing OpenShift clusters and Quay container registries. Used by platform engineers and DevOps teams to provision clusters, manage machine pools, and maintain container image repositories.\"\n  tags:\n    - Red Hat\n    - OpenShift\n    - Quay\n    - Platform Engineering\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      RED_HAT_BEARER_TOKEN: RED_HAT_BEARER_TOKEN\n      QUAY_BEARER_TOKEN: QUAY_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: openshift-cluster-manager\n      location: ./shared/openshift-cluster-manager.yaml\n    - import: quay\n      location: ./shared/quay.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: platform-management-api\n      description: \"Unified REST API for OpenShift cluster and Quay registry management.\"\n      resources:\n        - path: /v1/clusters\n\
  \          name: clusters\n          description: \"OpenShift clusters.\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all managed clusters.\"\n              call: \"openshift-cluster-manager.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create a new cluster.\"\n              call: \"openshift-cluster-manager.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{cluster_id}\n          name: cluster-detail\n          description: \"Specific cluster operations.\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details.\"\n              call: \"openshift-cluster-manager.get-cluster\"\n\
  \              with:\n                cluster_id: \"rest.cluster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cluster\n              description: \"Delete a cluster.\"\n              call: \"openshift-cluster-manager.delete-cluster\"\n              with:\n                cluster_id: \"rest.cluster_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{cluster_id}/machine-pools\n          name: machine-pools\n          description: \"Cluster machine pools.\"\n          operations:\n            - method: GET\n              name: list-machine-pools\n              description: \"List machine pools.\"\n              call: \"openshift-cluster-manager.list-machine-pools\"\n              with:\n                cluster_id: \"rest.cluster_id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/cloud-providers\n          name: cloud-providers\n          description: \"Available cloud providers.\"\n          operations:\n            - method: GET\n              name: list-cloud-providers\n              description: \"List cloud providers.\"\n              call: \"openshift-cluster-manager.list-cloud-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/versions\n          name: versions\n          description: \"OpenShift versions.\"\n          operations:\n            - method: GET\n              name: list-versions\n              description: \"List OpenShift versions.\"\n              call: \"openshift-cluster-manager.list-versions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories\n          name: repositories\n          description: \"Container image\
  \ repositories.\"\n          operations:\n            - method: GET\n              name: list-repositories\n              description: \"List container repositories.\"\n              call: \"quay.list-repositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-repository\n              description: \"Create a container repository.\"\n              call: \"quay.create-repository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{repository}/tags\n          name: tags\n          description: \"Image tags.\"\n          operations:\n            - method: GET\n              name: list-repository-tags\n              description: \"List image tags.\"\n              call: \"quay.list-repository-tags\"\n              with:\n                repository: \"rest.repository\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{repository}/manifests/{manifestref}/security\n          name: manifest-security\n          description: \"Image vulnerability scanning.\"\n          operations:\n            - method: GET\n              name: get-manifest-security\n              description: \"Get vulnerability scan results.\"\n              call: \"quay.get-manifest-security\"\n              with:\n                repository: \"rest.repository\"\n                manifestref: \"rest.manifestref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: platform-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted OpenShift and Quay management.\"\n      tools:\n        - name: list-clusters\n          description: \"List all managed OpenShift clusters.\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"openshift-cluster-manager.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster\n          description: \"Get details of a specific cluster.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"openshift-cluster-manager.get-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cluster\n          description: \"Create a new OpenShift cluster.\"\n          hints:\n            readOnly: false\n          call: \"openshift-cluster-manager.create-cluster\"\n          with:\n            name: \"tools.name\"\n            cloud_provider: \"tools.cloud_provider\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: delete-cluster\n          description: \"Delete an OpenShift cluster.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"openshift-cluster-manager.delete-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-machine-pools\n          description: \"List machine pools for a cluster.\"\n          hints:\n            readOnly: true\n          call: \"openshift-cluster-manager.list-machine-pools\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cloud-providers\n          description: \"List available cloud providers.\"\n          hints:\n            readOnly: true\n          call: \"openshift-cluster-manager.list-cloud-providers\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-versions\n          description: \"List available OpenShift versions.\"\n          hints:\n            readOnly: true\n          call: \"openshift-cluster-manager.list-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-addons\n          description: \"List available cluster add-ons.\"\n          hints:\n            readOnly: true\n          call: \"openshift-cluster-manager.list-addons\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List cluster subscriptions.\"\n          hints:\n            readOnly: true\n          call: \"openshift-cluster-manager.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-repositories\n          description: \"List container image repositories.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"quay.list-repositories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-repository\n          description: \"Get container repository details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"quay.get-repository\"\n          with:\n            repository: \"tools.repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-repository\n          description: \"Create a new container repository.\"\n          hints:\n            readOnly: false\n          call: \"quay.create-repository\"\n          with:\n            namespace: \"tools.namespace\"\n            repository: \"tools.repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-repository-tags\n      \
  \    description: \"List tags for a container image.\"\n          hints:\n            readOnly: true\n          call: \"quay.list-repository-tags\"\n          with:\n            repository: \"tools.repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-manifest-security\n          description: \"Get vulnerability scan results for a container image.\"\n          hints:\n            readOnly: true\n          call: \"quay.get-manifest-security\"\n          with:\n            repository: \"tools.repository\"\n            manifestref: \"tools.manifestref\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat/refs/heads/main/capabilities/platform-management.yaml
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
