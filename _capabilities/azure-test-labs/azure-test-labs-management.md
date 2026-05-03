---
api_specs:
- filename: azure-test-labs-openapi.yaml
  format: yaml
  label: azure-test-labs
  slug: azure-test-labs
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-test-labs/refs/heads/main/openapi/azure-test-labs-openapi.yaml
categories: []
consumed_apis:
- azure-test-labs
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
- infrastructure
- testing
- labs
- list formula resources
- list lab resources
- list all resources
- cloud
- list environment resources
- virtual machines
- list virtualmachine resources
- list virtual machines
- azure
- list environments
- list custom images
- management
- resource management
- list
- list customimage resources
- azure resource management
- development
- list labs
- list formulas
slug: azure-test-labs-management
source_filename: azure-test-labs-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure DevTest Labs Management\"\n  description: \"Workflow capability for managing Azure DevTest Labs resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-test-labs\n      location: ./shared/azure-test-labs.yaml\n\n  exposes:\n    - type: rest\n      port: 8088\n      namespace: azure-test-labs-management-api\n      description: \"Unified REST API for Azure DevTest Labs management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\n   \
  \           call: \"azure-test-labs.list-labs\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9098\n      namespace: azure-test-labs-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure DevTest Labs management.\"\n      tools:\n        - name: list-labs\n          description: \"List Lab resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-test-labs.list-labs\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-virtual-machines\n          description: \"List VirtualMachine resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-test-labs.list-virtual-machines\"\
  \n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: \"List Environment resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-test-labs.list-environments\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-formulas\n          description: \"List Formula resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-test-labs.list-formulas\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-images\n          description: \"List CustomImage resources\"\n \
  \         hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-test-labs.list-custom-images\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
