---
categories:
- object-storage
consumed_apis:
- azure-cosmos
- azure-blob
- azure-keyvault
- azure-arm
description: Unified workflow for Azure data infrastructure and security combining Cosmos DB for NoSQL data, Blob Storage for object storage, Key Vault for secrets management, and Resource Manager for infrastructure governance. Used by cloud architects, data engineers, and security teams.
layout: capability
name: Azure Data and Security
operations:
- description: List Cosmos DB databases
  method: GET
  name: list-databases
  path: /v1/databases
- description: List blobs in a container
  method: GET
  name: list-blobs
  path: /v1/blobs
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: List subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
personas: []
provider_name: Microsoft Azure
provider_slug: microsoft-azure
search_terms:
- list cosmos db databases
- subscription management
- list subscriptions
- t1
- arm list resources
- list blobs
- get blob properties
- list secrets
- cloud computing
- list items in a container
- keyvault list secrets
- resource manager
- infrastructure as a service
- key vault
- arm list tags
- blob list blobs
- blob storage
- api management
- keyvault list keys
- cosmos list items
- list resource providers
- keyvault list certificates
- get a secret value
- cloud
- cosmos list containers
- list azure subscriptions
- cosmos db database management
- list cryptographic keys
- arm list subscriptions
- arm list providers
- list resources in a subscription
- list subscription tags
- list databases
- list blobs in a container
- platform as a service
- list certificates
- list containers in a database
- list resource groups
- blob download
- azure
- cosmos db
- cosmos list databases
- key vault secret management
- blob storage operations
- blob get properties
- download a blob
- arm list resource groups
- keyvault get secret
- enterprise
slug: data-and-security
source_filename: data-and-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Data and Security\"\n  description: \"Unified workflow for Azure data infrastructure and security combining Cosmos DB for NoSQL data, Blob Storage for object storage, Key Vault for secrets management, and Resource Manager for infrastructure governance. Used by cloud architects, data engineers, and security teams.\"\n  tags:\n    - Azure\n    - Cosmos DB\n    - Blob Storage\n    - Key Vault\n    - Resource Manager\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\n      AZURE_COSMOS_KEY: AZURE_COSMOS_KEY\n      AZURE_STORAGE_KEY: AZURE_STORAGE_KEY\n      AZURE_KEY_VAULT_TOKEN: AZURE_KEY_VAULT_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-cosmos\n      location: ./shared/cosmos-db.yaml\n    - import: azure-blob\n      location: ./shared/blob-storage.yaml\n    - import: azure-keyvault\n      location: ./shared/key-vault.yaml\n\
  \    - import: azure-arm\n      location: ./shared/resource-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: azure-data-security-api\n      description: \"Unified REST API for Azure data and security operations.\"\n      resources:\n        - path: /v1/databases\n          name: databases\n          description: \"Cosmos DB database management\"\n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List Cosmos DB databases\"\n              call: \"azure-cosmos.list-databases\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blobs\n          name: blobs\n          description: \"Blob storage operations\"\n          operations:\n            - method: GET\n              name: list-blobs\n              description: \"List blobs in a container\"\n              call: \"azure-blob.list-blobs\"\n              with:\n            \
  \    containerName: \"rest.containerName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: secrets\n          description: \"Key Vault secret management\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List secrets\"\n              call: \"azure-keyvault.list-secrets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Subscription management\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List subscriptions\"\n              call: \"azure-arm.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace:\
  \ azure-data-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure data and security operations.\"\n      tools:\n        - name: cosmos-list-databases\n          description: \"List Cosmos DB databases\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-cosmos.list-databases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cosmos-list-containers\n          description: \"List containers in a database\"\n          hints:\n            readOnly: true\n          call: \"azure-cosmos.list-containers\"\n          with:\n            databaseId: \"tools.databaseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cosmos-list-items\n          description: \"List items in a container\"\n          hints:\n            readOnly: true\n          call: \"azure-cosmos.list-items\"\n          with:\n  \
  \          databaseId: \"tools.databaseId\"\n            containerId: \"tools.containerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: blob-list-blobs\n          description: \"List blobs in a container\"\n          hints:\n            readOnly: true\n          call: \"azure-blob.list-blobs\"\n          with:\n            containerName: \"tools.containerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: blob-download\n          description: \"Download a blob\"\n          hints:\n            readOnly: true\n          call: \"azure-blob.download-blob\"\n          with:\n            containerName: \"tools.containerName\"\n            blobName: \"tools.blobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: blob-get-properties\n          description: \"Get blob properties\"\n          hints:\n            readOnly:\
  \ true\n          call: \"azure-blob.get-blob-properties\"\n          with:\n            containerName: \"tools.containerName\"\n            blobName: \"tools.blobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: keyvault-list-keys\n          description: \"List cryptographic keys\"\n          hints:\n            readOnly: true\n          call: \"azure-keyvault.list-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: keyvault-list-secrets\n          description: \"List secrets\"\n          hints:\n            readOnly: true\n          call: \"azure-keyvault.list-secrets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: keyvault-get-secret\n          description: \"Get a secret value\"\n          hints:\n            readOnly: true\n          call: \"azure-keyvault.get-secret\"\n          with:\n            secretName:\
  \ \"tools.secretName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: keyvault-list-certificates\n          description: \"List certificates\"\n          hints:\n            readOnly: true\n          call: \"azure-keyvault.list-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-list-subscriptions\n          description: \"List Azure subscriptions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-arm.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-list-resource-groups\n          description: \"List resource groups\"\n          hints:\n            readOnly: true\n          call: \"azure-arm.list-resource-groups\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: arm-list-resources\n          description: \"List resources in a subscription\"\n          hints:\n            readOnly: true\n          call: \"azure-arm.list-resources\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-list-providers\n          description: \"List resource providers\"\n          hints:\n            readOnly: true\n          call: \"azure-arm.list-providers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-list-tags\n          description: \"List subscription tags\"\n          hints:\n            readOnly: true\n          call: \"azure-arm.list-tags\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n  \
  \          - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure/refs/heads/main/capabilities/data-and-security.yaml
tags:
- Azure
- Cosmos DB
- Blob Storage
- Key Vault
- Resource Manager
tools:
- description: List Cosmos DB databases
  hints:
    openWorld: true
    readOnly: true
  name: cosmos-list-databases
- description: List containers in a database
  hints:
    readOnly: true
  name: cosmos-list-containers
- description: List items in a container
  hints:
    readOnly: true
  name: cosmos-list-items
- description: List blobs in a container
  hints:
    readOnly: true
  name: blob-list-blobs
- description: Download a blob
  hints:
    readOnly: true
  name: blob-download
- description: Get blob properties
  hints:
    readOnly: true
  name: blob-get-properties
- description: List cryptographic keys
  hints:
    readOnly: true
  name: keyvault-list-keys
- description: List secrets
  hints:
    readOnly: true
  name: keyvault-list-secrets
- description: Get a secret value
  hints:
    readOnly: true
  name: keyvault-get-secret
- description: List certificates
  hints:
    readOnly: true
  name: keyvault-list-certificates
- description: List Azure subscriptions
  hints:
    openWorld: true
    readOnly: true
  name: arm-list-subscriptions
- description: List resource groups
  hints:
    readOnly: true
  name: arm-list-resource-groups
- description: List resources in a subscription
  hints:
    readOnly: true
  name: arm-list-resources
- description: List resource providers
  hints:
    readOnly: true
  name: arm-list-providers
- description: List subscription tags
  hints:
    readOnly: true
  name: arm-list-tags
---
