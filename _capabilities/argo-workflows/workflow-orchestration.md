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
- scheduled cron workflows
- workflow engine
- list workflow templates
- submit a new workflow
- machine learning
- data engineering
- open source
- list historical archived workflow executions
- list cron workflows
- container-native workflow execution and lifecycle management
- list workflows
- list reusable workflow templates in a namespace
- list all cron workflows
- Platform Engineer
- manages argo workflows platform, templates, and scheduling
- Data Engineer
- containers
- list archived workflows
- list scheduled cron workflows in a namespace
- list all workflows in a namespace
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
- create workflow
- list all workflow templates
- runs ml training, data processing, and etl workflows on kubernetes
- workflow execution history
- argo workflows
- list all argo workflows in a kubernetes namespace with status
- cncf
- list archived workflow runs
- parallel data transformation, ml training, and etl
- container orchestration platform
- kubernetes
- reusable workflow templates
- workflow lifecycle management
- submit a new argo workflow to a kubernetes namespace
- data processing
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
