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
- azure resource management
- azure
- cloud storage
- resource management
- list all resources
- list
- blob storage
- table storage
- management
- list storage accounts
- list queues
- cloud
- file storage
- list blobcontainer resources
- list queue resources
- list fileshare resources
- list storageaccount resources
- storage
- list file shares
- list blob containers
- queue storage
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
