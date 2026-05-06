---
categories:
- object-storage
consumed_apis: []
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
- key vault secret management
- arm list resource groups
- list blobs
- resource manager
- platform as a service
- list resource providers
- arm list providers
- list resource groups
- list cosmos db databases
- azure
- blob storage
- arm list resources
- cloud
- list items in a container
- list subscription tags
- arm list tags
- list azure subscriptions
- download a blob
- enterprise
- list certificates
- cloud computing
- list subscriptions
- cosmos db
- list resources in a subscription
- get blob properties
- keyvault list certificates
- blob storage operations
- arm list subscriptions
- t1
- keyvault get secret
- subscription management
- blob get properties
- keyvault list keys
- infrastructure as a service
- list blobs in a container
- get a secret value
- cosmos list databases
- api management
- list databases
- cosmos db database management
- list containers in a database
- cosmos list items
- list cryptographic keys
- list secrets
- blob list blobs
- keyvault list secrets
- key vault
- blob download
- cosmos list containers
slug: data-and-security
source_filename: data-and-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Data and Security\n  description: Unified workflow for Azure data infrastructure and security combining Cosmos DB for NoSQL data, Blob Storage\n    for object storage, Key Vault for secrets management, and Resource Manager for infrastructure governance. Used by cloud\n    architects, data engineers, and security teams.\n  tags:\n  - Azure\n  - Cosmos DB\n  - Blob Storage\n  - Key Vault\n  - Resource Manager\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\n    AZURE_COSMOS_KEY: AZURE_COSMOS_KEY\n    AZURE_STORAGE_KEY: AZURE_STORAGE_KEY\n    AZURE_KEY_VAULT_TOKEN: AZURE_KEY_VAULT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-cosmos\n    baseUri: https://{accountName}.documents.azure.com\n    description: Azure Cosmos DB REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AZURE_COSMOS_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: databases\n      path: /dbs\n      description: Database operations\n      operations:\n      - name: list-databases\n        method: GET\n        description: List databases\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database\n        method: POST\n        description: Create a database\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-database\n        method: GET\n        description: Get a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: delete-database\n        method: DELETE\n        description: Delete a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers\n      path: /dbs/{databaseId}/colls\n      description: Container operations\n      operations:\n      - name: list-containers\n        method: GET\n        description: List containers in a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-container\n        method: POST\n        description: Create a container\n    \
  \    inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /dbs/{databaseId}/colls/{containerId}/docs\n      description: Item (document) operations\n      operations:\n      - name: list-items\n        method: GET\n        description: List items in a container\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-item\n        method: POST\n       \
  \ description: Create an item\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stored-procedures\n      path: /dbs/{databaseId}/colls/{containerId}/sprocs\n      description: Stored procedure operations\n      operations:\n      - name: list-stored-procedures\n        method: GET\n        description: List stored procedures\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n          description: Database ID\n        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-blob\n    baseUri: https://{accountName}.blob.core.windows.net\n    description: Azure Blob Storage API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AZURE_STORAGE_KEY}}'\n      placement: header\n    resources:\n    - name: service\n      path: /\n      description: Service-level operations\n      operations:\n      - name: get-service-properties\n        method: GET\n        description: Get blob service properties\n        inputParameters:\n        - name: restype\n          in: query\n          type: string\n          required: true\n          description: Resource type (service)\n        - name: comp\n          in: query\n          type: string\n          required: true\n          description: Component (properties)\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: containers\n      path: /{containerName}\n      description: Container operations\n      operations:\n      - name: create-container\n        method: PUT\n        description: Create a blob container\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-blobs\n        method: GET\n        description: List blobs in a container\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-container\n    \
  \    method: DELETE\n        description: Delete a blob container\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blobs\n      path: /{containerName}/{blobName}\n      description: Blob operations\n      operations:\n      - name: download-blob\n        method: GET\n        description: Download a blob\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        - name: blobName\n          in: path\n          type: string\n          required: true\n          description: Blob name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ upload-blob\n        method: PUT\n        description: Upload a blob\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        - name: blobName\n          in: path\n          type: string\n          required: true\n          description: Blob name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-blob\n        method: DELETE\n        description: Delete a blob\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        - name: blobName\n          in: path\n          type: string\n          required: true\n          description: Blob name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-blob-properties\n        method: HEAD\n        description: Get blob properties\n        inputParameters:\n        - name: containerName\n          in: path\n          type: string\n          required: true\n          description: Container name\n        - name: blobName\n          in: path\n          type: string\n          required: true\n          description: Blob name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-keyvault\n    baseUri: https://{vaultName}.vault.azure.net\n    description: Azure Key Vault API\n    authentication:\n      type: bearer\n      token: '{{AZURE_KEY_VAULT_TOKEN}}'\n    resources:\n    - name: keys\n      path: /keys\n      description: Cryptographic key management\n      operations:\n      - name: list-keys\n        method: GET\n        description: List keys in the vault\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-key\n        method: POST\n        description: Create a cryptographic key\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-key\n        method: GET\n        description: Get a key by name\n        inputParameters:\n        - name: keyName\n          in: path\n          type: string\n          required: true\n          description: Key name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-key\n        method: PATCH\n        description: Update key attributes\n        inputParameters:\n        - name: keyName\n          in: path\n          type: string\n          required: true\n          description: Key name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-key\n        method: DELETE\n        description: Delete a key\n        inputParameters:\n        - name: keyName\n          in: path\n          type: string\n          required: true\n          description: Key name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets\n      path: /secrets\n      description: Secret management\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List secrets in the vault\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-secret\n        method: PUT\n        description: Set a secret\n        inputParameters:\n        - name: secretName\n          in: path\n          type: string\n   \
  \       required: true\n          description: Secret name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-secret\n        method: GET\n        description: Get a secret value\n        inputParameters:\n        - name: secretName\n          in: path\n          type: string\n          required: true\n          description: Secret name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-secret\n        method: DELETE\n        description: Delete a secret\n        inputParameters:\n        - name: secretName\n          in: path\n          type: string\n          required: true\n          description: Secret name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates\n      path: /certificates\n      description:\
  \ Certificate management\n      operations:\n      - name: list-certificates\n        method: GET\n        description: List certificates\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-certificate\n        method: POST\n        description: Create a certificate\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-arm\n    baseUri: https://management.azure.com\n    description: Azure Resource Manager API\n    authentication:\n      type: bearer\n      token: '{{AZURE_MANAGEMENT_TOKEN}}'\n    resources:\n    - name: subscriptions\n      path: /subscriptions\n      description: Subscription management\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List subscriptions\n     \
  \   inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-subscription\n        method: GET\n        description: Get a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource-groups\n      path: /subscriptions/{subscriptionId}/resourcegroups\n      description: Resource group management\n      operations:\n      - name: list-resource-groups\n        method: GET\n        description: List resource groups\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-resource-group\n        method: GET\n        description: Get a resource group\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-resource-group\n        method: PUT\n        description: Create or update a resource group\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n    \
  \      required: true\n          description: Resource group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-resource-group\n        method: DELETE\n        description: Delete a resource group\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /subscriptions/{subscriptionId}/resources\n      description: Resource management\n      operations:\n      - name: list-resources\n        method: GET\n        description: List resources in a subscription\n        inputParameters:\n\
  \        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments\n      description: Deployment management\n      operations:\n      - name: create-deployment\n        method: PUT\n        description: Create or update a deployment\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: get-deployment\n        method: GET\n        description: Get a deployment\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers\n      path: /subscriptions/{subscriptionId}/providers\n      description: Provider management\n      operations:\n      - name: list-providers\n        method: GET\n        description: List resource providers\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /subscriptions/{subscriptionId}/tagNames\n      description: Tag management\n      operations:\n      - name: list-tags\n        method: GET\n        description: List subscription tags\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: azure-data-security-api\n    description: Unified REST API for Azure data and security operations.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Cosmos DB database management\n      operations:\n      - method: GET\n        name: list-databases\n        description: List Cosmos DB databases\n        call: azure-cosmos.list-databases\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blobs\n      name: blobs\n      description: Blob storage operations\n      operations:\n      - method: GET\n        name: list-blobs\n        description: List blobs in a container\n        call: azure-blob.list-blobs\n        with:\n          containerName: rest.containerName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets\n      name: secrets\n      description: Key Vault secret management\n      operations:\n      - method: GET\n        name: list-secrets\n        description: List secrets\n        call: azure-keyvault.list-secrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscription management\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List subscriptions\n        call: azure-arm.list-subscriptions\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: azure-data-security-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure data and security operations.\n    tools:\n    - name: cosmos-list-databases\n      description: List Cosmos DB databases\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-cosmos.list-databases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cosmos-list-containers\n      description: List containers in a database\n      hints:\n        readOnly: true\n      call: azure-cosmos.list-containers\n      with:\n        databaseId: tools.databaseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cosmos-list-items\n      description: List items in a container\n      hints:\n        readOnly: true\n      call: azure-cosmos.list-items\n      with:\n        databaseId: tools.databaseId\n\
  \        containerId: tools.containerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: blob-list-blobs\n      description: List blobs in a container\n      hints:\n        readOnly: true\n      call: azure-blob.list-blobs\n      with:\n        containerName: tools.containerName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: blob-download\n      description: Download a blob\n      hints:\n        readOnly: true\n      call: azure-blob.download-blob\n      with:\n        containerName: tools.containerName\n        blobName: tools.blobName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: blob-get-properties\n      description: Get blob properties\n      hints:\n        readOnly: true\n      call: azure-blob.get-blob-properties\n      with:\n        containerName: tools.containerName\n        blobName: tools.blobName\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: keyvault-list-keys\n      description: List cryptographic keys\n      hints:\n        readOnly: true\n      call: azure-keyvault.list-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keyvault-list-secrets\n      description: List secrets\n      hints:\n        readOnly: true\n      call: azure-keyvault.list-secrets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keyvault-get-secret\n      description: Get a secret value\n      hints:\n        readOnly: true\n      call: azure-keyvault.get-secret\n      with:\n        secretName: tools.secretName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keyvault-list-certificates\n      description: List certificates\n      hints:\n        readOnly: true\n      call: azure-keyvault.list-certificates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: arm-list-subscriptions\n      description: List Azure subscriptions\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-arm.list-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: arm-list-resource-groups\n      description: List resource groups\n      hints:\n        readOnly: true\n      call: azure-arm.list-resource-groups\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: arm-list-resources\n      description: List resources in a subscription\n      hints:\n        readOnly: true\n      call: azure-arm.list-resources\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: arm-list-providers\n      description: List resource providers\n      hints:\n        readOnly: true\n      call: azure-arm.list-providers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: arm-list-tags\n      description: List subscription tags\n      hints:\n        readOnly: true\n      call: azure-arm.list-tags\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure/refs/heads/main/capabilities/data-and-security.yaml
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
