---
categories: []
consumed_apis: []
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
- list all resources
- list blobcontainer resources
- file storage
- storage
- list blob containers
- azure
- blob storage
- cloud
- list queue resources
- list queues
- table storage
- list storageaccount resources
- cloud storage
- azure resource management
- list fileshare resources
- list
- management
- list file shares
- list storage accounts
- resource management
- queue storage
slug: azure-storage-accounts-management
source_filename: azure-storage-accounts-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Storage Accounts Management\n  description: Workflow capability for managing Azure Storage Accounts resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-storage-accounts\n    baseUri: https://management.azure.com\n    description: Azure Storage Accounts REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: storage-account\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.StorageAccount/StorageAccounts\n      description: Manage StorageAccount resources\n      operations:\n      - name: list-storage-accounts\n        method: GET\n        description: List all StorageAccount\
  \ resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blob-container\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.BlobContainer/BlobContainers\n      description: Manage BlobContainer resources\n      operations:\n      - name: list-blob-containers\n        method: GET\n        description: List all BlobContainer resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: file-share\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.FileShare/FileShares\n\
  \      description: Manage FileShare resources\n      operations:\n      - name: list-file-shares\n        method: GET\n        description: List all FileShare resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queue\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Queue/Queues\n      description: Manage Queue resources\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all Queue resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: azure-storage-accounts-management-api\n    description: Unified REST API for Azure Storage Accounts management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-storage-accounts.list-storage-accounts\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: azure-storage-accounts-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Storage Accounts management.\n    tools:\n    - name: list-storage-accounts\n      description: List StorageAccount resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-storage-accounts.list-storage-accounts\n\
  \      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-blob-containers\n      description: List BlobContainer resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-storage-accounts.list-blob-containers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-file-shares\n      description: List FileShare resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-storage-accounts.list-file-shares\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List Queue resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-storage-accounts.list-queues\n      with:\n        subscriptionId: tools.subscriptionId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-storage-accounts/refs/heads/main/capabilities/azure-storage-accounts-management.yaml
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
