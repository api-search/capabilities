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
- list blobcontainer resources
- blob storage
- list all resources
- cloud
- table storage
- list queues
- list blob containers
- list file shares
- list storageaccount resources
- azure resource management
- file storage
- list queue resources
- list storage accounts
- list fileshare resources
- cloud storage
- resource management
- management
- list
- queue storage
- azure
- storage
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
