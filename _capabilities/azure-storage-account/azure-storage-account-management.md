---
consumed_apis:
- azure-storage-account
description: Workflow capability for managing Azure Storage Account resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Storage Account Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Storage Account
provider_slug: azure-storage-account
search_terms:
- list
- storage
- azure
- cloud
- list blob containers
- list all resources
- azure resource management
- management
- list storageaccount resources
- list storage accounts
- list blobcontainer resources
- file storage
- list queue resources
- list queues
- microsoft
- list fileshare resources
- list file shares
- cloud storage
- resource management
- blob storage
slug: azure-storage-account-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List StorageAccount resources
  hints:
    openWorld: true
    readOnly: true
  name: list-storage-accounts
- description: List BlobContainer resources
  hints:
    openWorld: true
    readOnly: true
  name: list-blob-containers
- description: List FileShare resources
  hints:
    openWorld: true
    readOnly: true
  name: list-file-shares
- description: List Queue resources
  hints:
    openWorld: true
    readOnly: true
  name: list-queues
---
