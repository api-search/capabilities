---
categories: []
consumed_apis: []
description: Unified workflow capability for managing Scaleway cloud infrastructure including virtual machine instances, Kubernetes clusters, node pools, and secret management. Used by cloud engineers and DevOps teams to provision and manage European cloud resources programmatically through a single interface.
layout: capability
name: Scaleway Cloud Infrastructure
operations:
- description: List all Instances in a zone
  method: GET
  name: list-instances
  path: /v1/instances
- description: Create a new Instance
  method: POST
  name: create-instance
  path: /v1/instances
- description: Get Instance details
  method: GET
  name: get-instance
  path: /v1/instances/{id}
- description: Delete an Instance
  method: DELETE
  name: delete-instance
  path: /v1/instances/{id}
- description: Execute a lifecycle action (poweron, poweroff, reboot)
  method: POST
  name: execute-instance-action
  path: /v1/instances/{id}/action
- description: List Kubernetes clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a Kubernetes cluster
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: Get cluster details
  method: GET
  name: get-cluster
  path: /v1/clusters/{id}
- description: Get cluster kubeconfig
  method: GET
  name: get-cluster-kubeconfig
  path: /v1/clusters/{id}/kubeconfig
- description: List node pools
  method: GET
  name: list-node-pools
  path: /v1/clusters/{id}/pools
- description: Create a node pool
  method: POST
  name: create-node-pool
  path: /v1/clusters/{id}/pools
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create a secret
  method: POST
  name: create-secret
  path: /v1/secrets
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- get a secret from scaleway secret manager
- get instance details
- compute
- execute instance action
- list nodes in a kubernetes cluster
- execute a lifecycle action (poweron, poweroff, reboot)
- get details of a specific scaleway instance
- delete secret
- download kubeconfig for a scaleway kubernetes cluster
- storage
- infrastructure
- delete a scaleway instance
- devops
- list kubernetes clusters
- create a new secret in scaleway secret manager
- serverless
- list nodes
- virtual machine instance management
- delete cluster
- european cloud
- security
- get cluster kubeconfig
- create a node pool
- containers
- ai
- list available os images for scaleway instances
- cloud computing
- kubernetes
- execute a lifecycle action on an instance (poweron, poweroff, reboot)
- list instance images
- list instances
- list all instances in a zone
- cluster node pool management
- delete an instance
- manage a specific instance
- add a node pool to a kubernetes cluster
- create secret
- delete a scaleway kubernetes cluster
- get cluster details
- get secret
- database
- secret management
- delete a secret from scaleway secret manager
- list node pools
- create cluster
- create a new managed kubernetes cluster on scaleway
- get details of a scaleway kubernetes cluster
- list node pools in a kubernetes cluster
- scaleway
- kubernetes cluster management
- get cluster
- create a secret
- create a new scaleway virtual machine instance
- manage a specific kubernetes cluster
- execute instance lifecycle actions
- create instance
- list secrets in scaleway secret manager
- list scaleway managed kubernetes clusters
- cluster access credentials
- list secrets
- list all scaleway virtual machine instances in a zone
- list clusters
- get instance
- create a new instance
- create node pool
- delete instance
- create a kubernetes cluster
slug: cloud-infrastructure
source_filename: cloud-infrastructure.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scaleway Cloud Infrastructure\n  description: Unified workflow capability for managing Scaleway cloud infrastructure including virtual machine instances,\n    Kubernetes clusters, node pools, and secret management. Used by cloud engineers and DevOps teams to provision and manage\n    European cloud resources programmatically through a single interface.\n  tags:\n  - Cloud Computing\n  - Compute\n  - DevOps\n  - Infrastructure\n  - Kubernetes\n  - Scaleway\n  - Security\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALEWAY_API_KEY: SCALEWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scaleway-instance\n    baseUri: https://api.scaleway.com\n    description: Scaleway Instance API for virtual machine management\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: servers\n\
  \      path: /instance/v1/zones/{zone}/servers\n      description: Virtual machine instance management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List all Instances in a zone\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n          description: Availability zone (e.g., fr-par-1)\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of instances per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by state (running, stopped)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-server\n      \
  \  method: POST\n        description: Create a new Instance\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n          description: Availability zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            commercial_type: '{{tools.commercial_type}}'\n            image: '{{tools.image}}'\n            project: '{{tools.project}}'\n      - name: get-server\n        method: GET\n        description: Get a specific Instance\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n          description: Availability zone\n        - name: server_id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-server\n        method: DELETE\n        description: Delete an Instance\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: server_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-actions\n      path: /instance/v1/zones/{zone}/servers/{server_id}/action\n      description: Instance lifecycle actions\n      operations:\n      - name: execute-server-action\n        method: POST\n        description: Execute a lifecycle action on an Instance (poweron, poweroff, reboot, stop_in_place)\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: server_id\n \
  \         in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n    - name: images\n      path: /instance/v1/zones/{zone}/images\n      description: Instance image management\n      operations:\n      - name: list-images\n        method: GET\n        description: List Instance images\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-kubernetes\n    baseUri: https://api.scaleway.com\n    description: Scaleway Kubernetes API (Kapsule and\
  \ Kosmos)\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: clusters\n      path: /k8s/v1/regions/{region}/clusters\n      description: Kubernetes cluster lifecycle management\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List Kubernetes clusters\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n          description: Region (e.g., fr-par)\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Create a new Kubernetes cluster\n      \
  \  inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            version: '{{tools.version}}'\n            cni: '{{tools.cni}}'\n            project_id: '{{tools.project_id}}'\n      - name: get-cluster\n        method: GET\n        description: Get a Kubernetes cluster\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description: Delete a Kubernetes cluster\n\
  \        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubeconfig\n      path: /k8s/v1/regions/{region}/clusters/{cluster_id}/kubeconfig\n      description: Kubernetes cluster access configuration\n      operations:\n      - name: get-cluster-kubeconfig\n        method: GET\n        description: Download the kubeconfig for a cluster\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pools\n\
  \      path: /k8s/v1/regions/{region}/clusters/{cluster_id}/pools\n      description: Node pool management\n      operations:\n      - name: list-pools\n        method: GET\n        description: List node pools in a cluster\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pool\n        method: POST\n        description: Create a node pool in a cluster\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            node_type: '{{tools.node_type}}'\n            size: '{{tools.size}}'\n    - name: nodes\n      path: /k8s/v1/regions/{region}/clusters/{cluster_id}/nodes\n      description: Node management\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List nodes in a cluster\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-secrets\n    baseUri: https://api.scaleway.com\n    description: Scaleway Secret Manager API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: secrets\n      path: /secret-manager/v1beta1/regions/{region}/secrets\n      description: Secret management\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List all secrets in a project\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: project_id\n          in: query\n          type: string\n          required: false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-secret\n        method: POST\n        description: Create a new secret\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            project_id: '{{tools.project_id}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n      - name: get-secret\n        method: GET\n        description: Get a secret by ID\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-secret\n        method: DELETE\n        description: Delete a secret\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: secret_id\n          in: path\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: scaleway-cloud-infra-api\n    description: Unified REST API for Scaleway cloud infrastructure management.\n    resources:\n    - path: /v1/instances\n      name: instances\n      description: Virtual machine instance management\n      operations:\n      - method: GET\n        name: list-instances\n        description: List all Instances in a zone\n        call: scaleway-instance.list-servers\n        with:\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-instance\n        description: Create a new Instance\n        call: scaleway-instance.create-server\n        with:\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/instances/{id}\n      name: instance\n      description: Manage a specific Instance\n      operations:\n      - method: GET\n        name: get-instance\n        description: Get Instance details\n        call: scaleway-instance.get-server\n        with:\n          zone: rest.zone\n          server_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-instance\n        description: Delete an Instance\n        call: scaleway-instance.delete-server\n        with:\n          zone: rest.zone\n          server_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}/action\n      name: instance-action\n      description: Execute instance lifecycle actions\n      operations:\n      - method: POST\n        name: execute-instance-action\n        description: Execute a lifecycle action (poweron, poweroff, reboot)\n        call: scaleway-instance.execute-server-action\n\
  \        with:\n          zone: rest.zone\n          server_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters\n      name: clusters\n      description: Kubernetes cluster management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List Kubernetes clusters\n        call: scaleway-kubernetes.list-clusters\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description: Create a Kubernetes cluster\n        call: scaleway-kubernetes.create-cluster\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{id}\n      name: cluster\n      description: Manage a specific Kubernetes cluster\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get\
  \ cluster details\n        call: scaleway-kubernetes.get-cluster\n        with:\n          region: rest.region\n          cluster_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{id}/kubeconfig\n      name: cluster-kubeconfig\n      description: Cluster access credentials\n      operations:\n      - method: GET\n        name: get-cluster-kubeconfig\n        description: Get cluster kubeconfig\n        call: scaleway-kubernetes.get-cluster-kubeconfig\n        with:\n          region: rest.region\n          cluster_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{id}/pools\n      name: node-pools\n      description: Cluster node pool management\n      operations:\n      - method: GET\n        name: list-node-pools\n        description: List node pools\n        call: scaleway-kubernetes.list-pools\n        with:\n          region: rest.region\n          cluster_id:\
  \ rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-node-pool\n        description: Create a node pool\n        call: scaleway-kubernetes.create-pool\n        with:\n          region: rest.region\n          cluster_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets\n      name: secrets\n      description: Secret management\n      operations:\n      - method: GET\n        name: list-secrets\n        description: List secrets\n        call: scaleway-secrets.list-secrets\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-secret\n        description: Create a secret\n        call: scaleway-secrets.create-secret\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: scaleway-cloud-infra-mcp\n    transport: http\n    description: MCP server for AI-assisted Scaleway cloud infrastructure management.\n    tools:\n    - name: list-instances\n      description: List all Scaleway virtual machine instances in a zone\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-instance.list-servers\n      with:\n        zone: tools.zone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-instance\n      description: Create a new Scaleway virtual machine instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-instance.create-server\n      with:\n        zone: tools.zone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance\n      description: Get details of a specific Scaleway instance\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ scaleway-instance.get-server\n      with:\n        zone: tools.zone\n        server_id: tools.server_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-instance\n      description: Delete a Scaleway instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-instance.delete-server\n      with:\n        zone: tools.zone\n        server_id: tools.server_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-instance-action\n      description: Execute a lifecycle action on an instance (poweron, poweroff, reboot)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-instance.execute-server-action\n      with:\n        zone: tools.zone\n        server_id: tools.server_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instance-images\n      description:\
  \ List available OS images for Scaleway instances\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-instance.list-images\n      with:\n        zone: tools.zone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clusters\n      description: List Scaleway managed Kubernetes clusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-kubernetes.list-clusters\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Create a new managed Kubernetes cluster on Scaleway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-kubernetes.create-cluster\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get details of a Scaleway Kubernetes\
  \ cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-kubernetes.get-cluster\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Delete a Scaleway Kubernetes cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-kubernetes.delete-cluster\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster-kubeconfig\n      description: Download kubeconfig for a Scaleway Kubernetes cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-kubernetes.get-cluster-kubeconfig\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-node-pools\n      description: List node pools in a Kubernetes cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-kubernetes.list-pools\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-node-pool\n      description: Add a node pool to a Kubernetes cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-kubernetes.create-pool\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List nodes in a Kubernetes cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-kubernetes.list-nodes\n      with:\n        region: tools.region\n        cluster_id: tools.cluster_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets\n      description: List secrets in Scaleway Secret Manager\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-secrets.list-secrets\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-secret\n      description: Create a new secret in Scaleway Secret Manager\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-secrets.create-secret\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-secret\n      description: Get a secret from Scaleway Secret Manager\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-secrets.get-secret\n      with:\n        region: tools.region\n        secret_id: tools.secret_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-secret\n      description: Delete a secret from Scaleway Secret Manager\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-secrets.delete-secret\n      with:\n        region: tools.region\n        secret_id: tools.secret_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/cloud-infrastructure.yaml
tags:
- Cloud Computing
- Compute
- DevOps
- Infrastructure
- Kubernetes
- Scaleway
- Security
tools:
- description: List all Scaleway virtual machine instances in a zone
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: Create a new Scaleway virtual machine instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-instance
- description: Get details of a specific Scaleway instance
  hints:
    openWorld: false
    readOnly: true
  name: get-instance
- description: Delete a Scaleway instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-instance
- description: Execute a lifecycle action on an instance (poweron, poweroff, reboot)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-instance-action
- description: List available OS images for Scaleway instances
  hints:
    openWorld: true
    readOnly: true
  name: list-instance-images
- description: List Scaleway managed Kubernetes clusters
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Create a new managed Kubernetes cluster on Scaleway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-cluster
- description: Get details of a Scaleway Kubernetes cluster
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster
- description: Delete a Scaleway Kubernetes cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cluster
- description: Download kubeconfig for a Scaleway Kubernetes cluster
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster-kubeconfig
- description: List node pools in a Kubernetes cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-node-pools
- description: Add a node pool to a Kubernetes cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-node-pool
- description: List nodes in a Kubernetes cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-nodes
- description: List secrets in Scaleway Secret Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Create a new secret in Scaleway Secret Manager
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-secret
- description: Get a secret from Scaleway Secret Manager
  hints:
    openWorld: false
    readOnly: true
  name: get-secret
- description: Delete a secret from Scaleway Secret Manager
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-secret
---
