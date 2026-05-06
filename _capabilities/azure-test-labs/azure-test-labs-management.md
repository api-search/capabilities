---
categories: []
consumed_apis: []
description: Workflow capability for managing Azure DevTest Labs resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure DevTest Labs Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure DevTest Labs
provider_slug: azure-test-labs
search_terms:
- list virtual machines
- list all resources
- labs
- list environments
- list lab resources
- list custom images
- infrastructure
- virtual machines
- azure
- cloud
- list virtualmachine resources
- development
- list environment resources
- list formulas
- azure resource management
- list formula resources
- list
- list labs
- list customimage resources
- management
- testing
- resource management
slug: azure-test-labs-management
source_filename: azure-test-labs-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure DevTest Labs Management\n  description: Workflow capability for managing Azure DevTest Labs resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-test-labs\n    baseUri: https://management.azure.com\n    description: Azure DevTest Labs REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: lab\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Lab/Labs\n      description: Manage Lab resources\n      operations:\n      - name: list-labs\n        method: GET\n        description: List all Lab resources\n        inputParameters:\n        - name: subscriptionId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-machine\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.VirtualMachine/VirtualMachines\n      description: Manage VirtualMachine resources\n      operations:\n      - name: list-virtual-machines\n        method: GET\n        description: List all VirtualMachine resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environment\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Environment/Environments\n      description: Manage Environment resources\n\
  \      operations:\n      - name: list-environments\n        method: GET\n        description: List all Environment resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: formula\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Formula/Formulas\n      description: Manage Formula resources\n      operations:\n      - name: list-formulas\n        method: GET\n        description: List all Formula resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: custom-image\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.CustomImage/CustomImages\n      description: Manage CustomImage resources\n      operations:\n      - name: list-custom-images\n        method: GET\n        description: List all CustomImage resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8088\n    namespace: azure-test-labs-management-api\n    description: Unified REST API for Azure DevTest Labs management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-test-labs.list-labs\n \
  \       with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9098\n    namespace: azure-test-labs-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure DevTest Labs management.\n    tools:\n    - name: list-labs\n      description: List Lab resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-test-labs.list-labs\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-machines\n      description: List VirtualMachine resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-test-labs.list-virtual-machines\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List Environment\
  \ resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-test-labs.list-environments\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-formulas\n      description: List Formula resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-test-labs.list-formulas\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-images\n      description: List CustomImage resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-test-labs.list-custom-images\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-test-labs/refs/heads/main/capabilities/azure-test-labs-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Lab resources
  hints:
    openWorld: true
    readOnly: true
  name: list-labs
- description: List VirtualMachine resources
  hints:
    openWorld: true
    readOnly: true
  name: list-virtual-machines
- description: List Environment resources
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List Formula resources
  hints:
    openWorld: true
    readOnly: true
  name: list-formulas
- description: List CustomImage resources
  hints:
    openWorld: true
    readOnly: true
  name: list-custom-images
---
