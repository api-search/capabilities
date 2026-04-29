---
categories: []
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
- list fileshare resources
- list file shares
- list
- list queue resources
- azure resource management
- azure
- resource management
- storage
- list queues
- cloud storage
- list blob containers
- list storage accounts
- cloud
- list all resources
- file storage
- microsoft
- blob storage
- management
- list storageaccount resources
- list blobcontainer resources
slug: azure-storage-account-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Storage Account Management\"\n  description: \"Workflow capability for managing Azure Storage Account resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-storage-account\n      location: ./shared/azure-storage-account.yaml\n\n  exposes:\n    - type: rest\n      port: 8086\n      namespace: azure-storage-account-management-api\n      description: \"Unified REST API for Azure Storage Account management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"\
  List all resources\"\n              call: \"azure-storage-account.list-storage-accounts\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9096\n      namespace: azure-storage-account-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Storage Account management.\"\n      tools:\n        - name: list-storage-accounts\n          description: \"List StorageAccount resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-storage-account.list-storage-accounts\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blob-containers\n          description: \"List BlobContainer resources\"\n          hints:\n       \
  \     readOnly: true\n            openWorld: true\n          call: \"azure-storage-account.list-blob-containers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-file-shares\n          description: \"List FileShare resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-storage-account.list-file-shares\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-queues\n          description: \"List Queue resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-storage-account.list-queues\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-storage-account/refs/heads/main/capabilities/azure-storage-account-management.yaml
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
