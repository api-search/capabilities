---
categories: []
consumed_apis: []
description: Workflow capability for managing Azure DevOps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure DevOps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure DevOps
provider_slug: azure-dev-ops
search_terms:
- azure resource management
- resource management
- list
- devops
- list organization resources
- ci/cd
- list repositorys
- project management
- list repository resources
- list projects
- list pipelines
- list project resources
- management
- list organizations
- list all resources
- cloud
- version control
- list pipeline resources
- azure
slug: azure-dev-ops-management
source_filename: azure-dev-ops-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure DevOps Management\n  description: Workflow capability for managing Azure DevOps resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-dev-ops\n    baseUri: https://management.azure.com\n    description: Azure DevOps REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: pipeline\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Pipeline/Pipelines\n      description: Manage Pipeline resources\n      operations:\n      - name: list-pipelines\n        method: GET\n        description: List all Pipeline resources\n        inputParameters:\n        - name: subscriptionId\n\
  \          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Project/Projects\n      description: Manage Project resources\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all Project resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Organization/Organizations\n      description: Manage Organization resources\n      operations:\n \
  \     - name: list-organizations\n        method: GET\n        description: List all Organization resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Repository/Repositorys\n      description: Manage Repository resources\n      operations:\n      - name: list-repositorys\n        method: GET\n        description: List all Repository resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8083\n    namespace: azure-dev-ops-management-api\n    description: Unified REST API for Azure DevOps management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-dev-ops.list-pipelines\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: azure-dev-ops-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure DevOps management.\n    tools:\n    - name: list-pipelines\n      description: List Pipeline resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-dev-ops.list-pipelines\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-projects\n      description: List Project resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-dev-ops.list-projects\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organizations\n      description: List Organization resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-dev-ops.list-organizations\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repositorys\n      description: List Repository resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-dev-ops.list-repositorys\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-dev-ops/refs/heads/main/capabilities/azure-dev-ops-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Pipeline resources
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: List Project resources
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List Organization resources
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List Repository resources
  hints:
    openWorld: true
    readOnly: true
  name: list-repositorys
---
