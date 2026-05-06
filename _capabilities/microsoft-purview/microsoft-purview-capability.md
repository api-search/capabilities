---
categories: []
consumed_apis: []
description: APIs for managing Purview accounts, configurations, and administrative settings through Azure Resource Manager. Provides resource management operations for creating, updating, and deleting Purview accounts.
layout: capability
name: Microsoft Purview Account API
operations:
- description: Microsoft Purview Create or update a Purview account
  method: PUT
  name: createorupdateaccount
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}
- description: Microsoft Purview Get a Purview account
  method: GET
  name: getaccount
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}
- description: Microsoft Purview Update a Purview account
  method: PATCH
  name: updateaccount
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}
- description: Microsoft Purview Delete a Purview account
  method: DELETE
  name: deleteaccount
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}
- description: Microsoft Purview List accounts by resource group
  method: GET
  name: listaccountsbyresourcegroup
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts
- description: Microsoft Purview List accounts by subscription
  method: GET
  name: listaccountsbysubscription
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/accounts
- description: Microsoft Purview List account keys
  method: POST
  name: listaccountkeys
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/listkeys
- description: Microsoft Purview Add root collection admin
  method: POST
  name: addrootcollectionadmin
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/addRootCollectionAdmin
- description: Microsoft Purview Check name availability
  method: POST
  name: checknameavailability
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/checkNameAvailability
- description: Microsoft Purview List private endpoint connections
  method: GET
  name: listprivateendpointconnections
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections
- description: Microsoft Purview Get a private endpoint connection
  method: GET
  name: getprivateendpointconnection
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections/{privateEndpointConnectionName}
- description: Microsoft Purview List available operations
  method: GET
  name: listoperations
  path: /providers/Microsoft.Purview/operations
personas: []
provider_name: Microsoft Purview
provider_slug: microsoft-purview
search_terms:
- microsoft purview list account keys
- microsoft purview get a private endpoint connection
- createorupdateaccount
- checknameavailability
- microsoft purview check name availability
- listprivateendpointconnections
- information protection
- listaccountkeys
- microsoft purview list private endpoint connections
- deleteaccount
- compliance
- microsoft purview get a purview account
- getaccount
- data governance
- microsoft purview delete a purview account
- microsoft purview add root collection admin
- microsoft purview list available operations
- microsoft purview update a purview account
- listoperations
- data loss prevention
- api
- updateaccount
- microsoft purview list accounts by resource group
- getprivateendpointconnection
- microsoft purview create or update a purview account
- addrootcollectionadmin
- listaccountsbysubscription
- listaccountsbyresourcegroup
- microsoft purview list accounts by subscription
- purview
- data catalog
- microsoft
- data classification
slug: microsoft-purview-capability
source_filename: microsoft-purview-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Purview Account API\n  description: APIs for managing Purview accounts, configurations, and administrative settings through Azure Resource Manager.\n    Provides resource management operations for creating, updating, and deleting Purview accounts.\n  tags:\n  - Microsoft\n  - Purview\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-purview\n    baseUri: https://management.azure.com\n    description: Microsoft Purview Account API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_PURVIEW_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}\n      operations:\n      - name: createorupdateaccount\n        method: PUT\n        description: Microsoft Purview Create\
  \ or update a Purview account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getaccount\n        method: GET\n        description: Microsoft Purview Get a Purview account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Microsoft Purview Update a Purview account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccount\n        method: DELETE\n        description: Microsoft Purview Delete a Purview account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts\n\
  \      operations:\n      - name: listaccountsbyresourcegroup\n        method: GET\n        description: Microsoft Purview List accounts by resource group\n        inputParameters:\n        - name: $skipToken\n          in: query\n          type: string\n          description: The skip token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/accounts\n      operations:\n      - name: listaccountsbysubscription\n        method: GET\n        description: Microsoft Purview List accounts by subscription\n        inputParameters:\n        - name: $skipToken\n          in: query\n          type: string\n          description: The skip token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/listkeys\n      operations:\n      - name: listaccountkeys\n        method: POST\n        description: Microsoft Purview List account keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/addRootCollectionAdmin\n      operations:\n      - name: addrootcollectionadmin\n        method: POST\n        description: Microsoft Purview Add root collection admin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n\
  \      path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/checkNameAvailability\n      operations:\n      - name: checknameavailability\n        method: POST\n        description: Microsoft Purview Check name availability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections\n      operations:\n      - name: listprivateendpointconnections\n        method: GET\n        description: Microsoft Purview List private endpoint connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections/{privateEndpointConnectionName}\n\
  \      operations:\n      - name: getprivateendpointconnection\n        method: GET\n        description: Microsoft Purview Get a private endpoint connection\n        inputParameters:\n        - name: privateEndpointConnectionName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers-microsoft-purview-operations\n      path: /providers/Microsoft.Purview/operations\n      operations:\n      - name: listoperations\n        method: GET\n        description: Microsoft Purview List available operations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-purview-rest\n    description: REST adapter for Microsoft Purview Account API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}\n\
  \      name: createorupdateaccount\n      operations:\n      - method: PUT\n        name: createorupdateaccount\n        description: Microsoft Purview Create or update a Purview account\n        call: microsoft-purview.createorupdateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Microsoft Purview Get a Purview account\n        call: microsoft-purview.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Microsoft Purview Update a Purview\
  \ account\n        call: microsoft-purview.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}\n      name: deleteaccount\n      operations:\n      - method: DELETE\n        name: deleteaccount\n        description: Microsoft Purview Delete a Purview account\n        call: microsoft-purview.deleteaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts\n      name: listaccountsbyresourcegroup\n      operations:\n      - method: GET\n        name: listaccountsbyresourcegroup\n        description: Microsoft Purview List accounts by resource group\n        call: microsoft-purview.listaccountsbyresourcegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/accounts\n      name: listaccountsbysubscription\n      operations:\n      - method: GET\n        name: listaccountsbysubscription\n        description: Microsoft Purview List accounts by subscription\n        call: microsoft-purview.listaccountsbysubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/listkeys\n      name: listaccountkeys\n      operations:\n      - method: POST\n        name: listaccountkeys\n        description: Microsoft Purview List account keys\n        call: microsoft-purview.listaccountkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/addRootCollectionAdmin\n      name: addrootcollectionadmin\n\
  \      operations:\n      - method: POST\n        name: addrootcollectionadmin\n        description: Microsoft Purview Add root collection admin\n        call: microsoft-purview.addrootcollectionadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Purview/checkNameAvailability\n      name: checknameavailability\n      operations:\n      - method: POST\n        name: checknameavailability\n        description: Microsoft Purview Check name availability\n        call: microsoft-purview.checknameavailability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections\n      name: listprivateendpointconnections\n      operations:\n      - method: GET\n        name: listprivateendpointconnections\n        description: Microsoft Purview\
  \ List private endpoint connections\n        call: microsoft-purview.listprivateendpointconnections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Purview/accounts/{accountName}/privateEndpointConnections/{privateEndpointConnectionName}\n      name: getprivateendpointconnection\n      operations:\n      - method: GET\n        name: getprivateendpointconnection\n        description: Microsoft Purview Get a private endpoint connection\n        call: microsoft-purview.getprivateendpointconnection\n        with:\n          privateEndpointConnectionName: rest.privateEndpointConnectionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /providers/Microsoft.Purview/operations\n      name: listoperations\n      operations:\n      - method: GET\n        name: listoperations\n        description: Microsoft Purview List available operations\n\
  \        call: microsoft-purview.listoperations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-purview-mcp\n    transport: http\n    description: MCP adapter for Microsoft Purview Account API for AI agent use.\n    tools:\n    - name: createorupdateaccount\n      description: Microsoft Purview Create or update a Purview account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.createorupdateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Microsoft Purview Get a Purview account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccount\n      description: Microsoft Purview Update a Purview account\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-purview.updateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaccount\n      description: Microsoft Purview Delete a Purview account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-purview.deleteaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccountsbyresourcegroup\n      description: Microsoft Purview List accounts by resource group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.listaccountsbyresourcegroup\n      with:\n        $skipToken: tools.$skipToken\n      inputParameters:\n      - name: $skipToken\n        type: string\n        description: The skip token for pagination\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listaccountsbysubscription\n      description: Microsoft Purview List accounts by subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.listaccountsbysubscription\n      with:\n        $skipToken: tools.$skipToken\n      inputParameters:\n      - name: $skipToken\n        type: string\n        description: The skip token for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccountkeys\n      description: Microsoft Purview List account keys\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-purview.listaccountkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addrootcollectionadmin\n      description: Microsoft Purview Add root collection admin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: microsoft-purview.addrootcollectionadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checknameavailability\n      description: Microsoft Purview Check name availability\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-purview.checknameavailability\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprivateendpointconnections\n      description: Microsoft Purview List private endpoint connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.listprivateendpointconnections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprivateendpointconnection\n      description: Microsoft Purview Get a private endpoint connection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.getprivateendpointconnection\n\
  \      with:\n        privateEndpointConnectionName: tools.privateEndpointConnectionName\n      inputParameters:\n      - name: privateEndpointConnectionName\n        type: string\n        description: privateEndpointConnectionName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoperations\n      description: Microsoft Purview List available operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-purview.listoperations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_PURVIEW_TOKEN: MICROSOFT_PURVIEW_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-purview/refs/heads/main/capabilities/microsoft-purview-capability.yaml
tags:
- Microsoft
- Purview
- API
tools:
- description: Microsoft Purview Create or update a Purview account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorupdateaccount
- description: Microsoft Purview Get a Purview account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Microsoft Purview Update a Purview account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Microsoft Purview Delete a Purview account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: Microsoft Purview List accounts by resource group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountsbyresourcegroup
- description: Microsoft Purview List accounts by subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountsbysubscription
- description: Microsoft Purview List account keys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listaccountkeys
- description: Microsoft Purview Add root collection admin
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addrootcollectionadmin
- description: Microsoft Purview Check name availability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checknameavailability
- description: Microsoft Purview List private endpoint connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprivateendpointconnections
- description: Microsoft Purview Get a private endpoint connection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprivateendpointconnection
- description: Microsoft Purview List available operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperations
---
