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
- list cosmos db databases
- get blob properties
- keyvault get secret
- list resource groups
- azure
- list resource providers
- infrastructure as a service
- blob storage
- blob storage operations
- resource manager
- list blobs in a container
- list certificates
- get a secret value
- enterprise
- arm list subscriptions
- arm list resource groups
- keyvault list certificates
- list azure subscriptions
- cosmos list containers
- api management
- arm list tags
- key vault
- blob list blobs
- cloud computing
- cloud
- list items in a container
- arm list resources
- list databases
- blob download
- keyvault list keys
- list blobs
- keyvault list secrets
- cosmos list databases
- blob get properties
- key vault secret management
- list secrets
- cosmos list items
- arm list providers
- download a blob
- list cryptographic keys
- platform as a service
- list subscription tags
- list resources in a subscription
- list subscriptions
- cosmos db database management
- list containers in a database
- cosmos db
- t1
- subscription management
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
