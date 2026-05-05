---
categories: []
consumed_apis: []
description: A capability that mirrors Azure DevOps build pipelines into Backstage as TechDocs entities, so platform engineers can browse pipelines without leaving the developer portal.
layout: capability
name: Azure Devops Pipeline To Backstage Entity
operations:
- description: Pull all Azure DevOps pipelines and upsert as Backstage entities.
  method: POST
  name: sync-pipelines
  path: /sync
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- pull all azure devops pipelines and upsert as backstage entities.
- backstage
- spec-driven integration
- azure devops
- mcp
- capabilities
- naftiko
- sync pipelines
- api integration
- list azdo pipelines
- governance
- ai
slug: azure-devops-pipeline-to-backstage-entity
source_filename: azure-devops-pipeline-to-backstage-entity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Azure Devops Pipeline To Backstage Entity\n  description: A capability that mirrors Azure DevOps build pipelines into Backstage as TechDocs entities, so platform engineers can browse pipelines without leaving the developer portal.\n  tags: [Naftiko, Azure DevOps, Backstage]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: azuredevops-env\n  keys: {AZDO_ORG: AZDO_ORG, AZDO_PROJECT: AZDO_PROJECT, AZDO_TOKEN: AZDO_TOKEN}\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: azuredevops\n    type: http\n    baseUri: https://dev.azure.com\n    authentication: {type: bearer, token: '{{AZDO_TOKEN}}'}\n    resources:\n    - name: pipelines\n      path: /{{AZDO_ORG}}/{{AZDO_PROJECT}}/_apis/pipelines\n      operations: [{name: list-pipelines, method: GET}]\n    - name: pipeline\n      path: /{{AZDO_ORG}}/{{AZDO_PROJECT}}/_apis/pipelines/{{pipeline_id}}\n\
  \      operations:\n      - {name: get-pipeline, method: GET, inputParameters: [{name: pipeline_id, in: path}]}\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: catalog-entities, path: /api/catalog/entities, operations: [{name: upsert-entity, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: azure-devops-pipeline-to-backstage-entity-rest\n    description: REST surface mirroring Azure DevOps pipelines into Backstage.\n    resources:\n    - {name: sync, path: /sync, operations: [{method: POST, name: sync-pipelines, description: Pull all Azure DevOps pipelines and upsert as Backstage entities., call: azuredevops.list-pipelines}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: azure-devops-pipeline-to-backstage-entity-mcp\n    description: MCP for pipeline-to-Backstage sync.\n    tools:\n    -\
  \ {name: list-azdo-pipelines, hints: {readOnly: true}, call: azuredevops.list-pipelines}\n    - {name: sync-pipelines, call: azuredevops.list-pipelines}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: azure-devops-pipeline-to-backstage-entity-skills\n    description: Skill bundle for AzDO→Backstage sync.\n    skills:\n    - name: azure-devops-pipeline-to-backstage-entity\n      description: Mirror Azure DevOps pipelines as Backstage entities.\n      location: file:///opt/naftiko/skills/azure-devops-pipeline-to-backstage-entity\n      allowed-tools: list-azdo-pipelines,sync-pipelines\n      tools:\n      - {name: list-azdo-pipelines, from: {sourceNamespace: azure-devops-pipeline-to-backstage-entity-mcp, action: list-azdo-pipelines}}\n      - {name: sync-pipelines, from: {sourceNamespace: azure-devops-pipeline-to-backstage-entity-mcp, action: sync-pipelines}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/azure-devops-pipeline-to-backstage-entity.yaml
tags:
- Naftiko
- Azure DevOps
- Backstage
tools:
- description: ''
  hints:
    readOnly: true
  name: list-azdo-pipelines
- description: ''
  hints: {}
  name: sync-pipelines
---
