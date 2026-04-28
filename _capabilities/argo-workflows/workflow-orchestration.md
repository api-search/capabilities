---
categories:
- container-orchestration
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
- submit a new argo workflow to a kubernetes namespace
- list archived workflows
- workflow lifecycle management
- containers
- list workflows
- list reusable workflow templates in a namespace
- list cron workflows
- parallel data transformation, ml training, and etl
- list workflow templates
- argo workflows
- list all workflow templates
- kubernetes
- data processing
- create workflow
- container-native workflow execution and lifecycle management
- list all argo workflows in a kubernetes namespace with status
- Data Engineer
- submit a new workflow
- machine learning
- list all cron workflows
- workflow execution history
- Platform Engineer
- runs ml training, data processing, and etl workflows on kubernetes
- cncf
- manages argo workflows platform, templates, and scheduling
- list scheduled cron workflows in a namespace
- scheduled cron workflows
- list archived workflow runs
- open source
- workflow engine
- list historical archived workflow executions
- list all workflows in a namespace
- reusable workflow templates
- data engineering
- container orchestration platform
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
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
