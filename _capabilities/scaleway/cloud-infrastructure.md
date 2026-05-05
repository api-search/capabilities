---
categories: []
consumed_apis:
- scaleway-instance
- scaleway-kubernetes
- scaleway-secrets
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
- virtual machine instance management
- list secrets
- manage a specific kubernetes cluster
- execute a lifecycle action on an instance (poweron, poweroff, reboot)
- containers
- list nodes in a kubernetes cluster
- security
- delete a secret from scaleway secret manager
- download kubeconfig for a scaleway kubernetes cluster
- delete an instance
- create secret
- create a node pool
- list node pools
- add a node pool to a kubernetes cluster
- serverless
- ai
- list kubernetes clusters
- get details of a specific scaleway instance
- delete secret
- storage
- get cluster
- execute instance action
- create a secret
- get details of a scaleway kubernetes cluster
- list secrets in scaleway secret manager
- delete instance
- get a secret from scaleway secret manager
- list instances
- cloud computing
- manage a specific instance
- get cluster kubeconfig
- cluster node pool management
- create a new managed kubernetes cluster on scaleway
- list node pools in a kubernetes cluster
- list all instances in a zone
- list scaleway managed kubernetes clusters
- database
- get cluster details
- delete a scaleway instance
- devops
- create instance
- create a new secret in scaleway secret manager
- list available os images for scaleway instances
- create cluster
- compute
- scaleway
- create a new instance
- get instance
- get secret
- infrastructure
- secret management
- list nodes
- european cloud
- execute instance lifecycle actions
- list clusters
- delete a scaleway kubernetes cluster
- create a new scaleway virtual machine instance
- create node pool
- delete cluster
- kubernetes cluster management
- list instance images
- get instance details
- kubernetes
- list all scaleway virtual machine instances in a zone
- create a kubernetes cluster
- cluster access credentials
- execute a lifecycle action (poweron, poweroff, reboot)
slug: cloud-infrastructure
source_filename: cloud-infrastructure.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scaleway Cloud Infrastructure\"\n  description: >-\n    Unified workflow capability for managing Scaleway cloud infrastructure including\n    virtual machine instances, Kubernetes clusters, node pools, and secret management.\n    Used by cloud engineers and DevOps teams to provision and manage European cloud resources\n    programmatically through a single interface.\n  tags:\n    - Cloud Computing\n    - Compute\n    - DevOps\n    - Infrastructure\n    - Kubernetes\n    - Scaleway\n    - Security\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCALEWAY_API_KEY: SCALEWAY_API_KEY\n\ncapability:\n  consumes:\n    - import: scaleway-instance\n      location: ./shared/instance.yaml\n    - import: scaleway-kubernetes\n      location: ./shared/kubernetes.yaml\n    - import: scaleway-secrets\n      location: ./shared/secret-manager.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: scaleway-cloud-infra-api\n      description: \"Unified REST API for Scaleway cloud infrastructure management.\"\n      resources:\n        - path: /v1/instances\n          name: instances\n          description: \"Virtual machine instance management\"\n          operations:\n            - method: GET\n              name: list-instances\n              description: \"List all Instances in a zone\"\n              call: \"scaleway-instance.list-servers\"\n              with:\n                zone: \"rest.zone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-instance\n              description: \"Create a new Instance\"\n              call: \"scaleway-instance.create-server\"\n              with:\n                zone: \"rest.zone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{id}\n\
  \          name: instance\n          description: \"Manage a specific Instance\"\n          operations:\n            - method: GET\n              name: get-instance\n              description: \"Get Instance details\"\n              call: \"scaleway-instance.get-server\"\n              with:\n                zone: \"rest.zone\"\n                server_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-instance\n              description: \"Delete an Instance\"\n              call: \"scaleway-instance.delete-server\"\n              with:\n                zone: \"rest.zone\"\n                server_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{id}/action\n          name: instance-action\n          description: \"Execute instance lifecycle actions\"\n          operations:\n\
  \            - method: POST\n              name: execute-instance-action\n              description: \"Execute a lifecycle action (poweron, poweroff, reboot)\"\n              call: \"scaleway-instance.execute-server-action\"\n              with:\n                zone: \"rest.zone\"\n                server_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters\n          name: clusters\n          description: \"Kubernetes cluster management\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List Kubernetes clusters\"\n              call: \"scaleway-kubernetes.list-clusters\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create\
  \ a Kubernetes cluster\"\n              call: \"scaleway-kubernetes.create-cluster\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{id}\n          name: cluster\n          description: \"Manage a specific Kubernetes cluster\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details\"\n              call: \"scaleway-kubernetes.get-cluster\"\n              with:\n                region: \"rest.region\"\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{id}/kubeconfig\n          name: cluster-kubeconfig\n          description: \"Cluster access credentials\"\n          operations:\n            - method: GET\n              name: get-cluster-kubeconfig\n\
  \              description: \"Get cluster kubeconfig\"\n              call: \"scaleway-kubernetes.get-cluster-kubeconfig\"\n              with:\n                region: \"rest.region\"\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{id}/pools\n          name: node-pools\n          description: \"Cluster node pool management\"\n          operations:\n            - method: GET\n              name: list-node-pools\n              description: \"List node pools\"\n              call: \"scaleway-kubernetes.list-pools\"\n              with:\n                region: \"rest.region\"\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-node-pool\n              description: \"Create a node pool\"\n              call: \"scaleway-kubernetes.create-pool\"\
  \n              with:\n                region: \"rest.region\"\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: secrets\n          description: \"Secret management\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List secrets\"\n              call: \"scaleway-secrets.list-secrets\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-secret\n              description: \"Create a secret\"\n              call: \"scaleway-secrets.create-secret\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: scaleway-cloud-infra-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Scaleway cloud infrastructure management.\"\n      tools:\n        - name: list-instances\n          description: \"List all Scaleway virtual machine instances in a zone\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-instance.list-servers\"\n          with:\n            zone: \"tools.zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-instance\n          description: \"Create a new Scaleway virtual machine instance\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-instance.create-server\"\n          with:\n            zone: \"tools.zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-instance\n\
  \          description: \"Get details of a specific Scaleway instance\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-instance.get-server\"\n          with:\n            zone: \"tools.zone\"\n            server_id: \"tools.server_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-instance\n          description: \"Delete a Scaleway instance\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-instance.delete-server\"\n          with:\n            zone: \"tools.zone\"\n            server_id: \"tools.server_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-instance-action\n          description: \"Execute a lifecycle action on an instance (poweron, poweroff, reboot)\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: false\n          call: \"scaleway-instance.execute-server-action\"\n          with:\n            zone: \"tools.zone\"\n            server_id: \"tools.server_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-instance-images\n          description: \"List available OS images for Scaleway instances\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-instance.list-images\"\n          with:\n            zone: \"tools.zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clusters\n          description: \"List Scaleway managed Kubernetes clusters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-kubernetes.list-clusters\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-cluster\n          description: \"Create a new managed Kubernetes cluster on Scaleway\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-kubernetes.create-cluster\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster\n          description: \"Get details of a Scaleway Kubernetes cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-kubernetes.get-cluster\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cluster\n          description: \"Delete a Scaleway Kubernetes cluster\"\n \
  \         hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-kubernetes.delete-cluster\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster-kubeconfig\n          description: \"Download kubeconfig for a Scaleway Kubernetes cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-kubernetes.get-cluster-kubeconfig\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-node-pools\n          description: \"List node pools in a Kubernetes cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"\
  scaleway-kubernetes.list-pools\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-node-pool\n          description: \"Add a node pool to a Kubernetes cluster\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-kubernetes.create-pool\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-nodes\n          description: \"List nodes in a Kubernetes cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-kubernetes.list-nodes\"\n          with:\n            region: \"tools.region\"\n            cluster_id: \"tools.cluster_id\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n          description: \"List secrets in Scaleway Secret Manager\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-secrets.list-secrets\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-secret\n          description: \"Create a new secret in Scaleway Secret Manager\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-secrets.create-secret\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-secret\n          description: \"Get a secret from Scaleway Secret Manager\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"scaleway-secrets.get-secret\"\n          with:\n            region: \"tools.region\"\n            secret_id: \"tools.secret_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-secret\n          description: \"Delete a secret from Scaleway Secret Manager\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-secrets.delete-secret\"\n          with:\n            region: \"tools.region\"\n            secret_id: \"tools.secret_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
