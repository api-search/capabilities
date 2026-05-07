---
categories: []
consumed_apis: []
description: Create and manage action groups that define notification and automation actions triggered by Azure Monitor alerts, including email, SMS, webhooks, and Azure Functions.
layout: capability
name: Azure Monitor Action Groups API
operations:
- description: Azure Monitor Create or update an action group
  method: PUT
  name: actiongroups-createorupdate
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}
- description: Azure Monitor Get an action group
  method: GET
  name: actiongroups-get
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}
- description: Azure Monitor Delete an action group
  method: DELETE
  name: actiongroups-delete
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}
- description: Azure Monitor Update an action group
  method: PATCH
  name: actiongroups-update
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}
- description: Azure Monitor List action groups in a subscription
  method: GET
  name: actiongroups-listbysubscriptionid
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/actionGroups
- description: Azure Monitor List action groups in a resource group
  method: GET
  name: actiongroups-listbyresourcegroup
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups
- description: Azure Monitor Enable a receiver in an action group
  method: POST
  name: actiongroups-enablereceiver
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}/subscribe
- description: Azure Monitor Send test notifications
  method: POST
  name: actiongroups-posttestnotifications
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/createNotifications
- description: Azure Monitor Get test notification results
  method: GET
  name: actiongroups-gettestnotifications
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/notificationStatus/{notificationId}
personas: []
provider_name: Azure Monitor
provider_slug: microsoft-azure-monitor
search_terms:
- actiongroups enablereceiver
- actiongroups gettestnotifications
- azure monitor update an action group
- api
- actiongroups get
- actiongroups createorupdate
- azure monitor create or update an action group
- monitoring
- azure monitor get test notification results
- azure monitor enable a receiver in an action group
- monitor
- microsoft
- logs
- azure monitor delete an action group
- actiongroups listbyresourcegroup
- azure monitor get an action group
- azure monitor list action groups in a resource group
- observability
- cloud
- azure monitor send test notifications
- metrics
- actiongroups update
- azure
- azure monitor list action groups in a subscription
- application insights
- actiongroups posttestnotifications
- actiongroups delete
- actiongroups listbysubscriptionid
slug: microsoft-azure-monitor-capability
source_filename: microsoft-azure-monitor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Monitor Action Groups API\n  description: Create and manage action groups that define notification and automation actions triggered by Azure Monitor\n    alerts, including email, SMS, webhooks, and Azure Functions.\n  tags:\n  - Microsoft\n  - Azure\n  - Monitor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-monitor\n    baseUri: https://management.azure.com\n    description: Azure Monitor Action Groups API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_MONITOR_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}\n      operations:\n      - name: actiongroups-createorupdate\n        method: PUT\n        description: Azure Monitor Create\
  \ or update an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: actiongroups-get\n        method: GET\n        description: Azure Monitor Get an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: actiongroups-delete\n        method: DELETE\n        description: Azure Monitor Delete an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: actiongroups-update\n        method: PATCH\n        description: Azure Monitor Update an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/actionGroups\n\
  \      operations:\n      - name: actiongroups-listbysubscriptionid\n        method: GET\n        description: Azure Monitor List action groups in a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups\n      operations:\n      - name: actiongroups-listbyresourcegroup\n        method: GET\n        description: Azure Monitor List action groups in a resource group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}/subscribe\n      operations:\n    \
  \  - name: actiongroups-enablereceiver\n        method: POST\n        description: Azure Monitor Enable a receiver in an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/createNotifications\n      operations:\n      - name: actiongroups-posttestnotifications\n        method: POST\n        description: Azure Monitor Send test notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/notificationStatus/{notificationId}\n      operations:\n      - name: actiongroups-gettestnotifications\n        method: GET\n        description: Azure Monitor Get test\
  \ notification results\n        inputParameters:\n        - name: notificationId\n          in: path\n          type: string\n          required: true\n          description: The notification ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-monitor-rest\n    description: REST adapter for Azure Monitor Action Groups API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}\n      name: actiongroups-createorupdate\n      operations:\n      - method: PUT\n        name: actiongroups-createorupdate\n        description: Azure Monitor Create or update an action group\n        call: microsoft-azure-monitor.actiongroups-createorupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}\n\
  \      name: actiongroups-get\n      operations:\n      - method: GET\n        name: actiongroups-get\n        description: Azure Monitor Get an action group\n        call: microsoft-azure-monitor.actiongroups-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}\n      name: actiongroups-delete\n      operations:\n      - method: DELETE\n        name: actiongroups-delete\n        description: Azure Monitor Delete an action group\n        call: microsoft-azure-monitor.actiongroups-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}\n      name: actiongroups-update\n      operations:\n      - method: PATCH\n        name: actiongroups-update\n        description:\
  \ Azure Monitor Update an action group\n        call: microsoft-azure-monitor.actiongroups-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/actionGroups\n      name: actiongroups-listbysubscriptionid\n      operations:\n      - method: GET\n        name: actiongroups-listbysubscriptionid\n        description: Azure Monitor List action groups in a subscription\n        call: microsoft-azure-monitor.actiongroups-listbysubscriptionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups\n      name: actiongroups-listbyresourcegroup\n      operations:\n      - method: GET\n        name: actiongroups-listbyresourcegroup\n        description: Azure Monitor List action groups in a resource group\n        call: microsoft-azure-monitor.actiongroups-listbyresourcegroup\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Insights/actionGroups/{actionGroupName}/subscribe\n      name: actiongroups-enablereceiver\n      operations:\n      - method: POST\n        name: actiongroups-enablereceiver\n        description: Azure Monitor Enable a receiver in an action group\n        call: microsoft-azure-monitor.actiongroups-enablereceiver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/createNotifications\n      name: actiongroups-posttestnotifications\n      operations:\n      - method: POST\n        name: actiongroups-posttestnotifications\n        description: Azure Monitor Send test notifications\n        call: microsoft-azure-monitor.actiongroups-posttestnotifications\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Insights/notificationStatus/{notificationId}\n      name: actiongroups-gettestnotifications\n      operations:\n      - method: GET\n        name: actiongroups-gettestnotifications\n        description: Azure Monitor Get test notification results\n        call: microsoft-azure-monitor.actiongroups-gettestnotifications\n        with:\n          notificationId: rest.notificationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-monitor-mcp\n    transport: http\n    description: MCP adapter for Azure Monitor Action Groups API for AI agent use.\n    tools:\n    - name: actiongroups-createorupdate\n      description: Azure Monitor Create or update an action group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-createorupdate\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: actiongroups-get\n      description: Azure Monitor Get an action group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-delete\n      description: Azure Monitor Delete an action group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-update\n      description: Azure Monitor Update an action group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-monitor.actiongroups-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-listbysubscriptionid\n\
  \      description: Azure Monitor List action groups in a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-listbysubscriptionid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-listbyresourcegroup\n      description: Azure Monitor List action groups in a resource group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-listbyresourcegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-enablereceiver\n      description: Azure Monitor Enable a receiver in an action group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-monitor.actiongroups-enablereceiver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ actiongroups-posttestnotifications\n      description: Azure Monitor Send test notifications\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-monitor.actiongroups-posttestnotifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: actiongroups-gettestnotifications\n      description: Azure Monitor Get test notification results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-monitor.actiongroups-gettestnotifications\n      with:\n        notificationId: tools.notificationId\n      inputParameters:\n      - name: notificationId\n        type: string\n        description: The notification ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_MONITOR_TOKEN: MICROSOFT_AZURE_MONITOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-monitor/refs/heads/main/capabilities/microsoft-azure-monitor-capability.yaml
tags:
- Microsoft
- Azure
- Monitor
- API
tools:
- description: Azure Monitor Create or update an action group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: actiongroups-createorupdate
- description: Azure Monitor Get an action group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actiongroups-get
- description: Azure Monitor Delete an action group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: actiongroups-delete
- description: Azure Monitor Update an action group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: actiongroups-update
- description: Azure Monitor List action groups in a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actiongroups-listbysubscriptionid
- description: Azure Monitor List action groups in a resource group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actiongroups-listbyresourcegroup
- description: Azure Monitor Enable a receiver in an action group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: actiongroups-enablereceiver
- description: Azure Monitor Send test notifications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: actiongroups-posttestnotifications
- description: Azure Monitor Get test notification results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actiongroups-gettestnotifications
---
