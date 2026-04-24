---
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
- list resources in a subscription
- list certificates
- resource manager
- list containers in a database
- get a secret value
- blob storage
- arm list tags
- keyvault list keys
- cosmos list items
- arm list subscriptions
- cloud
- list resource providers
- list cosmos db databases
- platform as a service
- arm list providers
- blob list blobs
- cosmos db
- blob storage operations
- list subscriptions
- cosmos list containers
- blob get properties
- list secrets
- list items in a container
- cosmos list databases
- list blobs in a container
- subscription management
- api management
- arm list resources
- list azure subscriptions
- t1
- list resource groups
- list databases
- blob download
- list subscription tags
- list blobs
- keyvault get secret
- key vault
- cosmos db database management
- get blob properties
- enterprise
- download a blob
- list cryptographic keys
- cloud computing
- infrastructure as a service
- keyvault list certificates
- key vault secret management
- azure
- keyvault list secrets
- arm list resource groups
slug: data-and-security
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
