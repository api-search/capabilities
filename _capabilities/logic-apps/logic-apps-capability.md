---
categories: []
consumed_apis: []
description: The Azure Logic Apps Management REST API exposes operations for managing workflows, runs, triggers, versions and integration accounts in the multitenant (Consumption) Logic Apps service. Operations are reached via the Azure Resource Manager endpoint and require an Azure AD bearer token along with subscription-scoped resource group and workflow path parameters.
layout: capability
name: Azure Logic Apps Management API
operations:
- description: List workflows by subscription
  method: GET
  name: listworkflowsbysubscription
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Logic/workflows
- description: List workflows by resource group
  method: GET
  name: listworkflowsbyresourcegroup
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows
- description: Get a workflow
  method: GET
  name: getworkflow
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}
- description: Create or update a workflow
  method: PUT
  name: createorupdateworkflow
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}
- description: Delete a workflow
  method: DELETE
  name: deleteworkflow
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}
- description: Disable a workflow
  method: POST
  name: disableworkflow
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/disable
- description: Enable a workflow
  method: POST
  name: enableworkflow
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/enable
- description: List workflow runs
  method: GET
  name: listworkflowruns
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs
- description: Get a workflow run
  method: GET
  name: getworkflowrun
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}
- description: Cancel a workflow run
  method: POST
  name: cancelworkflowrun
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}/cancel
- description: List workflow triggers
  method: GET
  name: listworkflowtriggers
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers
- description: Run a workflow trigger
  method: POST
  name: runworkflowtrigger
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers/{triggerName}/run
- description: List workflow versions
  method: GET
  name: listworkflowversions
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/versions
personas: []
provider_name: Azure Logic Apps
provider_slug: logic-apps
search_terms:
- getworkflowrun
- create or update a workflow
- list workflow runs
- delete a workflow
- disableworkflow
- workflow automation
- cancel a workflow run
- listworkflowruns
- api
- deleteworkflow
- get a workflow run
- listworkflowversions
- list workflow versions
- enableworkflow
- list workflow triggers
- integration
- microsoft
- logic
- list workflows by subscription
- listworkflowtriggers
- enable a workflow
- getworkflow
- listworkflowsbysubscription
- apps
- ipaas
- enterprise
- listworkflowsbyresourcegroup
- list workflows by resource group
- get a workflow
- azure
- run a workflow trigger
- disable a workflow
- runworkflowtrigger
- createorupdateworkflow
- cancelworkflowrun
slug: logic-apps-capability
source_filename: logic-apps-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Logic Apps Management API\n  description: The Azure Logic Apps Management REST API exposes operations for managing workflows, runs, triggers, versions\n    and integration accounts in the multitenant (Consumption) Logic Apps service. Operations are reached via the Azure Resource\n    Manager endpoint and require an Azure AD bearer token along with subscription-scoped resource group and workflow path\n    parameters.\n  tags:\n  - Logic\n  - Apps\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: logic-apps\n    baseUri: https://management.azure.com\n    description: Azure Logic Apps Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LOGIC_APPS_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Logic/workflows\n      operations:\n   \
  \   - name: listworkflowsbysubscription\n        method: GET\n        description: List workflows by subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows\n      operations:\n      - name: listworkflowsbyresourcegroup\n        method: GET\n        description: List workflows by resource group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Get a workflow\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdateworkflow\n        method: PUT\n        description: Create or update a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflow\n        method: DELETE\n        description: Delete a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/disable\n      operations:\n      - name: disableworkflow\n        method: POST\n        description: Disable a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/enable\n      operations:\n      - name: enableworkflow\n        method: POST\n        description: Enable a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs\n      operations:\n      - name: listworkflowruns\n        method: GET\n        description: List workflow runs\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          description: The maximum number of runs to return.\n        - name: $filter\n          in: query\n          type: string\n          description: OData\
  \ filter expression for run status, time, etc.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}\n      operations:\n      - name: getworkflowrun\n        method: GET\n        description: Get a workflow run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}/cancel\n      operations:\n      - name: cancelworkflowrun\n        method: POST\n        description: Cancel a workflow run\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers\n      operations:\n      - name: listworkflowtriggers\n        method: GET\n        description: List workflow triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers/{triggerName}/run\n      operations:\n      - name: runworkflowtrigger\n        method: POST\n        description: Run a workflow trigger\n        inputParameters:\n        - name: triggerName\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/versions\n      operations:\n      - name: listworkflowversions\n        method: GET\n        description: List workflow versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: logic-apps-rest\n    description: REST adapter for Azure Logic Apps Management API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Logic/workflows\n      name: listworkflowsbysubscription\n      operations:\n      - method: GET\n        name: listworkflowsbysubscription\n        description: List workflows by subscription\n        call: logic-apps.listworkflowsbysubscription\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows\n      name: listworkflowsbyresourcegroup\n      operations:\n      - method: GET\n        name: listworkflowsbyresourcegroup\n        description: List workflows by resource group\n        call: logic-apps.listworkflowsbyresourcegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Get a workflow\n        call: logic-apps.getworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}\n\
  \      name: createorupdateworkflow\n      operations:\n      - method: PUT\n        name: createorupdateworkflow\n        description: Create or update a workflow\n        call: logic-apps.createorupdateworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}\n      name: deleteworkflow\n      operations:\n      - method: DELETE\n        name: deleteworkflow\n        description: Delete a workflow\n        call: logic-apps.deleteworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/disable\n      name: disableworkflow\n      operations:\n      - method: POST\n        name: disableworkflow\n        description: Disable a workflow\n        call: logic-apps.disableworkflow\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/enable\n      name: enableworkflow\n      operations:\n      - method: POST\n        name: enableworkflow\n        description: Enable a workflow\n        call: logic-apps.enableworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs\n      name: listworkflowruns\n      operations:\n      - method: GET\n        name: listworkflowruns\n        description: List workflow runs\n        call: logic-apps.listworkflowruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}\n\
  \      name: getworkflowrun\n      operations:\n      - method: GET\n        name: getworkflowrun\n        description: Get a workflow run\n        call: logic-apps.getworkflowrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/runs/{runName}/cancel\n      name: cancelworkflowrun\n      operations:\n      - method: POST\n        name: cancelworkflowrun\n        description: Cancel a workflow run\n        call: logic-apps.cancelworkflowrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers\n      name: listworkflowtriggers\n      operations:\n      - method: GET\n        name: listworkflowtriggers\n        description: List workflow triggers\n        call: logic-apps.listworkflowtriggers\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/triggers/{triggerName}/run\n      name: runworkflowtrigger\n      operations:\n      - method: POST\n        name: runworkflowtrigger\n        description: Run a workflow trigger\n        call: logic-apps.runworkflowtrigger\n        with:\n          triggerName: rest.triggerName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Logic/workflows/{workflowName}/versions\n      name: listworkflowversions\n      operations:\n      - method: GET\n        name: listworkflowversions\n        description: List workflow versions\n        call: logic-apps.listworkflowversions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: logic-apps-mcp\n    transport: http\n    description: MCP adapter for Azure Logic Apps Management API for AI agent use.\n    tools:\n    - name: listworkflowsbysubscription\n      description: List workflows by subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.listworkflowsbysubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkflowsbyresourcegroup\n      description: List workflows by resource group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.listworkflowsbyresourcegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflow\n      description: Get a workflow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.getworkflow\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: createorupdateworkflow\n      description: Create or update a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: logic-apps.createorupdateworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkflow\n      description: Delete a workflow\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: logic-apps.deleteworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disableworkflow\n      description: Disable a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logic-apps.disableworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enableworkflow\n      description: Enable a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: logic-apps.enableworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkflowruns\n      description: List workflow runs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.listworkflowruns\n      with:\n        $top: tools.$top\n        $filter: tools.$filter\n      inputParameters:\n      - name: $top\n        type: integer\n        description: The maximum number of runs to return.\n      - name: $filter\n        type: string\n        description: OData filter expression for run status, time, etc.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflowrun\n      description: Get a workflow run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.getworkflowrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelworkflowrun\n\
  \      description: Cancel a workflow run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logic-apps.cancelworkflowrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkflowtriggers\n      description: List workflow triggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.listworkflowtriggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runworkflowtrigger\n      description: Run a workflow trigger\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logic-apps.runworkflowtrigger\n      with:\n        triggerName: tools.triggerName\n      inputParameters:\n      - name: triggerName\n        type: string\n        description: triggerName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listworkflowversions\n      description: List workflow versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logic-apps.listworkflowversions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LOGIC_APPS_TOKEN: LOGIC_APPS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/logic-apps/refs/heads/main/capabilities/logic-apps-capability.yaml
tags:
- Logic
- Apps
- API
tools:
- description: List workflows by subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowsbysubscription
- description: List workflows by resource group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowsbyresourcegroup
- description: Get a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Create or update a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorupdateworkflow
- description: Delete a workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkflow
- description: Disable a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: disableworkflow
- description: Enable a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enableworkflow
- description: List workflow runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowruns
- description: Get a workflow run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowrun
- description: Cancel a workflow run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelworkflowrun
- description: List workflow triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowtriggers
- description: Run a workflow trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runworkflowtrigger
- description: List workflow versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowversions
---
