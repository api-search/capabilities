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
- list secrets
- arm list subscriptions
- blob storage
- blob list blobs
- arm list resources
- list subscription tags
- cosmos db database management
- subscription management
- cloud
- list cosmos db databases
- infrastructure as a service
- keyvault get secret
- list azure subscriptions
- arm list resource groups
- list containers in a database
- blob get properties
- azure
- download a blob
- list certificates
- cosmos db
- enterprise
- blob storage operations
- keyvault list secrets
- get a secret value
- resource manager
- api management
- list resource groups
- arm list providers
- list resource providers
- list databases
- list items in a container
- list blobs in a container
- key vault secret management
- keyvault list certificates
- blob download
- list resources in a subscription
- cosmos list containers
- arm list tags
- list cryptographic keys
- list subscriptions
- cosmos list items
- platform as a service
- get blob properties
- list blobs
- keyvault list keys
- key vault
- cloud computing
- cosmos list databases
- t1
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
