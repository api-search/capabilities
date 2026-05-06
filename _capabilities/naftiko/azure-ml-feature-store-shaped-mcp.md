---
categories: []
consumed_apis: []
description: A capability over Azure Machine Learning feature store, exposing typed feature retrieval as a shaped MCP tool.
layout: capability
name: Azure Ml Feature Store Shaped Mcp
operations:
- description: ''
  method: GET
  name: list-feature-stores
  path: /feature-stores
- description: ''
  method: GET
  name: get-feature-set
  path: /feature-sets/{{name}}/{{version}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list feature stores
- get feature set
- feature store
- api integration
- governance
- spec-driven integration
- ai
- mcp
- azure ml
- capabilities
slug: azure-ml-feature-store-shaped-mcp
source_filename: azure-ml-feature-store-shaped-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Azure Ml Feature Store Shaped Mcp\n  description: A capability over Azure Machine Learning feature store, exposing typed feature retrieval as a shaped MCP tool.\n  tags: [Naftiko, Azure ML, Feature Store]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: azureml-env\n  keys: {AZUREML_TOKEN: AZUREML_TOKEN, AZUREML_SUBSCRIPTION: AZUREML_SUBSCRIPTION, AZUREML_RESOURCE_GROUP: AZUREML_RESOURCE_GROUP, AZUREML_WORKSPACE: AZUREML_WORKSPACE}\ncapability:\n  consumes:\n  - namespace: azureml\n    type: http\n    baseUri: https://management.azure.com\n    authentication: {type: bearer, token: '{{AZUREML_TOKEN}}'}\n    resources:\n    - name: feature-stores\n      path: /subscriptions/{{AZUREML_SUBSCRIPTION}}/resourceGroups/{{AZUREML_RESOURCE_GROUP}}/providers/Microsoft.MachineLearningServices/workspaces/{{AZUREML_WORKSPACE}}/featurestores\n      operations: [{name: list-feature-stores, method: GET}]\n    - name: feature-set\n\
  \      path: /subscriptions/{{AZUREML_SUBSCRIPTION}}/resourceGroups/{{AZUREML_RESOURCE_GROUP}}/providers/Microsoft.MachineLearningServices/workspaces/{{AZUREML_WORKSPACE}}/featuresets/{{name}}/versions/{{version}}\n      operations:\n      - {name: get-feature-set, method: GET, inputParameters: [{name: name, in: path}, {name: version, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: azure-ml-feature-store-shaped-mcp-rest\n    description: REST surface for typed Azure ML feature-set access.\n    resources:\n    - {name: feature-stores, path: /feature-stores, operations: [{method: GET, name: list-feature-stores, call: azureml.list-feature-stores}]}\n    - name: feature-set\n      path: /feature-sets/{{name}}/{{version}}\n      operations:\n      - method: GET\n        name: get-feature-set\n        inputParameters: [{name: name, in: path, type: string}, {name: version, in: path, type: string}]\n        call: azureml.get-feature-set\n  - type:\
  \ mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: azure-ml-feature-store-shaped-mcp-mcp\n    description: MCP for typed Azure ML feature-store access.\n    tools:\n    - {name: list-feature-stores, hints: {readOnly: true}, call: azureml.list-feature-stores}\n    - name: get-feature-set\n      hints: {readOnly: true}\n      inputParameters: [{name: name, type: string, required: true}, {name: version, type: string, required: true}]\n      call: azureml.get-feature-set\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: azure-ml-feature-store-shaped-mcp-skills\n    description: Skill bundle for Azure ML feature store.\n    skills:\n    - name: azure-ml-feature-store-shaped-mcp\n      description: Typed Azure ML feature-set retrieval.\n      location: file:///opt/naftiko/skills/azure-ml-feature-store-shaped-mcp\n      allowed-tools: list-feature-stores,get-feature-set\n      tools:\n      - {name: list-feature-stores, from: {sourceNamespace: azure-ml-feature-store-shaped-mcp-mcp,\
  \ action: list-feature-stores}}\n      - {name: get-feature-set, from: {sourceNamespace: azure-ml-feature-store-shaped-mcp-mcp, action: get-feature-set}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/azure-ml-feature-store-shaped-mcp.yaml
tags:
- Naftiko
- Azure ML
- Feature Store
tools:
- description: ''
  hints:
    readOnly: true
  name: list-feature-stores
- description: ''
  hints:
    readOnly: true
  name: get-feature-set
---
