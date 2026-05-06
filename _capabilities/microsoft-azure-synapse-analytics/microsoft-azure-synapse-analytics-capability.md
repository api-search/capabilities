---
categories: []
consumed_apis: []
description: Manage role assignments, role definitions, and access control for Synapse workspace resources. Supports Synapse role-based access control for fine-grained permissions.
layout: capability
name: Azure Synapse Analytics - Access Control API
operations:
- description: Azure Synapse Analytics List role assignments
  method: GET
  name: roleassignments-listroleassignments
  path: /roleAssignments
- description: Azure Synapse Analytics Get role assignment
  method: GET
  name: roleassignments-getroleassignmentbyid
  path: /roleAssignments/{roleAssignmentId}
- description: Azure Synapse Analytics Create role assignment
  method: PUT
  name: roleassignments-createroleassignment
  path: /roleAssignments/{roleAssignmentId}
- description: Azure Synapse Analytics Delete role assignment
  method: DELETE
  name: roleassignments-deleteroleassignmentbyid
  path: /roleAssignments/{roleAssignmentId}
personas: []
provider_name: Azure Synapse Analytics
provider_slug: microsoft-azure-synapse-analytics
search_terms:
- roleassignments listroleassignments
- data integration
- analytics
- big data
- azure synapse analytics get role assignment
- azure
- apache spark
- azure synapse analytics create role assignment
- etl
- synapse
- sql
- data warehouse
- roleassignments deleteroleassignmentbyid
- roleassignments createroleassignment
- azure synapse analytics list role assignments
- api
- roleassignments getroleassignmentbyid
- microsoft
- azure synapse analytics delete role assignment
slug: microsoft-azure-synapse-analytics-capability
source_filename: microsoft-azure-synapse-analytics-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Synapse Analytics - Access Control API\n  description: Manage role assignments, role definitions, and access control for Synapse workspace resources. Supports Synapse\n    role-based access control for fine-grained permissions.\n  tags:\n  - Microsoft\n  - Azure\n  - Synapse\n  - Analytics\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-synapse-analytics\n    baseUri: https://myworkspace.dev.azuresynapse.net\n    description: Azure Synapse Analytics - Access Control API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_SYNAPSE_ANALYTICS_TOKEN}}'\n    resources:\n    - name: roleassignments\n      path: /roleAssignments\n      operations:\n      - name: roleassignments-listroleassignments\n        method: GET\n        description: Azure Synapse Analytics List role assignments\n        inputParameters:\n        -\
  \ name: roleId\n          in: query\n          type: string\n          description: Synapse Built-In Role Id.\n        - name: principalId\n          in: query\n          type: string\n          description: Object ID of the AAD principal or security-group.\n        - name: scope\n          in: query\n          type: string\n          description: Scope of the Synapse Built-In Role.\n        - name: x-ms-continuation\n          in: header\n          type: string\n          description: Continuation token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roleassignments-roleassignmentid\n      path: /roleAssignments/{roleAssignmentId}\n      operations:\n      - name: roleassignments-getroleassignmentbyid\n        method: GET\n        description: Azure Synapse Analytics Get role assignment\n        inputParameters:\n        - name: roleAssignmentId\n          in: path\n          type: string\n  \
  \        required: true\n          description: The ID of the role assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: roleassignments-createroleassignment\n        method: PUT\n        description: Azure Synapse Analytics Create role assignment\n        inputParameters:\n        - name: roleAssignmentId\n          in: path\n          type: string\n          required: true\n          description: The ID of the role assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: roleassignments-deleteroleassignmentbyid\n        method: DELETE\n        description: Azure Synapse Analytics Delete role assignment\n        inputParameters:\n        - name: roleAssignmentId\n          in: path\n          type: string\n          required: true\n        - name: scope\n          in: query\n          type:\
  \ string\n          description: Scope of the Synapse Built-In Role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-synapse-analytics-rest\n    description: REST adapter for Azure Synapse Analytics - Access Control API.\n    resources:\n    - path: /roleAssignments\n      name: roleassignments-listroleassignments\n      operations:\n      - method: GET\n        name: roleassignments-listroleassignments\n        description: Azure Synapse Analytics List role assignments\n        call: microsoft-azure-synapse-analytics.roleassignments-listroleassignments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roleAssignments/{roleAssignmentId}\n      name: roleassignments-getroleassignmentbyid\n      operations:\n      - method: GET\n        name: roleassignments-getroleassignmentbyid\n        description:\
  \ Azure Synapse Analytics Get role assignment\n        call: microsoft-azure-synapse-analytics.roleassignments-getroleassignmentbyid\n        with:\n          roleAssignmentId: rest.roleAssignmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roleAssignments/{roleAssignmentId}\n      name: roleassignments-createroleassignment\n      operations:\n      - method: PUT\n        name: roleassignments-createroleassignment\n        description: Azure Synapse Analytics Create role assignment\n        call: microsoft-azure-synapse-analytics.roleassignments-createroleassignment\n        with:\n          roleAssignmentId: rest.roleAssignmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roleAssignments/{roleAssignmentId}\n      name: roleassignments-deleteroleassignmentbyid\n      operations:\n      - method: DELETE\n        name: roleassignments-deleteroleassignmentbyid\n        description: Azure Synapse Analytics\
  \ Delete role assignment\n        call: microsoft-azure-synapse-analytics.roleassignments-deleteroleassignmentbyid\n        with:\n          roleAssignmentId: rest.roleAssignmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-synapse-analytics-mcp\n    transport: http\n    description: MCP adapter for Azure Synapse Analytics - Access Control API for AI agent use.\n    tools:\n    - name: roleassignments-listroleassignments\n      description: Azure Synapse Analytics List role assignments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-synapse-analytics.roleassignments-listroleassignments\n      with:\n        roleId: tools.roleId\n        principalId: tools.principalId\n        scope: tools.scope\n      inputParameters:\n      - name: roleId\n        type: string\n        description: Synapse Built-In Role Id.\n      - name:\
  \ principalId\n        type: string\n        description: Object ID of the AAD principal or security-group.\n      - name: scope\n        type: string\n        description: Scope of the Synapse Built-In Role.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: roleassignments-getroleassignmentbyid\n      description: Azure Synapse Analytics Get role assignment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-synapse-analytics.roleassignments-getroleassignmentbyid\n      with:\n        roleAssignmentId: tools.roleAssignmentId\n      inputParameters:\n      - name: roleAssignmentId\n        type: string\n        description: The ID of the role assignment.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: roleassignments-createroleassignment\n      description: Azure Synapse Analytics Create role assignment\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-synapse-analytics.roleassignments-createroleassignment\n      with:\n        roleAssignmentId: tools.roleAssignmentId\n      inputParameters:\n      - name: roleAssignmentId\n        type: string\n        description: The ID of the role assignment.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: roleassignments-deleteroleassignmentbyid\n      description: Azure Synapse Analytics Delete role assignment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-synapse-analytics.roleassignments-deleteroleassignmentbyid\n      with:\n        roleAssignmentId: tools.roleAssignmentId\n        scope: tools.scope\n      inputParameters:\n      - name: roleAssignmentId\n        type: string\n        description: roleAssignmentId\n        required: true\n      - name: scope\n        type:\
  \ string\n        description: Scope of the Synapse Built-In Role.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_SYNAPSE_ANALYTICS_TOKEN: MICROSOFT_AZURE_SYNAPSE_ANALYTICS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-synapse-analytics/refs/heads/main/capabilities/microsoft-azure-synapse-analytics-capability.yaml
tags:
- Microsoft
- Azure
- Synapse
- Analytics
- API
tools:
- description: Azure Synapse Analytics List role assignments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: roleassignments-listroleassignments
- description: Azure Synapse Analytics Get role assignment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: roleassignments-getroleassignmentbyid
- description: Azure Synapse Analytics Create role assignment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: roleassignments-createroleassignment
- description: Azure Synapse Analytics Delete role assignment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: roleassignments-deleteroleassignmentbyid
---
