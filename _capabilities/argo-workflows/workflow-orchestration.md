---
consumed_apis:
- argoworkflows
description: Unified capability for container-native workflow orchestration on Kubernetes using Argo Workflows. Combines workflow lifecycle management, template reuse, cron scheduling, and workflow history for Data Engineers and Platform Engineers.
layout: capability
name: Argo Workflows Orchestration
operations:
- description: List all workflows in a namespace
  method: GET
  name: list-workflows
  path: /v1/workflows/{namespace}
- description: Submit a new workflow
  method: POST
  name: create-workflow
  path: /v1/workflows/{namespace}
- description: List all workflow templates
  method: GET
  name: list-workflow-templates
  path: /v1/workflow-templates/{namespace}
- description: List all cron workflows
  method: GET
  name: list-cron-workflows
  path: /v1/cron-workflows/{namespace}
- description: List archived workflow runs
  method: GET
  name: list-archived-workflows
  path: /v1/archived-workflows
personas: []
provider_name: Argo Workflows
provider_slug: argo-workflows
search_terms:
- kubernetes
- open source
- list all cron workflows
- machine learning
- list historical archived workflow executions
- submit a new workflow
- list workflows
- list cron workflows
- Platform Engineer
- reusable workflow templates
- list archived workflows
- submit a new argo workflow to a kubernetes namespace
- manages argo workflows platform, templates, and scheduling
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
- workflow execution history
- argo workflows
- list archived workflow runs
- list workflow templates
- containers
- runs ml training, data processing, and etl workflows on kubernetes
- Data Engineer
- cncf
- workflow engine
- list all argo workflows in a kubernetes namespace with status
- create workflow
- container-native workflow execution and lifecycle management
- data processing
- list reusable workflow templates in a namespace
- workflow lifecycle management
- list all workflows in a namespace
- container orchestration platform
- scheduled cron workflows
- list scheduled cron workflows in a namespace
- parallel data transformation, ml training, and etl
- data engineering
- list all workflow templates
slug: workflow-orchestration
tags:
- Argo Workflows
- Kubernetes
- Workflow Engine
- CNCF
- Data Engineering
tools:
- description: List all Argo Workflows in a Kubernetes namespace with status
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: Submit a new Argo Workflow to a Kubernetes namespace
  hints:
    destructive: false
    readOnly: false
  name: create-workflow
- description: List reusable workflow templates in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-templates
- description: List scheduled cron workflows in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-cron-workflows
- description: List historical archived workflow executions
  hints:
    openWorld: true
    readOnly: true
  name: list-archived-workflows
---
