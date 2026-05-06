---
categories: []
consumed_apis: []
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
- get manifest security
- list all managed openshift clusters.
- openshift versions.
- get vulnerability scan results.
- create a new openshift cluster.
- get repository
- list machine pools.
- container image repositories.
- openshift clusters.
- create a container repository.
- list available openshift versions.
- list available cluster add-ons.
- list container image repositories.
- red hat
- platform engineering
- list tags for a container image.
- hybrid cloud
- list repositories
- get cluster details.
- available cloud providers.
- delete a cluster.
- cloud
- delete cluster
- delete an openshift cluster.
- containers
- list versions
- image vulnerability scanning.
- enterprise
- specific cluster operations.
- image tags.
- list container repositories.
- kubernetes
- linux
- cluster machine pools.
- list subscriptions
- open source
- list repository tags
- list addons
- create a new container repository.
- list all managed clusters.
- list machine pools
- list cluster subscriptions.
- create cluster
- list machine pools for a cluster.
- get cluster
- get vulnerability scan results for a container image.
- list image tags.
- quay
- openshift
- list available cloud providers.
- get container repository details.
- list cloud providers
- list cloud providers.
- list openshift versions.
- list clusters
- get details of a specific cluster.
- create repository
- create a new cluster.
slug: platform-management
source_filename: platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat Platform Management\n  description: Unified workflow for managing OpenShift clusters and Quay container registries. Used by platform engineers\n    and DevOps teams to provision clusters, manage machine pools, and maintain container image repositories.\n  tags:\n  - Red Hat\n  - OpenShift\n  - Quay\n  - Platform Engineering\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RED_HAT_BEARER_TOKEN: RED_HAT_BEARER_TOKEN\n    QUAY_BEARER_TOKEN: QUAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: openshift-cluster-manager\n    baseUri: https://api.openshift.com\n    description: OpenShift Cluster Manager API for cluster lifecycle management.\n    authentication:\n      type: bearer\n      token: '{{RED_HAT_BEARER_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /api/clusters_mgmt/v1/clusters\n      description: Manage OpenShift clusters.\n      operations:\n \
  \     - name: list-clusters\n        method: GET\n        description: List all managed clusters.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Create a new OpenShift cluster.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n \
  \           cloud_provider: '{{tools.cloud_provider}}'\n            region: '{{tools.region}}'\n      - name: get-cluster\n        method: GET\n        description: Get a specific cluster.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cluster\n        method: PATCH\n        description: Update a cluster configuration.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-cluster\n        method:\
  \ DELETE\n        description: Delete a cluster.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machine-pools\n      path: /api/clusters_mgmt/v1/clusters/{cluster_id}/machine_pools\n      description: Manage compute node machine pools.\n      operations:\n      - name: list-machine-pools\n        method: GET\n        description: List machine pools for a cluster.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-machine-pool\n        method: POST\n        description: Create a machine\
  \ pool.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            instance_type: '{{tools.instance_type}}'\n            replicas: '{{tools.replicas}}'\n    - name: identity-providers\n      path: /api/clusters_mgmt/v1/clusters/{cluster_id}/identity_providers\n      description: Configure cluster identity providers.\n      operations:\n      - name: list-cluster-identity-providers\n        method: GET\n        description: List identity providers for a cluster.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-cluster-identity-provider\n        method: POST\n        description: Add an identity provider to a cluster.\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: cloud-providers\n      path: /api/clusters_mgmt/v1/cloud_providers\n      description: Available cloud providers and regions.\n      operations:\n      - name: list-cloud-providers\n        method: GET\n        description: List available cloud providers.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: list-cloud-provider-regions\n        method: GET\n        description: List regions for a cloud provider.\n        inputParameters:\n        - name: cloud_provider_id\n          in: path\n          type: string\n          required: true\n          description: Cloud provider ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /api/clusters_mgmt/v1/versions\n      description: Available OpenShift versions.\n      operations:\n      - name: list-versions\n        method: GET\n        description: List available OpenShift versions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addons\n      path: /api/clusters_mgmt/v1/addons\n      description: Cluster add-ons.\n      operations:\n      - name: list-addons\n\
  \        method: GET\n        description: List available cluster add-ons.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /api/accounts_mgmt/v1/subscriptions\n      description: Cluster subscriptions.\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List cluster subscriptions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: quay\n    baseUri: https://quay.io/api/v1\n    description: Red Hat Quay container registry API.\n    authentication:\n      type: bearer\n      token: '{{QUAY_BEARER_TOKEN}}'\n    resources:\n    - name: repositories\n      path: /repository\n      description: Container image repositories.\n      operations:\n      - name: list-repositories\n\
  \        method: GET\n        description: List visible repositories.\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter by namespace\n        - name: starred\n          in: query\n          type: boolean\n          required: false\n          description: Filter starred repos\n        - name: public\n          in: query\n          type: boolean\n          required: false\n          description: Include public repos\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repository\n        method: POST\n        description: Create a new repository.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            namespace: '{{tools.namespace}}'\n\
  \            repository: '{{tools.repository}}'\n            visibility: '{{tools.visibility}}'\n      - name: get-repository\n        method: GET\n        description: Get repository details.\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path (namespace/name)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-repository\n        method: DELETE\n        description: Delete a repository.\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /repository/{repository}/tag\n      description: Image tags.\n      operations:\n\
  \      - name: list-repository-tags\n        method: GET\n        description: List tags for a repository.\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: change-tag\n        method: PUT\n        description: Change or create a tag.\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path\n        - name: tag\n          in: path\n          type: string\n          required: true\n          description: Tag name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-tag\n        method: DELETE\n        description: Delete a tag.\n      \
  \  inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path\n        - name: tag\n          in: path\n          type: string\n          required: true\n          description: Tag name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: manifests\n      path: /repository/{repository}/manifest\n      description: Image manifests and security scanning.\n      operations:\n      - name: get-manifest-security\n        method: GET\n        description: Get security scan results for a manifest.\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n          description: Repository path\n        - name: manifestref\n          in: path\n          type: string\n          required: true\n          description: Manifest digest\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organization\n      description: Organization management.\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get organization details.\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: robot-accounts\n      path: /organization/{orgname}/robots\n      description: Robot accounts for automated access.\n      operations:\n      - name: get-org-robot\n        method: GET\n        description: Get a robot account.\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n          description: Organization\
  \ name\n        - name: robot_shortname\n          in: path\n          type: string\n          required: true\n          description: Robot short name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-org-robot\n        method: PUT\n        description: Create or update a robot account.\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: robot_shortname\n          in: path\n          type: string\n          required: true\n          description: Robot short name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /user\n      description: User operations.\n      operations:\n      - name: get-logged-in-user\n        method: GET\n        description: Get the\
  \ currently logged-in user.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: platform-management-api\n    description: Unified REST API for OpenShift cluster and Quay registry management.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: OpenShift clusters.\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all managed clusters.\n        call: openshift-cluster-manager.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description: Create a new cluster.\n        call: openshift-cluster-manager.create-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{cluster_id}\n      name: cluster-detail\n\
  \      description: Specific cluster operations.\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get cluster details.\n        call: openshift-cluster-manager.get-cluster\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cluster\n        description: Delete a cluster.\n        call: openshift-cluster-manager.delete-cluster\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{cluster_id}/machine-pools\n      name: machine-pools\n      description: Cluster machine pools.\n      operations:\n      - method: GET\n        name: list-machine-pools\n        description: List machine pools.\n        call: openshift-cluster-manager.list-machine-pools\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/cloud-providers\n      name: cloud-providers\n      description: Available cloud providers.\n      operations:\n      - method: GET\n        name: list-cloud-providers\n        description: List cloud providers.\n        call: openshift-cluster-manager.list-cloud-providers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/versions\n      name: versions\n      description: OpenShift versions.\n      operations:\n      - method: GET\n        name: list-versions\n        description: List OpenShift versions.\n        call: openshift-cluster-manager.list-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories\n      name: repositories\n      description: Container image repositories.\n      operations:\n      - method: GET\n        name: list-repositories\n        description: List container repositories.\n        call: quay.list-repositories\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-repository\n        description: Create a container repository.\n        call: quay.create-repository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{repository}/tags\n      name: tags\n      description: Image tags.\n      operations:\n      - method: GET\n        name: list-repository-tags\n        description: List image tags.\n        call: quay.list-repository-tags\n        with:\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{repository}/manifests/{manifestref}/security\n      name: manifest-security\n      description: Image vulnerability scanning.\n      operations:\n      - method: GET\n        name: get-manifest-security\n        description: Get vulnerability scan results.\n        call: quay.get-manifest-security\n\
  \        with:\n          repository: rest.repository\n          manifestref: rest.manifestref\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: platform-management-mcp\n    transport: http\n    description: MCP server for AI-assisted OpenShift and Quay management.\n    tools:\n    - name: list-clusters\n      description: List all managed OpenShift clusters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-manager.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get details of a specific cluster.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: openshift-cluster-manager.get-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Create a new OpenShift\
  \ cluster.\n      hints:\n        readOnly: false\n      call: openshift-cluster-manager.create-cluster\n      with:\n        name: tools.name\n        cloud_provider: tools.cloud_provider\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Delete an OpenShift cluster.\n      hints:\n        readOnly: false\n        destructive: true\n      call: openshift-cluster-manager.delete-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-machine-pools\n      description: List machine pools for a cluster.\n      hints:\n        readOnly: true\n      call: openshift-cluster-manager.list-machine-pools\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cloud-providers\n      description: List available cloud providers.\n      hints:\n\
  \        readOnly: true\n      call: openshift-cluster-manager.list-cloud-providers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-versions\n      description: List available OpenShift versions.\n      hints:\n        readOnly: true\n      call: openshift-cluster-manager.list-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-addons\n      description: List available cluster add-ons.\n      hints:\n        readOnly: true\n      call: openshift-cluster-manager.list-addons\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List cluster subscriptions.\n      hints:\n        readOnly: true\n      call: openshift-cluster-manager.list-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repositories\n      description: List container image repositories.\n      hints:\n        readOnly: true\n   \
  \     openWorld: true\n      call: quay.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repository\n      description: Get container repository details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quay.get-repository\n      with:\n        repository: tools.repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repository\n      description: Create a new container repository.\n      hints:\n        readOnly: false\n      call: quay.create-repository\n      with:\n        namespace: tools.namespace\n        repository: tools.repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repository-tags\n      description: List tags for a container image.\n      hints:\n        readOnly: true\n      call: quay.list-repository-tags\n      with:\n        repository: tools.repository\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-manifest-security\n      description: Get vulnerability scan results for a container image.\n      hints:\n        readOnly: true\n      call: quay.get-manifest-security\n      with:\n        repository: tools.repository\n        manifestref: tools.manifestref\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
