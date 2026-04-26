---
consumed_apis:
- azure-storage-accounts
description: Workflow capability for managing Azure Storage Accounts resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Storage Accounts Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Storage Accounts
provider_slug: azure-storage-accounts
search_terms:
- list file shares
- blob storage
- cloud
- list all resources
- list blobcontainer resources
- management
- list blob containers
- resource management
- list storageaccount resources
- cloud storage
- list queues
- storage
- queue storage
- azure
- azure resource management
- list fileshare resources
- list queue resources
- list storage accounts
- table storage
- file storage
- list
slug: azure-storage-accounts-management
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
