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
- cloud storage
- management
- azure resource management
- azure
- list storage accounts
- resource management
- list blob containers
- list blobcontainer resources
- list fileshare resources
- list storageaccount resources
- list file shares
- list queues
- list
- list all resources
- cloud
- list queue resources
- file storage
- blob storage
- storage
- microsoft
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
